## 0 和 1 不是概率

作者：Eliezer Yudkowsky

一、二、三都是整数，负四也是。如果你不断地数上去，或者不断地数下来，你会遇到很多很多整数。但是你不会遇到任何被称为“正无穷”或“负无穷”的东西，所以它们不是整数。

正无穷和负无穷并不是整数，而是用来描述整数行为的特殊符号。人们有时候会说：“5 + 无穷 = 无穷”，因为如果你从 5 开始不停地往上数，你会得到越来越大的数字，没有尽头。但这并不意味着“无穷 - 无穷 = 5”。你不能从 0 开始数个不停，然后再不停地数回来，最后停在 5。

由此我们可以看出，无穷不仅不是整数，它的行为甚至不像整数。如果你不明智地把无穷和整数混在一起用，你就需要引入各种奇怪、看似不一致的行为规则，而对 1、2、3 等真正的整数却不需要这些。

即使无穷不是整数，你也不用担心会因此缺少数字。虽然人们确实见过五只羊、数百万粒沙子、还有无数个原子，但从来没有人真的数过一个“无穷”的东西。同样地，对于连续量——人们测量过直径一毫米的尘埃、一米长的动物、数公里宽的城市、还有几千光年宽的星系，但从没有人测量过“无限大”的东西。在现实世界中，你并不需要太多“无穷”。<sup>1</sup>

在通常的概率表示方式中，概率是介于 0 和 1 之间的。比如一枚硬币正面朝上的概率可能是 0.5，天气预报员可能给明天下雨的概率赋值为 0.9。

不过，这并不是表示概率的唯一方法。你可以通过一个变换将概率转换为**赔率（odds）**，变换公式是 O = (P / (1 - P))。所以 50% 的概率转换为 0.5 / 0.5，即赔率为 1，通常写作 1:1；而 0.9 的概率转换为 0.9 / 0.1，即赔率为 9，写作 9:1。要把赔率转换回概率，则用 P = (O / (1 + O))，这是完全可逆的，因此这个变换是一个**同构映射**——一种双向可逆的对应关系。所以概率和赔率是同构的，你可以根据方便性选择其一来使用。

例如，在进行贝叶斯更新时，使用赔率更加方便。假设我掷一个六面骰子：如果掷出的不是 1，那么听到铃声的概率是 10%；如果掷出的是 1，听到铃声的概率是 20%。现在我掷了骰子，并且确实听到了铃声。那么骰子正面朝上的概率是多少？我们可以这么算：先验赔率是 1:5（即 1/5 = 0.20），似然比是 0.2:0.1（即真实数值 2），直接相乘得到后验赔率 2:5（对应真实数值 2/5 或 0.40）。然后再转换回概率，得到 (0.4 / 1.4) = 2/7 ≈ 29%。

所以在进行贝叶斯更新时，使用赔率更易操作——如果使用概率，就得使用更复杂的贝叶斯公式。但在处理其他问题时，例如“我掷一个六面骰子，掷出 1 到 4 的概率是多少？”，使用概率更方便：你可以将 1/6 概率相加得到 4/6，但你无法直接相加赔率 0.2 得到赔率总和 0.8。

为什么我要说这些？是为了说明：“赔率”作为将不确定性映射到实数上的方式，与“概率”一样合法。某些情况下使用赔率更方便，某些情况下使用概率更方便。著名的 **Cox 定理**（以及它的一些拓展和精炼版本）证明了：所有满足某些合理约束的表示不确定性的方式，最终都彼此同构。

为什么说赔率和概率一样合法很重要？因为概率的通常写法是在 0 到 1 之间，而 0 和 1 看起来像是“可达”的值——我们很容易看到 1 只斑马，或者 0 只独角兽。但当你把概率转换为赔率时，0 映射到 0，而 1 则映射到正无穷。此时，**绝对真理**看起来就不再那么“容易得到”了。

一种更适合做贝叶斯更新的表示方法是**对数赔率（log odds）**——这也是 E. T. Jaynes 推荐的概率思维方式。例如，假设一个命题的先验概率是 0.0001 —— 其对应的对数赔率是约 -40 分贝（dB）。然后你获得了一个证据，如果该命题为真，这个证据出现的可能性是其为假的 100 倍。这相当于 20 分贝的证据。所以更新后对数赔率是 -40 dB + 20 dB = -20 dB，即后验概率约为 0.01。

当你把概率转为对数赔率时，0 映射为负无穷，1 映射为正无穷。这使得“无限确定性”与“无限荒谬”都显得遥不可及。

在概率表示下，0.9999 和 0.99999 看似只相差了 0.00009，好像 0.502 比 0.503 之间的差距更大。但转为赔率后，0.502 和 0.503 分别变为 1.008 和 1.012，而 0.9999 和 0.99999 则变为 9,999 和 99,999。再转换为对数赔率时，0.502 和 0.503 对应 0.03 dB 和 0.05 dB，而 0.9999 和 0.99999 对应 40 dB 和 50 dB。

在对数赔率表示下，**任意两个不确定度之间的距离，就等于将其中一个转为另一个所需的证据强度**。也就是说，对数赔率为我们提供了一个自然的信心度量标准。

使用对数赔率表明：要达到“无限确定性”，你就需要“无限强的证据”；要达到“无限荒谬”，你也需要“无限强的反证”。

此外，如果你试图在概率中直接代入 0 或 1，很多标准的概率定理都会出现特例问题——比如如果你尝试用一个你赋予概率 0 的观察值进行贝叶斯更新，会发生什么？

因此我主张，**可以认为 0 和 1 并不属于“概率”**；就像正无穷和负无穷不满足实数的基本运算法则，所以它们不属于实数一样。

这可能会让一些概率理论家不太高兴，因为我们必须重新推导某些假设“所有联合概率相加等于 1”的定理。

但在现实世界中，当你掷一个骰子，它并不是真的有“必定”落在 1 到 6 的面上的无限确定性。骰子可能会立在边上；可能会被陨石击中；甚至矩阵中的黑暗领主可能突然伸手，把一面改成“37”。

如果你创造一个神奇的符号，代表“所有我未曾考虑的可能性”，你就可以把它加入到事件集合中进行边缘化，最终得出一个表示“无限确定”的神奇符号 T。

但我宁愿问：有没有什么办法在**不依赖这些特殊符号**的前提下推导出相关定理？那样更优雅。就像有些数学家拒绝相信“排中律”或“无限集合”一样，我愿做一个不相信“绝对确定性”的概率理论家。

---

<sup>1</sup>我要提醒更有数学素养的读者，不必写信来详细解释序数与基数的区别。我了解集合论中关于“无穷”的不同概念，但我认为它们在概率论中并没有什么实际用途。

---

## 0 And 1 Are Not Probabilities

by Eliezer Yudkowsky

One, two, and three are all integers, and so is negative four. If you keep counting up, or keep counting down, you’re bound to encounter a whole lot more integers. You will not, however, encounter anything called “positive infinity” or “negative infinity,” so these are not integers.

Positive and negative infinity are not integers, but rather special symbols for talking about the behavior of integers. People sometimes say something like, “5 + infinity = infinity,” because if you start at 5 and keep counting up without ever stopping, you’ll get higher and higher numbers without limit. But it doesn’t follow from this that “infinity - infinity = 5.” You can’t count up from 0 without ever stopping, and then count down without ever stopping, and then find yourself at 5 when you’re done.

From this we can see that infinity is not only not-an-integer, it doesn’t even behave like an integer. If you unwisely try to mix up infinities with integers, you’ll need all sorts of special new inconsistent-seeming behaviors which you don’t need for 1, 2, 3 and other actual integers.

Even though infinity isn’t an integer, you don’t have to worry about being left at a loss for numbers. Although people have seen five sheep, millions of grains of sand, and septillions of atoms, no one has ever counted an infinity of anything. The same with continuous quantities—people have measured dust specks a millimeter across, animals a meter across, cities kilometers across, and galaxies thousands of lightyears across, but no one has ever measured anything an infinity across. In the real world, you don’t need a whole lot of infinity.<sup>1</sup>

In the usual way of writing probabilities, probabilities are between 0 and 1. A coin might have a probability of 0.5 of coming up tails, or the weatherman might assign probability 0.9 to rain tomorrow.

This isn’t the only way of writing probabilities, though. For example, you can transform probabilities into odds via the transformation O = (P/(1 - P)). So a probability of 50% would go to odds of 0.5/0.5 or 1, usually written 1:1, while a probability of 0.9 would go to odds of 0.9/0.1 or 9, usually written 9:1. To take odds back to probabilities you use P = (O∕(1 + O)), and this is perfectly reversible, so the transformation is an isomorphism—a two-way reversible mapping. Thus, probabilities and odds are isomorphic, and you can use one or the other according to convenience.

For example, it’s more convenient to use odds when you’re doing Bayesian updates. Let’s say that I roll a six-sided die: If any face except 1 comes up, there’s a 10% chance of hearing a bell, but if the face 1 comes up, there’s a 20% chance of hearing the bell. Now I roll the die, and hear a bell. What are the odds that the face showing is 1? Well, the prior odds are 1:5 (corresponding to the real number 1/5 = 0.20) and the likelihood ratio is 0.2:0.1 (corresponding to the real number 2) and I can just multiply these two together to get the posterior odds 2:5 (corresponding to the real number 2/5 or 0.40). Then I convert back into a probability, if I like, and get (0.4/1.4) = 2/7 = ~29%.

So odds are more manageable for Bayesian updates—if you use probabilities, you’ve got to deploy Bayes’s Theorem in its complicated version. But probabilities are more convenient for answering questions like “If I roll a six-sided die, what’s the chance of seeing a number from 1 to 4?” You can add up the probabilities of 1/6 for each side and get 4/6, but you can’t add up the odds ratios of 0.2 for each side and get an odds ratio of 0.8.

Why am I saying all this? To show that “odd ratios” are just as legitimate a way of mapping uncertainties onto real numbers as “probabilities.” Odds ratios are more convenient for some operations, probabilities are more convenient for others. A famous proof called Cox’s Theorem (plus various extensions and refinements thereof) shows that all ways of representing uncertainties that obey some reasonable-sounding constraints, end up isomorphic to each other.

Why does it matter that odds ratios are just as legitimate as probabilities? Probabilities as ordinarily written are between 0 and 1, and both 0 and 1 look like they ought to be readily reachable quantities—it’s easy to see 1 zebra or 0 unicorns. But when you transform probabilities onto odds ratios, 0 goes to 0, but 1 goes to positive infinity. Now absolute truth doesn’t look like it should be so easy to reach.

A representation that makes it even simpler to do Bayesian updates is the log odds—this is how E. T. Jaynes recommended thinking about probabilities. For example, let’s say that the prior probability of a proposition is 0.0001—this corresponds to a log odds of around -40 decibels. Then you see evidence that seems 100 times more likely if the proposition is true than if it is false. This is 20 decibels of evidence. So the posterior odds are around -40 dB + 20 dB = -20 dB, that is, the posterior probability is ~0.01.

When you transform probabilities to log odds, 0 goes to negative infinity and 1 goes to positive infinity. Now both infinite certainty and infinite improbability seem a bit more out-of-reach.

In probabilities, 0.9999 and 0.99999 seem to be only 0.00009 apart, so that 0.502 is much further away from 0.503 than 0.9999 is from 0.99999. To get to probability 1 from probability 0.99999, it seems like you should need to travel a distance of merely 0.00001.

But when you transform to odds ratios, 0.502 and 0.503 go to 1.008 and 1.012, and 0.9999 and 0.99999 go to 9,999 and 99,999. And when you transform to log odds, 0.502 and 0.503 go to 0.03 decibels and 0.05 decibels, but 0.9999 and 0.99999 go to 40 decibels and 50 decibels.

When you work in log odds, **the distance between any two degrees of uncertainty equals the amount of evidence you would need to go from one to the other**. That is, the log odds gives us a natural measure of spacing among degrees of confidence.

Using the log odds exposes the fact that reaching infinite certainty requires infinitely strong evidence, just as infinite absurdity requires infinitely strong counterevidence.

Furthermore, all sorts of standard theorems in probability have special cases if you try to plug 1s or 0s into them—like what happens if you try to do a Bayesian update on an observation to which you assigned probability 0.

So I propose that it makes sense to say that 1 and 0 are not in the probabilities; just as negative and positive infinity, which do not obey the field axioms, are not in the real numbers.

The main reason this would upset probability theorists is that we would need to rederive theorems previously obtained by assuming that we can marginalize over a joint probability by adding up all the pieces and having them sum to 1.

However, in the real world, when you roll a die, it doesn’t literally have infinite certainty of coming up some number between 1 and 6. The die might land on its edge; or get struck by a meteor; or the Dark Lords of the Matrix might reach in and write “37” on one side.

If you made a magical symbol to stand for “all possibilities I haven’t considered,” then you could marginalize over the events including this magical symbol, and arrive at a magical symbol “T” that stands for infinite certainty.

But I would rather ask whether there’s some way to derive a theorem without using magic symbols with special behaviors. That would be more elegant. Just as there are mathematicians who refuse to believe in the law of the excluded middle or infinite sets, I would like to be a probability theorist who doesn’t believe in absolute certainty.

---

<sup>1</sup>I should note for the more sophisticated reader that they do not need to write me with elaborate explanations of, say, the difference between ordinal numbers and cardinal numbers. I’m familiar with the different set-theoretic notions of infinity, but I don’t see a good use for them in probability theory.