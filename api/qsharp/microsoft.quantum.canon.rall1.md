---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 45892f9811faf56d7b9a0eb34e4bde0a32d5586d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695976"
---
# <a name="rall1-operation"></a><span data-ttu-id="95d5f-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="95d5f-102">RAll1 operation</span></span>

<span data-ttu-id="95d5f-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="95d5f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="95d5f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95d5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95d5f-105">执行阶段移位操作。</span><span class="sxs-lookup"><span data-stu-id="95d5f-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="95d5f-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="95d5f-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="95d5f-107">输入</span><span class="sxs-lookup"><span data-stu-id="95d5f-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="95d5f-108">阶段： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="95d5f-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="95d5f-109">阶段 $ \phi $ 应用于状态 $ \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="95d5f-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="95d5f-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="95d5f-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="95d5f-111">其状态将旋转 $R $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="95d5f-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95d5f-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95d5f-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

