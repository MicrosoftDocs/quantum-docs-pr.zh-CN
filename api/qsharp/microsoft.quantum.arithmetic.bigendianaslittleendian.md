---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: cb4cf68753468952c7541fae23250ed1fd1914f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843367"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="04a35-102">BigEndianAsLittleEndian 函数</span><span class="sxs-lookup"><span data-stu-id="04a35-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="04a35-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="04a35-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="04a35-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="04a35-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="04a35-105">`BigEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `LittleEndian` qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="04a35-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="04a35-106">输入</span><span class="sxs-lookup"><span data-stu-id="04a35-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="04a35-107">输入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="04a35-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="04a35-108">Qubit 寄存器 `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="04a35-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="04a35-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="04a35-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="04a35-110">Qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="04a35-110">Qubit register in `LittleEndian` format.</span></span>