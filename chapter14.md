## Chapter 14、Evaluate multiple ideas in parallel during error analysis

**在错误分析过程中并行评估多个想法**

你的团队有以下几个想法来改进猫检测器：

- 解决狗被错认为是猫的问题
- 解决“大形猫科类动物（great cats）”(狮子，豹等)被错认为是家猫（宠物）的问题
- 提高系统在模糊图像上的表现
- ……

你可以并行且有效地评估所有这些想法。我通常会创建一个电子表格，查看100个分类错误的开发集样本并填写在表格上，同时记下可以帮助我记住具体样本的注释。用有小开发集里的4个错误分类样本来说明这个过程，你的电子表格大概如下所示： 

![这里写图片描述](http://oow6unnib.bkt.clouddn.com/myl-c14-0.jpg)

表格中的图片3在Great Cat 和Blurry两列都被勾选了：可以将一个样本与多个类别相关联。这就是为什么底部的百分比加起来不一定等于100%。

虽然我已经将这个过程首先描述为类别分类（Dog, Great cat, Blurry），然后查看样例并对它们进行分类。实践中，当你在查看样例时，可能受到启发而提出一些新的错误类别。例如，也许查看过十几张图像后，你发现许多错误的图片都经过Instagram 过滤器的预处理。你可以返回并在电子表格中添加“Instagram”列。手动查看算法出错的样例，并思考人是 如何/是否 能正确地分类这些样例，这通常会启发你提出新的类别和解决办法。

你有想法去改进的错误类别是最有用的。例如，如果你办法“undoing” Instagram 过滤器从而恢复原始图像，那Instagram类别的添加是最有用的。但是你不必只局限于你已经有想法去改进的错误类别；这个过程的目的是建立一种哪些领域是最有希望关注的直觉。

错误分析是一个迭代的过程。开始的时候你在脑海里甚至可以没有任何分类。通过查看图片，你可能会提出一些关于错误类别的想法。然后查看并手动分类一些图片以后，可能会启发你想出一些新的错误类别，根据新的类别再返回重新检查这些图片，以此类推。

假如你完成了100个开发集样本的错误分析，得到如下表格： 

![这里写图片描述](http://oow6unnib.bkt.clouddn.com/myl-c14-1.jpg)

你现在知道解决狗分类错误的项目可以消除最多8%的错误。致力于Great cat和Blurry的错误分类对项目帮助更大。因此，你可能会挑选后两者之一来进行处理。如果你的团队有足够多的人可以同时展开多个方向，你也可以让一些工程师处理Great cat问题，另外一些解决Blurry的问题。

错误分析并不会得出一个明确的数学公式来告诉你什么才是最高优先级的任务。你还必须考虑你希望在不同错误类别上取得多少进展，以及处理每个错误类别所需要的工作量。
