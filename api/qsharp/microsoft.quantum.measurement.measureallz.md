---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: 4ac36a77b37f672859e61f3db89a43f4ca1fc93c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695326"
---
# <a name="measureallz-operation"></a><span data-ttu-id="16e15-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="16e15-102">MeasureAllZ operation</span></span>

<span data-ttu-id="16e15-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="16e15-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="16e15-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="16e15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="16e15-105">共同度量 Pauli Z 基础的 qubits 寄存器。</span><span class="sxs-lookup"><span data-stu-id="16e15-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="16e15-106">说明</span><span class="sxs-lookup"><span data-stu-id="16e15-106">Description</span></span>

<span data-ttu-id="16e15-107">度量 $Z \otimes Z \otimes \cdots \otimes Z $ 基础中的 qubits 的寄存器，表示整个寄存器的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="16e15-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="16e15-108">输入</span><span class="sxs-lookup"><span data-stu-id="16e15-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="16e15-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="16e15-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="16e15-110">要测量的寄存器。</span><span class="sxs-lookup"><span data-stu-id="16e15-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="16e15-111">输出： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="16e15-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="16e15-112">度量 $Z \otimes Z \otimes \cdots \otimes Z $ 的结果。</span><span class="sxs-lookup"><span data-stu-id="16e15-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>