**真正属于你的一部分**

作者：Eliezer Yudkowsky

Drew McDermott的经典论文《人工智能遇到自然愚蠢》批评了那些试图用语义网络来表示像“幸福是一种心理状态”这样的概念的AI程序：

> STATE-OF-MIND
> ∧
> \| IS-A
> |
> HAPPINESS

当然，HAPPINESS节点里面什么也没有；它只是一个裸露的LISP符号，带着一个暗示性的英文名称。

因此，McDermott说：“对于有纪律的程序员来说，一个很好的测试是尝试在关键位置使用gensym，看看他是否仍然欣赏自己的系统。例如，如果将STATE-OF-MIND重命名为G1073...，”那么我们就得到了IS-A(HAPPINESS, G1073)，这看起来就更加值得怀疑了。”

或者我可以稍微改述一下这个观点：如果你将所有带有暗示性英文名称的符号替换为随机符号，你将完全无法弄清楚G1071(G1072, G1073)是什么意思。这个AI程序是用来表示汉堡吗？苹果吗？幸福吗？谁知道呢？如果你删除了这些带有暗示性的英文名称，它们就不会再长回来了。

假设一个物理学家告诉你“光是波”，而你相信这个物理学家。你现在在脑海里有一个小网络，表示：

> IS-A(LIGHT, WAVES)

正如McDermott所说：“整个问题在于让听者注意到它被告知了什么，而不是‘理解’，而是‘注意’。”假设物理学家告诉你：“光是由一些小的弯曲物质组成的。”你会感到有什么不同的预期体验吗？

你如何意识到你不应该信任“光是波”这一看似的知识？你可以通过一个测试来验证：“如果它被从我的脑海中删除，我能否重新获得他的知识？”

这与在AI程序中将带有暗示性名称的LISP符号混乱起来，并看看其他人是否能弄清楚它们所谓的“指代”是什么意思，在精神上是类似的。它也类似于观察到一个人工算术计算机（[Artificial Arithmetician](https://www.lesswrong.com/rationality/artificial-addition)）被编程来记录和回放：

> Plus-Of(Seven, Six) = Thirteen

如果你从记忆中删除它，它无法重新获得这些知识，直到另一个人重新将其输入数据库。就像如果你忘记了“光是波”，你无法通过其他方式重新获得这一知识，除非你再次向物理学家询问。你不能像物理学家最初获得这些知识那样为自己生成这些知识。

相同的经历让我们形成一个信念，将信念与其他知识、感官输入和运动输出连接起来。如果你看到一只海狸咬着一根原木，那么你知道这种“咬木头的东西”是什么样子的，以后无论它是否被称为“海狸”，你都能认出它。但如果你是通过别人告诉你关于“海狸”的事实来获得的信念，你可能无法认出一只海狸。

这就是试图告诉人工智能一些它无法自己学习的事实的巨大危险。这也是试图告诉某人关于物理学的知识的巨大危险，尤其是当他们无法自己验证这些知识时。因为物理学家所说的“波”并不是“某种小的弯曲物”，而是一个纯粹的数学概念。

正如Donald Davidson所观察到的，如果你相信“海狸”生活在沙漠中，成年时全身雪白，重达300磅，那么你对海狸并没有任何真实的信念，无论这个信念是否正确。你对“海狸”的信念甚至没有正确到可以被证伪的程度。<sup>2</sup>如果你没有足够的经验来在信念被删除后重新生成它们，那么你是否有足够的经验将该信念与任何事物相连接？维特根斯坦说：“一个能够转动但没有其他东西与之共同转动的轮子，不是机制的一部分。”

几乎在我开始阅读关于人工智能的内容时——甚至在我读到McDermott之前——我意识到，一个非常好的主意是：我应该经常问自己：“如果我的记忆中删除了这个知识，我如何再生这个知识？”

删除越深，测试就越严格。如果我脑海中删除了毕达哥拉斯定理的所有证明，我能否重新证明它？我想可以。如果我脑海中删除了所有关于毕达哥拉斯定理的知识，我是否会注意到需要重新证明这个定理？如果不进行测试，很难夸口说自己可以做到，但如果你递给我一个边长为3和4的直角三角形，并告诉我斜边的长度是可以计算的，我想我能够计算出来，只要我仍然掌握其他所有的数学知识。

那么，关于数学证明的概念呢？如果从来没有人告诉我这个概念，我会不会根据我掌握的其他信念重新发明它？曾经有一段时间，人类没有这个概念。一定是有人发明了它。那个人当时注意到了什么？如果我看到其他同样新颖且同样重要的事情，我会注意到吗？我能否跳出框框思考得这么远？

你能重新生成多少知识？从多深的删除开始？这不仅仅是一个用来摒弃不充分连接的信念的测试。它是一种吸收知识源泉的方式，而不仅仅是一个事实。

一个牧羊人建立了一个通过每当一只羊离开羊圈时扔一块石子进桶，羊回来时再从桶中拿出一块石子的计数系统。如果你，作为学徒，无法理解这个系统——如果它是无缘无故起作用的魔法——那么当你不小心把一块额外的石子扔进桶里时，你就不知道该怎么做。你不能自己制作的东西，当情境需要它时，你就无法重新制作出来。你不能回到源头，调整其中的某个参数，并且在没有源头的情况下重新生成结果。如果“二加四等于六”对你来说是一个事实，而某个元素变成了“五”，那么当你只知道“二加四等于六”时，你如何知道“二加五等于七”？

如果你看到一株小植物，每当一只鸟飞过时，它就掉下一颗种子，你不会意识到你可以用这种植物来部分自动化羊计数器。尽管你学到了原始制造者会用来改进他们发明的东西，但你不能回到源头并重新创造它。

当你掌握了某个思想的源头时，这个思想就能随着你获得新知识和新技能而变化。当你掌握了某个思想的源头时，它就真正成为你的一部分，并随着你一起成长。

努力让自己成为每个值得思考的思想的源头。如果这个思想最初来自外部，确保它也来自内部。不断问自己：“如果这个思想被删除，我将如何再生它？”当你有了答案时，想象这个知识也被删除了。当你找到了泉源，看看它还能流出什么。

---

<sup>1</sup>顺便说一下，这并不正确。

<sup>2</sup>Rorty，《Out of the Matrix: How the Late Philosopher Donald Davidson Showed That Reality Can’t Be an Illusion》，2003，[http://archive.boston.com/news/globe/ideas/articles/2003/10/05/out\_of\_the\_matrix/](http://archive.boston.com/news/globe/ideas/articles/2003/10/05/out_of_the_matrix/)

---

## Truly Part of You

by Eliezer Yudkowsky

A classic paper by Drew McDermott, “Artificial Intelligence Meets Natural Stupidity,” criticized AI programs that would try to represent notions like happiness is a state of mind using a semantic network:

>   STATE-OF-MIND
>       ∧
>       | IS-A
>       |
>   HAPPINESS

And of course there’s nothing inside the HAPPINESS node; it’s just a naked LISP token with a suggestive English name.

So, McDermott says, “A good test for the disciplined programmer is to try using gensyms in key places and see if he still admires his system. For example, if STATE-OF-MIND is renamed G1073. . .” then we would have IS-A(HAPPINESS, G1073) “which looks much more dubious.”

Or as I would slightly rephrase the idea: If you substituted randomized symbols for all the suggestive English names, you would be completely unable to figure out what G1071(G1072, G1073) meant. Was the AI program meant to represent hamburgers? Apples? Happiness? Who knows? _If you delete the suggestive English names, they don’t grow back._

Suppose a physicist tells you that “Light is waves,” and you believe the physicist. You now have a little network in your head that says:

>    IS-A(LIGHT, WAVES).

As McDermott says, “The whole problem is getting the hearer to notice what it has been told. Not ‘understand,’ but ‘notice.’ ” Suppose that instead the physicist told you, “Light is made of little curvy things.”<sup>1</sup> Would you notice any difference of anticipated experience?

How can you realize that you shouldn’t trust your seeming knowledge that “light is waves”? One test you could apply is asking, “Could I regenerate his knowledge if it were somehow deleted from my mind?”

This is similar in spirit to scrambling the names of suggestively named lisp tokens in your AI program, and seeing if someone else can figure out what they allegedly “refer” to. It’s also similar in spirit to observing that an [Artificial Arithmetician](https://www.lesswrong.com/rationality/artificial-addition) programmed to record and play back

>    Plus-Of(Seven, Six) = Thirteen

can’t regenerate the knowledge if you delete it from memory, until another human re-enters it in the database. Just as if you forgot that “light is waves,” you couldn’t get back the knowledge except the same way you got the knowledge to begin with—by asking a physicist. You couldn’t generate the knowledge for yourself, the way that physicists originally generated it.

The same experiences that lead us to formulate a belief, connect that belief to other knowledge and sensory input and motor output. If you see a beaver chewing a log, then you know what this thing-that-chews-through-logs looks like, and you will be able to recognize it on future occasions whether it is called a “beaver” or not. But if you acquire your beliefs about beavers by someone else telling you facts about “beavers,” you may not be able to recognize a beaver when you see one.

This is the terrible danger of trying to tell an artificial intelligence facts that it could not learn for itself. It is also the terrible danger of trying to tell someone about physics that they cannot verify for themselves. For what physicists mean by “wave” is not “little squiggly thing” but a purely mathematical concept.

As Donald Davidson observes, if you believe that “beavers” live in deserts, are pure white in color, and weigh 300 pounds when adult, then you do not have any beliefs about beavers, true or false. Your belief about “beavers” is not right enough to be wrong.<sup>2</sup> If you don’t have enough experience to regenerate beliefs when they are deleted, then do you have enough experience to connect that belief to anything at all? Wittgenstein: “A wheel that can be turned though nothing else moves with it, is not part of the mechanism.”

Almost as soon as I started reading about AI—even before I read McDermott—I realized it would be a really good idea to always ask myself: “How would I regenerate this knowledge if it were deleted from my mind?”

The deeper the deletion, the stricter the test. If all proofs of the Pythagorean Theorem were deleted from my mind, could I re-prove it? I think so. If all knowledge of the Pythagorean Theorem were deleted from my mind, would I notice the Pythagorean Theorem to re-prove? That’s harder to boast, without putting it to the test; but if you handed me a right triangle with sides of length 3 and 4, and told me that the length of the hypotenuse was calculable, I think I would be able to calculate it, if I still knew all the rest of my math.

What about the notion of mathematical proof? If no one had ever told it to me, would I be able to reinvent that on the basis of other beliefs I possess? There was a time when humanity did not have such a concept. Someone must have invented it. What was it that they noticed? Would I notice if I saw something equally novel and equally important? Would I be able to think that far outside the box?

How much of your knowledge could you regenerate? From how deep a deletion? It’s not just a test to cast out insufficiently connected beliefs. It’s a way of absorbing a fountain of knowledge, not just one fact.

A shepherd builds a counting system that works by throwing a pebble into a bucket whenever a sheep leaves the fold, and taking a pebble out whenever a sheep returns. If you, the apprentice, do not understand this system—if it is magic that works for no apparent reason—then you will not know what to do if you accidentally drop an extra pebble into the bucket. That which you cannot make yourself, you cannot remake when the situation calls for it. You cannot go back to the source, tweak one of the parameter settings, and regenerate the output, without the source. If “two plus four equals six” is a brute fact unto you, and then one of the elements changes to “five,” how are you to know that “two plus five equals seven” when you were simply told that “two plus four equals six”?

If you see a small plant that drops a seed whenever a bird passes it, it will not occur to you that you can use this plant to partially automate the sheep-counter. Though you learned something that the original maker would use to improve on their invention, you can’t go back to the source and re-create it.

When you contain the source of a thought, that thought can change along with you as you acquire new knowledge and new skills. When you contain the source of a thought, it becomes truly a part of you and grows along with you.

Strive to make yourself the source of every thought worth thinking. If the thought originally came from outside, make sure it comes from inside as well. Continually ask yourself: “How would I regenerate the thought if it were deleted?” When you have an answer, imagine that knowledge being deleted as well. And when you find a fountain, see what else it can pour.

---

<sup>1</sup>Not true, by the way.

<sup>2</sup>Rorty, “Out of the Matrix: How the Late Philosopher Donald Davidson Showed That Reality Can’t Be an Illusion,” 2003, http://archive.boston.com/news/globe/ideas/articles/2003/10/05/out_of_the_matrix/.