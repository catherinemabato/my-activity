# 在系统中四处移动

早期的 Shell 允许你在文件系统中进行目录跳转并运行命令，而现代的 Shell 如 Nu 也允许你这样做。让我们来看看你在与系统交互时可能会用到的一些常用命令。

## 查看目录内容

@[code](@snippets/moving_around/ls_example.sh)

正如我们在其他章节中所看到的，[`ls`](/commands/docs/ls.md) 是一个用于查看路径内容的命令。Nu 将以表格的形式返回内容并供我们使用。

[`ls`](/commands/docs/ls.md) 命令还需要一个可选的参数，以改变你想查看的内容。例如，我们可以列出以 `.md` 结尾的文件：

@[code](@snippets/moving_around/ls_shallow_glob_example.sh)

## 通配符

上述可选参数 `*.md` 中的星号（\*）有时被称为通配符（wildcards）或 Glob，它让我们可以匹配任何东西。你可以把 glob `*.md` 理解为“匹配以 `.md` 结尾的任何文件名”。

最通用的通配符是 `*`，能够匹配所有路径。它经常和其他模式（pattern）组合使用，比如 `*.bak` 和 `temp*`。

Nu 也使用现代 Globs，它允许你访问更深的目录。比如，`ls **/*.md` 将递归地罗列当前目录下、所有后缀为 `.md` 的非隐藏文件:

@[code](@snippets/moving_around/ls_deep_glob_example.sh)

- `**` 表示“从这里开始的任何目录中”；
- `*.md` 表示“任意后缀为 `.md` 的文件名”（不包括隐藏文件，要额外添加 `--all, -a` 选项）；
- 除了 `*`，还有 `?` 用来匹配单个字符。比如，可以使用 `p???` 模式匹配 `port` 字符串。

结合 [字符串的处理](/zh-CN/book/working_with_strings.md) 能够写出更强大的模式。但是，请牢记 Nu 类似一种 [编译型语言](/zh-CN/book/thinking_in_nu.md#把-nushell-想象成一种编译型语言)。

## 改变当前目录

@[code](@snippets/book/moving_around/cd_example.nu)

要从当前目录换到一个新目录，我们使用 [`cd`](/commands/docs/cd.md) 命令。就像在其他 Shells 中一样，我们可以使用目录的名称，或者如果我们想进入父目录，我们可以使用 `..` 的快捷方式。

如果 [`cd`](/commands/docs/cd.md) 被省略，只给出一个路径本身，也可以改变当前工作目录：

@[code](@snippets/book/moving_around/cd_without_command_example.nu)

:::warning
用 [`cd`](/commands/docs/cd.md) 改变目录会改变 `PWD` 环境变量。这意味着目录的改变会保留到当前代码块中，一旦你退出这个代码块，你就会返回到以前的目录。你可以在 [环境篇](environment.md) 中了解更多关于这方面的信息。
:::

## 文件系统命令

Nu 还提供了一些基本的文件系统命令，并且可以跨平台工作。

我们可以使用 [`mv`](/commands/docs/mv.md) 命令将一个目录或文件从一个地方移动到另一个地方：

@[code](@snippets/moving_around/mv_example.sh)

我们可以通过 [`cp`](/commands/docs/cp.md) 命令把一个目录或文件从一个地方复制到另一个地方：

@[code](@snippets/moving_around/cp_example.sh)

:::danger
`cp` 在 Windows 系统，即使目标文件存在，命令也没有附加 `--force, -f`，目标文件仍会被覆盖！
:::

我们也可以通过 [`rm`](/commands/docs/rm.md) 命令删除一个目录或文件：

@[code](@snippets/moving_around/rm_example.sh)

这三个命令也可以使用我们先前看到的 [`ls`](/commands/docs/ls.md) 的 Glob 功能。

最后，我们可以使用 [`mkdir`](/commands/docs/mkdir.md) 命令创建一个新目录：

@[code](@snippets/moving_around/mkdir_example.sh)
