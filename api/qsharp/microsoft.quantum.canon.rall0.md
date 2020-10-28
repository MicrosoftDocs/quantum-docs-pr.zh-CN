---
uid: Microsoft.Quantum.Canon.RAll0
title: RAll0 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll0
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.
ms.openlocfilehash: 6185e66e08d2af3aa0b35791638820b4dcc5af35
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695977"
---
# <a name="rall0-operation"></a><span data-ttu-id="52991-102">RAll0 操作</span><span class="sxs-lookup"><span data-stu-id="52991-102">RAll0 operation</span></span>

<span data-ttu-id="52991-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="52991-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="52991-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="52991-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="52991-105">执行阶段移位操作。</span><span class="sxs-lookup"><span data-stu-id="52991-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="52991-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="52991-106">$R=\boldone-(1-e^{i \phi})\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>

```qsharp
operation RAll0 (phase : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="52991-107">输入</span><span class="sxs-lookup"><span data-stu-id="52991-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="52991-108">阶段： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="52991-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="52991-109">阶段 $ \phi $ 应用于状态 $ \ket{0\cdots 0} \bra{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="52991-109">The phase $\phi$ applied to state $\ket{0\cdots 0}\bra{0\cdots 0}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="52991-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="52991-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="52991-111">其状态将旋转 $R $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="52991-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="52991-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="52991-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="52991-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52991-113">See Also</span></span>

- [<span data-ttu-id="52991-114">Canon. RAll1</span><span class="sxs-lookup"><span data-stu-id="52991-114">Microsoft.Quantum.Canon.RAll1</span></span>](xref:Microsoft.Quantum.Canon.RAll1)