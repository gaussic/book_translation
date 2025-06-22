## 0 和 1 不是概率

一、二、三都是整数，负四也是。如果你一直往上数，或者一直往下数，你会遇到很多整数。但你不会遇到所谓的“正无穷”或“负无穷”，所以它们不是整数。

正无穷和负无穷不是整数，而是用来描述整数行为的特殊符号。人们有时会说“5 + 无穷 = 无穷”，因为如果你从 5 开始一直不停地往上数，你会得到越来越大的数，没有上限。但这并不意味着“无穷 − 无穷 = 5”。你不能从 0 一直往上数到无穷，再一直往下数到无穷，最后停在 5。

由此可见，无穷不仅不是整数，甚至行为方式也和整数完全不同。如果你不小心把无穷和整数混在一起用，就需要各种特殊的新规则来处理它们，这些规则在 1、2、3 等实际整数之间并不需要。

即使无穷不是整数，你也不用担心会“缺少数字”。虽然人们见过五只羊、几百万粒沙子、千万亿个原子，但没人真的数过无穷多个什么东西。连续量也是如此——人们测量过毫米级的尘埃、米级的动物、千米级的城市、数千光年宽的星系，但没人测量过“无穷大”的东西。在现实世界里，你根本用不上无穷。

通常我们写概率时，概率值在 0 到 1 之间。比如硬币正面概率是 0.5，天气预报说明天下雨概率是 0.9。

但这不是表示概率的唯一方式。例如，你可以用赔率来表示概率，转换公式是 O = (P / (1 − P))。所以 50% 的概率对应赔率 0.5/0.5 = 1，通常写作 1:1；0.9 的概率对应赔率 0.9/0.1 = 9，写作 9:1。要把赔率转回概率，用 P = (O / (1 + O))，这是完全可逆的，所以这种转换是同构的——即双向可逆映射。因此，概率和赔率是同构的，可以根据需要任选其一。

例如，在做贝叶斯更新时，用赔率更方便。假设我掷一个六面骰子：如果掷出 1 以外的面，有 10% 的概率听到铃声；如果掷出 1，有 20% 的概率听到铃声。现在我掷骰子，听到了铃声。掷出 1 的赔率是多少？先验赔率是 1:5（对应实数 1/5 = 0.20），似然比是 0.2:0.1（对应实数 2），两者相乘得后验赔率 2:5（对应实数 2/5 或 0.40）。然后可以转回概率，得到 (0.4/1.4) = 2/7 ≈ 29%。

所以做贝叶斯更新时用赔率更顺手——如果用概率，就得用复杂版的贝叶斯公式。但如果你想问“掷一个六面骰子，出现 1 到 4 的概率是多少？”，用概率更方便。你可以把每一面的 1/6 概率相加得到 4/6，但赔率不能直接相加。

为什么要说这些？是为了说明“赔率”作为将不确定性映射到实数的方式和“概率”一样合法。某些运算用赔率方便，某些运算用概率方便。著名的考克斯定理（Cox’s Theorem）及其各种扩展和完善，证明了所有满足合理约束的不确定性表示方法，最终都是同构的。

为什么赔率和概率一样合法很重要？通常写法下，概率在 0 到 1 之间，0 和 1 看起来都很容易达到——看到 1 只斑马或 0 只独角兽都很简单。但当你把概率转换为赔率时，0 变成 0，而 1 变成正无穷。此时，绝对真理看起来就没那么容易达到。

还有一种更方便做贝叶斯更新的表示法是对数赔率——E. T. Jaynes 推荐用这种方式思考概率。例如，某命题的先验概率是 0.0001，对应对数赔率约为 −40 分贝。你看到一条证据，如果命题为真时出现的概率是为假时的 100 倍，这就是 20 分贝的证据。后验对数赔率就是 −40 dB + 20 dB = −20 dB，即后验概率约为 0.01。

当你把概率转换为对数赔率时，0 变成负无穷，1 变成正无穷。此时，无限确定性和无限不可能性都变得遥不可及。

在概率表示下，0.9999 和 0.99999 只差 0.00009，所以 0.502 和 0.503 之间的距离比 0.9999 和 0.99999 之间还远。但转换为赔率后，0.502 和 0.503 变成 1.008 和 1.012，0.9999 和 0.99999 变成 9,999 和 99,999。再转换为对数赔率，0.502 和 0.503 变成 0.03 分贝和 0.05 分贝，而 0.9999 和 0.99999 变成 40 分贝和 50 分贝。

用对数赔率时，**任意两个不确定度之间的距离，等于你需要多少证据才能从一个状态转到另一个状态。**也就是说，对数赔率为我们提供了一个自然的信心间距度量。

用对数赔率可以看出，达到无限确定性需要无限强的证据，就像达到无限荒谬性需要无限强的反证一样。

此外，概率论中的许多标准定理，如果你试图把 1 或 0 代入，会出现特殊情况——比如你试图对一个概率为 0 的事件做贝叶斯更新时会出问题。

所以我建议，可以认为 1 和 0 并不属于概率的范畴；就像正负无穷不属于实数域一样，因为它们不满足域的公理。

概率论者可能会因此不满，主要原因是我们需要重新推导一些定理，这些定理原本假设可以把联合概率的所有部分加起来，和为 1。

但在现实世界里，当你掷骰子时，它并不是“绝对确定”会出现 1 到 6 之间的某个数。骰子可能立在边上，可能被陨石击中，或者矩阵黑暗领主可能突然伸手在某一面写上“37”。

如果你用一个魔法符号代表“所有我没考虑到的可能性”，那么你可以把这些事件加起来，得到一个代表无限确定性的魔法符号“T”。

但我更希望能找到一种不用魔法符号和特殊规则的方法来推导定理。那样会更优雅。就像有些数学家拒绝相信排中律或无限集合一样，我也想成为一个不相信绝对确定性的概率论者。

---

<sup>1</sup>有经验的读者无需给我写信解释序数和基数的区别。我熟悉集合论中不同的无穷概念，但我认为它们在概率论中没什么用。

---

## 0 And 1 Are Not Probabilities

One, two, and three are all integers, and so is negative four. If you keep counting up, or keep counting down, you’re bound to encounter a whole lot more integers. You will not, however, encounter anything called “positive infinity” or “negative infinity,” so these are not integers.

Positive and negative infinity are not integers, but rather special symbols for talking about the behavior of integers. People sometimes say something like, “5 + infinity = infinity,” because if you start at 5 and keep counting up without ever stopping, you’ll get higher and higher numbers without limit. But it doesn’t follow from this that “infinity− infinity = 5.” You can’t count up from 0 without ever stopping, and then count down without ever stopping, and then find yourself at 5 when you’re done.

From this we can see that infinity is not only not-an-integer, it doesn’t even behave like an integer. If you unwisely try to mix up infinities with integers, you’ll need all sorts of special new inconsistent-seeming behaviors which you don’t need for 1, 2, 3 and other actual integers.

Even though infinity isn’t an integer, you don’t have to worry about being left at a loss for numbers. Although people have seen five sheep, millions of grains of sand, and septillions of atoms, no one has ever counted an infinity of anything. The same with continuous quantities—people have measured dust specks a millimeter across, animals a meter across, cities kilometers across, and galaxies thousands of lightyears across, but no one has ever measured anything an infinity across. In the real world, you don’t need a whole lot of infinity.<sup>1</sup>

In the usual way of writing probabilities, probabilities are between 0 and 1. A coin might have a probability of 0.5 of coming up tails, or the weatherman might assign probability 0.9 to rain tomorrow.

This isn’t the only way of writing probabilities, though. For example, you can transform probabilities into odds via the transformation O= (P/(1− P)). So a probability of 50% would go to odds of 0.5/0.5 or 1, usually written 1:1, while a probability of 0.9 would go to odds of 0.9/0.1 or 9, usually written 9:1. To take odds back to probabilities you use P= (O/(1 + O)), and this is perfectly reversible, so the transformation is an isomorphism—a two-way reversible mapping. Thus, probabilities and odds are isomorphic, and you can use one or the other according to convenience.

For example, it’s more convenient to use odds when you’re doing Bayesian updates. Let’s say that I roll a six-sided die: If any face except 1 comes up, there’s a 10% chance of hearing a bell, but if the face 1 comes up, there’s a 20% chance of hearing the bell. Now I roll the die, and hear a bell. What are the odds that the face showing is 1? Well, the prior odds are 1:5 (corresponding to the real number 1/5= 0.20) and the likelihood ratio is 0.2:0.1 (corresponding to the real number 2) and I can just multiply these two together to get the posterior odds 2:5 (corresponding to the real number 2/5 or 0.40). Then I convert back into a probability, if I like, and get (0.4/1.4)= 2/7= ∼29%.

So odds are more manageable for Bayesian updates—if you use probabilities, you’ve got to deploy Bayes’s Theorem in its complicated version. But probabilities are more convenient for answering questions like “If I roll a six-sided die, what’s the chance of seeing a number from 1 to 4?” You can add up the probabilities of 1/6 for each side and get 4/6, but you can’t add up the odds ratios of 0.2 for each side and get an odds ratio of 0.8.

Why am I saying all this? To show that “odd ratios” are just as legitimate a way of mapping uncertainties onto real numbers as “probabilities.” Odds ratios are more convenient for some operations, probabilities are more convenient for others. A famous proof called Cox’s Theorem (plus various extensions and refinements thereof) shows that all ways of representing uncertainties that obey some reasonable-sounding constraints, end up isomorphic to each other.

Why does it matter that odds ratios are just as legitimate as probabilities? Probabilities as ordinarily written are between 0 and 1, and both 0 and 1 look like they ought to be readily reachable quantities—it’s easy to see 1 zebra or 0 unicorns. But when you transform probabilities onto odds ratios, 0 goes to 0, but 1 goes to positive infinity. Now absolute truth doesn’t look like it should be so easy to reach.

A representation that makes it even simpler to do Bayesian updates is the log odds—this is how E. T. Jaynes recommended thinking about probabilities. For example, let’s say that the prior probability of a proposition is 0.0001— this corresponds to a log odds of around−40 decibels. Then you see evidence that seems 100 times more likely if the proposition is true than if it is false. This is 20 decibels of evidence. So the posterior odds are around −40 dB + 20 dB= −20 dB, that is, the posterior probability is∼0.01.

When you transform probabilities to log odds, 0 goes to negative infinity and 1 goes to positive infinity. Now both infinite certainty and infinite improbability seem a bit more out-of-reach.

In probabilities, 0.9999 and 0.99999 seem to be only 0.00009 apart, so that 0.502 is much further away from 0.503 than 0.9999 is from 0.99999. To get to probability 1 from probability 0.99999, it seems like you should need to travel a distance of merely 0.00001.

But when you transform to odds ratios, 0.502 and 0.503 go to 1.008 and 1.012, and 0.9999 and 0.99999 go to 9,999 and 99,999. And when you transform to log odds, 0.502 and 0.503 go to 0.03 decibels and 0.05 decibels, but 0.9999 and 0.99999 go to 40 decibels and 50 decibels.

When you work in log odds, **the distance between any two degrees of uncertainty equals the amount of evidence you would need to go from one to the other.** That is, the log odds gives us a natural measure of spacing among degrees of confidence.

Using the log odds exposes the fact that reaching infinite certainty requires infinitely strong evidence, just as infinite absurdity requires infinitely strong counterevidence.

Furthermore, all sorts of standard theorems in probability have special cases if you try to plug 1s or 0s into them—like what happens if you try to do a Bayesian update on an observation to which you assigned probability 0.

So I propose that it makes sense to say that 1 and 0 are not in the probabilities; just as negative and positive infinity, which do not obey the field axioms, are not in the real numbers.

The main reason this would upset probability theorists is that we would need to rederive theorems previously obtained by assuming that we can marginalize over a joint probability by adding up all the pieces and having them sum to 1.

However, in the real world, when you roll a die, it doesn’t literally have infinite certainty of coming up some number between 1 and 6. The die might land on its edge; or get struck by a meteor; or the Dark Lords of the Matrix might reach in and write “37” on one side.

If you made a magical symbol to stand for “all possibilities I haven’t considered,” then you could marginalize over the events including this magical symbol, and arrive at a magical symbol “T” that stands for infinite certainty.

But I would rather ask whether there’s some way to derive a theorem without using magic symbols with special behaviors. That would be more elegant. Just as there are mathematicians who refuse to believe in the law of the excluded middle or infinite sets, I would like to be a probability theorist who doesn’t believe in absolute certainty.

---

<sup>1</sup>I should note for the more sophisticated reader that they do not need to write me with elaborate explanations of, say, the difference between ordinal numbers and cardinal numbers.

I’m familiar with the different set-theoretic notions of infinity, but I don’t see a good use for them in probability theory.