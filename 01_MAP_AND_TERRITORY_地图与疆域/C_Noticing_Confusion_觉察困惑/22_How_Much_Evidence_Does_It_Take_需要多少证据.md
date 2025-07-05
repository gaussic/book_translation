## 需要多少证据？

之前我把证据定义为“通过因果链条与你想要了解的事物纠缠在一起的事件”，而“纠缠”则是“在目标的不同可能状态下会有不同结果的事件”。那么，支撑一个信念到底需要多少纠缠——多少理性证据？

让我们从一个足够简单、可以用数学描述的问题开始：你需要多强的“纠缠”才能赢得彩票？假设有70个球，不放回地抽取，中奖需要匹配6个数字。那么一共有131,115,985种可能的中奖组合，因此随机选一张彩票中奖的概率是1/131,115,985（约0.0000007%）。要想赢得彩票，你需要足够有选择性的证据，让某一个组合在131,115,984个其他组合中脱颖而出。

假设你可以做一些测试，概率性地区分中奖号码和非中奖号码。比如，你可以把一个组合输入一个小黑盒子，如果是中奖组合，盒子一定会响；如果是错误组合，盒子有1/4（25%）的概率会响。用贝叶斯术语说，这个盒子的似然比是4:1。也就是说，输入正确组合时盒子响的概率，是输入错误组合时的4倍。

但可能的组合还是很多。如果你输入20个错误组合，盒子平均会响5次（纯粹是偶然）。如果你把全部131,115,985种组合都输入一遍，盒子会在中奖组合时必然响一次，同时还会在32,778,996个错误组合上响（平均而言）。

所以，这个盒子不能让你稳赢彩票，但总比没有好。如果你用这个盒子，你的中奖概率会从1/131,115,985提升到1/32,778,997。你在庞大的可能性空间中，朝着目标——真相——迈进了一步。

假设你可以用另一个黑盒子独立地再测试一次。两个盒子对中奖票都会响，但对错误组合，每个盒子独立有1/4的概率响，因此两个盒子都响的概率是1/16。我们可以说，两次独立测试的累积证据，似然比是16:1。通过两次测试的错误彩票平均还有8,194,749张。

既然有131,115,985种可能的彩票，你可能会猜想，你需要强度约为131,115,985:1的证据——即某个事件或一系列事件，在中奖组合下发生的概率是非中奖组合下的131,115,985倍。实际上，这样的证据只能让你有一半的概率赢得彩票。为什么？因为如果你用这么强的筛选器过滤1.31亿张错误彩票，平均会有一张错误票通过筛选。中奖票也会通过筛选。你最终会剩下两张票，其中只有一张是真的中奖票。如果你只能买一张票，中奖概率就是50%。

换一种更好的理解方式：一开始有1张中奖票和131,115,984张错误票，所以你的中奖赔率是1:131,115,984。如果你用一个盒子，中奖票响的概率是1，错误票是0.25。所以我们把1:131,115,984乘以1:0.25，得到1:32,778,996。再加一个盒子，赔率再乘以1:0.25，变成1:8,194,749。

用“比特”来衡量证据很方便——不是硬盘上的比特，而是数学意义上的比特。数学上的比特是概率以1/2为底的对数。例如，如果有A、B、C、D四种可能结果，概率分别为50%、25%、12.5%、12.5%，我告诉你结果是“D”，那么我传递了3比特信息，因为我告诉了你一个概率为1/8的结果。

巧的是，131,115,984略小于2的27次方。所以，14个盒子或28比特的证据——即某事件在假设为真时发生的概率是假设为假时的268,435,456:1——会把赔率从1:131,115,984变成268,435,456:131,115,984，约等于2:1。2:1的赔率意味着每输一次有两次赢的机会，所以有28比特证据时，中奖概率是2/3。再加一个盒子（再加2比特证据），赔率变成8:1。再加两个盒子，中奖概率就变成128:1。

所以，如果你想要有充分理由坚信自己会中彩票——比如定义为出错概率小于1%——那么关于中奖组合的34比特证据就足够了。一般来说，判断“需要多少证据”遵循类似的规律：假设所在的可能性空间越大，假设先验上越不可能，或者你想要的信心越高，你就需要越多的证据。

你无法违背这些规则；你不能凭借不足的证据形成准确的信念。假设你有10个盒子排成一排，你开始往盒子里输入组合。你不能在第一个让10个盒子都响的组合上就停下来，说：“这种情况在错误组合上发生的概率是一百万分之一！我就无视那些象牙塔里的贝叶斯规则，直接停在这里。”实际上，每有1个中奖票通过测试，就有131张错误票也能通过。考虑到可能性空间和先验概率，你基于不足的证据得出了过于强烈的结论。这不是官僚主义的无聊规定，而是数学。

当然，如果你愿意，你还是可以凭不足的证据相信某事；但你无法准确地相信。就像你试图不加油就开车，因为你不相信“车要加油才能跑”这种老古董观念。如果我们决定废除“汽车需要燃料”这条定律，岂不是更有趣、更省钱？

你可以试试。你甚至可以闭上眼睛假装车在动。但如果你真的想获得准确的信念，就需要证据这份“燃料”，而你想走得越远，需要的燃料就越多。

---

## How Much Evidence Does It Take?

Previously, I defined evidence as “an event entangled, by links of cause and effect, with whatever you want to know about,” and entangled as “happening differently for different possible states of the target.” So how much entanglement—how much rational evidence—is required to support a belief?

Let’s start with a question simple enough to be mathematical: How hard would you have to entangle yourself with the lottery in order to win? Suppose there are seventy balls, drawn without replacement, and six numbers to match for the win. Then there are 131,115,985 possible winning combinations, hence a randomly selected ticket would have a 1/131,115,985 probability of winning (0.0000007%). To win the lottery, you would need evidence selective enough to visibly favor one combination over 131,115,984 alternatives.

Suppose there are some tests you can perform which discriminate, probabilistically, between winning and losing lottery numbers. For example, you can punch a combination into a little black box that always beeps if the combination is the winner, and has only a 1/4 (25%) chance of beeping if the combination is wrong. In Bayesian terms, we would say the likelihood ratio is 4 to 1. This means that the box is 4 times as likely to beep when we punch in a correct combination, compared to how likely it is to beep for an incorrect combination.

There are still a whole lot of possible combinations. If you punch in 20 incorrect combinations, the box will beep on 5 of them by sheer chance (on average). If you punch in all 131,115,985 possible combinations, then while the box is certain to beep for the one winning combination, it will also beep for 32,778,996 losing combinations (on average).

So this box doesn’t let you win the lottery, but it’s better than nothing. If you used the box, your odds of winning would go from 1 in 131,115,985 to 1 in 32,778,997. You’ve made some progress toward finding your target, the truth, within the huge space of possibilities.

Suppose you can use another black box to test combinations twice, independently. Both boxes are certain to beep for the winning ticket. But the chance of a box beeping for a losing combination is 1/4 independently for each box; hence the chance of both boxes beeping for a losing combination is 1/16. We can say that the cumulative evidence, of two independent tests, has a likelihood ratio of 16:1. The number of losing lottery tickets that pass both tests will be (on average) 8,194,749.

Since there are 131,115,985 possible lottery tickets, you might guess that you need evidence whose strength is around 131,115,985 to 1—an event, or series of events, which is 131,115,985 times more likely to happen for a winning combination than a losing combination. Actually, this amount of evidence would only be enough to give you an even chance of winning the lottery. Why? Because if you apply a filter of that power to 131 million losing tickets, there will be, on average, one losing ticket that passes the filter. The winning ticket will also pass the filter. So you’ll be left with two tickets that passed the filter, only one of them a winner. Fifty percent odds of winning, if you can only buy one ticket.

A better way of viewing the problem: In the beginning, there is 1 winning ticket and 131,115,984 losing tickets, so your odds of winning are 1:131,115,984. If you use a single box, the odds of it beeping are 1 for a winning ticket and 0.25 for a losing ticket. So we multiply 1:131,115,984 by 1:0.25 and get 1:32,778,996. Adding another box of evidence multiplies the odds by 1:0.25 again, so now the odds are 1 winning ticket to 8,194,749 losing tickets.

It is convenient to measure evidence in bits—not like bits on a hard drive, but mathematician’s bits, which are conceptually different. Mathematician’s bits are the logarithms, base 1/2, of probabilities. For example, if there are four possible outcomes A, B, C, and D, whose probabilities are 50%, 25%, 12.5%, and 12.5%, and I tell you the outcome was “D,” then I have transmitted three bits of information to you, because I informed you of an outcome whose probability was 1/8.

It so happens that 131,115,984 is slightly less than 2 to the 27th power. So 14 boxes or 28 bits of evidence—an event 268,435,456:1 times more likely to happen if the ticket-hypothesis is true than if it is false—would shift the odds from 1:131,115,984 to 268,435,456:131,115,984, which reduces to 2:1. Odds of 2 to 1 mean two chances to win for each chance to lose, so the probability of winning with 28 bits of evidence is 2/3. Adding another box, another 2 bits of evidence, would take the odds to 8:1. Adding yet another two boxes would take the chance of winning to 128:1.

So if you want to license a strong belief that you will win the lottery— arbitrarily defined as less than a 1% probability of being wrong—34 bits of evidence about the winning combination should do the trick. In general, the rules for weighing “how much evidence it takes” follow a similar pattern: The larger the space of possibilities in which the hypothesis lies, or the more unlikely the hypothesis seems a priori compared to its neighbors, or the more confident you wish to be, the more evidence you need.

You cannot defy the rules; you cannot form accurate beliefs based on inadequate evidence. Let’s say you’ve got 10 boxes lined up in a row, and you start punching combinations into the boxes. You cannot stop on the first combination that gets beeps from all 10 boxes, saying, “But the odds of that happening for a losing combination are a million to one! I’ll just ignore those ivory-tower Bayesian rules and stop here.” On average, 131 losing tickets will pass such a test for every winner. Considering the space of possibilities and the prior improbability, you jumped to a too-strong conclusion based on insufficient evidence. That’s not a pointless bureaucratic regulation; it’s math.

Of course, you can still believe based on inadequate evidence, if that is your whim; but you will not be able to believe accurately. It is like trying to drive your car without any fuel, because you don’t believe in the fuddyduddy concept that it ought to take fuel to go places. Wouldn’t it be so much more fun, and so much less expensive, if we just decided to repeal the law that cars need fuel?

Well, you can try. You can even shut your eyes and pretend the car is moving. But really arriving at accurate beliefs requires evidence-fuel, and the further you want to go, the more fuel you need.