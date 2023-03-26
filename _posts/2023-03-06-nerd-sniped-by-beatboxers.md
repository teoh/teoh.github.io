---
layout: post
title:  "Nerd-sniped by beatboxers"
date:   2023-03-06 09:00:00 -0800
thumbnail: "/assets/20230306beatbox-nerdsnipe/thumbnail.png"
categories: blog
---
**TLDR: If you scored 25th in the first round of wildcard solos, it’s still mathematically possible for you to make it to GBB (Top 11 overall), but impossible for you to get 1st place overall (after the 2 rounds of wildcards). If your first round was at least as good as 24th, 1st place overall is possible. No comments about probability… yet.**

## Grand Beatbox Battle is here

For beatboxing, it’s that time of year again. SwissBeatbox (SBX) has released the wildcard rankings for this year's Grand Beatbox Battle (GBB) 2023 solos ([full post](https://www.instagram.com/p/CpN5CgPN64x/)). If you're not familiar, SwissBeatbox is a beatboxing YouTube channel that organizes one of the largest beatboxing competitions in the world.

(They had to update these rankings because they apparently [messed up their spreadsheet](https://www.reddit.com/r/beatbox/comments/11gv8ki/solo_wildcard_ranking_seems_to_be_incorrect/), but that’s another story!)

Here’s how GBB usually works:

1. Beatboxers submit a wildcard (i.e. an entry video) before some deadline.
2. A team of judges evaluate each video based on things like originality, musicality, execution, etc.
3. Beatboxers get a score for the video they sent, based on the judging.
4. Some people get (reasonably) upset about the ranking, and I hold back the urge to tell everyone that the only acceptable ranking is the one where my favourites are on top. (Actually, why not try [predictive optimization](https://predictive-optimization.cs.princeton.edu/)? 🤣)
5. The top ranked beatboxers (usually ≈8) go to GBB to compete!

## With a twist

This year, SBX added a second round of wildcard rankings. I’ll spare you the lengthy quote ([page](https://swissbeatbox.com/newsfeed/gbb-2023-wildcard-competition/)). Here’s the gist:

1. Top 25 from the first round (above) submit a second wildcard video
2. The judges rank these videos
3. Your final score (??) is the average of your rank from the first and second rounds.
4. Your final *rank* comes from this final score
5. Top 11 make it to the GBB 23 event

Here’s a small table for an example:

| Beatboxer name | Round 1 rank | Round 2 rank | Final score <br />(Average rank, smaller number is better) | Final rank |
| -------------- | ------------ | ------------ | ----------- | ---------- |
| a | 1 | 2 | 1.5 | 1 🥇 |
| b | 2 | 3 | 2.5 | 3 🥉 |
| c | 3 | 1 | 2 | 2 🥈 |
{:class="table-bordered"}
<br>

<div style="display: flex; flex-wrap: wrap;">
  <div style="flex: 1">
    <p>SBX conflates scores with ranks here (which I do not like), so I’ve assumed that:</p>
    <ul>
        <li>The final “score” comes from averaging the literal rank numbers from rounds 1 and 2.</li>
        <li>A lower “final score” is better (i.e. if your average is 1, you’re in first place).</li>
    </ul>
    <p>I’ll also assume that ties in the final ranks are valid, as long as it’s still clear who makes top 11 overall. For example, a 25-way tie doesn’t count (see the picture on the right), and we won’t consider that here.
</p>
  </div>
  <div style="flex: 1; padding: 10px; padding-left: 20px;">
    <figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0001-25tie.png" alt="A 25-way tie. Who’s in the top 11? No one knows." style="max-width: 100%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    A 25-way tie. Who’s in the top 11? No one knows.
    </figcaption>
    </figure>
  </div>
</div>

## If you came 25th in Round 1, can you still make it to GBB?

For solos, we really just care about the top 25 beatboxers, since they’re the only ones who submit a second wildcard.

If you came 25th in the first round, do you still have a chance to make it to GBB? **In other words: if you placed 25th in Round 1, is it possible to score well enough in Round 2, so that your average places you in the Top 11 over all?**

**TLDR: yes.**

##### ❌ **Case study 1: Everyone’s performance (including yours) is exactly the same between Rounds 1 and 2**

This one’s pretty self-explanatory.
<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0002-noChange.png" alt="Everyone performs the same between Rounds, so your position remains the same." style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    Everyone performs the between Rounds, so your position remains the same.
    </figcaption>
</figure>

Let’s see what else could happen to you, based on what happens in Round 2.

##### ❌ **Case study 2: You comes 1st in Round 2, but everyone else is relatively the same**

By “relatively the same”, I mean that `a` scores 2nd in Round 2, `b` scores 3rd, and so on. Your final score is 14, and so is the final rank, so you don’t make it 😟.

<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0003-1stRound2.png" alt="You placed 1st in Round 2, but didn’t make it to the top 11 overall." style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    You placed 1st in Round 2, but didn’t make it to the top 11 overall.
    </figcaption>
</figure>

We can also see that your **best possible final score** after Round 2 is 13. This happens when you place 1st in Round 2. With this best possible score, was there any hope for you to make top 11 to begin with, provided that others place in **just the right (wrong) way**? Yes!

##### ✅ **Case study 3: You place 1st in Round 2, and folks `k` to `x` have a bad day.**

For you to place top 11 overall, it depends on everyone performing in a very specific way during Round 2:

1. You rank 1st, giving your best final score of 13.
2. Beatboxers `a`-`j` do (almost) just as well. `a` gets 2nd place, `b` gets 3rd, and so on. This gives each of them a final *score* smaller (i.e. better) than your 13, and a *rank* that looks identical to Round 1.
3. Beatboxers `k`-`x` perform roughly *inversely* to how they did in Round 1. `k` places 25th (last), `l` places 24th, and so on. This gives them each a final score of 18, which is larger (i.e. worse) than your 13, and a 14-way tie for 12th place overall.

<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0004-youMake11th.png" alt="You placed 1st in Round 2, but didn’t make it to the top 11 overall." style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    You placed 1st in Round 2, and made it into the top 11 overall!
    </figcaption>
</figure>

## 11th? Why stop there?

We’ve shown that placing 25th in Round 1 is not hopeless. You have hope: there exists a Round 2 ranking where you do well enough to place 11th overall, and make it to GBB.

**Next question: what’s the limit to this? Is there hope to make 10th place overall? 9th? What about 1st?**

We know two things so far:

1. You have hope to score *as least as well as* 11th overall. We showed this in the previous result.
2. You can’t score 1st overall.

To see why (2) is true, remember that your best final score is 13. Beatboxer `a`’s *worst overall score* is also 13 (this happens when they place 25th in Round 2), which means you can never score better than them.

Here’s the short answer: your best possible (overall) rank after Round 2 is 2nd place overall.

Here’s the slightly longer, math-y version:
- To produce this outcome, beatboxers `b`-`x` need to have a final score that’s worse (i.e. larger) than your final score of 13.
- Beatboxer `b` achieves this only if their Round 2 rank is 25, giving a final score of 13.5
- Anything better than 25th in Round 2 gives a final score better than your 13.

You can apply the same reasoning for the remainder of the list.

<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0005-secondPlace.png" alt="It’s possible for you to score 2nd place overall." style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    It’s possible for you to score 2nd place overall.
    </figcaption>
</figure>

## When can you get 1st overall?

We showed that you can’t get 1st overall if you placed 25th in Round 1. How well do you have to do in Round 1 to have any hope of getting 1st overall?

We showed above that you can’t get 1st overall if you placed 25th in Round 1. This was because your *best* overall score, and `a`'s *worst* overall score, were both 13, so you couldn’t beat that. How well do you have to do in Round 1 (it has to be better than 25th, only way is up!) to have any hope of getting 1st overall?

**In other words: what needs to happen in Round 1 so that an overall score less (i.e. better) than 13 is possible?**

Short answer: placing 24th is good enough.

Long answer:
- The final score is an average of your ranks from Rounds 1 and 2.
- Your best rank in Round 2 is 1st place, so we need an outcome (i.e. rank) in Round 1 that brings the average below 13 (beatboxer `a`'s best score).
- This can happen if you place 24th in Round 1, because the average of 24 and 1 is 12.5 < 13.

<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0006-howFirst.png" alt="You get 1st place overall." style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    You get 1st place overall.
    </figcaption>
</figure>

## Final thoughts

The math in this problem was not complicated at all, and the fun of this exercise lies mostly in reasoning about monotonic properties. For example, when we asked about you making top 11 overall, it was good enough to analyze what happened if you scored 1st place in Round 2.

Why? If we found that it was impossible, even after scoring 1st in Round 2, then no other outcome of Round 2 (you scoring 2nd, 3rd, etc.) would have helped you get to top 11 overall, *because they’re all strictly worse* than scoring 1st in Round 2! In fact, this is the reasoning we used to say that scoring 1st overall was impossible.

Finally, I gave examples to demonstrate that ranking 11th or 2nd overall was possible, but I haven’t thought long enough to say whether those examples are unique.

For example, maybe there are other Round 2 outcomes that would give you 11th overall, besides the one I shared. I also showed that these outcomes were *possible*, but did not say whether they were *probable*. That needs enough analysis (and assumptions) to make a second blog post.

---
## Addendum Mar 22, 2023
I posted this on the r/beatbox subreddit ([link](https://www.reddit.com/r/beatbox/comments/11ynz2k/getting_nerd_sniped_by_gbb/)), and people got more excited about this than I expected.

### What's the worst you can do in Round 2, and still have a shot at getting into GBB?
User `Speek1Wif2Mee3` asked a great question ([link](https://www.reddit.com/r/beatbox/comments/11ynz2k/comment/jd8yt55/)) that I really liked:
> What is the lowest possible rank Remix can get in order to be in. First round he was 20th.

And user `bjallen619` gave a great answer ([link](https://www.reddit.com/r/beatbox/comments/11ynz2k/comment/jd9m7xg/)) that I also really liked:
> I don’t know if this exactly answers what you’re asking, but I have a strong feeling that the answer is: 15th.
>
> Since we’re wondering the lowest score possible, then we don’t really care about the competitors ranked 1-10 after the first round—just the beatboxer ranked 11th (Stitch).
>
> Hypothetically if the beatboxer ranked #11 after round 1 was given 25th place in round 2, his average “score” would be (11+25)/2=18.
>
> At worst, Remix would need to beat that average “score”. (20+X)/2<18 ; 20+X<36 ; X<16, hence 15th.

Seems pretty good to me! To give you a sense of what that looks like, everyone else (11th-19th, and 21st-25th in the Round 1) would have to score a certain way.

<figure>
    <img src="/assets/20230306beatbox-nerdsnipe/0007-remix.png" alt="If you scored 20th in Round 1, what's the bare minimum to make it to GBB?" style="max-width: 40%; height: auto;">
    <figcaption style="color: #555; font-style: italic;">
    If you scored 20th in Round 1, what's the bare minimum to make it to GBB?
    </figcaption>
</figure>

We can generalize this for any beatboxer who scored a rank of $$r_1$$ in Round 1, $$r_2$$ in Round 2, and final score $$r_{\text{final}}=\frac{r_1 + r_2}{2}$$.

The question is: "Given your $$r_1$$, what is the worst $$r_2$$ you can get while still having a chance to make it to GBB?"

**TLDR**: $$\boxed{r_2=\text{min}(35-r_1, 25)}$$

We can break this down into 3 cases.
<style>
.details-section {
  background-color: #f5f5f5; /* change this to the desired color */
  padding: 10px; /* add padding for better readability */
}
</style>

Case 1: $$r_1 \leq 10$$.
<details>
  <summary>👈 Click here for the Case 1 proof:</summary>
  <p></p>

  <div class="details-section">
  <div class="tip" markdown="1">
  Consider a beatboxer $$c$$ (your "competitor") who scored 11th in Round 1. Assume everyone else who ranked above $$c$$ (in Round 1) ranked the same in Round 2, which puts at most 9 beatboxers above you that you can't beat.

  If you can beat $$c$$ in Round 2, then you have a spot in GBB. With $$c_1=11$$, we have that:
  \\[
    c_{\text{final}}=\frac{11 + c_2}{2}.
  \\]

  Since $$c_2 \in [1, 25] $$ (i.e. our competitor can score anywhere from 1-25 in Round 2), then

  \\[
    c_{\text{final}}\in[11.5, 18].
  \\]

  The left boundary occurs when $$c_2=1$$, and the right occurs when $$c_2=25$$.

  If you scored $$r_2=25$$, then
  - $$c$$'s worst score is $$c_2=24\implies c_{\text{final}}=\frac{11 + 24}{2}=17.5$$
  - Your final score is $$r_{\text{final}}=\frac{r_1 + 25}{2}$$

  Since $$r_1\leq10$$, then $$r_{\text{final}}\leq\frac{10 + 25}{2}=17.5$$. This means that if you score 25th in Round 2, it's still possible to stay above $$c$$ overall and make it to GBB: $$c$$ just needs to score 24th in Round 2. (At the boundary of $$r_{\text{final}} =17.5$$, you tie with $$c$$, but this is not a problem. With 9 other beatboxers who ranked above you, there's enough room for you and $$c$$ in the top 11.)

  For this case, your worst possible Round 2 score (while still having a chance to make it to GBB) is 25th, which satisfies that claim that $$r_2=\text{min}(35-r_1, 25)$$. (We have to use $$\text{min}$$ here to cap the final number, because your $$r_2$$ might go out of bounds, e.g. when $$r_1=1$$.)
  </div>
  </div>
</details>
<br>
Case 2: $$r_1=11$$.
<details>
  <summary>👈 Click here for the Case 2 proof:</summary>
  <p></p>

  <div class="details-section">
  <div class="tip" markdown="1">
  You ranked 11th in Round 1, which puts 10 people ahead of you. The next in line to take your place is your competitor $$c$$, who ranked 12th in Round 1 ($$c_1=12$$). How poorly can you do in Round 2 and still have a shot?

  What happens if you place 25th in Round 2? If we apply the logic from Case 1, we get a tie between you and $$c$$.
  - $$r_2=25\implies r_{\text{final}}=\frac{11+25}{2}=18$$.
  - In the best case, $$c_2=24\implies c_{\text{final}}=\frac{12+24}{2}=18$$.

  Since there are 10 beatboxers ahead of you, this tie creates ambiguity on who makes 11th, so we can't have it.

  If you rank 24th in Round 2 ($$r_2=24$$), then your best shot is when $$c_2=25$$, which gives:
  - $$r_{\text{final}}=\frac{11+24}{2}=17.5$$, and
  - $$c_{\text{final}}=\frac{12+25}{2}=18.5$$.

  Thus, your worst possible Round 2 score (while still having a chance to make it to GBB) is 24th, which satisfies the claim that $$r_2=\text{min}(35-r_1, 25)$$.
  </div>
  </div>
</details>
<br>
Case 3: $$r_1>11$$.
<details>
  <summary>👈 Click here for the Case 3 proof:</summary>
  <p></p>

  <div class="details-section">
  <div class="tip" markdown="1">
  This is a straightforward application of the original reddit comment. Let's consider again your competitor $$c$$ who scored $$c_1=11$$ in Round 1.

  Similar to the proof in Case 1, we have that: $$c_{\text{final}}\in[11.5, 18]$$; $$c_{\text{final}}=18$$ when $$c_2=25$$.

  If $$c$$ does poorly in Round 2 and gets $$c_2=25$$, your final score needs to be $$r_{\text{final}}=\frac{r_1 + r_2}{2} < 18$$ for you to beat them and get top 11 overall.

  We can rearrange this give: $$r_2<36-r_1$$, which gives $$r_2\leq 35-r_1$$. This means that if $$c_2=25$$, you can score $$r_2=35-r_1$$ and get 11th overall, which satisifies $$r_2=\text{min}(35-r_1, 25)$$.
  </div>
  </div>
</details>
<br>
