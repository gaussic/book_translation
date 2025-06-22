## 奥卡姆剃刀

一个解释越复杂，你在信念空间中找到它所需的证据就越多。（传统理性主义常常误导性地表述为：“命题越复杂，论证它所需的证据就越多。”）那么，我们如何衡量一个解释的复杂度？又如何判断需要多少证据？

奥卡姆剃刀常被表述为“最简单且符合事实的解释”。罗伯特·海因莱因曾反驳说，最简单的解释是“街对面的女士是女巫，是她干的。”我们可以发现，用英语句子的长度来衡量“复杂度”并不合适。而且，仅仅“符合”事实（即没有排除事实）也是不够的。

为什么英语句子的长度不是衡量复杂度的好方法？因为当你说出一句话时，你用的是听众已经共享的概念标签——对方已经在头脑中存储了这些复杂性。假设我们把海因莱因那句话缩写成“Tldtsiawsdi!”，这样整个解释就能用一个词表达；或者更进一步，给它一个随意的短标签，比如“Fnord!”。这会降低复杂度吗？不会，因为你必须事先告诉听众“Tldtsiawsdi!”代表“街对面的女士是女巫，是她干的。”而“女巫”本身就是一系列非同寻常断言的标签——仅仅因为我们都知道它的意思，并不代表这个概念就简单。

一道巨大的闪电从天而降击中了某物，北欧部落的人说：“也许是某个强大的意志体发怒，扔下了雷电。”人脑是已知宇宙中最复杂的造物。如果“愤怒”看起来很简单，那只是因为我们看不到实现这种情感的全部神经回路。（想象你要向没有幽默感的外星人解释《周六夜现场》为什么好笑。但别自以为是——你自己也没有“fnord感”。）“愤怒”的复杂性，乃至“智能”的复杂性，都被假设雷神托尔的古人一笔带过了。

对人类来说，麦克斯韦方程组比托尔要难解释得多。人类没有像对“愤怒”那样的内建微积分词汇。你得先解释你的语言、语言背后的语言，甚至数学的概念本身，才能开始讲电学。

但我们又觉得，某种意义上，麦克斯韦方程组应该比人脑，或者比雷神托尔要简单。

确实如此。事实证明，写一个模拟麦克斯韦方程组的计算机程序，要比写一个模拟像托尔那样有智能和情感的心智的程序容易得多。

所罗门诺夫归纳的形式主义用“能生成该描述的最短计算机程序的长度”来衡量“描述的复杂度”。要谈论“最短的计算机程序”，你需要指定一个程序空间，这就需要一种语言和解释器。所罗门诺夫归纳用的是图灵机，或者说，是指定图灵机的比特串。如果你不喜欢图灵机？那你只需付出一个常数级的复杂度惩罚，设计自己的通用图灵机来解释你喜欢的任何编程语言。不同的归纳形式主义之间，最坏情况下只相差一个常数因子，这对应于为该形式主义写一个通用解释器所需的大小。

在我认为更好的所罗门诺夫归纳版本中，计算机程序不是给出确定性预测，而是为字符串分配概率。例如，我们可以写一个程序来解释一枚公平硬币的方法，就是让它为所有长度为N的2^N个字符串分配相等概率。这就是所罗门诺夫归纳拟合观测数据的方法。程序为观测数据分配的概率越高，拟合得就越好。而所有概率之和必须为1，所以如果一个程序想让某种可能性拟合得更好，就必须从其他可能性那里“偷”概率质量，这样其他可能性就会拟合得更差。不存在那种能同时给正反两面都分配100%概率的“超级公平硬币”。

我们如何权衡数据拟合度与程序复杂度？如果你忽略复杂度惩罚，只考虑拟合度，那你总会偏好那些声称能确定性预测数据、给出100%概率的程序。如果硬币结果是HTTHHT，那么声称硬币被操控成HTTHHT的程序，比声称硬币是公平的程序拟合度高64倍。反过来，如果你只考虑复杂度，忽略拟合度，那么“公平硬币”假说总是比其他假说更简单。即使硬币结果是HTHHTHHHTHHHHTHHHHHT……

实际上，公平硬币确实更简单，而且它对这组数据的拟合度和对任何其他20次抛硬币结果的拟合度完全一样——不多也不少——但我们又看到另一个假说，看起来也不太复杂，却能更好地拟合数据。

如果你让程序多存储一位二进制信息，它就能把可能性空间减半，从而为剩下空间的所有点分配两倍概率。这意味着，程序复杂度每增加一比特，拟合度的提升就至少要有“两倍”的回报。如果你试图写一个程序，明确存储HTTHHT这样的结果，那么你在复杂度上损失的6比特，必须抵消拟合度提升64倍带来的所有合理性。否则，你迟早会得出所有公平硬币都是被操控的结论。

除非你的程序很聪明，能压缩数据，否则仅仅把一位数据从数据本身转移到程序描述里是没有意义的。

所罗门诺夫归纳预测序列的方式，是对所有允许的计算机程序求和——如果允许所有程序，所罗门诺夫归纳就变得不可计算——每个程序的先验概率是2的负代码长度次方，然后再根据其对已观测数据的拟合度加权。这样你就得到了一个加权的专家混合体，可以用来预测未来的比特。

最短消息长度（Minimum Message Length）形式主义几乎等价于所罗门诺夫归纳。你先发送一串描述代码的字符串，然后再发送一串用该代码描述数据的字符串。哪个解释导致总消息最短，哪个就是最优解释。如果你把允许的代码集看作计算机程序空间，把代码描述语言看作通用机，那么最短消息长度就几乎等价于所罗门诺夫归纳。<sup>1</sup>

这让我们清楚地看到，用“街对面的女士是女巫，是她干的”来解释序列0101010101的问题。如果你要给朋友发消息，描述你观察到的序列，你必须说：“街对面的女士是女巫，她让序列变成了0101010101。”你指控女巫并不能让剩下的信息变短；你仍然需要完整描述她的“巫术”导致的数据。

“女巫”也许在定性上允许了我们的观测结果；但那是因为“女巫”什么都允许，就像说“燃素！”一样。所以，即使你说了“女巫”，你还是得把所有观测数据完整描述一遍。你并没有通过传递关于女巫的信息压缩描述观测的总长度；你只是加了个无用的前言，反而让总长度变长了。

真正的偷换隐藏在“是她干的”这句话里的“它”——女巫到底干了什么？

当然，由于事后偏见、锚定效应、伪解释、伪因果、正偏见和动机性认知，我们很容易觉得“如果一个女人是女巫，她当然会让硬币出现0101010101”。但我很快会谈到这些……

---

<sup>1</sup> 之所以说“几乎”，是因为最短消息长度选择的是最短的程序，而不是对所有程序求和。

---

## Occam’s Razor

The more complex an explanation is, the more evidence you need just to find it in belief-space. (In Traditional Rationality this is often phrased misleadingly, as “The more complex a proposition is, the more evidence is required to argue for it.”) How can we measure the complexity of an explanation? How can we determine how much evidence is required?

Occam’s Razor is often phrased as “The simplest explanation that fits the facts.” Robert Heinlein replied that the simplest explanation is “The lady down the street is a witch; she did it.” One observes that the length of an English sentence is not a good way to measure “complexity.” And “fitting” the facts by merely failing to prohibit them is insufficient.

Why, exactly, is the length of an English sentence a poor measure of complexity? Because when you speak a sentence aloud, you are using labels for concepts that the listener shares—the receiver has already stored the complexity in them. Suppose we abbreviated Heinlein’s whole sentence as “Tldtsiawsdi!” so that the entire explanation can be conveyed in one word; better yet, we’ll give it a short arbitrary label like “Fnord!” Does this reduce the complexity? No, because you have to tell the listener in advance that “Tldtsiawsdi!” stands for “The lady down the street is a witch; she did it.” “Witch,” itself, is a label for some extraordinary assertions—just because we all know what it means doesn’t mean the concept is simple.

An enormous bolt of electricity comes out of the sky and hits something, and the Norse tribesfolk say, “Maybe a really powerful agent was angry and threw a lightning bolt.” The human brain is the most complex artifact in the known universe. If anger seems simple, it’s because we don’t see all the neural circuitry that’s implementing the emotion. (Imagine trying to explain why Saturday Night Live is funny, to an alien species with no sense of humor. But don’t feel superior; you yourself have no sense of fnord.) The complexity of anger, and indeed the complexity of intelligence, was glossed over by the humans who hypothesized Thor the thunder-agent.

To a human, Maxwell’s equations take much longer to explain than Thor. Humans don’t have a built-in vocabulary for calculus the way we have a built-in vocabulary for anger. You’ve got to explain your language, and the language behind the language, and the very concept of mathematics, before you can start on electricity.

And yet it seems that there should be some sense in which Maxwell’s equations are simpler than a human brain, or Thor the thunder-agent.

There is. It’s enormously easier (as it turns out) to write a computer program that simulates Maxwell’s equations, compared to a computer program that simulates an intelligent emotional mind like Thor.

The formalism of Solomonoff induction measures the “complexity of a description” by the length of the shortest computer program which produces that description as an output. To talk about the “shortest computer program” that does something, you need to specify a space of computer programs, which requires a language and interpreter. Solomonoff induction uses Turing machines, or rather, bitstrings that specify Turing machines. What if you don’t like Turing machines? Then there’s only a constant complexity penalty to design your own universal Turing machine that interprets whatever code you give it in whatever programming language you like. Different inductive formalisms are penalized by a worst-case constant factor relative to each other, corresponding to the size of a universal interpreter for that formalism.

In the better (in my humble opinion) versions of Solomonoff induction, the computer program does not produce a deterministic prediction, but assigns probabilities to strings. For example, we could write a program to explain a fair coin by writing a program that assigns equal probabilities to all 2N strings of length N. This is Solomonoff induction’s approach to fitting the observed data. The higher the probability a program assigns to the observed data, the better that program fits the data. And probabilities must sum to 1, so for a program to better “fit” one possibility, it must steal probability mass from some other possibility which will then “fit” much more poorly. There is no superfair coin that assigns 100% probability to heads and 100% probability to tails.

How do we trade off the fit to the data, against the complexity of the program? If you ignore complexity penalties, and think only about fit, then you will always prefer programs that claim to deterministically predict the data, assign it 100% probability. If the coin shows HTTHHT, then the program that claims that the coin was fixed to show HTTHHT fits the observed data 64 times better than the program which claims the coin is fair. Conversely, if you ignore fit, and consider only complexity, then the “fair coin” hypothesis will always seem simpler than any other hypothesis. Even if the coin turns up HTHHTHHHTHHHHTHHHHHT . . .

Indeed, the fair coin is simpler and it fits this data exactly as well as it fits any other string of 20 coinflips—no more, no less—but we see another hypothesis, seeming not too complicated, that fits the data much better.

If you let a program store one more binary bit of information, it will be able to cut down a space of possibilities by half, and hence assign twice as much probability to all the points in the remaining space. This suggests that one bit of program complexity should cost at least a “factor of two gain” in the fit. If you try to design a computer program that explicitly stores an outcome like HTTHHT, the six bits that you lose in complexity must destroy all plausibility gained by a 64-fold improvement in fit. Otherwise, you will sooner or later decide that all fair coins are fixed.

Unless your program is being smart, and compressing the data, it should do no good just to move one bit from the data into the program description.

The way Solomonoff induction works to predict sequences is that you sum up over all allowed computer programs—if every program is allowed, Solomonoff induction becomes uncomputable—with each program having a prior probability of 1/2 to the power of its code length in bits, and each program is further weighted by its fit to all data observed so far. This gives you a weighted mixture of experts that can predict future bits.

The Minimum Message Length formalism is nearly equivalent to Solomonoff induction. You send a string describing a code, and then you send a string describing the data in that code. Whichever explanation leads to the shortest total message is the best. If you think of the set of allowable codes as a space of computer programs, and the code description language as a universal machine, then Minimum Message Length is nearly equivalent to Solomonoff induction.<sup>1</sup>

This lets us see clearly the problem with using “The lady down the street is a witch; she did it” to explain the pattern in the sequence 0101010101. If you’re sending a message to a friend, trying to describe the sequence you observed, you would have to say: “The lady down the street is a witch; she made the sequence come out 0101010101.” Your accusation of witchcraft wouldn’t let you shorten the rest of the message; you would still have to describe, in full detail, the data which her witchery caused.

Witchcraft may fit our observations in the sense of qualitatively permitting them; but this is because witchcraft permits everything, like saying “Phlogiston!” So, even after you say “witch,” you still have to describe all the observed data in full detail. You have not compressed the total length of the message describing your observations by transmitting the message about witchcraft; you have simply added a useless prologue, increasing the total length.

The real sneakiness was concealed in the word “it” of “A witch did it.” A witch did what?

Of course, thanks to hindsight bias and anchoring and fake explanations and fake causality and positive bias and motivated cognition, it may seem all too obvious that if a woman is a witch, of course she would make the coin come up 0101010101. But I’ll get to that soon enough. . .

---

<sup>1</sup>Nearly, because it chooses the shortest program, rather than summing up over all programs.