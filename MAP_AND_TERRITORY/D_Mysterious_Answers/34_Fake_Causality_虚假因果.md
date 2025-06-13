## 虚假因果

燃素是十八世纪化学家对希腊炼金术“元素之火”的回答。点燃木头，让它燃烧。那橙色明亮的“火”是什么？为什么木头会变成灰烬？对于这两个问题，十八世纪的化学家都回答：“燃素。”

……就是这样，你看，这就是他们的答案：“燃素。”

燃素会以可见的火焰形式从燃烧物中逸出。随着燃素的逸出，燃烧物失去燃素，于是变成了灰烬，也就是“真正的物质”。密闭容器里的火焰会熄灭，因为空气被燃素“饱和”，无法再容纳更多燃素。木炭燃烧后几乎没有残渣，因为它几乎全是燃素。

当然，人们并不会用燃素理论来预测化学变化的结果。你是先看到了结果，然后用燃素理论来解释它。燃素理论家并不是预测火焰会在密闭容器中熄灭；而是他们点燃火焰，看着它熄灭，然后说：“空气一定是被燃素饱和了。”你甚至不能用燃素理论来说明你“不应该看到”什么；它可以解释一切。

那是科学的早期时代。很长时间里，没有人意识到这里有问题。虚假解释并不会让人觉得它是假的，这正是它们危险的地方。

现代研究表明，人类思考因果关系时，使用的方式类似于贝叶斯网络的有向无环图（DAG）。因为下雨，所以人行道是湿的；因为人行道湿了，所以它很滑：

    雨 -----> 人行道湿 -----> 人行道滑

由此我们可以推断——或者在贝叶斯网络中，严格地用概率计算——当人行道很滑时，很可能下过雨；但如果我们已经知道人行道是湿的，再得知它很滑，并不能让我们更了解是否下过雨。

为什么火燃烧时又热又亮？

    燃素 -----> 火热且亮

这听起来像是个解释。它用的是同样的认知数据格式。但人类大脑并不会自动检测到因果箭头是否真的对结果有约束力。更糟的是，由于事后偏见，我们会觉得原因约束了结果，其实只是事后贴合了结果。

有趣的是，我们对因果概率推理的现代理解，能精确描述燃素理论家错在哪里。贝叶斯网络的一个主要灵感，就是注意到如果推理在因果和结果之间来回共振，会导致证据被重复计算的问题。例如，假设我得到一些不太可靠的信息，说人行道是湿的。这应该让我觉得下雨的可能性更大。但如果下雨的可能性更大，难道不意味着人行道更可能是湿的？那人行道更湿，是不是又让它更滑？但如果人行道很滑，那它很可能是湿的；于是我又该提高下雨的概率……

Judea Pearl 用了一个排队数士兵的算法比喻。假设你在队伍里，看到前后各有一个士兵，加上你自己就是三个人。你问后面的士兵：“你看到多少士兵？”他环顾四周说：“三个。”于是你以为总共有六个士兵。显然，这不是正确的算法。

更聪明的做法是，问你前面的士兵：“你前面有多少士兵？”问后面的士兵：“你后面有多少士兵？”“你前面有多少士兵？”这个问题可以作为信息无歧义地传递。如果你在队伍最前面，你就传递“前面有1个士兵”（你自己）。你后面的人收到“前面有1个士兵”，再传递“前面有2个士兵”给他后面的人。与此同时，每个士兵也会从后面收到“N个士兵”的信息，并传递“N+1个士兵”给前面的人。总共有多少士兵？把你收到的两个数字加起来，再加上你自己，就是队伍总人数。

关键在于，每个士兵都要分别追踪前向和后向的信息，只在最后才加在一起。你永远不会把收到的后向信息加到你传递的前向信息里。实际上，总人数这个信息从不会被直接传递——没人会把它说出来。

在严格的因果概率推理中也有类似原则。如果你通过除观察人行道湿之外的其他渠道得知是否下雨，这会从“雨”节点向“人行道湿”节点发送前向信息，提高我们对人行道湿的预期。如果你观察到人行道湿，这会向我们对下雨的信念发送后向信息，这个信息会从“雨”节点传播到所有相邻节点，除了“人行道湿”节点。我们每条证据只计一次，更新信息不会来回反弹。具体算法可见 Judea Pearl 的经典著作《智能系统中的概率推理：可信推断网络》。

那么，燃素理论到底错在哪里？当我们观察到火又热又亮时，“火热且亮”节点会向“燃素”节点发送后向证据，让我们更新对燃素的信念。但如果这样，我们就不能把这当作燃素理论的成功前向预测。信息只能单向传递，不能来回反弹。

可惜，人类并不会用严格的算法来更新信念网络。我们通过观察子节点了解父节点，通过对父节点的信念预测子节点。但我们不会严格区分前向和后向的信息。我们只记得燃素是热的，燃素让火变热。所以看起来燃素理论预测了火的热度。或者更糟，只是觉得燃素让火变热。

除非你注意到没有任何前瞻性预测被做出，否则这个无约束的因果节点不会被标记为“虚假”。它和你信念网络里的其他节点一样被表示。它感觉就像一个事实，和你知道的其他事实一样：燃素让火变热。

一个设计良好的AI会立刻发现这个问题。这甚至不需要特殊代码，只要正确记录信念网络即可。（可惜我们人类不能像AI那样重写自己的代码。）

所谓“事后偏见”，其实就是人类没有严格区分前向和后向信息，导致前向信息被后向信息污染的非技术性说法。

那些当年走上燃素理论道路的人，并不是想当傻瓜。没有科学家会故意把自己困在死胡同里。你头脑中有没有虚假解释？如果有，我敢保证它们不会被标记为“虚假解释”，所以你搜索“虚假”这个关键词也找不到。

由于事后偏见，仅仅检查你的理论对你已知事实的“预测”效果还不够。你必须预测明天，而不是昨天。这是混乱的人类大脑唯一能确保发送纯粹前向信息的方法。

---

## Fake Causality

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

It feels like an explanation. It’s represented using the same cognitive data format. But the human mind does not automatically detect when a cause has an unconstraining arrow to its effect. Worse, thanks to hindsight bias, it may feel like the cause constrains the effect, when it was merely fitted to the effect.

Interestingly, our modern understanding of probabilistic reasoning about causality can describe precisely what the phlogiston theorists were doing wrong. One of the primary inspirations for Bayesian networks was noticing the problem of double-counting evidence if inference resonates between an effect and a cause. For example, let’s say that I get a bit of unreliable information that the sidewalk is wet. This should make me think it’s more likely to be raining. But, if it’s more likely to be raining, doesn’t that make it more likely that the sidewalk is wet? And wouldn’t that make it more likely that the sidewalk is slippery? But if the sidewalk is slippery, it’s probably wet; and then I should again raise my probability that it’s raining . . .

Judea Pearl uses the metaphor of an algorithm for counting soldiers in a line. Suppose you’re in the line, and you see two soldiers next to you, one in front and one in back. That’s three soldiers, including you. So you ask the soldier behind you, “How many soldiers do you see?” They look around and say, “Three.” So that’s a total of six soldiers. This, obviously, is not how to do it.

A smarter way is to ask the soldier in front of you, “How many soldiers forward of you?” and the soldier in back, “How many soldiers backward of you?” The question “How many soldiers forward?” can be passed on as a message without confusion. If I’m at the front of the line, I pass the message “1 soldier forward,” for myself. The person directly in back of me gets the message “1 soldier forward,” and passes on the message “2 soldiers forward” to the soldier behind them. At the same time, each soldier is also getting the message “N soldiers backward” from the soldier behind them, and passing it on as “N + 1 soldiers backward” to the soldier in front of them. How many soldiers in total? Add the two numbers you receive, plus one for yourself: that is the total number of soldiers in line.

The key idea is that every soldier must separately track the two messages, the forward-message and backward-message, and add them together only at the end. You never add any soldiers from the backward-message you receive to the forward-message you pass back. Indeed, the total number of soldiers is never passed as a message—no one ever says it aloud.

An analogous principle operates in rigorous probabilistic reasoning about causality. If you learn something about whether it’s raining, from some source other than observing the sidewalk to be wet, this will send a forward-message from **Rain** to **Sidewalk Wet** and raise our expectation of the sidewalk being wet. If you observe the sidewalk to be wet, this sends a backward-message to our belief that it is raining, and this message propagates from **Rain** to all neighboring nodes except the **Sidewalk Wet** node. We count each piece of evidence exactly once; no update message ever “bounces” back and forth. The exact algorithm may be found in Judea Pearl’s classic Probabilistic Reasoning in Intelligent Systems: Networks of Plausible Inference.

So what went wrong in phlogiston theory? When we observe that fire is hot and bright, the **Fire Hot and Bright** node can send backward-evidence to the **Phlogiston** node, leading us to update our beliefs about phlogiston. But if so, we can’t count this as a successful forward-prediction of phlogiston theory. The message should go in only one direction, and not bounce back.

Alas, human beings do not use a rigorous algorithm for updating belief networks. We learn about parent nodes from observing children, and predict child nodes from beliefs about parents. But we don’t keep rigorously separate books for the backward-message and forward-message. We just remember that phlogiston is hot, which causes fire to be hot. So it seems like phlogiston theory predicts the hotness of fire. Or, worse, it just feels like phlogiston makes the fire hot.

Until you notice that no advance predictions are being made, the nonconstraining causal node is not labeled “fake.” It’s represented the same way as any other node in your belief network. It feels like a fact, like all the other facts you know: Phlogiston makes the fire hot.

A properly designed AI would notice the problem instantly. This wouldn’t even require special-purpose code, just correct bookkeeping of the belief network. (Sadly, we humans can’t rewrite our own code, the way a properly designed AI could.)

Speaking of “hindsight bias” is just the nontechnical way of saying that humans do not rigorously separate forward and backward messages, allowing forward messages to be contaminated by backward ones.

Those who long ago went down the path of phlogiston were not trying to be fools. No scientist deliberately wants to get stuck in a blind alley. Are there any fake explanations in your mind? If there are, I guarantee they’re not labeled “fake explanation,” so polling your thoughts for the “fake” keyword will not turn them up.

Thanks to hindsight bias, it’s also not enough to check how well your theory “predicts” facts you already know. You’ve got to predict for tomorrow, not yesterday. It’s the only way a messy human mind can be guaranteed of sending a pure forward message.
