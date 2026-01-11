---
layout: post
title: "I never stop learning"
date: 2026-01-11 09:00:00 -0800
categories: blog
---

I never stop learning the same lesson, because I keep forgetting it: don’t debug while you’re tired.

**TLDR: I spent an hour in dependency hell only to realize that my version of Ruby was old and needed a version bump.**

## What did I waste my hour on?

This week, I wanted to add something new to my blog (not this post of course... lol). I hadn't touched this blog since late 2024. Since then, I had replaced my machine and no longer had the dev environment set up, including whatever Ruby version I had back then. My blog runs on Jekyll, and to set this up, I followed the steps from the [Jekyll quickstart page](https://jekyllrb.com/docs/), which were simple and looked something like this:

1. Install Ruby:
   1. `brew install chruby ruby-install`
   2. `ruby-install ruby 3.4.1`
2. Install Jekyll: `gem install jekyll bundler`
3. Install more stuff: `bundle install`
4. Run the blog: `bundle exec jekyll serve`

<details>
<summary>Click here to see the error I got.</summary>
<pre style="background-color: #f6f8fa; padding: 16px; border-radius: 6px; overflow-x: auto;"><code>% bundle exec jekyll serve
...
Generating...
Remote Theme: Using theme aterenin/minima-reboot
jekyll 3.9.3 | Error: SSL_connect returned=1 errno=0 peeraddr=140.82.116.10:443 state=error: certificate verify failed (unable to get certificate CRL)
/Users/mat/.rubies/ruby-3.4.1/lib/ruby/3.4.0/net/protocol.rb:46:in 'OpenSSL::SSL::SSLSocket#connect_nonblock': SSL_connect returned=1 errno=0 peeraddr=140.82.116.10:443 state=error: certificate verify failed (unable to get certificate CRL) (OpenSSL::SSL::SSLError)
from /Users/mat/.rubies/ruby-3.4.1/lib/ruby/3.4.0/net/protocol.rb:46:in 'Net::Protocol#ssl_socket_connect'
...
</code></pre>
</details>
<br>
Never seen this before. I should have created a README with the exact steps I used back then. After several tired exchanges with Codex, I thought I was getting somewhere: Ruby could not load my theme of choice.

```yml
# _config.yml
remote_theme: aterenin/minima-reboot
```

Since I was using a `remote_theme`, Ruby has to download that theme from somewhere remote. Doing so required Ruby to have SSL verification from Github. My version of Ruby apparently did not have that. What to do?

It was getting late, and I didn't want to ruin my sleep by thinking too hard about this. I asked Codex to run some commands to fix this for me. That was a mistake, not because the suggestions were bad, but because I was too tired to evaluate them properly.

Codex tried many things, most of which felt increasingly desperate. Here are three I dug up.

<details style="margin-bottom: 1em;">
<summary>Configuring my SSL certificates</summary>
<pre style="background-color: #f6f8fa; padding: 16px; border-radius: 6px; overflow-x: auto;"><code class="language-bash">export SSL_CERT_FILE=/opt/homebrew/etc/ca-certificates/cert.pem</code></pre>
</details>
<details style="margin-bottom: 1em;">
<summary>Rebuilding Ruby against Homebrew SSL</summary>
<pre style="background-color: #f6f8fa; padding: 16px; border-radius: 6px; overflow-x: auto;"><code class="language-bash">brew update
brew upgrade openssl@3 ca-certificates
brew postinstall ca-certificates
openssl s_client -connect codeload.github.com:443 -CAfile /opt/homebrew/etc/ca-certificates/cert.pem
RUBY_CONFIGURE_OPTS="--with-openssl-dir=$(brew --prefix openssl@3)" ruby-install ruby 3.4.1</code></pre>
</details>
<details style="margin-bottom: 1em;">
<summary>Running Jekyll with a custom OpenSSL config</summary>
<pre style="background-color: #f6f8fa; padding: 16px; border-radius: 6px; overflow-x: auto;"><code class="language-bash">cat > /tmp/openssl_nocrl.cnf <<'EOF'
openssl_conf = openssl_init
[openssl_init]
ssl_conf = ssl_sect
[ssl_sect]
system_default = system_default_sect
[system_default_sect]
VerifyFlags = -CRL_CHECK
EOF
OPENSSL_CONF=/tmp/openssl_nocrl.cnf bundle exec jekyll serve</code></pre>
</details>

The majority of this hour was me looking up what each of these approaches was actually doing, since I was not comfortable letting Codex run things I didn't understand. By the end of the hour, none of these worked, and I don't think my brain absorbed much that late at night. Off to bed.

## Sleep is the best debugger

I woke up the next day and realized that `ruby-install ruby 3.4.1` looked similar to the command I ran the last time I worked on this blog. Maybe I should be on a newer version?

```bash
ruby-install ruby 3.4.8
```

And a minute later, the rest of the steps:
```bash
gem install jekyll bundler
bundle install
bundle exec jekyll serve
```

It worked! Sleep is the best debugger! Pour one out for the hour of my life I will never get back.

Lesson learned, until next time... probably at 11:47pm.
