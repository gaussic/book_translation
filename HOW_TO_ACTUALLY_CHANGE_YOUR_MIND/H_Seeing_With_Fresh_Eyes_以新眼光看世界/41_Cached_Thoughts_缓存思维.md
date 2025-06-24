## 缓存思维

关于人脑最令人困惑的谜题之一，就是它到底是怎么运作的——毕竟大多数神经元每秒只发放10到20次脉冲，最多也就200Hz。神经科学中有个“百步规则”：任何假设中的操作都必须在最多100个连续步骤内完成——你可以有任意多的并行处理，但不能假设有超过100（最好更少）个神经脉冲依次传递。

你能想象用100Hz的CPU编程吗？无论你有多少颗CPU，要想实时完成任务，你都需要一千亿个处理器。

如果你真的需要为一千亿个100Hz处理器写实时程序，你会极力利用的一种技巧就是缓存。也就是把之前操作的结果存储起来，下次直接查找，而不是每次都从头计算。这非常符合神经网络的风格——识别、联想、模式补全。

很有理由猜测，人类认知的绝大部分其实都是缓存查找。

我有时会在某些时刻想到这个问题。

有个很好的例子，可惜我没能找到原文链接：有个人的邻居总是自以为是，曾随口说过，拆除自家烟囱的最佳方法是：先敲掉壁炉，让砖头掉下一层，再敲掉那层的砖头，如此反复，直到烟囱消失。多年后，这个人真的想拆自家烟囱时，这个缓存的想法就突然冒了出来……

正如他事后总结的——你可以猜到结果并不理想——他的邻居其实并不懂这些，也不是值得信赖的消息源。如果他当时质疑一下，可能就会意识到这主意很糟。有些缓存的答案，我们最好还是重新计算。但大脑会自动补全模式——如果你没有意识到这个模式需要修正，你就会被一个已经补全的模式所左右。

我怀疑，如果这个想法是他自己突然想到的——如果是他本人灵光一现地想出拆烟囱的方法——他会更批判性地审视这个主意。但如果是别人已经想过的点子，你就可以省下思考的力气，直接缓存他们的结论——对吧？

尤其在现代社会，没有人能快到完全靠自己思考。如果我小时候被丢在森林里，由狼或不会说话的机器人养大，我几乎不会像个人类。没人能在一生中，从零开始重现一个狩猎采集部落的全部智慧。至于一个有文字文明的社会的智慧，就更不用说了。

但反过来，我也经常看到那些自诩为批判性思考者的人，重复着根本不是批判性思考者发明的缓存思维。

一个很好的例子是怀疑论者常说：“你无法用事实证据证明或证伪宗教。”正如我在别处指出的，<sup>1</sup> 这在概率论上是错的。在宗教的真实心理学层面上也是错的——几百年前，说这句话会让你被活活烧死。一个女儿得了癌症的母亲会祈祷：“上帝，请治愈我的女儿。”而不会说：“亲爱的上帝，我知道宗教不能有任何可证伪的结果，所以你不可能治好我的女儿……其实我只是为了让自己好受点才祈祷，而不是做点真正能帮到女儿的事。”

但人们读到“你无法用事实证据证明或证伪宗教”这句话，下次看到某个证据能证伪宗教时，大脑就会自动补全这个模式。甚至有些无神论者也会毫不犹豫地重复这个荒谬的说法。如果这是他们自己想出来的主意，反而会更怀疑一点。

死亡。补全模式：“死亡赋予生命意义。”

和善良正直的人谈论生存风险时——这些人一辈子都不会主动想要消灭人类——你会听到他们说：“也许人类并不值得存续。”他们绝不会亲手杀死自己的孩子（孩子也是人类的一部分），但大脑会自动补全这个模式。

你脑海中有哪些被自动补全的模式，其实你从未主动选择过？

理性。补全模式：“爱是不理性的。”

如果这个想法是你自己突然想到的，作为一个全新的念头，你会如何批判性地审视它？我知道我会怎么说，但你会怎么想？用新眼光看问题其实很难。试着让自己不要用标准、意料之中、早已熟悉的方式补全答案。也许标准答案就是最好的，但只有当你能阻止大脑自动补全答案时，你才能真正思考这个问题。

现在你读到这里，下次你听到有人毫不犹豫地重复一个你觉得愚蠢或错误的观点时，你会想到“缓存思维”。我的这个观点现在也在你脑海里，等着被补全。但它是真的吗？别让大脑自动补全！思考吧！

---

<sup>1</sup>参见《地图与领地》中的《宗教声称不可证伪》。

---

## Cached Thoughts

One of the single greatest puzzles about the human brain is how the damn thing works at all when most neurons fire 10–20 times per second, or 200Hz tops. In neurology, the “hundred-step rule” is that any postulated operation has to complete in at most 100 sequential steps—you can be as parallel as you like, but you can’t postulate more than 100 (preferably fewer) neural spikes one after the other.

Can you imagine having to program using 100Hz CPUs, no matter how many of them you had? You’d also need a hundred billion processors just to get anything done in realtime.

If you did need to write realtime programs for a hundred billion 100Hz processors, one trick you’d use as heavily as possible is caching. That’s when you store the results of previous operations and look them up next time, instead of recomputing them from scratch. And it’s a very neural idiom—recognition, association, completing the pattern.

It’s a good guess that the actual majority of human cognition consists of cache lookups.

This thought does tend to go through my mind at certain times.

There was a wonderfully illustrative story which I thought I had bookmarked, but couldn’t re-find: it was the story of a man whose know-it-all neighbor had once claimed in passing that the best way to remove a chimney from your house was to knock out the fireplace, wait for the bricks to drop down one level, knock out those bricks, and repeat until the chimney was gone. Years later, when the man wanted to remove his own chimney, this cached thought was lurking, waiting to pounce . . .

As the man noted afterward—you can guess it didn’t go well—his neighbor was not particularly knowledgeable in these matters, not a trusted source. If he’d questioned the idea, he probably would have realized it was a poor one. Some cache hits we’d be better off recomputing. But the brain completes the pattern automatically—and if you don’t consciously realize the pattern needs correction, you’ll be left with a completed pattern.

I suspect that if the thought had occurred to the man himself—if he’d personally had this bright idea for how to remove a chimney—he would have examined the idea more critically. But if someone else has already thought an idea through, you can save on computing power by caching their conclusion—right?

In modern civilization particularly, no one can think fast enough to think their own thoughts. If I’d been abandoned in the woods as an infant, raised by wolves or silent robots, I would scarcely be recognizable as human. No one can think fast enough to recapitulate the wisdom of a huntergatherer tribe in one lifetime, starting from scratch. As for the wisdom of a literate civilization, forget it.

But the flip side of this is that I continually see people who aspire to critical thinking, repeating back cached thoughts which were not invented by critical thinkers.

A good example is the skeptic who concedes, “Well, you can’t prove or disprove a religion by factual evidence.” As I have pointed out elsewhere,<sup>1</sup> this is simply false as probability theory. And it is also simply false relative to the real psychology of religion—a few centuries ago, saying this would have gotten you burned at the stake. A mother whose daughter has cancer prays, “God, please heal my daughter,” not, “Dear God, I know that religions are not allowed to have any falsifiable consequences, which means that you can’t possibly heal my daughter, so . . . well, basically, I’m praying to make myself feel better, instead of doing something that could actually help my daughter.”

But people read “You can’t prove or disprove a religion by factual evidence,” and then, the next time they see a piece of evidence disproving a religion, their brain completes the pattern. Even some atheists repeat this absurdity without hesitation. If they’d thought of the idea themselves, rather than hearing it from someone else, they would have been more skeptical.

Death. Complete the pattern: “Death gives meaning to life.”

It’s frustrating, talking to good and decent folk—people who would never in a thousand years spontaneously think of wiping out the human species—raising the topic of existential risk, and hearing them say, “Well, maybe the human species doesn’t deserve to survive.” They would never in a thousand years shoot their own child, who is a part of the human species, but the brain completes the pattern.

What patterns are being completed, inside your mind, that you never chose to be there?

Rationality. Complete the pattern: “Love isn’t rational.”

If this idea had suddenly occurred to you personally, as an entirely new thought, how would you examine it critically? I know what I would say, but what would you? It can be hard to see with fresh eyes. Try to keep your mind from completing the pattern in the standard, unsurprising, already-known way. It may be that there is no better answer than the standard one, but you can’t think about the answer until you can stop your brain from filling in the answer automatically.

Now that you’ve read this, the next time you hear someone unhesitatingly repeating a meme you think is silly or false, you’ll think, “Cached thoughts.” My belief is now there in your mind, waiting to complete the pattern. But is it true? Don’t let your mind complete the pattern! Think!

---

<sup>1</sup>See ‘Religion’s Claim to be Non-Disprovable,” in Map and Territory.