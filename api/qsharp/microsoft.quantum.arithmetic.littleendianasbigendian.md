---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699833"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="c8eda-102">LittleEndianAsBigEndian 函数</span><span class="sxs-lookup"><span data-stu-id="c8eda-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="c8eda-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c8eda-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c8eda-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8eda-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8eda-105">`LittleEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `BigEndian` qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="c8eda-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="c8eda-106">输入</span><span class="sxs-lookup"><span data-stu-id="c8eda-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="c8eda-107">输入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="c8eda-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="c8eda-108">Qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="c8eda-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="c8eda-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="c8eda-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="c8eda-110">Qubit 寄存器 `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="c8eda-110">Qubit register in `BigEndian` format.</span></span>