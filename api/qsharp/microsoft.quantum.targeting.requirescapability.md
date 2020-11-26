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
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="a5d67-102">RequiresCapability 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a5d67-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="a5d67-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="a5d67-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="a5d67-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a5d67-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a5d67-105">编译器可识别的属性，用于使用其所需的运行时功能标记可调用的特性。</span><span class="sxs-lookup"><span data-stu-id="a5d67-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="a5d67-106">命名项</span><span class="sxs-lookup"><span data-stu-id="a5d67-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="a5d67-107">Level： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a5d67-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a5d67-108">可调用的所需的运行时功能级别的名称。</span><span class="sxs-lookup"><span data-stu-id="a5d67-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="a5d67-109">原因： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a5d67-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a5d67-110">此调用需要此运行时功能的原因的说明。</span><span class="sxs-lookup"><span data-stu-id="a5d67-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a5d67-111">备注</span><span class="sxs-lookup"><span data-stu-id="a5d67-111">Remarks</span></span>

<span data-ttu-id="a5d67-112">编译器会自动将此特性添加到 callables，除非该属性的一个实例已存在于可调用的上。</span><span class="sxs-lookup"><span data-stu-id="a5d67-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="a5d67-113">在少数情况下不应使用它，除非编译器不会正确推断所需的功能。</span><span class="sxs-lookup"><span data-stu-id="a5d67-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="a5d67-114">下面是功能级别名称列表，按功能增加或降低限制顺序排列：</span><span class="sxs-lookup"><span data-stu-id="a5d67-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="a5d67-115">度量结果不能比较是否相等。</span><span class="sxs-lookup"><span data-stu-id="a5d67-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="a5d67-116">只能在操作中的 if 语句条件表达式中比较度量结果的相等性。</span><span class="sxs-lookup"><span data-stu-id="a5d67-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="a5d67-117">依赖于结果的 if 语句块不能包含在块或 return 语句外声明的可变变量的 set 语句。</span><span class="sxs-lookup"><span data-stu-id="a5d67-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="a5d67-118">无运行时限制。</span><span class="sxs-lookup"><span data-stu-id="a5d67-118">No runtime restrictions.</span></span> <span data-ttu-id="a5d67-119">可执行任何 Q # 程序。</span><span class="sxs-lookup"><span data-stu-id="a5d67-119">Any Q# program can be executed.</span></span>