## 论证屏蔽权威

*作者：Eliezer Yudkowsky*

**场景一：** Barry 是一位著名地质学家。Charles 是一名十四岁的少年惯犯，有多次被捕记录，且偶尔会有精神病发作。Barry 向 Arthur 断言了一个关于岩石的反直觉观点，Arthur 判断其成立的概率为 90%。接着 Charles 也作出一个同样反直觉的断言，Arthur 判断它成立的概率为 10%。显然，Arthur 在决定是否相信陈述时，将说话者的**权威**纳入了考量。

**场景二：** David 提出了一个反直觉的物理观点，并向 Arthur 提供了详尽的论证，包括引用资料。Ernie 也提出了一个同样反直觉的观点，但给出的论证很站不住脚，充满了跳跃式推理。David 和 Ernie 都声称，这就是他们能给出的**最佳解释**（不只是对 Arthur，而是对任何人）。Arthur 听完 David 的解释后，给该观点赋予 90% 的概率，而 Ernie 的观点只有 10%。

这两个场景看起来好像是对称的：Arthur 都是在权衡证据，不管是强/弱权威，还是强/弱论证。

但现在假设 Arthur 要求 Barry 和 Charles 提供完整的技术论证，附带参考文献；Barry 和 Charles 交出的论证都一样好，Arthur 也核查了文献，发现没有问题。然后 Arthur 再要求 David 和 Ernie 出示资历，发现他们的资历差不多——也许都是小丑，也许都是物理学家。

**如果 Arthur 有足够的知识理解所有技术论证**——否则它们不过是响亮的噪音——那么他仍然会觉得 David 的观点比 Ernie 的更可信得多，而 Barry 相较于 Charles 顶多是略胜一筹。

事实上，如果技术论证足够有力，Barry 对 Charles 的优势甚至可以忽略不计。**一个好的技术论证，其目的正是排除了对说话人权威的依赖。**

同样地，如果我们真诚地相信 Ernie 的论证已经是他能给出的最好论证——包括他进行的所有推理步骤，以及他所参考的所有资料和权威——那么我们几乎可以忽略 Ernie 的资历。不管他是物理学家还是小丑，这都不该成为影响因素。（再次强调，这一切都基于我们有能力理解他的论证。否则他只是在念咒语，而我们是否“相信”这些咒语，就非常依赖他的权威。）

所以这里存在一种**论证和权威之间的不对称性**。如果我们已知某人的权威，我们仍然很想听听他的论证；但如果我们完全了解了论证，就没多少理由再去关心说话人是否有权威。

新手可能会说：很显然，**权威和论证是本质上不同的证据类型**，而贝叶斯概率论那种枯燥简洁的方法无法解释这种差异。<sup>1</sup>
毕竟，两种情境中我们赋予的概率强度（90% 对比 10%）是一样的，可它们在被**结合使用时**却表现出不同的行为。那么我们该如何解释这一点？

以下是概率论中表示这种差异的“半个技术性演示”。（剩下的部分，你可以凭我的权威接受，或自己查阅参考书。）

如果
P(H|E1) = 90%，
P(H|E2) = 9%，
那 P(H|E1, E2) 是多少？

也就是说，如果得知 E1 为真让我们将 H 的概率设为 90%，得知 E2 为真则设为 9%，那么如果我们同时得知 E1 和 E2 为真，该把 H 的概率设为多少？

这个问题**在已知信息的基础上，是无法用概率论计算出来的。**
问题不在于缺少 H 的先验概率。问题是，E1 和 E2 可能**不是相互独立**的。

假设 H 是“我的人行道很滑”，E1 是“我的喷头正在喷水”，E2 是“现在是夜晚”。
喷头从启动后 1 分钟起使人行道变滑，一直到喷水结束后一会儿为止。喷头总共喷水 10 分钟。
所以，如果我们知道喷头正在工作，判断人行道滑的概率是 90%。
喷头在夜间工作的时间占比是 10%，所以如果只知道是夜晚，判断人行道滑的概率为 9%。
但如果我们同时知道是夜晚**且**喷头在喷水——即知道 E1 和 E2 都成立——那么人行道滑的概率还是 90%。

我们可以用**图模型**来表示如下：

```
夜晚 ——→ 喷头 ——→ 滑
```

是否为夜晚影响喷头是否开启，而喷头是否开启影响人行道是否打滑。

箭头的方向是有含义的。如果我们写成：

```
夜晚 ——→ 喷头 ←—— 滑
```

这就意味着，如果我不知道喷头的状态，那么“夜晚”和“人行道滑”两个事件是独立的。

再看一个例子，我掷两个骰子，得出它们点数之和：

```
骰子1 ——→ 总和 ←—— 骰子2
```

如果你没有告诉我总和是多少，只告诉我第一个骰子是 6，那么我对第二个骰子的点数仍然一无所知。
但如果你又告诉我总和是 7，那我就知道第二个骰子是 1。

要弄清楚在已知某些背景信息的前提下，哪些信息是相互独立的、哪些是相关的，其实是一个很技术性的课题。
推荐阅读的书籍是 Judea Pearl 的《Probabilistic Reasoning in Intelligent Systems》和《Causality》。
（如果只能读一本，就读第一本。）

如果你懂得如何阅读因果图，就会立刻看到以下事实：

* P(骰子1, 骰子2) = P(骰子1) × P(骰子2)
* P(骰子1, 骰子2 | 总和) ≠ P(骰子1 | 总和) × P(骰子2 | 总和)

再看我们刚才那张“滑倒”的图：

* P(滑 | 夜晚) ≠ P(滑)
* P(滑 | 喷头) ≠ P(滑)
* P(滑 | 夜晚, 喷头) = P(滑 | 喷头)

也就是说，在已知喷头状态和时间的情况下，我们对滑倒的判断，仅依赖喷头，时间信息已变得无关。

这叫做\*\*“屏蔽”（screening off）\*\*，而能从因果图中读出这种条件独立关系的标准叫做 **D 分离（D-separation）**。

在论证与权威的情境下，对应的因果图是这样的：

```
真相 ——→ 论证质量 ——→ 专家信念
```

如果某个命题是真的，它就可能存在支持它的好论据；专家观察到这些证据后，便调整其信念。（**理论上**是如此！）

如果我们看到某位专家相信某个观点，我们就可以推测**存在某些支持性证据**（尽管我们不知道那些证据具体是什么）；然后我们再从这些抽象证据的存在，推回该观点可能为真的结论。

但是，如果我们**知道了“论证质量”这一节点的值**，根据 D 分离的原则，它就会**阻断“真相”与“专家信念”之间的所有路径**。因此我们可以直接从图中得出：

> P(真相 | 论证, 专家) = P(真相 | 论证)

这并**不**违反普通概率论。
它只是用更简洁的方式表达了某些概率事实。
你也可以从原始的概率分布中得出相同的等式或不等式——只是更难直观看出而已。
“权威”和“论证”**并不需要两种不同的概率类型**，正如喷头和阳光不属于本体上不同的存在。

当然，现实中我们**永远无法完全排除对权威的依赖**。
一个好的权威更可能知道那些尚未被提及、但应该纳入考量的反证；而权威较低的人更可能忽略这些反证，从而使其论证更不可靠。
这个因素，仅凭他们所呈现的论据是无法


弥补的。

此外，将论证还原为纯数学本身就很困难；很多推理强度的判断，还依赖你是否具备三十年经验积累下来的直觉。

所以，把 E.T. Jaynes 对贝叶斯概率的某个说法赋予略高的可信度，相比我 Eliezer Yudkowsky 说同一句话，这是有合理性的。
五十年的额外经验，不可能**完全**没有影响力。

但这种权威的作用只是“其他条件相同时”成立，随时可能被更强有力的论证所取代。
Jaynes 的书中有一个小错误，是我指出的——因为代数推理胜过权威。

---

<sup>1</sup>参见《地图与领地》一书中的“什么是证据？”章节。

---

## Argument Screens Off Authority

by Eliezer Yudkowsky

Scenario 1: Barry is a famous geologist. Charles is a fourteen-year-old juvenile delinquent with a long arrest record and occasional psychotic episodes. Barry flatly asserts to Arthur some counterintuitive statement about rocks, and Arthur judges it 90% probable. Then Charles makes an equally counterintuitive flat assertion about rocks, and Arthur judges it 10% probable. Clearly, Arthur is taking the speaker’s authority into account in deciding whether to believe the speaker’s assertions.

Scenario 2: David makes a counterintuitive statement about physics and gives Arthur a detailed explanation of the arguments, including references. Ernie makes an equally counterintuitive statement, but gives an unconvincing argument involving several leaps of faith. Both David and Ernie assert that this is the best explanation they can possibly give (to anyone, not just Arthur). Arthur assigns 90% probability to David’s statement after hearing his explanation, but assigns a 10% probability to Ernie’s statement.

It might seem like these two scenarios are roughly symmetrical: both involve taking into account useful evidence, whether strong versus weak authority, or strong versus weak argument.

But now suppose that Arthur asks Barry and Charles to make full technical cases, with references; and that Barry and Charles present equally good cases, and Arthur looks up the references and they check out. Then Arthur asks David and Ernie for their credentials, and it turns out that David and Ernie have roughly the same credentials—maybe they’re both clowns, maybe they’re both physicists.

Assuming that Arthur is knowledgeable enough to understand all the technical arguments—otherwise they’re just impressive noises—it seems that Arthur should view David as having a great advantage in plausibility over Ernie, while Barry has at best a minor advantage over Charles.

Indeed, if the technical arguments are good enough, Barry’s advantage over Charles may not be worth tracking. A good technical argument is one that eliminates reliance on the personal authority of the speaker.

Similarly, if we really believe Ernie that the argument he gave is the best argument he could give, which includes all of the inferential steps that Ernie executed, and all of the support that Ernie took into account—citing any authorities that Ernie may have listened to himself—then we can pretty much ignore any information about Ernie’s credentials. Ernie can be a physicist or a clown, it shouldn’t matter. (Again, this assumes we have enough technical ability to process the argument. Otherwise, Ernie is simply uttering mystical syllables, and whether we “believe” these syllables depends a great deal on his authority.)

So it seems there’s an asymmetry between argument and authority. If we know authority we are still interested in hearing the arguments; but if we know the arguments fully, we have very little left to learn from authority.

Clearly (says the novice) authority and argument are fundamentally different kinds of evidence, a difference unaccountable in the boringly clean methods of Bayesian probability theory.<sup>1</sup> For while the strength of the evidences—90% versus 10%—is just the same in both cases, they do not behave similarly when combined. How will we account for this?

Here’s half a technical demonstration of how to represent this difference in probability theory. (The rest you can take on my personal authority, or look up in the references.)

If P(H|E1) = 90% and P(H|E2) = 9%, what is the probability P(H|E1,E2)? If learning E1 is true leads us to assign 90% probability to H, and learning E2 is true leads us to assign 9% probability to H, then what probability should we assign to H if we learn both E1 and E2? This is simply not something you can calculate in probability theory from the information given. No, the missing information is not the prior probability of H. The events E1 and E2 may not be independent of each other.

Suppose that H is “My sidewalk is slippery,” E1 is “My sprinkler is running,” and E2 is “It’s night.” The sidewalk is slippery starting from one minute after the sprinkler starts, until just after the sprinkler finishes, and the sprinkler runs for ten minutes. So if we know the sprinkler is on, the probability is 90% that the sidewalk is slippery. The sprinkler is on during 10% of the nighttime, so if we know that it’s night, the probability of the sidewalk being slippery is 9%. If we know that it’s night and the sprinkler is on—that is, if we know both facts—the probability of the sidewalk being slippery is 90%.

We can represent this in a graphical model as follows:

> Night ----> Sprinkler ----> Slippery

Whether or not it’s Night causes the Sprinkler to be on or off, and whether the Sprinkler is on causes the sidewalk to be Slippery or unSlippery.

The direction of the arrows is meaningful. Say we had:

> Night ----> Sprinkler <---- Slippery

This would mean that, if I didn’t know anything about the sprinkler, the probability of Nighttime and Slipperiness would be independent of each other. For example, suppose that I roll Die One and Die Two, and add up the showing numbers to get the Sum:

> Die One ----> Sum <---- Die Two

If you don’t tell me the sum of the two numbers, and you tell me the first die showed 6, this doesn’t tell me anything about the result of the second die, yet. But if you now also tell me the sum is 7, I know the second die showed 1.

Figuring out when various pieces of information are dependent or independent of each other, given various background knowledge, actually turns into a quite technical topic. The books to read are Judea Pearl’s Probabilistic Reasoning in Intelligent Systems: Networks of Plausible Inference and Causality: Models, Reasoning, and Inference. (If you only have time to read one book, read the first one.)

If you know how to read causal graphs, then you look at the dice-roll graph and immediately see:

_P(Die 1,Die 2) = P(Die 1) ✕ P(Die 2)_

_P(Die 1,Die 2|Sum) ≠ P(Die 1)|Sum) ✕ P(Die 2|Sum)._

If you look at the correct sidewalk diagram, you see facts like:

_P(Slippery|Night) ≠ P(Slippery)_

_P(Slippery|Sprinkler) ≠ P(Slippery)_

_P(Slippery|Night,Sprinkler) = P(Slippery|Sprinkler)._

That is, the probability of the sidewalk being Slippery, given knowledge about the Sprinkler and the Night, is the same probability we would assign if we knew only about the Sprinkler. Knowledge of the Sprinkler has made knowledge of the Night irrelevant to inferences about Slipperiness.

This is known as screening off, and the criterion that lets us read such conditional independences off causal graphs is known as D-separation.

For the case of argument and authority, the causal diagram looks like this:

> Truth ----> Argument Goodness ----> Expert Belief

If something is true, then it therefore tends to have arguments in favor of it, and the experts therefore observe these evidences and change their opinions. (In theory!)

If we see that an expert believes something, we infer back to the existence of evidence-in-the-abstract (even though we don’t know what that evidence is exactly), and from the existence of this abstract evidence, we infer back to the truth of the proposition.

But if we know the value of the Argument node, this D-separates the node “Truth” from the node “Expert Belief” by blocking all paths between them, according to certain technical criteria for “path blocking” that seem pretty obvious in this case. So even without checking the exact probability distribution, we can read off from the graph that:

_P(truth|argument, expert)= P(truth|argument)._

This does not represent a contradiction of ordinary probability theory. It’s just a more compact way of expressing certain probabilistic facts. You could read the same equalities and inequalities off an unadorned probability distribution—but it would be harder to see it by eyeballing. Authority and argument don’t need two different kinds of probability, any more than sprinklers are made out of ontologically different stuff than sunlight.

In practice you can never completely eliminate reliance on authority. Good authorities are more likely to know about any counterevidence that exists and should be taken into account; a lesser authority is less likely to know this, which makes their arguments less reliable. This is not a factor you can eliminate merely by hearing the evidence they did take into account.

It’s also very hard to reduce arguments to pure math; and otherwise, judging the strength of an inferential step may rely on intuitions you can’t duplicate without the same thirty years of experience.

There is an ineradicable legitimacy to assigning slightly higher probability to what E. T. Jaynes tells you about Bayesian probability, than you assign to Eliezer Yudkowsky making the exact same statement. Fifty additional years of experience should not count for literally zero influence.

But this slight strength of authority is only ceteris paribus, and can easily be overwhelmed by stronger arguments. I have a minor erratum in one of Jaynes’s books—because algebra trumps authority.

---

<sup>1</sup>See “What Is Evidence?” in Map and Territory.