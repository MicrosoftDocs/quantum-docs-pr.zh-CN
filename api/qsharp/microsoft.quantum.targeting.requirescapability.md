---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 0d9e4eb294b3ce91058c204d5dba37ea29b4ac28
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231001"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Targeting)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


编译器可识别的属性，用于使用其所需的运行时功能标记可调用的特性。

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>命名项

### <a name="level--string"></a>Level： [String](xref:microsoft.quantum.lang-ref.string)

可调用的所需的运行时功能级别的名称。
### <a name="reason--string"></a>原因： [字符串](xref:microsoft.quantum.lang-ref.string)

此调用需要此运行时功能的原因的说明。

## <a name="remarks"></a>备注

编译器会自动将此特性添加到 callables，除非该属性的一个实例已存在于可调用的上。 在少数情况下不应使用它，除非编译器不会正确推断所需的功能。

下面是功能级别名称列表，按功能增加或降低限制顺序排列：

## `"BasicQuantumFunctionality"`

度量结果不能比较是否相等。

## `"BasicMeasurementFeedback"`

只能在操作中的 if 语句条件表达式中比较度量结果的相等性。 依赖于结果的 if 语句块不能包含在块或 return 语句外声明的可变变量的 set 语句。

## `"FullComputation"`

无运行时限制。 可执行任何 Q # 程序。