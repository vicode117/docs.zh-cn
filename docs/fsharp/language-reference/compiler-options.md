---
title: 编译器选项
description: 使用F#编译器命令行选项来控制F#应用和库的编译。
ms.date: 12/10/2018
ms.openlocfilehash: ecaae538a5db2f5dfefa79cb8e7b8b51d39c440d
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628873"
---
# <a name="compiler-options"></a>编译器选项

本主题介绍编译器的编译器命令行选项F# fsc.exe。

还可以通过设置项目属性来控制编译环境。 对于以 .NET Core 为目标的项目，`.fsproj`中 `<OtherFlags>...</OtherFlags>` 的 "其他 flags" 属性用于指定额外的命令行选项。

## <a name="compiler-options-listed-alphabetically"></a>按字母顺序列出的编译器选项

下表显示了按字母顺序列出的编译器选项。 一些F#编译器选项类似于C#编译器选项。 如果是这种情况，则提供C#编译器选项主题的链接。

|编译器选项|说明|
|---------------|-----------|
|`-a filename.fs`|从指定的文件生成一个库。 此选项是 `--target:library filename.fs`的一种简短形式。|
|`--baseaddress:address`|指定要加载 DLL 的首选基址。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;baseaddress&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/2fdbz5xd.aspx)。|
|`--codepage:id`|指定在编译期间，如果所需的页不是系统的当前默认代码页，则要使用的代码页。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请参阅[ &#47;代码&#40;页&#35; C 编译器&#41;选项](../../csharp/language-reference/compiler-options/codepage-compiler-option.md)。|
|`--consolecolors`|指定错误和警告使用控制台上的颜色编码文本。|
|`--crossoptimize[+|-]`|启用或禁用跨模块优化。|
|<code>--delaysign[+&#124;-]</code>|仅使用强名称密钥的公共部分对程序集进行延迟签名。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;delaysign&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/ta1sxwy8.aspx)。|
|<code>--checked[+&#124;-]</code>|启用或禁用溢出检查的生成。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;checked&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/h25wtyxf.aspx)。|
|<code>--debug[+&#124;-]</code><br /><br /><code>-g[+&#124;-]</code><br /><br /><code>--debug:[full&#124;pdbonly]</code><br /><br /><code>-g: [full&#124;pdbonly]</code>|启用或禁用调试信息的生成，或指定要生成的调试信息的类型。 默认值为 full，这允许附加到正在运行的程序。 选择**pdbonly**可获取 pdb （程序数据库）文件中存储的有限调试信息。<br /><br />等效于具有C#相同名称的编译器选项。 有关详细信息，请参阅<br /><br />[调试 C&#35;选项&#41;。 &#47; &#40;](https://msdn.microsoft.com/library/8cw0bt21.aspx)|
|`--define:symbol`<br /><br />`-d:symbol`|定义在条件编译中使用的符号。|
|<code>--deterministic[+&#124;-]</code>|生成一个确定性程序集（包括模块版本 GUID 和时间戳）。 此选项不能与通配符版本号一起使用，并且仅支持嵌入调试类型和可移植调试类型|
|`--doc:xmldoc-filename`|指示编译器生成指定文件的 XML 文档注释。 有关更多信息，请参见 [XML Documentation](xml-documentation.md)。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;doc&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/3260k4x7.aspx)。|
|`--fullpaths`|指示编译器生成完全限定的路径。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;fullpaths&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/d315xc66.aspx)。|
|`--help`<br /><br />`-?`|显示用法信息，其中包括所有编译器选项的简短说明。|
|<code>--highentropyva[+&#124;-]</code>|启用或禁用高熵地址空间布局随机化（ASLR），这是一项增强的安全功能。 操作系统随机化内存中的位置，其中加载了应用程序的基础结构（如堆栈和堆）。 如果启用此选项，操作系统可以使用此随机选项在64位计算机上使用完整的64位地址空间。|
|`--keycontainer:key-container-name`|指定强名称密钥容器。|
|`--keyfile:filename`|指定用于对生成的程序集进行签名的公钥文件的名称。|
|`--lib:folder-name`<br /><br />`-I:folder-name`|指定要在其中搜索引用的程序集的目录。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;lib&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/s5bac5fx.aspx)。|
|`--linkresource:resource-info`|将指定的资源链接到程序集。 资源信息的格式 <code>filename[name[public&#124;private]]</code><br /><br />使用此选项链接单个资源是一种将整个资源文件与 `--resource` 选项一起嵌入的替代方法。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;linkresource&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/xawyf94k.aspx)。|
|`--mlcompatibility`|当你使用旨在与其他版本的 ML 兼容的功能时，将忽略出现的警告。|
|`--noframework`|禁用对 .NET Framework 程序集的默认引用。|
|`--nointerfacedata`|指示编译器忽略它通常添加到包含F#特定元数据的程序集的资源。|
|`--nologo`|启动编译器时不显示横幅文本。|
|`--nooptimizationdata`|指示编译器仅包括实现内联构造所必需的优化。 禁止跨模块内联，但提高二进制兼容性。|
|`--nowin32manifest`|指示编译器忽略默认的 Win32 清单。|
|`--nowarn:warning-number-list`|禁用按编号列出的特定警告。 用逗号分隔每个警告编号。 可以从编译输出中发现任何警告的警告编号。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;nowarn&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/7f28x9z3.aspx)。|
|<code>--optimize[+&#124;-][optimization-option-list]</code><br /><br /><code>-O[+&#124;-] [optimization-option-list]</code>|启用或禁用优化。 可以通过列出某些优化选项来有选择地将其禁用或启用。 这些是： `nojitoptimize`、`nojittracking`、`nolocaloptimize`、`nocrossoptimize`、`notailcalls`。|
|`--out:output-filename`<br /><br />`-o:output-filename`|指定已编译的程序集或模块的名称。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;out&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/bw3t50f3.aspx)。|
|`--pdb:pdb-filename`|命名输出调试 PDB （程序数据库）文件。 仅当同时启用了 `--debug` 时，此选项才适用。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;pdb&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/ms228625.aspx)。|
|`--platform:platform-name`|指定生成的代码将仅在指定的平台上运行（`x86`、`Itanium`或 `x64`）; 或者，如果选择了平台名称 `anycpu`，则指定生成的代码可以在任何平台上运行。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;平台&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/zekwfyz4.aspx)。|
|`--preferreduilang:lang`| 指定首选输出语言区域性名称（例如 `es-ES`、`ja-JP`）。 |
|`--quotations-debug`|指定应为从F#引号文本和反射定义派生的表达式发出额外的调试信息。 调试信息将添加到F#表达式树节点的自定义属性中。 请参阅[代码引用](code-quotations.md)和[CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)。|
|`--reference:assembly-filename`<br /><br />`-r:assembly-filename`|使F#或 .NET Framework 程序集中的代码可供正在编译的代码使用。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;reference&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/yabyz3h4.aspx)。|
|`--resource:resource-filename`|将托管资源文件嵌入到生成的程序集中。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;资源&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/c0tyye07.aspx)。|
|`--sig:signature-filename`|基于生成的程序集生成签名文件。 有关签名文件的详细信息，请参阅[签名](signature-files.md)。|
|`--simpleresolution`|指定应使用基于目录的 Mono 规则而不是 MSBuild 解析来解析程序集引用。 默认情况下，使用 MSBuild 解决方案，但在 Mono 下运行时除外。|
|`--standalone`|指定生成一个程序集，该程序集包含其所有依赖项，以便在不需要其他程序集（如F#库）的情况下单独运行。|
|`--staticlink:assembly-name`|以静态方式链接给定的程序集和依赖于此程序集的所有引用的 Dll。 使用程序集名称，而不是 DLL 名称。|
|`--subsystemversion`|指定生成的可执行文件要使用的 OS 子系统的版本。 将6.02 用于 Windows 8.1，6.01 用于 Windows 7，6.00 适用于 Windows Vista。 此选项仅适用于可执行文件，而不适用于 Dll，并且仅当你的应用程序依赖于特定操作系统版本上可用的特定安全功能时才需要使用。 如果使用此选项，并且用户尝试在较低版本的操作系统上执行应用程序，则会失败并出现一条错误消息。|
|<code>--tailcalls[+&#124;-]</code>|启用或禁用 tail IL 指令，这将导致为尾递归函数重用堆栈帧。 默认情况下该选项处于启用状态。|
|<code>--target:[exe&#124;winexe&#124;library&#124;module] filename</code>|指定生成的已编译代码的类型和文件名。<ul><li>`exe` 表示一个控制台应用程序。<br /></li><li>`winexe` 表示 Windows 应用程序，该应用程序与控制台应用程序不同，因为它未定义标准输入/输出流（stdin、stdout 和 stderr）。<br /></li><li>`library` 是没有入口点的程序集。<br /></li><li>`module` 是 .NET Framework 模块（. .netmodule），稍后可将其与其他模块组合到一个程序集中。<br /></li><ul/>此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;目标&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/6h25dztx.aspx)。|
|`--times`|显示编译的计时信息。|
|`--utf8output`|启用以 utf-8 编码格式输出编译器。|
|`--warn:warning-level`|设置警告等级（0到5）。 默认级别为3。 每个警告的严重性为一个级别。 级别5提供的警告比级别1多得多，但严重性更少。<br /><br />级别5警告为：21（运行时检查的递归使用）、22（`let rec` 按顺序计算）、45（完全抽象）和52（防御性复制）。 所有其他警告都是级别2。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;警告&#35; C 编译器&#41;选项](https://msdn.microsoft.com/library/13b90fz7.aspx)。|
|`--warnon:warning-number-list`|启用默认情况下可能关闭或被另一个命令行选项禁用的特定警告。 在F# 3.0 中，默认情况下仅关闭1182（未使用的变量）警告。|
|<code>--warnaserror[+&#124;-] [warning-number-list]</code>|启用或禁用将警告报告为错误的选项。 您可以提供要禁用或启用的特定警告编号。 稍后在命令行中的选项将覆盖命令行中的选项。 例如，若要指定不希望报告为错误的警告，请指定 `--warnaserror+` `--warnaserror-:warning-number-list`。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;warnaserror&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/406xhdz3.aspx)。|
|`--win32manifest:manifest-filename`|将 Win32 清单文件添加到编译。 此编译器选项等效于同名的C#编译器选项。 有关详细信息，请[ &#47;参阅&#40;win32manifest&#35; C 编译器&#41;Options](https://msdn.microsoft.com/library/bb545961.aspx)。|
|`--win32res:resource-filename`|将 Win32 资源文件添加到编译。<br /><br />此编译器选项等效于同名的C#编译器选项。 有关详细信息，请参阅[ &#47;win32res&#40;（&#35;C）编译器&#41;选项](https://msdn.microsoft.com/library/8f2f5x2e.aspx)。|

## <a name="related-articles"></a>相关文章

|标题|说明|
|-----|-----------|
|[F# Interactive 选项](fsharp-interactive-options.md)|介绍F#解释器（fsi.exe）支持的命令行选项。|
|[项目属性引用](/visualstudio/ide/reference/project-properties-reference)|介绍项目的 UI，包括提供生成选项的项目属性页。|
