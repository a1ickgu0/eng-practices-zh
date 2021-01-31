# Emergencies
# 紧急变更

Sometimes there are emergency CLs that must pass through the entire code review
process as quickly as possible.

有时候会遇到一些紧急的 CL 需要尽快通过代码评审的情况。


## What Is An Emergency? {#what}

## 什么是紧急变更？{#what}

An emergency CL would be a **small** change that: allows a major launch to
continue instead of rolling back, fixes a bug significantly affecting users in
production, handles a pressing legal issue, closes a major security hole, etc.

紧急的 CL 应该是个 **小的** 变更：重要的非回退的代码变更，通常是产生环境中对用户有重大影响、处理紧迫的法律问题、关闭重要的安全漏洞，等等。

In emergencies we really do care about the speed of the entire code review
process, not just the [speed of response](reviewer/speed.md). In this case
*only*, the reviewer should care more about the speed of the review and the
correctness of the code (does it actually resolve the emergency?) than anything
else. Also (perhaps obviously) such reviews should take priority over all other
code reviews, when they come up.

在紧急变更中，最为关键的是代码评审时效，而不只是 [快速反馈](reviewer/speed.md) 。代码评审人 *仅* 这种情况下重点关注代码变更的时间、以及代码修订的正确性（针对代码是否解决了紧急问题），而无需过多关注其他。同时（显然的），这类变更的评审优先级别高于其他所有的变更。

However, after the emergency is resolved you should look over the emergency CLs again and give them a [more thorough review](reviewer/looking-for.md).

然而，在紧急问题处理结束之后，此时需要针对此 CL 进行 [再次评审](reviewer/looking-for.md)。

## What Is Not An Emergency? {#not}

## 哪些不属于紧急变更？{#not}

To be clear, the following cases are *not* an emergency:

-   Wanting to launch this week rather than next week (unless there is some
    actual [hard deadline](#deadlines) for launch such as a partner agreement).
-   The developer has worked on a feature for a very long time and they really
    want to get the CL in.
-   The reviewers are all in another timezone where it is currently nighttime or
    they are away on an off-site.
-   It is the end of the day on a Friday and it would just be great to get this
    CL in before the developer leaves for the weekend.
-   A manager says that this review has to be complete and the CL checked in
    today because of a [soft (not hard) deadline](#deadlines).
-   Rolling back a CL that is causing test failures or build breakages.

And so on.

可以明确，以下情况 *肯定不属于* 紧急情况：

- 对于赶发布进度的情况，比如，项目希望/不接受下周发布，要求快速提交以便当周发布的情况。（不过，对于影响与外部合作方/客户所签定合同中的[硬截止日期](#deadlines)情况除外）。
- 开发人员已经花了大量时间在开发规格，完成后急于将 CL 变更入库。
- 所有评审人员在其他时区，此时他们的时间正在半夜，无法及时评审。
- CL 正好赶上周五下班时间，开发人员急将代码提交后下班放假。
- 项目经理说，这个代码已经评审过了，CL 要赶紧提交，要赶[软截止日期(soft deadline)](#deadlines)时间点。
- 回退导致测试失败或软件构建失败的 CL 。

## What Is a Hard Deadline? {#deadlines}

## 什么刚性期限(Deadline)？{#deadlines}

A hard deadline is one where **something disastrous would happen** if you miss
it. For example:

- Submitting your CL by a certain date is necessary for a contractual obligation.
- Your product will completely fail in the marketplace if not released by a certain date.
- Some hardware manufacturers only ship new hardware once a year. If you miss the deadline to submit code to them, that could be disastrous, depending on what type of code you’re trying to ship.


刚性期限是指，一但错过可能将造成 **灾难性** 的损失的时间期限。 例如：

- 有合同约定一定要完成指定时间完成交付的 CL 。
- 如果产品未在特定日期发布，则将导致产品在市场上彻底失败。
- 一些硬件厂商每年仅发布一次新产品，如果错过向他们提交代码的截止日期，这可能是灾难性的，具体取决于发布的软件性质。

Delaying a release for a week is not disastrous. Missing an important conference
might be disastrous, but often is not.

将发布推迟一个星期并不是灾难性的，或许错过重要的会议将造成灾难性后果，不过通常并不会如此。

Most deadlines are soft deadlines, not hard deadlines. They represent a desire
for a feature to be done by a certain time. They are important, but you
shouldn’t be sacrificing code health to make them.

大多数的截止日期都是软性的，而非硬性的。通常是希望在一定时间之前完成某项功能发布，这很重要，但不应通过牺牲代码的质量来达成。

If you have a long release cycle (several weeks) it can be tempting to sacrifice code review quality to get a feature in before the next cycle. However, this pattern, if repeated, is a common way for projects to build up overwhelming technical debt. If developers are routinely submitting CLs near the end of the cycle that "must get in" with only superficial review, then the team should modify its process so that large feature changes happen early in the cycle and have enough time for good review.

如果软件发布周期比较长（比如，几周才发布一次），那么可能会取临时性地采取牺牲代码评审质量，以满足功能尽早发布的要求。然而，如果这种情况多次发生，那么项目将不断地欠巨额的技术债务。如果开发人员，常态地在临近发布周期进行 CL 变更，那么那些必须提交代码(must get in)的评审将会流于形式，此时，软件开发团队应该改变开发流程，确保大规格的代码变更能够在项目的早期进行，以便有足够的时间进行代码评审。


