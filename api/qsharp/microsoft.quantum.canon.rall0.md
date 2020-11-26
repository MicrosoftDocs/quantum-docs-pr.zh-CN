---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: bd1f796209a15f290315e55b872ae3b3e508a68b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205654"
---
# <a name="rall0-operation"></a><span data-ttu-id="5d577-102">RAll0 操作</span><span class="sxs-lookup"><span data-stu-id="5d577-102">RAll0 operation</span></span>

<span data-ttu-id="5d577-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="5d577-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="5d577-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d577-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d577-105">执行阶段移位操作。</span><span class="sxs-lookup"><span data-stu-id="5d577-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="5d577-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="5d577-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5d577-107">输入</span><span class="sxs-lookup"><span data-stu-id="5d577-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="5d577-108">阶段： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5d577-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5d577-109">阶段 $ \phi $ 应用于状态 $ \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="5d577-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="5d577-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="5d577-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="5d577-111">其状态将旋转 $R $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="5d577-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5d577-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5d577-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="5d577-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d577-113">See Also</span></span>

- [<span data-ttu-id="5d577-114">Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="5d577-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)