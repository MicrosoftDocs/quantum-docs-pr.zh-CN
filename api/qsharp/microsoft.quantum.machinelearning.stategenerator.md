---
uid: Microsoft.Quantum.MachineLearning.StateGenerator
title: StateGenerator 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: StateGenerator
qsharp.summary: Describes an operation that prepares a given input to a sequential classifier.
ms.openlocfilehash: e3026dbae7209acd41924c0038a6f9b2c4b41197
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700260"
---
# <a name="stategenerator-user-defined-type"></a><span data-ttu-id="a5ee8-102">StateGenerator 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a5ee8-102">StateGenerator user defined type</span></span>

<span data-ttu-id="a5ee8-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a5ee8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a5ee8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a5ee8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a5ee8-105">描述为顺序分类器准备给定输入的操作。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-105">Describes an operation that prepares a given input to a sequential classifier.</span></span>

```qsharp

newtype StateGenerator = (NQubits : Int, Prepare : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl));
```



## <a name="named-items"></a><span data-ttu-id="a5ee8-106">命名项</span><span class="sxs-lookup"><span data-stu-id="a5ee8-106">Named Items</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="a5ee8-107">NQubits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a5ee8-107">NQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a5ee8-108">在其上定义编码输入的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-108">The number of qubits on which the encoded input is defined.</span></span>
### <a name="prepare--littleendian--unit-adj--ctl"></a><span data-ttu-id="a5ee8-109">准备： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a5ee8-109">Prepare : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a5ee8-110">一种操作，用于在 qubits 的小 endian 寄存器上准备编码的输入 `NQubits` 。</span><span class="sxs-lookup"><span data-stu-id="a5ee8-110">An operation which prepares the encoded input on a little-endian register of `NQubits` qubits.</span></span>