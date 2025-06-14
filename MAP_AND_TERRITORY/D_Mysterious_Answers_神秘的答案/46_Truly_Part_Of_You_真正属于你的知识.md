## 真正属于你的知识

Drew McDermott 在经典论文《人工智能遇上自然愚蠢》中批评了那些试图用语义网络来表示诸如“幸福是一种心理状态”这类概念的 AI 程序：

>   STATE-OF-MIND  
>       ∧  
>       | IS-A  
>       |  
>   HAPPINESS

当然，HAPPINESS 节点里什么都没有；它只是一个带有暗示性英文名的裸 LISP 符号。

所以，McDermott 说：“对程序员来说，一个很好的自律测试是，把关键位置的名字都换成 gensym（随机符号），看看他是否还会欣赏自己的系统。例如，如果 STATE-OF-MIND 被重命名为 G1073……”那么我们就有了 IS-A(HAPPINESS, G1073)，“看起来就可疑多了。”

或者换个说法：如果你把所有暗示性的英文名都换成随机符号，你就完全无法弄清 G1071(G1072, G1073) 到底是什么意思。这个 AI 程序到底是在表示汉堡？苹果？还是幸福？谁知道呢？如果你删掉了这些暗示性的英文名，它们是不会自己长回来的。

假设有个物理学家告诉你“光是波”，你相信了他。你脑海里就有了这样一个小网络：

>    IS-A(LIGHT, WAVES).

如果有人问你“光是什么做的？”，你就能回答“波！”

正如 McDermott 所说，“整个问题在于让听者注意到他被告知了什么。不是‘理解’，而是‘注意’。”假如物理学家告诉你，“光是由小弯曲的东西组成的。”<sup>1</sup> 你会觉得你的预期体验有任何不同吗？

你怎么才能意识到自己不该相信“光是波”这种貌似的知识？你可以问自己：“如果这段知识被从我脑中抹去，我还能重新获得它吗？”

这和把 AI 程序里带暗示性的 LISP 符号名打乱，看别人能否猜出它们“指代”什么，是类似的思路。也类似于观察一个人工算术员被编程为记录和回放

>    Plus-Of(Seven, Six) = Thirteen

如果你把这条记录从内存中删掉，它就无法再生出这个知识，除非有另一个人重新输入数据库。就像你忘了“光是波”，你也只能像最初那样——去问物理学家——才能重新获得这段知识。你无法像物理学家最初那样自己推导出这段知识。

那些让我们形成信念的体验，会把信念和其他知识、感官输入、动作输出联系起来。如果你见过海狸啃木头，你就知道“啃木头的那个东西”长什么样，无论它叫不叫“海狸”，你以后都能认出来。但如果你只是听别人讲“海狸”的事实，你可能见到海狸时根本认不出来。

这正是试图告诉人工智能它自己无法学会的事实的巨大危险，也是试图告诉别人他们无法自行验证的物理知识的巨大危险。物理学家说的“波”不是“小弯曲的东西”，而是一个纯粹的数学概念。

正如 Donald Davidson 所说，如果你相信“海狸生活在沙漠里，成年后全身雪白，体重300磅”，那么你对“海狸”其实没有任何信念，无论真假。你对“海狸”的信念甚至还不够错。<sup>2</sup> 如果你没有足够的体验来在知识被删除时重新获得它，那么你也没有足够的体验把这个信念和其他任何东西联系起来。维特根斯坦说：“一个可以转动但不会带动其他部件的轮子，不算是机械的一部分。”

我刚开始读 AI 相关内容时——甚至在读 McDermott 之前——就意识到，时刻问自己：“如果这段知识被从我脑中抹去，我还能怎么重新获得它？”是个好主意。

删除越深，测试越严格。如果我脑中所有关于勾股定理的证明都被抹去，我还能重新证明它吗？我觉得可以。如果我脑中所有关于勾股定理的知识都被抹去，我还能注意到勾股定理并重新证明吗？这就难说了，但如果你给我一个边长为3和4的直角三角形，并告诉我斜边的长度可以算出来，我觉得我还是能算出来，只要我还记得其他数学知识。

那么“数学证明”这个概念呢？如果没人告诉过我，我能不能凭已有的信念重新发明出来？人类曾经没有这个概念，总有人最早发明了它。他们注意到了什么？如果我遇到同样新颖、同样重要的东西，我会注意到吗？我能想得那么“出格”吗？

你的知识有多少是你能自己重新获得的？能从多深的删除中恢复？这不仅是用来剔除联系不够紧密信念的测试，更是吸收知识源泉的方法，而不仅仅是记住一个事实。

牧羊人用扔石子进桶、羊回来时取出石子的方式来计数。如果你作为学徒不理解这个系统——如果它对你来说只是“神奇地有效”，那你就不知道如果不小心多扔了一颗石子该怎么办。你无法自己重建这个系统，也无法在需要时调整参数重新生成结果。如果“二加四等于六”对你来说只是个死记硬背的事实，当其中一个数变成五时，你怎么知道“二加五等于七”？你只是被告知“二加四等于六”而已。

如果你看到一种小植物，每当有鸟飞过就掉下一颗种子，你不会想到可以用它来部分自动化牧羊计数器。虽然你学到了原始发明者会用来改进发明的东西，但你无法回到源头重新创造它。

当你掌握了思想的源头，这个思想就能随着你获得新知识和新技能而一起成长。当你拥有思想的源头，这个思想才真正成为你的一部分，并随你成长。

努力让自己成为每一个值得思考的思想的源头。如果这个思想最初来自外部，也要确保它能从你内心生发。不断问自己：“如果这段思想被删除，我该如何重新获得？”当你有了答案，再想象这段知识也被删除。每当你找到一口知识之泉，看看它还能涌出什么。

---

<sup>1</sup>顺便说一句，这并不是真的。

<sup>2</sup>Rorty, “Out of the Matrix: How the Late Philosopher Donald Davidson Showed That Reality Can’t Be an Illusion,” 2003, http://archive.boston.com/news/globe/ideas/articles/2003/10/05/out_of_the_matrix/。

---

## Truly Part of You

A classic paper by Drew McDermott, “Artificial Intelligence Meets Natural Stupidity,” criticized AI programs that would try to represent notions like happiness is a state of mind using a semantic network:

>   STATE-OF-MIND
>       ∧
>       | IS-A
>       |
>   HAPPINESS

And of course there’s nothing inside the HAPPINESS node; it’s just a naked LISP token with a suggestive English name.

So, McDermott says, “A good test for the disciplined programmer is to try using gensyms in key places and see if he still admires his system. For example, if STATE-OF-MIND is renamed G1073 . . .” then we would have IS-A(HAPPINESS, G1073) “which looks much more dubious.”

Or as I would slightly rephrase the idea: If you substituted randomized symbols for all the suggestive English names, you would be completely unable to figure out what G1071(G1072, G1073) meant. Was the AI program meant to represent hamburgers? Apples? Happiness? Who knows? If you delete the suggestive English names, they don’t grow back.

Suppose a physicist tells you that “Light is waves,” and you believe the physicist. You now have a little network in your head that says:

>    IS-A(LIGHT, WAVES).

If someone asks you “What is light made of?” you’ll be able to say “Waves!”

As McDermott says, “The whole problem is getting the hearer to notice what it has been told. Not ‘understand,’ but ‘notice.’ ” Suppose that instead the physicist told you, “Light is made of little curvy things.”<sup>1</sup> Would you notice any difference of anticipated experience?

How can you realize that you shouldn’t trust your seeming knowledge that “light is waves”? One test you could apply is asking, “Could I regenerate this knowledge if it were somehow deleted from my mind?”

This is similar in spirit to scrambling the names of suggestively named LISP tokens in your AI program, and seeing if someone else can figure out what they allegedly “refer” to. It’s also similar in spirit to observing that an Artificial Arithmetician programmed to record and play back

>    Plus-Of(Seven, Six) = Thirteen

can’t regenerate the knowledge if you delete it from memory, until another human re-enters it in the database. Just as if you forgot that “light is waves,” you couldn’t get back the knowledge except the same way you got the knowledge to begin with—by asking a physicist. You couldn’t generate the knowledge for yourself, the way that physicists originally generated it.

The same experiences that lead us to formulate a belief, connect that belief to other knowledge and sensory input and motor output. If you see a beaver chewing a log, then you know what this thing-that-chews-throughlogs looks like, and you will be able to recognize it on future occasions whether it is called a “beaver” or not. But if you acquire your beliefs about beavers by someone else telling you facts about “beavers,” you may not be able to recognize a beaver when you see one.

This is the terrible danger of trying to tell an artificial intelligence facts that it could not learn for itself. It is also the terrible danger of trying to tell someone about physics that they cannot verify for themselves. For what physicists mean by “wave” is not “little squiggly thing” but a purely mathematical concept.

As Donald Davidson observes, if you believe that “beavers” live in deserts, are pure white in color, and weigh 300 pounds when adult, then you do not have any beliefs about beavers, true or false. Your belief about “beavers” is not right enough to be wrong.<sup>2</sup> If you don’t have enough experience to regenerate beliefs when they are deleted, then do you have enough experience to connect that belief to anything at all? Wittgenstein: “A wheel that can be turned though nothing else moves with it, is not part of the mechanism.”

Almost as soon as I started reading about AI—even before I read McDermott—I realized it would be a really good idea to always ask myself: “How would I regenerate this knowledge if it were deleted from my mind?”

The deeper the deletion, the stricter the test. If all proofs of the Pythagorean Theorem were deleted from my mind, could I re-prove it? I think so. If all knowledge of the Pythagorean Theorem were deleted from my mind, would I notice the Pythagorean Theorem to re-prove? That’s harder to boast, without putting it to the test; but if you handed me a right triangle with sides of length 3 and 4, and told me that the length of the hypotenuse was calculable, I think I would be able to calculate it, if I still knew all the rest of my math.

What about the notion of mathematical proof ? If no one had ever told it to me, would I be able to reinvent that on the basis of other beliefs I possess? There was a time when humanity did not have such a concept. Someone must have invented it. What was it that they noticed? Would I notice if I saw something equally novel and equally important? Would I be able to think that far outside the box?

How much of your knowledge could you regenerate? From how deep a deletion? It’s not just a test to cast out insufficiently connected beliefs. It’s a way of absorbing a fountain of knowledge, not just one fact.

A shepherd builds a counting system that works by throwing a pebble into a bucket whenever a sheep leaves the fold, and taking a pebble out whenever a sheep returns. If you, the apprentice, do not understand this system—if it is magic that works for no apparent reason—then you will not know what to do if you accidentally drop an extra pebble into the bucket. That which you cannot make yourself, you cannot remake when the situation calls for it. You cannot go back to the source, tweak one of the parameter settings, and regenerate the output, without the source. If “two plus four equals six” is a brute fact unto you, and then one of the elements changes to “five,” how are you to know that “two plus five equals seven” when you were simply told that “two plus four equals six”?

If you see a small plant that drops a seed whenever a bird passes it, it will not occur to you that you can use this plant to partially automate the sheep-counter. Though you learned something that the original maker would use to improve on their invention, you can’t go back to the source and re-create it.

When you contain the source of a thought, that thought can change along with you as you acquire new knowledge and new skills. When you contain the source of a thought, it becomes truly a part of you and grows along with you.

Strive to make yourself the source of every thought worth thinking. If the thought originally came from outside, make sure it comes from inside as well. Continually ask yourself: “How would I regenerate the thought if it were deleted?” When you have an answer, imagine that knowledge being deleted as well. And when you find a fountain, see what else it can pour.

---

<sup>1</sup>Not true, by the way.

<sup>2</sup>Rorty, “Out of the Matrix: How the Late Philosopher Donald Davidson Showed That Reality Can’t Be an Illusion,” 2003, http://archive.boston.com/news/globe/ideas/articles/2003/10/05/out_of_the_matrix/.