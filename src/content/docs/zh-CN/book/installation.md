# 安装 Nu

有很多方法可以获取并使用 Nu。你可以从我们的 [发布页面](https://github.com/nushell/nushell/releases) 下载预编译的二进制文件，也可以 [使用你喜欢的软件包管理器](https://repology.org/project/nushell/versions)，或者从源码构建。

Nushell 的主要二进制文件被命名为 `nu`（或 Windows 下的 `nu.exe`）。安装完成后你可以通过输入 `nu` 来启动它：

@[code](@snippets/installation/run_nu.sh)

## 预编译二进制包

Nu 二进制文件在 [GitHub 的 Release 页](https://github.com/nushell/nushell/releases) 发布，适用于 Linux、macOS 和 Windows。只需下载并解压二进制文件，然后将其复制到你的系统 `PATH` 上的某个位置即可。

## 软件包管理器

Nu 可以通过几个软件包管理器获得：

[![打包状态](https://repology.org/badge/vertical-allrepos/nushell.svg)](https://repology.org/project/nushell/versions)

对于 macOS 和 Linux，[Homebrew](https://brew.sh/) 是一个流行的选择（`brew install nushell`）。

对于 Windows 用户：

- [Winget](https://docs.microsoft.com/en-us/windows/package-manager/winget/) (`winget install nushell`)
- [Chocolatey](https://chocolatey.org/) (`choco install nushell`)
- [Scoop](https://scoop.sh/) (`scoop install nu`)

跨平台安装：

- [npm](https://www.npmjs.com/) (`npm install -g nushell` 请注意，以这种方式安装，nu 插件是不包含在内的)

## 从源码构建

你也可以从源代码构建 `Nu`。首先，你需要设置 Rust 工具链和它的依赖项。

### 安装编译器套件

为了使 Rust 能够正常工作，你需要在你的系统上安装一个兼容的编译器套件。以下是推荐的编译器套件：

- Linux：GCC 或 Clang
- macOS：Clang（安装 Xcode）
- Windows：MSVC（安装 [Visual Studio](https://visualstudio.microsoft.com/vs/community/) 或 [Visual Studio Build Tools](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2022))
  - 请确保安装 "用 C++ 进行桌面开发" 相关包
  - 任何 Visual Studio 版本都可以（社区版是免费的）

### 安装 Rust

如果我们的系统中还没有 Rust，最好的方法是通过 [rustup](https://rustup.rs/) 来安装它。Rustup 是一种管理 Rust 安装的工具，可以管理使用不同的 Rust 版本。

Nu 目前需要 **最新（1.66.1 或更高）的稳定** 版本的 Rust。最好的方法是让 `rustup` 为你找到正确的版本。当你第一次打开 `rustup` 时，它会询问你想安装哪个版本的 Rust：

@[code](@snippets/installation/rustup_choose_rust_version.sh)

一旦我们准备好了，我们就按 `1`，然后回车。

如果你不愿意通过 `rustup` 来安装 Rust，你也可以通过其他方法来安装它（比如从 Linux 发行版的软件包中）。只要确保安装 1.66.1 或更高版本的 Rust 即可。

### 依赖

#### Debian/Ubuntu

你将需要安装 "pkg-config" 和 "libssl-dev" 包：

@[code](@snippets/installation/install_pkg_config_libssl_dev.sh)

对于希望使用 "rawkey" 或 "clipboard" 可选功能的 Linux 用户，需要安装 "libx11-dev" 和 "libxcb-composite0-dev" 软件包。

@[code](@snippets/installation/use_rawkey_and_clipboard.sh)

#### 基于 RHEL 的发行版

你需要安装 "libxcb"、"openssl-devel" 和 "libX11-devel"：

@[code](@snippets/installation/install_rhel_dependencies.sh)

#### macOS

使用 [Homebrew](https://brew.sh/)，你需要通过如下方式安装 "openssl" 和 "cmake" ：

@[code](@snippets/installation/macos_deps.sh)

### 使用 [crates.io](https://crates.io) 进行构建

Nu 发行版会作为源码发布到流行的 Rust 包仓库 [crates.io](https://crates.io/)。这使得使用 `cargo` 构建并安装最新的 Nu 版本变得很容易：

@[code](@snippets/installation/cargo_install_nu.sh)

如此即可！`cargo` 工具将完成下载 Nu 及其源码依赖，构建并将其安装到 cargo bin 路径中，以便我们能够运行它。

如果你想要安装并支持 [dataframes](/zh-CN/book/dataframes.md) 功能，你可以在安装命令附上 `--features=dataframe`：

@[code](@snippets/installation/cargo_install_nu_more_features.sh)

### 从 GitHub 仓库构建

我们也可以从 GitHub 上的最新源码构建自己的 Nu。这让我们可以立即获得最新的功能和错误修复。首先，克隆源码仓库：

@[code](@snippets/installation/git_clone_nu.sh)

然后，我们可以用以下方式构建和运行 Nu：

@[code](@snippets/installation/build_nu_from_source.sh)

你也可以在**发布**模式下构建和运行 Nu，以获得更多的编译优化：

@[code](@snippets/installation/build_nu_from_source_release.sh)

熟悉 Rust 的人可能会问，如果 `run` 默认会构建，为什么我们还要做 `build` 和 `run` 这两个步骤？这是为了解决 Cargo 中新的 `default-run` 选项的缺陷，并确保所有插件都被构建，尽管这在将来可能不再需要。

## 设置登录 Shell（\*nix）

:::danger
Nu 仍在开发中，对于日常使用可能并不稳定！
:::

要设置登录 Shell，你可以使用 [`chsh`](https://linux.die.net/man/1/chsh) 命令。一些 Linux 发行版有一个位于 `/etc/shells` 的有效 Shell 列表，在 Nu 被列入白名单之前不允许改变 Shell。如果你没有更新 `shells` 文件，你可能会看到类似于下面的错误：

@[code](@snippets/installation/chsh_invalid_shell_error.sh)

你可以通过在 `shells` 文件中添加你的 Nu 二进制文件来把 Nu 添加到允许的 Shells 列表中。添加的路径可以用 `which nu` 命令找到，通常是 `$HOME/.cargo/bin/nu`。

## 设置默认的 Shell（Windows 终端）

如果你使用的是 [Windows Terminal](https://github.com/microsoft/terminal)，你可以通过添加如下内容到你的终端设置 `"profiles"`（JSON 文件）中来设置 `nu` 作为你的默认 Shell：

@[code](@snippets/installation/windows_terminal_default_shell.sh)

最后需要做的是将 `"defaultProfile"` 改为：

@[code](@snippets/installation/windows_change_default_profile.sh)

之后，`nu` 应该会在 **Windows Terminal** 启动时被加载。
