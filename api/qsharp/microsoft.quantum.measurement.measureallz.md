---
uid: Microsoft.Quantum.Measurement.MeasureAllZ
title: MeasureAllZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureAllZ
qsharp.summary: Jointly measures a register of qubits in the Pauli Z basis.
ms.openlocfilehash: cb3c7cab33efb612bbf5da3b51d2df5d1b8ba1df
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854674"
---
# <a name="measureallz-operation"></a><span data-ttu-id="5080c-102">MeasureAllZ 操作</span><span class="sxs-lookup"><span data-stu-id="5080c-102">MeasureAllZ operation</span></span>

<span data-ttu-id="5080c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="5080c-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="5080c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5080c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5080c-105">共同度量 Pauli Z 基础的 qubits 寄存器。</span><span class="sxs-lookup"><span data-stu-id="5080c-105">Jointly measures a register of qubits in the Pauli Z basis.</span></span>

```qsharp
operation MeasureAllZ (register : Qubit[]) : Result
```


## <a name="description"></a><span data-ttu-id="5080c-106">说明</span><span class="sxs-lookup"><span data-stu-id="5080c-106">Description</span></span>

<span data-ttu-id="5080c-107">度量 $Z \otimes Z \otimes \cdots \otimes Z $ 基础中的 qubits 的寄存器，表示整个寄存器的奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="5080c-107">Measures a register of qubits in the $Z \otimes Z \otimes \cdots \otimes Z$ basis, representing the parity of the entire register.</span></span>

## <a name="input"></a><span data-ttu-id="5080c-108">输入</span><span class="sxs-lookup"><span data-stu-id="5080c-108">Input</span></span>

### <a name="register--qubit"></a><span data-ttu-id="5080c-109">register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5080c-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5080c-110">要测量的寄存器。</span><span class="sxs-lookup"><span data-stu-id="5080c-110">The register to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="5080c-111">输出：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="5080c-111">Output : __invalid<Result>__</span></span>

<span data-ttu-id="5080c-112">度量 $Z \otimes Z \otimes \cdots \otimes Z $ 的结果。</span><span class="sxs-lookup"><span data-stu-id="5080c-112">The result of measuring $Z \otimes Z \otimes \cdots \otimes Z$.</span></span>