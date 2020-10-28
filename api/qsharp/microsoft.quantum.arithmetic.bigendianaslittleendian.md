---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699937"
---
# <a name="bigendianaslittleendian-function"></a><span data-ttu-id="83415-102">BigEndianAsLittleEndian 函数</span><span class="sxs-lookup"><span data-stu-id="83415-102">BigEndianAsLittleEndian function</span></span>

<span data-ttu-id="83415-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="83415-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="83415-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83415-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83415-105">`BigEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `LittleEndian` qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="83415-105">Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a><span data-ttu-id="83415-106">输入</span><span class="sxs-lookup"><span data-stu-id="83415-106">Input</span></span>

### <a name="input--bigendian"></a><span data-ttu-id="83415-107">输入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="83415-107">input : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="83415-108">Qubit 寄存器 `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="83415-108">Qubit register in `BigEndian` format.</span></span>



## <a name="output--littleendian"></a><span data-ttu-id="83415-109">输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="83415-109">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="83415-110">Qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="83415-110">Qubit register in `LittleEndian` format.</span></span>