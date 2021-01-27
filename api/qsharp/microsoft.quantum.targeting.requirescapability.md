---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 5e0db49d6f73398ac36003eb0f44e3a6520b7f1e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855153"
---
# <a name="requirescapability-user-defined-type"></a><span data-ttu-id="720da-102">RequiresCapability 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="720da-102">RequiresCapability user defined type</span></span>

<span data-ttu-id="720da-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Targeting)</span><span class="sxs-lookup"><span data-stu-id="720da-103">Namespace: [Microsoft.Quantum.Targeting](xref:Microsoft.Quantum.Targeting)</span></span>

<span data-ttu-id="720da-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="720da-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="720da-105">编译器可识别的属性，用于使用其所需的运行时功能标记可调用的特性。</span><span class="sxs-lookup"><span data-stu-id="720da-105">Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a><span data-ttu-id="720da-106">命名项</span><span class="sxs-lookup"><span data-stu-id="720da-106">Named Items</span></span>

### <a name="level--string"></a><span data-ttu-id="720da-107">Level： [String](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="720da-107">Level : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="720da-108">可调用的所需的运行时功能级别的名称。</span><span class="sxs-lookup"><span data-stu-id="720da-108">The name of the runtime capability level required by the callable.</span></span>
### <a name="reason--string"></a><span data-ttu-id="720da-109">原因： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="720da-109">Reason : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="720da-110">此调用需要此运行时功能的原因的说明。</span><span class="sxs-lookup"><span data-stu-id="720da-110">A description of why the callable requires this runtime capability.</span></span>

## <a name="remarks"></a><span data-ttu-id="720da-111">备注</span><span class="sxs-lookup"><span data-stu-id="720da-111">Remarks</span></span>

<span data-ttu-id="720da-112">编译器会自动将此特性添加到 callables，除非该属性的一个实例已存在于可调用的上。</span><span class="sxs-lookup"><span data-stu-id="720da-112">This attribute is automatically added to callables by the compiler, unless an instance of this attribute already exists on the callable.</span></span> <span data-ttu-id="720da-113">在少数情况下不应使用它，除非编译器不会正确推断所需的功能。</span><span class="sxs-lookup"><span data-stu-id="720da-113">It should not be used except in rare cases where the compiler does not infer the required capability correctly.</span></span>

<span data-ttu-id="720da-114">下面是功能级别名称列表，按功能增加或降低限制顺序排列：</span><span class="sxs-lookup"><span data-stu-id="720da-114">Below is the list of capability level names, in order of increasing capabilities or decreasing restrictions:</span></span>

## `"BasicQuantumFunctionality"`

<span data-ttu-id="720da-115">度量结果不能比较是否相等。</span><span class="sxs-lookup"><span data-stu-id="720da-115">Measurement results cannot be compared for equality.</span></span>

## `"BasicMeasurementFeedback"`

<span data-ttu-id="720da-116">只能在操作中的 if 语句条件表达式中比较度量结果的相等性。</span><span class="sxs-lookup"><span data-stu-id="720da-116">Measurement results can be compared for equality only in if-statement conditional expressions in operations.</span></span> <span data-ttu-id="720da-117">依赖于结果的 if 语句块不能包含在块或 return 语句外声明的可变变量的 set 语句。</span><span class="sxs-lookup"><span data-stu-id="720da-117">The block of an if-statement that depends on a result cannot contain set statements for mutable variables declared outside the block, or return statements.</span></span>

## `"FullComputation"`

<span data-ttu-id="720da-118">无运行时限制。</span><span class="sxs-lookup"><span data-stu-id="720da-118">No runtime restrictions.</span></span> <span data-ttu-id="720da-119">可执行任何 Q # 程序。</span><span class="sxs-lookup"><span data-stu-id="720da-119">Any Q# program can be executed.</span></span>