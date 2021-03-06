---
title: 任务并行库 (TPL)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- .NET, concurrency in
- .NET, parallel programming in
- Parallel Programming
ms.assetid: b8f99f43-9104-45fd-9bff-385a20488a23
ms.openlocfilehash: 487fe48462803ac19318f450f2576989f196a9be
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "73139955"
---
# <a name="task-parallel-library-tpl"></a>任务并行库 (TPL)
任务并行库 (TPL) 是 <xref:System.Threading?displayProperty=nameWithType> 和 <xref:System.Threading.Tasks?displayProperty=nameWithType> 空间中的一组公共类型和 API。 TPL 的目的是通过简化将并行和并发添加到应用程序的过程来提高开发人员的工作效率。 TPL 动态缩放并发的程度以最有效地使用所有可用的处理器。 此外，TPL 还处理工作分区、<xref:System.Threading.ThreadPool> 上的线程调度、取消支持、状态管理以及其他低级别的细节操作。 通过使用 TPL，你可以在将精力集中于程序要完成的工作，同时最大程度地提高代码的性能。  
  
 自 .NET Framework 4 起，首选 TPL 编写多线程代码和并行代码。 但是，并不是所有代码都适合并行化；例如，如果某个循环在每次迭代时只执行少量工作，或它在很多次迭代时都不运行，那么并行化的开销可能导致代码运行更慢。 此外，像任何多线程代码一样，并行化会增加程序执行的复杂性。 尽管 TPL 简化了多线程方案，但我们建议你对线程处理概念（例如，锁、死锁和争用条件）进行基本的了解，以便能够有效地使用 TPL。  
  
## <a name="related-topics"></a>相关主题  
  
|标题|说明|  
|-|-|  
|[数据并行](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)|描述如何创建并行的 `for` 和 `foreach` 循环（在 Visual Basic 中为 `For` 和 `For Each`）。|  
|[基于任务的异步编程](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)|描述如何通过使用 <xref:System.Threading.Tasks.Parallel.Invoke%2A?displayProperty=nameWithType> 隐式创建和运行任务，或通过直接使用 <xref:System.Threading.Tasks.Task> 对象显式创建和运行任务。|  
|[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)|描述如何使用 TPL 数据流库中的数据流组件处理多项运算，这些运算必须彼此通信，或在数据可用时处理数据。|  
|[将 TPL 和其他异步模式结合使用](../../../docs/standard/parallel-programming/using-tpl-with-other-asynchronous-patterns.md)|描述如何将 TPL 与 .NET 中的其他异步模式一起使用。|  
|[数据和任务并行的潜在问题](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)|描述一些常见缺陷以及如何避免它们。|  
|[并行 LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|描述如何使用 LINQ 查询实现数据并行化。|  
|[并行编程](../../../docs/standard/parallel-programming/index.md)|.NET 并行编程的顶级节点。|  
  
## <a name="see-also"></a>另请参阅

- [使用 .NET Framework 进行并行编程的示例](https://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
