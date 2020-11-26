---
uid: Microsoft.Quantum.Canon.RAll1
title: RAll1 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RAll1
qsharp.summary: >-
  Performs a phase shift operation.

  $R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.
ms.openlocfilehash: 36e460f93b4349bc2e3da9bfb22cb0aa82ef1795
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205520"
---
# <a name="rall1-operation"></a><span data-ttu-id="b86de-102">RAll1 操作</span><span class="sxs-lookup"><span data-stu-id="b86de-102">RAll1 operation</span></span>

<span data-ttu-id="b86de-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b86de-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b86de-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b86de-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b86de-105">执行阶段移位操作。</span><span class="sxs-lookup"><span data-stu-id="b86de-105">Performs a phase shift operation.</span></span>

<span data-ttu-id="b86de-106">$R = \boldone- (1-e ^ {i \phi} ) \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="b86de-106">$R=\boldone-(1-e^{i \phi})\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>

```qsharp
operation RAll1 (phase : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b86de-107">输入</span><span class="sxs-lookup"><span data-stu-id="b86de-107">Input</span></span>

### <a name="phase--double"></a><span data-ttu-id="b86de-108">阶段： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b86de-108">phase : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b86de-109">阶段 $ \phi $ 应用于状态 $ \ket{1\cdots 1} \bra{1\cdots 1} $。</span><span class="sxs-lookup"><span data-stu-id="b86de-109">The phase $\phi$ applied to state $\ket{1\cdots 1}\bra{1\cdots 1}$.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="b86de-110">qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="b86de-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="b86de-111">其状态将旋转 $R $ 的寄存器。</span><span class="sxs-lookup"><span data-stu-id="b86de-111">The register whose state is to be rotated by $R$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b86de-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b86de-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

