## 什么是被筛选的证据？

作者：Eliezer Yudkowsky

我讨论过一个聪明论辩者的两难处境：他被雇来推销一个盒子，这个盒子可能有钻石，也可能没有。他告诉你，这个盒子上有一个蓝色印章，而根据一个真实且已知的事实，有钻石的盒子比空盒子更有可能有蓝色印章。从贝叶斯视角来看，此时你该怎么做？你是否必须无助地更新你的概率，就像这个聪明论辩者希望的那样？

如果你能亲自查看盒子，你就可以自己加总所有迹象。但如果你看不到呢？如果你唯一拥有的证据，就是那个聪明论辩者所说的话，而他虽然受到法律约束只能说真话，但却并未告诉你他所知道的一切？他所说的每一句话都是有效的证据——那你怎么可能不更新你的概率？难道就因为这些话是被选择性的讲出来的，就不再成立了吗？例如在 Everett 分支或 Tegmark 平行宇宙中，只要盒子 B 有蓝色印章，它含有钻石的比例仍然是某个既定比例。根据 Jaynes 的观点，一个贝叶斯主义者必须基于所有已知证据进行条件判断，否则就会导致悖论。但如果这样的话，只要有足够多的迹象可供选择，聪明论辩者就可以让你相信他们想让你相信的任何事。听起来不太对劲，对吧？

我们来看一个更简单的例子：一个偏置的硬币，可能以 2/3 的概率出现正面（H）和 1/3 的概率出现反面（T），或者相反，两种情况在先验上是等概率的。每次出现 H，都是向硬币偏向 H 的假设提供了 1 比特的信息；每次出现 T，也向偏向 T 的假设提供 1 比特的信息。<sup>1</sup>
我把这枚硬币掷了十次，然后告诉你：“第 4 次、第 6 次和第 9 次是正面。”那么，现在这枚硬币是偏向正面的后验概率是多少？

答案是：这可以是几乎任何数值，取决于我说出这些话背后的因果链——也就是我选择报告哪几次抛掷的算法。

* 也许我遵循的是固定报告第 4、6、9 次结果的规则，不管那几次和其他次数的结果是什么。如果你知道我使用的是这种算法，那么后验概率是 8:1，倾向于认为硬币是偏向 H 的。
* 也许我只报告那些出现 H 的抛掷结果。这种情况下，你就知道其余 7 次都是反面（T），此时后验概率是 1:16，反而认为硬币更可能是偏向 T 的。
* 也许我事先设定好，只有当我算出硬币偏向 H 的概率超过 98% 时，我才会报告第 4、6、9 次的结果。诸如此类。

再来看另一个例子：**蒙提霍尔问题**：

> 在一个游戏节目中，你需要在三扇门中选择一扇。你知道其中一间房间有 \$100,000，其他两个是空的。你选择了第 1 号门。接着主持人打开第 2 号门，露出一个空房间。你会换到第 3 号门，还是坚持第 1 号门？

答案取决于主持人使用的策略。如果主持人总是打开一个门，并且总是选择通向空房间的门，那么你应该换到第 3 号门。如果主持人总是打开第 2 号门，不管那后面是什么，那么第 1 号和第 3 号门都有 50% 的可能藏有奖金。如果主持人只在你一开始就选中奖金那扇门的情况下才会开门，那么你就应该坚持选择第 1 号门。

你不能只根据“第 2 号门是空的”这个事实来更新概率，你还得考虑“主持人选择打开了第 2 号门”这一事实。很多人之所以被标准的蒙提霍尔问题困惑，是因为他们只更新了“#2 是空的”这一事实，这样一来 #1 和 #3 似乎就有同样的概率。这就是为什么贝叶斯主义者被告诫必须基于自己所有的知识进行条件判断，否则就会陷入悖论。

当有人说“第 4 次抛硬币是正面”，我们并不是在以“第 4 次抛硬币是正面”为条件去更新概率——我们不是在挑选所有“第 4 次为正面”的可能世界，而是在以“一个按某种算法行事的人说了‘第 4 次是正面’”这一事实为条件进行更新。说出的句子并不等同于那个事实本身——不要被语言的表面意义误导。

大多数法律程序的运作建立在一个假设上：每个案件都有两个对立方，而且相比于找到一个中立者，更容易找到两个有偏见的人。控方和辩方中总有人有动机去呈现某项证据，因此法院可以看到全部证据——这是理论。如果在那个盒子的问题中，有两个聪明论辩者，那虽不如一个好奇的求知者，但也几乎一样好。然而现实世界的问题往往有多面性，有深度，有不显而易见的答案，这些不是靠“蓝方”和“绿方”互相喊叫就能解决的。

但你也要小心，别滥用“被筛选的证据”这个概念，作为一种**万能反驳术**，来无视你不喜欢的所有证据，比如说：“那个论点是被筛选的，所以我可以忽略它。”如果你对一个反对意见感到恼火，那你显然已经熟悉该议题，也足够在乎以至于站队了。你很可能早就知道了自己那一方的最有力论据。你没有理由因为听到一个反对观点，就推断出某些你没见过的有利证据的存在。因此，你只能面对那些**令人不舒服的事实本身**；盒子 B 上的蓝色印章，**依然是证据**。

但如果你是**第一次**听到某个论点，而且你只听到了**单方面的**观点，那你确实需要当心！某种意义上，在你听过五分钟的创世论者的说法之前，你是无法真正信任自然选择理论的——**听完之后你才会知道，进化论确实站得住脚。**

---

<sup>1</sup> 此处的“比特”是衡量某事提供了多少信息的单位——是概率的对数，以 1/2 为底。
假设某个问题只有两种可能的答案，你最初对这两个答案的概率都是 50%。如果我告诉你第一个答案是对的，而你完全信任我，那你就获得了 1 比特的信息。如果有四个等可能选项，我告诉你第一个是对的，那是 2 比特；有八个选项并指出正确答案，就是 3 比特，以此类推。这个问题在《[要多少证据才够？](https://www.lesswrong.com/rationality/how-much-evidence-does-it-take)》（选自 *地图与领地*）中有进一步讨论。

---

## What Evidence Filtered Evidence?

by Eliezer Yudkowsky

I discussed the dilemma of the clever arguer, hired to sell you a box that may or may not contain a diamond. The clever arguer points out to you that the box has a blue stamp, and it is a valid known fact that diamond-containing boxes are more likely than empty boxes to bear a blue stamp. What happens at this point, from a Bayesian perspective? Must you helplessly update your probabilities, as the clever arguer wishes?

If you can look at the box yourself, you can add up all the signs yourself. What if you can’t look? What if the only evidence you have is the word of the clever arguer, who is legally constrained to make only true statements, but does not tell you everything they know? Each statement that the clever arguer makes is valid evidence—how could you not update your probabilities? Has it ceased to be true that, in such-and-such a proportion of Everett branches or Tegmark duplicates in which box B has a blue stamp, box B contains a diamond? According to Jaynes, a Bayesian must always condition on all known evidence, on pain of paradox. But then the clever arguer can make you believe anything they choose, if there is a sufficient variety of signs to selectively report. That doesn’t sound right.

Consider a simpler case, a biased coin, which may be biased to come up 2/3 heads and 1/3 tails, or 1/3 heads and 2/3 tails, both cases being equally likely a priori. Each H observed is 1 bit of evidence for an H-biased coin; each T observed is 1 bit of evidence for a T-biased coin.<sup>1</sup> I flip the coin ten times, and then I tell you, “The 4th flip, 6th flip, and 9th flip came up heads.” What is your posterior probability that the coin is H-biased?

And the answer is that it could be almost anything, depending on what chain of cause and effect lay behind my utterance of those words—my selection of which flips to report.

- I might be following the algorithm of reporting the result of the 4th, 6th, and 9th flips, regardless of the result of those and all other flips. If you know that I used this algorithm, the posterior odds are 8:1 in favor of an H-biased coin.
- I could be reporting on all flips, and only flips, that came up heads. In this case, you know that all 7 other flips came up tails, and the posterior odds are 1:16 against the coin being H-biased.
- I could have decided in advance to say the result of the 4th, 6th, and 9th flips only if the probability of the coin being H-biased exceeds 98%. And so on.

Or consider the Monty Hall problem:

> On a game show, you are given the choice of three doors leading to three rooms. You know that in one room is $100,000, and the other two are empty. The host asks you to pick a door, and you pick door #1. Then the host opens door #2, revealing an empty room. Do you want to switch to door #3, or stick with door #1?

The answer depends on the host’s algorithm. If the host always opens a door and always picks a door leading to an empty room, then you should switch to door #3. If the host always opens door #2 regardless of what is behind it, #1 and #3 both have 50% probabilities of containing the money. If the host only opens a door, at all, if you initially pick the door with the money, then you should definitely stick with #1.

You shouldn’t just condition on #2 being empty, but this fact plus the fact of the host choosing to open door #2. Many people are confused by the standard Monty Hall problem because they update only on #2 being empty, in which case #1 and #3 have equal probabilities of containing the money. This is why Bayesians are commanded to condition on all of their knowledge, on pain of paradox.

When someone says, “The 4th coinflip came up heads,” we are not conditioning on the 4th coinflip having come up heads—we are not taking the subset of all possible worlds where the 4th coinflip came up heads—but rather are conditioning on the subset of all possible worlds where a speaker following some particular algorithm said, “The 4th coinflip came up heads.” The spoken sentence is not the fact itself; don’t be led astray by the mere meanings of words.

Most legal processes work on the theory that every case has exactly two opposed sides and that it is easier to find two biased humans than one unbiased one. Between the prosecution and the defense, someone has a motive to present any given piece of evidence, so the court will see all the evidence; that is the theory. If there are two clever arguers in the box dilemma, it is not quite as good as one curious inquirer, but it is almost as good. But that is with two boxes. Reality often has many-sided problems, and deep problems, and nonobvious answers, which are not readily found by Blues and Greens shouting at each other.

Beware lest you abuse the notion of evidence-filtering as a Fully General Counterargument to exclude all evidence you don’t like: “That argument was filtered, therefore I can ignore it.” If you’re ticked off by a contrary argument, then you are familiar with the case, and care enough to take sides. You probably already know your own side’s strongest arguments. You have no reason to infer, from a contrary argument, the existence of new favorable signs and portents which you have not yet seen. So you are left with the uncomfortable facts themselves; a blue stamp on box B is still evidence.

But if you are hearing an argument for the first time, and you are only hearing one side of the argument, then indeed you should beware! In a way, no one can really trust the theory of natural selection until after they have listened to creationists for five minutes; and then they know it’s solid.

---

<sup>1</sup>“Bits” in this context are a measure of how much evidence something provides—they’re the logarithms of probabilities, base 1/2.

Suppose a question has exactly two possible (mutually exclusive) answers, and you initially assign 50% probability to each answer. If I then tell you that the first answer is correct (and you have complete faith in my claim), then you have acquired one bit of evidence. If there are four equally likely options, and I tell you the first one is correct, then I have given you two bits; if there are eight and I tell you the right one, then I have given you three bits; and so on. This is discussed further in “[How Much Evidence Does It Take?](https://www.lesswrong.com/rationality/how-much-evidence-does-it-take)” (in Map and Territory).