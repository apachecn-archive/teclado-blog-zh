# Python 的格式函数

> 原文：<https://blog.teclado.com/pythons-format-function/>

嘿，欢迎来到另一篇简短的 Python 片段帖子！这次我们来看看`format`函数。

我知道你们很多人在想什么:“菲尔，格式不是功能。是方法！如果你要教我们东西，至少要用正确的术语……”

我在这里告诉你有一个`format`方法**和**一个`format`函数，它们做完全不同的事情！

不出所料，`format`函数实际上与我们之前的格式化帖子非常接近，所以你可能想在进一步阅读之前熟悉一下这些。您可以在下面找到几个链接:

在这些帖子中，我们讨论使用 Python 的[格式规范迷你语言](https://docs.python.org/3/library/string.html#format-specification-mini-language)使用一些非常神秘的语法以各种方式格式化字符串。`format`函数是一种利用这种格式化语法而不使用字符串插值的方法。例如，您可以将`format`函数与字符串连接结合使用，或者在打印单个值时使用。

那么语法是什么样的呢？

```py
format(12, "02x")  # 0c 
```

我们可以看到`format`在这种情况下有两个参数。第一个是要格式化的值，这实际上是唯一必需的参数。我们稍后会详细讨论这个问题。

第二个参数是一个格式规范，为此我们必须传入一个表示我们想要应用的格式选项的字符串。当作为字符串插值的一部分执行这种格式化时，这些选项将出现在冒号之后，但在其他方面保持不变:

```py
f"{12:02x}"  # 0c
"{:02x}".format(12) 
```

那么，这到底做了什么？如果你一直关注我们的格式化系列，你可能会从我们的 RGB 到十六进制数转换器中认出这个代码。`02x`告诉 Python 我们想要用一个 2 位数的十六进制数来表示这个数，任何缺少的数字都用零来填充。

您可以在我之前链接的 Python 文档中找到格式化选项的详尽列表。一篇小小的帖子涵盖的内容太多了！

前面我提到过`format`只有一个必需的参数，那么当我们不提供格式规范作为第二个参数时会发生什么呢？

这实际上等同于将值传递给`str()`。对于传入的任何值，您只需要得到一个普通的字符串表示。

```py
example_tuple = 1, 2, 3
print(format(example_tuple))  # (1, 2, 3) 
```

## 包扎

`format`函数到此为止。我希望你学到了一些新的东西，我建议你再看看 Python 的内置函数。有一大堆我们几乎从未使用过的简洁函数。

如果您刚刚开始您的 Python 之旅，并且您有点迷路，请查看[完整的 Python 课程](https://www.udemy.com/the-complete-python-course/learn/?couponCode=BLOGGER)。您还应该注册下面的邮件列表，因为我们每个月都会发送优惠券，为您提供我们 Python 课程的最优惠价格！