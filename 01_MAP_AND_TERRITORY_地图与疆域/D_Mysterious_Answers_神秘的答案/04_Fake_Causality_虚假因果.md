## 虚假因果

作者：Eliezer Yudkowsky

燃素是十八世纪化学家对希腊炼金术“元素之火”的回答。点燃木头，让它燃烧。那橙色明亮的“火”是什么？为什么木头会变成灰烬？对于这两个问题，十八世纪的化学家都回答：“燃素。”

……这就是他们的答案：“燃素。”

燃素从燃烧的物质中以可见的火焰形式逸出。随着燃素逸出，燃烧的物质失去燃素，于是变成了灰烬，也就是“真正的物质”。密闭容器里的火焰熄灭，是因为空气被燃素饱和，无法再容纳更多燃素。木炭燃烧后几乎没有残渣，因为它几乎全是燃素。

当然，人们并不会用燃素理论来预测化学变化的结果。你先看到了结果，然后用燃素理论来解释。并不是燃素理论家预测火焰会在密闭容器中熄灭，而是他们点燃火焰，看着它熄灭，然后说：“空气一定是被燃素饱和了。”你甚至不能用燃素理论来说明你“不应该看到”什么；它可以解释一切。

那是科学的早期时代。很长时间里，没有人意识到这里有问题。虚假解释并不会让人觉得虚假，这正是它们危险的地方。

现代研究表明，人类思考因果关系时，使用的方式类似于贝叶斯网络的有向无环图（DAG）。因为下雨了，所以人行道是湿的；因为人行道是湿的，所以它很滑：

    雨 -----> 人行道湿 -----> 人行道滑

由此我们可以推断——或者在贝叶斯网络中用概率严格计算——当人行道很滑时，很可能下过雨；但如果我们已经知道人行道是湿的，再得知它很滑，对是否下雨就没有更多信息了。

为什么火在燃烧时又热又亮？

    燃素 -----> 火热且亮

这听起来像个解释。它用的是同样的认知数据格式。但人类大脑不会自动检测到因果箭头是否真的有约束力。更糟的是，由于事后偏见，我们会觉得因果关系有约束力，其实只是[事后拟合](https://www.lesswrong.com/rationality/conservation-of-expected-evidence)了结果。

有趣的是，我们对因果概率推理的现代理解，能精确描述燃素理论家错在哪里。贝叶斯网络的主要灵感之一，就是发现如果推理在因果和结果之间来回共振，会导致证据被重复计算。例如，假设我得到一点不太可靠的信息，说人行道是湿的。这应该让我觉得下雨的概率更高。但如果下雨的概率更高，难道不意味着人行道更可能是湿的？那人行道更可能滑？但如果人行道滑，说明它可能是湿的，于是我又该提高下雨的概率……

Judea Pearl 用了一个“排队数士兵”的比喻。假设你在队伍里，看到前后各有一个士兵，加上你自己是三个人。你问后面的士兵：“你看到多少士兵？”他环顾四周说：“三个。”于是你以为总共有六个士兵。显然，这不是正确的算法。

更聪明的做法是问前面的士兵：“你前面有多少人？”问后面的士兵：“你后面有多少人？”“前面有多少人？”这个问题可以作为消息一直往前传。如果你在队首，你就传递“前面有 1 人”，代表你自己。你后面的人收到“前面有 1 人”，再传递“前面有 2 人”给他后面的人。与此同时，每个人也会收到后面传来的“后面有 N 人”，再传递“后面有 N+1 人”给前面的人。总共有多少人？把你收到的两个数字加起来，再加上你自己，就是队伍总人数。

关键在于，每个人都要分别追踪前向消息和后向消息，最后才加在一起。你永远不会把收到的后向消息加到传回去的前向消息里。实际上，总人数这个消息从不会被直接传递——没人会直接说出总数。

在严格的因果概率推理中也有类似原则。如果你通过某种方式（不是观察人行道湿）得知是否下雨，这会从[雨]节点向[人行道湿]节点发送前向消息，提高我们对人行道湿的预期。如果你观察到人行道湿，这会向我们对下雨的信念发送后向消息，这个消息会从[雨]节点传递到所有相邻节点，除了[人行道湿]节点。我们每条证据只计算一次；没有任何更新消息会来回反弹。具体算法可见 Judea Pearl 的经典著作《智能系统中的概率推理》。

那么，燃素理论到底错在哪里？当我们观察到火是热且亮时，[火热且亮]节点会向[燃素]节点发送后向证据，让我们更新对燃素的信念。但如果这样，我们就不能把这当作燃素理论的成功前向预测。消息只能单向传递，不能反弹。

可惜，人类并不使用严格的信念网络更新算法。我们通过观察子节点来学习父节点，通过相信父节点来预测子节点。但我们不会严格区分前向消息和后向消息。我们只记得燃素是热的，导致火是热的。于是看起来燃素理论预测了火的热。或者更糟，只是觉得燃素让火变热。

除非你注意到没有任何前向预测被做出，这种无约束力的因果节点不会被标记为“虚假”。它和你信念网络里的其他节点一样被表示。它感觉就像一个事实，就像你知道的其他事实一样：“燃素让火变热。”

一个设计良好的 AI 会立刻发现这个问题。这甚至不需要特殊代码，只要正确记账信念网络即可。（可惜我们人类不能像 AI 那样重写自己的代码。）

所谓“事后偏见”，其实就是人类没有严格区分前向和后向消息，导致前向消息被后向消息污染的非技术性说法。

那些走上燃素之路的人，并不是想当傻瓜。没有科学家会故意走进死胡同。你头脑中有没有虚假解释？如果有，我保证它们不会被标记为“虚假解释”，所以你搜“虚假”这个词是找不到的。

由于事后偏见，仅仅检查你的理论对已知事实的“预测”效果还不够。你必须预测明天，而不是昨天。这是混乱的人类大脑唯一能确保自己发出纯粹前向消息的方法。

---

## Fake Causality

by Eliezer Yudkowsky

Phlogiston was the eighteenth century’s answer to the Elemental Fire of the Greek alchemists. Ignite wood, and let it burn. What is the orangey-bright “fire” stuff? Why does the wood transform into ash? To both questions, the eighteenth-century chemists answered, “phlogiston.”

. . . and that was it, you see, that was their answer: “Phlogiston.”

Phlogiston escaped from burning substances as visible fire. As the phlogiston escaped, the burning substances lost phlogiston and so became ash, the “true material.” Flames in enclosed containers went out because the air became saturated with phlogiston, and so could not hold any more. Charcoal left little residue upon burning because it was nearly pure phlogiston.

Of course, one didn’t use phlogiston theory to predict the outcome of a chemical transformation. You looked at the result first, then you used phlogiston theory to explain it. It’s not that phlogiston theorists predicted a flame would extinguish in a closed container; rather they lit a flame in a container, watched it go out, and then said, “The air must have become saturated with phlogiston.” You couldn’t even use phlogiston theory to say what you ought not to see; it could explain everything.

This was an earlier age of science. For a long time, no one realized there was a problem. Fake explanations don’t feel fake. That’s what makes them dangerous.

Modern research suggests that humans think about cause and effect using something like the directed acyclic graphs (DAGs) of Bayes nets. Because it rained, the sidewalk is wet; because the sidewalk is wet, it is slippery:

	Rain -----> Sidewalk Wet -----> Sidewalk Slippery

From this we can infer—or, in a Bayes net, rigorously calculate in probabilities—that when the sidewalk is slippery, it probably rained; but if we already know that the sidewalk is wet, learning that the sidewalk is slippery tells us nothing more about whether it rained.

Why is fire hot and bright when it burns?

	Phlogiston -----> Fire Hot and Bright

It feels like an explanation. It’s represented using the same cognitive data format. But the human mind does not automatically detect when a cause has an unconstraining arrow to its effect. Worse, thanks to hindsight bias, it may feel like the cause constrains the effect, when it was merely [fitted](https://www.lesswrong.com/rationality/conservation-of-expected-evidence) to the effect.

Interestingly, our modern understanding of probabilistic reasoning about causality can describe precisely what the phlogiston theorists were doing wrong. One of the primary inspirations for Bayesian networks was noticing the problem of double-counting evidence if inference resonates between an effect and a cause. For example, let’s say that I get a bit of unreliable information that the sidewalk is wet. This should make me think it’s more likely to be raining. But, if it’s more likely to be raining, doesn’t that make it more likely that the sidewalk is wet? And wouldn’t that make it more likely that the sidewalk is slippery? But if the sidewalk is slippery, it’s probably wet; and then I should again raise my probability that it’s raining . . .

Judea Pearl uses the metaphor of an algorithm for counting soldiers in a line. Suppose you’re in the line, and you see two soldiers next to you, one in front and one in back. That’s three soldiers, including you. So you ask the soldier behind you, “How many soldiers do you see?” They look around and say, “Three.” So that’s a total of six soldiers. This, obviously, is not how to do it.

A smarter way is to ask the soldier in front of you, “How many soldiers forward of you?” and the soldier in back, “How many soldiers backward of you?” The question “How many soldiers forward?” can be passed on as a message without confusion. If I’m at the front of the line, I pass the message “1 soldier forward,” for myself. The person directly in back of me gets the message “1 soldier forward,” and passes on the message “2 soldiers forward” to the soldier behind them. At the same time, each soldier is also getting the message “N soldiers backward” from the soldier behind them, and passing it on as “N + 1 soldiers backward” to the soldier in front of them. How many soldiers in total? Add the two numbers you receive, plus one for yourself: that is the total number of soldiers in line.

The key idea is that every soldier must separately track the two messages, the forward-message and backward-message, and add them together only at the end. You never add any soldiers from the backward-message you receive to the forward-message you pass back. Indeed, the total number of soldiers is never passed as a message—no one ever says it aloud.

An analogous principle operates in rigorous probabilistic reasoning about causality. If you learn something about whether it’s raining, from some source other than observing the sidewalk to be wet, this will send a forward-message from [Rain] to [Sidewalk Wet] and raise our expectation of the sidewalk being wet. If you observe the sidewalk to be wet, this sends a backward-message to our belief that it is raining, and this message propagates from [Rain] to all neighboring nodes except the [Sidewalk Wet] node. We count each piece of evidence exactly once; no update message ever “bounces” back and forth. The exact algorithm may be found in Judea Pearl’s classic Probabilistic Reasoning in Intelligent Systems: Networks of Plausible Inference.

So what went wrong in phlogiston theory? When we observe that fire is hot and bright, the [Fire Hot and Bright] node can send backward-evidence to the [Phlogiston] node, leading us to update our beliefs about phlogiston. But if so, we can’t count this as a successful forward-prediction of phlogiston theory. The message should go in only one direction, and not bounce back.

Alas, human beings do not use a rigorous algorithm for updating belief networks. We learn about parent nodes from observing children, and predict child nodes from beliefs about parents. But we don’t keep rigorously separate books for the backward-message and forward-message. We just remember that phlogiston is hot, which causes fire to be hot. So it seems like phlogiston theory predicts the hotness of fire. Or, worse, it just feels like phlogiston makes the fire hot.

Until you notice that no advance predictions are being made, the non-constraining causal node is not labeled “fake.” It’s represented the same way as any other node in your belief network. It feels like a fact, like all the other facts you know: Phlogiston makes the fire hot.

A properly designed AI would notice the problem instantly. This wouldn’t even require special-purpose code, just correct bookkeeping of the belief network. (Sadly, we humans can’t rewrite our own code, the way a properly designed AI could.)

Speaking of “hindsight bias” is just the nontechnical way of saying that humans do not rigorously separate forward and backward messages, allowing forward messages to be contaminated by backward ones.

Those who long ago went down the path of phlogiston were not trying to be fools. No scientist deliberately wants to get stuck in a blind alley. Are there any fake explanations in your mind? If there are, I guarantee they’re not labeled “fake explanation,” so polling your thoughts for the “fake” keyword will not turn them up.

Thanks to hindsight bias, it’s also not enough to check how well your theory “predicts” facts you already know. You’ve got to predict for tomorrow, not yesterday. It’s the only way a messy human mind can be guaranteed of sending a pure forward message.