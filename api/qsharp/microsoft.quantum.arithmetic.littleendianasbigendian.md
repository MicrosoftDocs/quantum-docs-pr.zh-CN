---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843077"
---
# <a name="littleendianasbigendian-function"></a><span data-ttu-id="30112-102">LittleEndianAsBigEndian 函数</span><span class="sxs-lookup"><span data-stu-id="30112-102">LittleEndianAsBigEndian function</span></span>

<span data-ttu-id="30112-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="30112-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="30112-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30112-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30112-105">`LittleEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `BigEndian` qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="30112-105">Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.</span></span>

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a><span data-ttu-id="30112-106">输入</span><span class="sxs-lookup"><span data-stu-id="30112-106">Input</span></span>

### <a name="input--littleendian"></a><span data-ttu-id="30112-107">输入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="30112-107">input : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="30112-108">Qubit 寄存器 `LittleEndian` 。</span><span class="sxs-lookup"><span data-stu-id="30112-108">Qubit register in `LittleEndian` format.</span></span>



## <a name="output--bigendian"></a><span data-ttu-id="30112-109">输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span><span class="sxs-lookup"><span data-stu-id="30112-109">Output : [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)</span></span>

<span data-ttu-id="30112-110">Qubit 寄存器 `BigEndian` 。</span><span class="sxs-lookup"><span data-stu-id="30112-110">Qubit register in `BigEndian` format.</span></span>