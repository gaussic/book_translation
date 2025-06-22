## 论证遮蔽权威

情景一：巴里是一位著名地质学家。查尔斯是一个十四岁的惯犯，屡次被捕，偶尔还有精神病发作。巴里向亚瑟断言了一个反直觉的关于岩石的说法，亚瑟判断其概率为90%。随后查尔斯也同样断言了一个反直觉的关于岩石的说法，亚瑟判断其概率为10%。显然，亚瑟在决定是否相信说话者的断言时，考虑了说话者的权威性。

情景二：大卫提出了一个关于物理学的反直觉说法，并向亚瑟详细解释了论据，包括参考文献。厄尼也提出了一个同样反直觉的说法，但给出的论据很不充分，充满了跳跃性的信念。大卫和厄尼都声称这已经是他们能给出的最佳解释（对任何人都是如此，不只是对亚瑟）。亚瑟听完大卫的解释后，给他的说法赋予90%的概率，而厄尼的说法只赋予10%的概率。

乍看之下，这两个情景似乎是对称的：都涉及到有用证据的权衡——强权威对弱权威，或强论据对弱论据。

但现在假设亚瑟要求巴里和查尔斯都给出完整的技术论证，并附上参考文献；巴里和查尔斯都给出了同样优秀的论证，亚瑟查阅了参考文献，发现都没问题。然后亚瑟又问大卫和厄尼的资历，发现他们的资历差不多——也许都是小丑，也许都是物理学家。

假设亚瑟有足够的知识理解所有技术论证——否则这些论证对他来说只是一些令人印象深刻的噪音——那么亚瑟应该认为大卫的说法比厄尼更有说服力，而巴里对查尔斯的优势则微乎其微。

事实上，如果技术论证足够好，巴里对查尔斯的优势甚至可以忽略不计。一个好的技术论证，就是能消除对说话者个人权威的依赖。

同样地，如果我们真的相信厄尼所说的论据已经是他能给出的最好论据，包含了他所有的推理步骤和所有他考虑过的支持（包括他自己参考过的权威），那么我们几乎可以忽略厄尼的资历。厄尼可以是物理学家，也可以是小丑，这都不重要。（再次强调，这假设我们有足够的技术能力处理论证。否则，厄尼只是说了一些神秘的音节，我们是否“相信”这些音节，很大程度上还是取决于他的权威性。）

所以，论证和权威之间存在一种不对称性。如果我们知道了权威，我们仍然想听论据；但如果我们完全了解论据，权威就几乎没什么可补充的了。

显然（新手会说），权威和论证是两种本质不同的证据，这种差别无法用贝叶斯概率论那种无聊而干净的方法解释。<sup>1</sup> 因为两者的证据强度——比如都是90%对10%——看似一样，但当它们结合时表现却不同。我们该如何解释这种现象？

下面是概率论中如何表达这种差别的半个技术性演示。（剩下的你可以凭我的权威相信，或者查查参考文献。）

如果 P(H|E1)=90%，P(H|E2)=9%，那么 P(H|E1, E2) 是多少？如果得知 E1 为真后我们对 H 的概率是90%，得知 E2 为真后对 H 的概率是9%，那么如果两者都为真，我们该给 H 多少概率？用概率论仅凭这些信息是算不出来的。缺的不是 H 的先验概率，而是 E1 和 E2 可能不是独立事件。

假设 H 是“我的人行道很滑”，E1 是“我的洒水器正在工作”，E2 是“现在是夜晚”。洒水器一开一分钟后人行道就会变滑，直到洒水器关掉后一会儿才恢复。洒水器每次运行十分钟。如果我们知道洒水器开着，人行道滑的概率是90%。洒水器只在夜晚的10%时间里开，所以如果只知道是夜晚，人行道滑的概率是9%。如果我们知道既是夜晚又开着洒水器（即两者都为真），人行道滑的概率还是90%。

我们可以用图模型表示如下：

    夜晚 ----> 洒水器 ----> 滑

是否为夜晚决定洒水器是否开启，洒水器是否开启决定人行道是否滑。

箭头的方向是有意义的。比如：

    夜晚 ----> 洒水器 <--- 滑

这意味着，如果我对洒水器一无所知，夜晚和滑之间是独立的。比如，假设我掷两个骰子，把点数相加得到总和：

    骰子一 ----> 总和 <--- 骰子二

如果你没告诉我总和，只告诉我第一个骰子是6，这对第二个骰子的结果没有任何信息。但如果你又告诉我总和是7，我就知道第二个骰子是1。

判断各种信息在不同背景知识下是否独立，其实是个很技术性的话题。推荐阅读 Judea Pearl 的《智能系统中的概率推理：可信推断网络》和《因果关系：模型、推理与推断》。如果只能读一本，建议读第一本。

如果你懂得如何阅读因果图，那么你看到骰子图就会立刻明白：

    P(骰子1, 骰子2) = P(骰子1) × P(骰子2)
    
    P(骰子1, 骰子2|总和) ≠ P(骰子1|总和) × P(骰子2|总和)

看正确的人行道图，你会看到如下事实：

    P(滑|夜晚) ≠ P(滑)
    P(滑|洒水器) ≠ P(滑)
    P(滑|夜晚, 洒水器) = P(滑|洒水器)

也就是说，已知洒水器和夜晚的情况下，人行道滑的概率和只知道洒水器时一样。洒水器的信息让夜晚的信息对滑的推断变得无关紧要。

这被称为“遮蔽（screening off）”，而让我们能从因果图中读出这种条件独立性的标准叫做 D-分离（D-separation）。

对于论证和权威的情况，因果图如下：

如果某事是真的，那么它倾向于有支持它的论据，因此专家会观察到这些证据并改变自己的观点。（理论上如此！）

    真相 ----> 论据好坏 <--- 专家信念

如果我们看到某个专家相信某事，我们会反推出存在某种抽象证据（即使我们不知道具体是什么），再由这种抽象证据反推出命题的真实性。

但如果我们知道“论据”节点的值，根据 D-分离原理，这会阻断“真相”与“专家信念”之间的所有路径。所以即使不查具体概率分布，我们也能从图上读出：

    P(真相|论据, 专家) = P(真相|论据)

这并不违背普通概率论，只是用更简洁的方式表达了某些概率事实。你也可以从普通概率分布中读出这些等式和不等式——只是没那么直观。权威和论证并不需要两种不同的概率，就像洒水器和阳光不是本体上不同的东西一样。

实际上，你永远无法完全消除对权威的依赖。好的权威更可能知道所有反证并加以考虑；权威较弱的人则不太可能知道这些，使得他们的论据不那么可靠。这不是你仅凭听到他们考虑过的证据就能消除的因素。

而且，把论证简化为纯粹的数学也很难；否则，判断推理步骤的强度可能还得依赖你无法复制的三十年经验。

因此，把 E. T. Jaynes 关于贝叶斯概率的说法赋予比 Eliezer Yudkowsky 完全相同说法更高的概率，是有合理性的。五十年的额外经验不应完全没有影响。

但这种权威的优势只是“其他条件相同”时的微弱优势，很容易被更强的论据压倒。我在 Jaynes 的书里还发现过小错误——因为代数胜过权威。

---

<sup>1</sup>参见《地图与领地》中的《什么是证据？》。

---

## Argument Screens Off Authority

Scenario 1: Barry is a famous geologist. Charles is a fourteen-year-old juvenile delinquent with a long arrest record and occasional psychotic episodes. Barry flatly asserts to Arthur some counterintuitive statement about rocks, and Arthur judges it 90% probable. Then Charles makes an equally counterintuitive flat assertion about rocks, and Arthur judges it 10% probable. Clearly, Arthur is taking the speaker’s authority into account in deciding whether to believe the speaker’s assertions.

Scenario 2: David makes a counterintuitive statement about physics and gives Arthur a detailed explanation of the arguments, including references. Ernie makes an equally counterintuitive statement, but gives an unconvincing argument involving several leaps of faith. Both David and Ernie assert that this is the best explanation they can possibly give (to anyone, not just Arthur). Arthur assigns 90% probability to David’s statement after hearing his explanation, but assigns a 10% probability to Ernie’s statement.

It might seem like these two scenarios are roughly symmetrical: both involve taking into account useful evidence, whether strong versus weak authority, or strong versus weak argument.

But now suppose that Arthur asks Barry and Charles to make full technical cases, with references; and that Barry and Charles present equally good cases, and Arthur looks up the references and they check out. Then Arthur asks David and Ernie for their credentials, and it turns out that David and Ernie have roughly the same credentials—maybe they’re both clowns, maybe they’re both physicists.

Assuming that Arthur is knowledgeable enough to understand all the technical arguments—otherwise they’re just impressive noises—it seems that Arthur should view David as having a great advantage in plausibility over Ernie, while Barry has at best a minor advantage over Charles.

Indeed, if the technical arguments are good enough, Barry’s advantage over Charles may not be worth tracking. A good technical argument is one that eliminates reliance on the personal authority of the speaker.

Similarly, if we really believe Ernie that the argument he gave is the best argument he could give, which includes all of the inferential steps that Ernie executed, and all of the support that Ernie took into account— citing any authorities that Ernie may have listened to himself—then we can pretty much ignore any information about Ernie’s credentials. Ernie can be a physicist or a clown, it shouldn’t matter. (Again, this assumes we have enough technical ability to process the argument. Otherwise, Ernie is simply uttering mystical syllables, and whether we “believe” these syllables depends a great deal on his authority.)

So it seems there’s an asymmetry between argument and authority. If we know authority we are still interested in hearing the arguments; but if we know the arguments fully, we have very little left to learn from authority.

Clearly (says the novice) authority and argument are fundamentally different kinds of evidence, a difference unaccountable in the boringly clean methods of Bayesian probability theory.<sup>1</sup> For while the strength of the evidences—90% versus 10%—is just the same in both cases, they do not behave similarly when combined. How will we account for this?

Here’s half a technical demonstration of how to represent this difference in probability theory. (The rest you can take on my personal authority, or look up in the references.)

If P(H|E1)= 90% and P(H|E2)= 9%, what is the probability P(H|E1, E2)? If learning E1 is true leads us to assign 90% probability to H, and learning E2 is true leads us to assign 9% probability to H, then what probability should we assign to H if we learn both E1 and E2? This is simply not something you can calculate in probability theory from the information given. No, the missing information is not the prior probability of H. The events E1 and E2 may not be independent of each other.

Suppose that H is “My sidewalk is slippery,” E1 is “My sprinkler is running,” and E2 is “It’s night.” The sidewalk is slippery starting from one minute after the sprinkler starts, until just after the sprinkler finishes, and the sprinkler runs for ten minutes. So if we know the sprinkler is on, the probability is 90% that the sidewalk is slippery. The sprinkler is on during 10% of the nighttime, so if we know that it’s night, the probability of the sidewalk being slippery is 9%. If we know that it’s night and the sprinkler is on—that is, if we know both facts—the probability of the sidewalk being slippery is 90%.

We can represent this in a graphical model as follows:

	Night ----> Sprinkler ----> Slippery

Whether or not it’s Night causes the Sprinkler to be on or off, and whether the Sprinkler is on causes the sidewalk to be Slippery or unSlippery.

The direction of the arrows is meaningful. Say we had:

	Night ----> Sprinkler <---Slippery

This would mean that, if I didn’t know anything about the sprinkler, the probability of Nighttime and Slipperiness would be independent of each other. For example, suppose that I roll Die One and Die Two, and add up the showing numbers to get the Sum:

	Die One ----> Sum <---Die Two

If you don’t tell me the sum of the two numbers, and you tell me the first die showed 6, this doesn’t tell me anything about the result of the second die, yet. But if you now also tell me the sum is 7, I know the second die showed 1.

Figuring out when various pieces of information are dependent or independent of each other, given various background knowledge, actually turns into a quite technical topic. The books to read are Judea Pearl’s Probabilistic Reasoning in Intelligent Systems: Networks of Plausible Inference and Causality: Models, Reasoning, and Inference. (If you only have time to read one book, read the first one.)

If you know how to read causal graphs, then you look at the dice-roll graph and immediately see:

	P(Die 1, Die 2)= P(Die 1) × P(Die 2)
	
	P(Die 1, Die 2|Sum) ̸= P(Die 1|Sum) × P(Die 2|Sum).

If you look at the correct sidewalk diagram, you see facts like:

	P(Slippery|Night) ̸= P(Slippery)

	P(Slippery|Sprinkler) ̸= P(Slippery)

	P(Slippery|Night, Sprinkler)= P(Slippery|Sprinkler).

That is, the probability of the sidewalk being Slippery, given knowledge about the Sprinkler and the Night, is the same probability we would assign if we knew only about the Sprinkler. Knowledge of the Sprinkler has made knowledge of the Night irrelevant to inferences about Slipperiness.

This is known as screening off, and the criterion that lets us read such conditional independences off causal graphs is known as D-separation.

For the case of argument and authority, the causal diagram looks like this:

If something is true, then it therefore tends to have arguments in favor of it, and the experts therefore observe these evidences and change their opinions. (In theory!)

	Truth ----> Argument Goodness <---Expert Belief

If we see that an expert believes something, we infer back to the existence of evidence-in-the-abstract (even though we don’t know what that evidence is exactly), and from the existence of this abstract evidence, we infer back to the truth of the proposition.

But if we know the value of the Argument node, this D-separates the node “Truth” from the node “Expert Belief” by blocking all paths between them, according to certain technical criteria for “path blocking” that seem pretty obvious in this case. So even without checking the exact probability distribution, we can read off from the graph that:

	P(truth|argument, expert)= P(truth|argument).

This does not represent a contradiction of ordinary probability theory. It’s just a more compact way of expressing certain probabilistic facts. You could read the same equalities and inequalities off an unadorned probability distribution—but it would be harder to see it by eyeballing. Authority and argument don’t need two different kinds of probability, any more than sprinklers are made out of ontologically different stuff than sunlight.

In practice you can never completely eliminate reliance on authority. Good authorities are more likely to know about any counterevidence that exists and should be taken into account; a lesser authority is less likely to know this, which makes their arguments less reliable. This is not a factor you can eliminate merely by hearing the evidence they did take into account.

It’s also very hard to reduce arguments to pure math; and otherwise, judging the strength of an inferential step may rely on intuitions you can’t duplicate without the same thirty years of experience.

There is an ineradicable legitimacy to assigning slightly higher probability to what E. T. Jaynes tells you about Bayesian probability, than you assign to Eliezer Yudkowsky making the exact same statement. Fifty additional years of experience should not count for literally zero influence.

But this slight strength of authority is only ceteris paribus, and can easily be overwhelmed by stronger arguments. I have a minor erratum in one of Jaynes’s books—because algebra trumps authority.

---

<sup>1</sup>See “What Is Evidence?” in Map and Territory.