## 缺乏证据就是缺乏存在的证据

引自 Robyn Dawes 的《不确定世界中的理性选择》：

    事实上，这种事后将证据强行套入假设的做法，曾在美国历史上酿成极其严重的一幕：二战初期对日裔美国人的集中营关押。1942年2月21日，加州州长厄尔·沃伦在旧金山的国会听证会上作证时，有人指出，直到那时为止，日裔美国人并没有进行任何破坏或间谍活动。沃伦回应说：“我认为，这种[颠覆活动]的缺失，正是我们整个局势中最不祥的信号。它比任何其他因素都更让我确信，我们即将遭遇的破坏、即将发生的‘第五纵队’活动，其时机就像珍珠港袭击一样……我相信我们只是被麻痹在一种虚假的安全感中。”

让我们从贝叶斯视角来分析沃伦的论点。当我们看到某个证据时，给这个证据分配更高似然度的假说，其概率会上升，而分配更低似然度的假说概率会下降。这是相对似然和相对概率的现象。即使你给某个证据分配了很高的似然度，如果有另一个假说分配的似然度更高，你仍然会失去概率质量。

沃伦似乎在主张，既然我们没有看到破坏行为，这就证明了“第五纵队”的存在。你可以辩称，“第五纵队”可能会延迟其破坏行为。但没有“第五纵队”时出现“没有破坏”的可能性，依然更高。

设 E 代表观察到破坏，¬E 代表没有观察到破坏。H1 代表“日裔美国人中存在第五纵队”的假说，H2 代表“没有第五纵队”的假说。条件概率 P(E|H)，即“在假设 H 成立时观察到 E 的概率”，表示如果假设为真，我们有多大信心会看到证据 E。

无论“第五纵队”不进行破坏的概率 P(¬E|H1) 有多大，它都不会比“没有第五纵队时没有破坏”的概率 P(¬E|H2) 更大。因此，观察到没有破坏行为，会提升“没有第五纵队”这个假说的概率。

没有破坏行为并不能证明没有第五纵队。缺乏证据并不等于证实不存在。在逻辑中，(A ⇒ B)（A 蕴含 B）并不等价于 (¬A ⇒ ¬B)（非A蕴含非B）。

但在概率论中，缺乏证据总是缺乏存在的证据。如果 E 是一个二元事件，且 P(H|E) > P(H)，即观察到 E 会提升 H 的概率，那么 P(H|¬E) < P(H)，也就是说，未观察到 E 会降低 H 的概率。P(H) 是 P(H|E) 和 P(H|¬E) 的加权平均，必然介于两者之间。<sup>1</sup>

在绝大多数现实情况下，某个原因未必总能可靠地产生自身的迹象，但没有这个原因时产生这些迹象的可能性更低。未观察到某个现象，可能是强有力的缺失证据，也可能只是很弱的证据，这取决于该原因产生该现象的可能性有多大。未观察到某个本就很难出现的现象（即使备选假说完全不允许出现），也只是很弱的缺失证据（但仍然是证据）。这就是“化石记录缺口”谬误——化石本来就很难形成；当已经有大量强有力的正面观测时，再强调某个弱观测的缺失是没有意义的。但如果完全没有正面观测，那就该警惕了，这就是“费米悖论”。

你作为理性主义者的力量，在于你能对虚构比对现实更感到困惑；如果你能同样轻松地解释任何结果，那你就一无所知。一个模型的力量不在于它能解释什么，而在于它不能解释什么，因为只有排除性才能约束预期。如果你没有注意到你的模型让证据变得不太可能，那你就等于没有模型，也等于没有证据——没有大脑，也没有眼睛。

---

<sup>1</sup>如果你觉得这些内容有些困惑，可以参考我在《幽灵中的机器》（《理性：从AI到僵尸》第三卷）结尾关于贝叶斯更新的讨论。

---

## Absence of Evidence Is Evidence of Absence

From Robyn Dawes’s Rational Choice in an Uncertain World:
	
	In fact, this post-hoc fitting of evidence to hypothesis was involved in a most grievous chapter in United States history: the internment of Japanese-Americans at the beginning of the Second World War. When California governor Earl Warren testified before a congressional hearing in San Francisco on February 21, 1942, a questioner pointed out that there had been no sabotage or any other type of espionage by the Japanese-Americans up to that time. Warren responded, “I take the view that this lack [of subversive activity] is the most ominous sign in our whole situation. It convinces me more than perhaps any other factor that the sabotage we are to get, the Fifth Column activities are to get, are timed just like Pearl Harbor was timed . . . I believe we are just being lulled into a false sense of security.”

Consider Warren’s argument from a Bayesian perspective. When we see evidence, hypotheses that assigned a higher likelihood to that evidence gain probability, at the expense of hypotheses that assigned a lower likelihood to the evidence. This is a phenomenon of relative likelihoods and relative probabilities. You can assign a high likelihood to the evidence and still lose probability mass to some other hypothesis, if that other hypothesis assigns a likelihood that is even higher.

Warren seems to be arguing that, given that we see no sabotage, this confirms that a Fifth Column exists. You could argue that a Fifth Column might delay its sabotage. But the likelihood is still higher that the absence of a Fifth Column would perform an absence of sabotage.

Let E stand for the observation of sabotage, and¬E for the observation of no sabotage. The symbol H1 stands for the hypothesis of a JapaneseAmerican Fifth Column, and H2 for the hypothesis that no Fifth Column exists. The conditional probability P(E|H), or “E given H,” is how confidently we’d expect to see the evidence E if we assumed the hypothesis H were true.

Whatever the likelihood that a Fifth Column would do no sabotage, the probability P(¬E|H1), it won’t be as large as the likelihood that there’s no sabotage given that there’s no Fifth Column, the probability P(¬E|H2). So observing a lack of sabotage increases the probability that no Fifth Column exists.

A lack of sabotage doesn’t prove that no Fifth Column exists. Absence of proof is not proof of absence. In logic, (A ⇒ B), read “A implies B,” is not equivalent to (¬A ⇒ ¬B), read “not-A implies not-B.”

But in probability theory, absence of evidence is always evidence of absence. If E is a binary event and P(H|E) > P(H), i.e., seeing E increases the probability of H, then P(H|¬E) < P(H), i.e., failure to observe E decreases the probability of H. The probability P(H) is a weighted mix of P(H|E) and P(H|¬E), and necessarily lies between the two.<sup>1</sup>

Under the vast majority of real-life circumstances, a cause may not reliably produce signs of itself, but the absence of the cause is even less likely to produce the signs. The absence of an observation may be strong evidence of absence or very weak evidence of absence, depending on how likely the cause is to produce the observation. The absence of an observation that is only weakly permitted (even if the alternative hypothesis does not allow it at all) is very weak evidence of absence (though it is evidence nonetheless). This is the fallacy of “gaps in the fossil record”—fossils form only rarely; it is futile to trumpet the absence of a weakly permitted observation when many strong positive observations have already been recorded. But if there are no positive observations at all, it is time to worry; hence the Fermi Paradox.

Your strength as a rationalist is your ability to be more confused by fiction than by reality; if you are equally good at explaining any outcome you have zero knowledge. The strength of a model is not what it can explain, but what it can’t, for only prohibitions constrain anticipation. If you don’t notice when your model makes the evidence unlikely, you might as well have no model, and also you might as well have no evidence; no brain and no eyes.

---

<sup>1</sup>If any of this sounds at all confusing, see my discussion of Bayesian updating toward the end of The Machine in the Ghost, the third volume of Rationality: From AI to Zombies.