---
title: 属性设计
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, properties
- properties [.NET Framework], design guidelines
ms.assetid: 127cbc0c-cbed-48fd-9c89-7c5d4f98f163
ms.openlocfilehash: 8b6570b1b7c292729b78f2fe52f24f73319efe6c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743665"
---
# <a name="property-design"></a>属性设计
虽然属性在技术上与方法非常相似，但它们的使用场景却截然不同。 属性应被视为聪明的字段。 它们兼具字段的调用语法和方法的灵活性。

 如果调用方不能更改属性的值，✔️确实要创建只获得属性。

 请记住，如果属性的类型是可变的引用类型，则即使属性为 get-only，也可以更改属性值。

 ❌ 不要提供仅限集的属性或属性，其中 setter 具有比 getter 更广泛的可访问性。

 例如，不要使用具有公共 setter 和受保护的 getter 的属性。

 如果无法提供属性 getter，请将该功能实现为方法。 请考虑使用 `Set` 启动方法名称，并遵循您命名的属性。 例如，<xref:System.AppDomain> 具有一个名为 `SetCachePath` 的方法，而不是将仅限集的属性称为 `CachePath`。

 ✔️为所有属性提供合理的默认值，确保默认值不会导致安全漏洞或极低效的代码。

 ✔️允许以任意顺序设置属性，即使这样会导致对象的临时无效状态。

 在给定同一对象上的其他属性的值的情况下，一个属性的某些值可能是无效的，这是导致两个或多个属性相关联的一种常见况。 在这种情况下，无效状态导致的异常应该会推迟，直到对象实际将这些相关属性一起使用。

 如果属性 setter 引发异常，✔️保留以前的值。

 ❌ 避免从属性 getter 引发异常。

 属性 getter 应该是简单的操作，不应该有任何前置条件。 如果某个 getter 可能会引发异常，则应该将其重新设计为方法。 请注意，此规则不适用于索引器，因为我们确实会因验证参数而导致异常。

### <a name="indexed-property-design"></a>索引属性设计
 索引属性是一个特殊属性，可以具有参数，并且可以使用与数组索引类似的特殊语法进行调用。

 索引属性通常称为索引器。 索引器应仅用于提供对逻辑集合中项目的访问的 API。 例如，字符串是字符的集合，添加 <xref:System.String?displayProperty=nameWithType> 上的索引器以访问其字符。

 ✔️考虑使用索引器来提供对存储在内部数组中的数据的访问。

 ✔️考虑为表示项集合的类型提供索引器。

 ❌ 避免使用具有多个参数的索引属性。

 如果设计需要多个参数，请重新考虑该属性是否真正代表逻辑集合的访问者。 如果不是，请改用方法。 请考虑 `Get` 或 `Set`中启动方法名称。

 ❌ 避免使用 <xref:System.Int32?displayProperty=nameWithType>、<xref:System.Int64?displayProperty=nameWithType>、<xref:System.String?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType>或枚举以外的参数类型的索引器。

 如果设计需要其他类型的参数，请仔细重新评估 API 是否真正代表逻辑集合的访问者。 如果不是，请使用方法。 请考虑 `Get` 或 `Set`中启动方法名称。

 ✔️使用索引属性的名称 `Item`，除非有明显更好的名称（例如，请参阅 `System.String`中的 <xref:System.String.Chars%2A> 属性）。

 在 C# 中，索引器默认名称为 Item。 <xref:System.Runtime.CompilerServices.IndexerNameAttribute> 可用于自定义此名称。

 ❌ 不提供在语义上等效的索引器和方法。

 ❌ 在一种类型中不提供多个重载索引器系列。

 此准则由 C# 编译器强制执行。

 ❌ 不使用非默认的索引属性。

 此准则由 C# 编译器强制执行。

### <a name="property-change-notification-events"></a>属性更改通知事件
 有时，提供用于通知用户属性值更改的事件是很有用的。 例如，`System.Windows.Forms.Control` 在其 `Text` 属性的值发生更改后引发 `TextChanged` 事件。

 ✔️在修改高级 Api （通常是设计器组件）中的属性值时，请考虑引发更改通知事件。

 如果具备可让用户知道对象的属性何时发生变化的有效方案，则该对象应该该属性引发更改通知事件。

 但是，可能并不值得为基础类型或集合等低级 API 引发此类事件。 例如，当向列表中添加新项并且 `Count` 属性发生更改时，<xref:System.Collections.Generic.List%601> 不会引发此类事件。

 ✔️考虑当属性的值通过外部强制更改时引发更改通知事件。

 如果属性值通过某种外力（通过调用对象上的方法以外的方式）发生更改。则引发事件向开发人员指示值正在更改并已更改。 一个很好的示例是文本框控件的 `Text` 属性。 当用户在 `TextBox`中键入文本时，属性值将自动更改。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [成员设计准则](../../../docs/standard/design-guidelines/member.md)
- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
