# 第 4 天:基本 Python 集合| Teclado

> 原文：<https://blog.teclado.com/python-30-day-4-lists-tuples/>

欢迎来到 Python 系列 [30 天的第 4 天！在这篇文章中，我们将介绍一些新的集合类型:列表和元组。](https://blog.teclado.com/30-days-of-python/)

如果你错过了[第三天](/30-days-of-python/python-30-day-3-string-formatting/)，我建议你查看一下，如果你需要复习以下内容:

*   串并置
*   使用`format`和 f 字符串的字符串插值
*   使用`lower`、`upper`、`capitalize`、`title`和`strip`处理字符串
*   使用注释记录代码

此外，我们还制作了第 1、2 和 3 天的简短回顾，您可以在此处查看来刷新您的记忆。

## 列表

我们要看的第一个新集合是列表。

简单地说，列表是其他值的容器。与字符串不同，字符串只是字符的集合，列表可以存储我们喜欢的任何值。如果我们愿意，我们甚至可以混合不同类型的值。

我们使用方括号定义一个列表，如下所示:

```
`names = ["John", "Alice", "Sarah", "George"]` 
```

每个值都放在方括号内，用逗号分隔。

在本例中，我们在一行中定义了一个列表。这里很好，但有时这可能有点难以理解。例如，如果我们试图存储一个电影标题列表，而我们有类似于，`"Eternal Sunshine of the Spotless Mind"`的字符串，该怎么办？我们很快就会发现代码超出了屏幕的宽度。如果我们有很多很多的值，情况也是如此。

当我们遇到这种情况时，我们可以将列表拆分成多行，如下所示:

```
`movie_titles = [
    "Eternal Sunshine of the Spotless Mind",
    "Memento",
    "Requiem for a Dream"
]` 
```

正如我之前提到的，我们可以在一个列表中混合我们想要的任何类型的值，你不必只有字符串，或者只有整数。

```
`friend_details = ["John", 27, "Web Developer"]` 
```

也可以定义一个没有内容的列表，由一对空的方括号`[]`表示。

我们可以通过将列表传递给`print`函数来打印整个列表，如下所示:

```
`friend_details = ["John", 27, "Web Developer"]

print(friend_details)` 
```

然而，通常我们感兴趣的是列表中的值，而不是整个列表，所以让我们看看如何访问列表值。

### 风格注释

抵制诱惑去做这样的事情:

```
`movie_titles = [
    "Eternal Sunshine of the Spotless Mind",
    "Memento", "Requiem for a Dream"
]` 
```

它可能比在每一行上放一个不同的值要短，但是它使得很难看到列表中有多少个值，并且它也使得很难看到值本身。例如，有一个相当微妙的区别:

```
`"Memento", "Requiem for a Dream"` 
```

和

```
`"Memento, Requiem for a Dream"` 
```

这在较长的列表中很容易被忽略。

当我们在一行上写列表时，在逗号后面加一个空格也是一个好习惯。同样，这对于可读性来说非常重要。

比较这个:

```
`numbers = [343.4,545.98,4,954.03,3.5]` 
```

对此:

```
`numbers = [343.4, 545.98, 4, 954.03, 3.5]` 
```

## 访问列表中的值

列表中的每个值都根据其在列表中的位置进行索引。第一个位置的项目位于索引`0`；第二个位置的项目位于索引`1`；诸如此类。

我们可以使用这些索引来访问列表中的值，并且我们通常使用一段称为*订阅表达式*的语法来实现这一点。

订阅表达式用于访问许多集合中的值。对于序列，它们用于通过索引访问元素。

它看起来像这样:

```
`names = ["John", "Alice", "Sarah", "George"]

print(names[2])  # Sarah` 
```

为了从`names`中检索值`"Sarah"`，我们写下我们想要访问的列表的名称，然后在一些方括号中放入我们想要检索的项目的索引。

也可以参考一个*负的*指数，它允许我们从列表的末尾开始工作。在这种情况下，索引`-1`处的项目是最后一个项目；索引为`-2`的项目是倒数第二个项目；诸如此类。

```
`names = ["John", "Alice", "Sarah", "George"]

print(names[-1])  # George` 
```

当我们需要列表中的最后一项时，这非常有用，因为它使我们不必做任何计算来找出最后一项的索引。

## 向列表中添加项目

列表的一个很好的特性是它们是可变的:我们可以改变里面的值。这意味着我们可以添加值、删除值、替换值、重新排序值等等。

首先，让我们关注使用`append`方法向列表添加条目。顾名思义，`append`让我们将一个项目添加到列表的末尾。再一次，我们需要使用点符号来调用`append`，当我们调用它时，我们把我们想要添加的值放在括号内。

```
`names = ["John", "Alice", "Sarah", "George"]
names.append("Simon")

print(names[-1])  # Simon` 
```

我们还可以使用`+`操作符向列表中添加另一个(或多个)项目。在这种情况下，两个操作数**必须**都是列表。

方法也有些不同，因为我们必须在操作中执行赋值。

```
`names = ["John", "Alice", "Sarah", "George"]
names = names + ["Simon"]

print(names[-1])  # Simon` 
```

这有时会很方便，因为它不会修改原始列表，而是生成一个新列表。另一方面，`append`修改现有列表。

除了`append`方法和`+`操作符之外，我们还有一个名为`extend`的方法，它允许我们将多个条目添加到现有列表的末尾。

这些对于在列表末尾添加一个条目都很有用，但是如果我们想在中间添加一个条目呢？为此，我们有`insert`方法。

比我们目前看到的选项要复杂一些，因为它需要两条信息。首先我们需要告诉它我们想在哪里插入值，其次我们需要告诉它我们想插入什么。

例如，假设我们有这样一个列表:

目前，我们在这个序列中缺少值`3`，我们想在索引`2`处插入这个值。我们因此需要这样称呼`insert`:

```
`numbers = [1, 2, 4, 5]
numbers.insert(2, 3)

print(numbers)  # [1, 2, 3, 4, 5]` 
```

如您所见，其他值被右移，以便为新添加的内容腾出空间。

你可能想知道，如果我们在定义的列表之外指定一个索引会发生什么？Python 只是将项目作为结尾:

```
`numbers = [1, 2, 4, 5]
numbers.insert(7, 3)

print(numbers)  # [1, 2, 4, 5, 3]` 
```

## 从列表中删除项目

就像添加项目一样，从列表中删除项目时，有几个选项可供使用。

首先，我们有`remove`方法。`remove`再次使用我们已经见过很多次的点语法，它删除第一个与我们传入的值相匹配的项。

例如，如果我们有这样一个列表:

```
`names = ["John", "Sarah", "Alice", "John"]` 
```

我们可以通过调用`remove`来删除第一个`"John"`:

```
`names = ["John", "Sarah", "Alice", "John"]
names.remove("John")

print(names)  # ['Sarah', 'Alice', 'John']` 
```

第二个实例`"John"`被原封不动地留下，所有的东西都被留了下来，这样我们的列表中就没有漏洞了。

有时我们不一定知道我们想要删除的值，但是我们知道*值在列表中的位置。在这种情况下，我们有几个选择。*

首先，我们可以使用`del`关键字。`del`可以用来删除我们想要的任何东西，包括整个列表，但是如果我们使用订阅表达式，我们可以用它来删除特定索引处的一个项目。

```
`names = ["John", "Sarah", "Alice", "Mike"]
del names[0]

print(names)  # ['Sarah', 'Alice', 'Mike']` 
```

我们使用`del`的主要选择是`pop`。默认情况下,`pop`将移除列表中的最后一项，但是我们可以选择传递一个索引作为参数来移除另一项。

```
`names = ["John", "Sarah", "Alice", "Mike"]
names.pop()

print(names)  # ['John', 'Sarah', 'Alice']

names.pop(1)

print(names)  # ['John', 'Alice']` 
```

关于`pop`真正有用的事情之一是方法调用表达式计算我们从列表中移除的项目。因此，我们可以用它来删除一个我们计划在以后的操作中使用的项目:

```
`names = ["John", "Sarah", "Alice", "Mike"]
last_in_line = names.pop()

print(names)         # ['John', 'Sarah', 'Alice']
print(last_in_line)  # Mike` 
```

最后，我们还有`clear`。这个非常简单，它将删除给定列表中的所有内容:

```
`names = ["John", "Sarah", "Alice", "John"]
names.clear()

print(names)  # []` 
```

## 元组

到目前为止，我们已经讨论了很多关于列表的内容，但是关于元组呢？

元组非常类似于列表，因为它们是其他值的容器，但是有一些重要的区别，我们将在后面讨论。

定义一个元组所需要的只是一系列逗号分隔的值:

```
`names = "John", "Sarah", "Alice"` 
```

然而，更常见的是，我们会看到元组被写成这样:

```
`names = ("John", "Sarah", "Alice")` 
```

大多数时候，这些括号是可选的——逗号才是重要的——但是有些情况下我们真的需要它们来区分元组内容和其他逗号分隔的值。

例如，将元组放在一个列表中是完全合法的(也是常见的)。也许我们希望将电影名称和上映日期一起存储在电影列表中，如下所示:

```
`movies = [
    ("Eternal Sunshine of the Spotless Mind", 2004),
    ("Memento", 2000),
    ("Requiem for a Dream", 2000)
]` 
```

这里我们有一个包含三个元组的列表，每个元组包含两个条目。

如果我们不在元组周围使用括号，就没有办法区分元组，因为列表也使用逗号来分隔值。

如果没有括号，我们会得到这样的结果:

```
`movies = [
    "Eternal Sunshine of the Spotless Mind", 2004,
    "Memento", 2000,
    "Requiem for a Dream", 2000
]` 
```

请记住，Python 不太关心列表中的换行符，所以这与下面的列表是一样的——一个包含 6 个元素的列表:

```
`movies = [
    "Eternal Sunshine of the Spotless Mind",
  2004,
    "Memento",
  2000,
    "Requiem for a Dream",
  2000
]` 
```

为了避免这样的问题，括号是强制性的。

我们必须记住的一个有点尴尬的语法是定义只有一个条目的元组。记住逗号是构成元组的要素，所以我们不能像这样写:

那只是一个括号里的字符串。如果我们想把它变成一个元组，我们必须这样写:

或者这个:

两者都很难看，但谢天谢地，这不是我们经常要写的东西。

## 访问元组中的值

与列表非常相似，元组是有序的集合，其中每个项目都可以根据它们在集合中的位置通过索引来访问。

我们甚至使用相同的订阅表达式语法来访问元组中的项目。

在这一点上，很明显元组和列表有很多相似之处，所以你可能会问自己，为什么我们两个都有？

## 元组与列表

元组和列表的最大区别之一是元组是不可变的。一旦我们定义了它们，我们就不能改变它们。

这意味着您不会找到任何针对元组的`pop`或`append`方法，并且`del`关键字不允许您使用索引删除值。

可以使用的一个操作符是`+`操作符，但是如果我们回想起我们对列表`+`的讨论，这个操作符给了我们一个新的集合。如果我们将它与一个元组一起使用，原始元组将保持不变:我们只是创建了一个新的元组。

注意，只能使用`+`来连接两个元组。

元组不能改变的事实是一个非常理想的属性，因为它允许我们为它们的内容定义一个一致的结构，这意味着我们像表格行中的单元格一样使用值。让我告诉你我的意思。

假设我们有三条信息，我们希望为我们的集合中的每部电影存储。我们需要电影的标题、导演的名字和上映年份。

我可能会这样定义我的`movies`系列:

```
`movies = [
    (
        "Eternal Sunshine of the Spotless Mind",
        "Michel Gondry",
        2004
    ),
    (
        "Memento",
        "Christopher Nolan",
        2000
    ),
    (
        "Requiem for a Dream",
        "Darren Aronofsky",
        2000
    )
]` 
```

对于每个元组，我都使用了相同的数据顺序，我们可以认为它代表了这样一个表中的一行:TitleDirectorRelease《纯洁心灵的永恒阳光》Michel gondry 2004《梦的挽歌》Darren Aronofsky2000 因为元组不能改变，所以我们可以肯定数据总是会与我们定义的约定相匹配。第一个索引中的项目总是电影标题。第二个索引中的项目将始终是导演姓名。

将此与列表进行比较。我已经不能确定顺序了，因为就我所知，列表可能已经添加了几个项目，删除了几个项目，并且列表可能已经按字母顺序排序了。它甚至可能是空的。我们只是不知道，这有时会是个问题。

另一方面，能够修改数据是非常非常有用的。例如，如果我们将`movies`创建为一个元组，我们就不能再向集合中添加其他电影。如果我们正在创建一个类似于电影库的东西，用户可能想要在以后添加新的电影，那就不好了。

没有哪一个比另一个更好:关键在于为工作选择正确的工具。

## 访问嵌套集合中的值

我们现在已经有了一些嵌套集合的实例——例如，列表中的元组——所以我们需要简单地讨论一下如何从这些内部集合中获取条目。

记住当我们写类似`my_list[0]`的东西时，这是一个订阅表达式。它给我们的值是我们指定的集合中所请求的索引处的值。

所以如果我们有这样一个系列:

```
`movies = [
    ("Eternal Sunshine of the Spotless Mind", 2004),
    ("Memento", 2000),
    ("Requiem for a Dream", 2000)
]` 
```

我们写道:

我们得到的是元组，

```
`("Eternal Sunshine of the Spotless Mind", 2004)` 
```

因此，如果我们想要这部电影的标题，我们知道它在索引`0`处，我们可以添加另一组方括号，如下所示:

```
`movies[0][0]  # "Eternal Sunshine of the Spotless Mind"` 
```

这相当于做这样的事情:

```
`movie = movies[0]  # ("Eternal Sunshine of the Spotless Mind", 2004)
movie[0]           # "Eternal Sunshine of the Spotless Mind"` 
```

我们有两个订阅表达式。第一个产生位于索引`0`的元组，然后第二个产生该元组的索引`0`的值。

## 练习

1.  创建一个包含单个元组的`movies`列表。元组应该包含电影标题、导演姓名、电影上映年份和电影预算。
2.  使用`input`功能收集另一部电影的信息。你需要一个标题，导演的名字，发行年份和预算。
3.  使用`input`从您收集的值创建一个新的元组。确保它们与您在`movies`列表中编写的元组顺序相同。
4.  通过访问您的新电影元组，使用一个 [f 字符串](/30-days-of-python/python-30-day-3-string-formatting/)打印电影名称和发行年份。
5.  使用`append`将新的电影元组添加到`movies`集合。
6.  打印`movies`收藏中的两部电影。
7.  从`movies`移除第一部电影。用你喜欢的任何方法。

你可以在这里找到这些练习的答案。

## 额外资源

我们有一个关于列表的`extend`方法的专门帖子，你可以在我们的博客上找到[。](https://blog.teclado.com/python-extending-lists/)