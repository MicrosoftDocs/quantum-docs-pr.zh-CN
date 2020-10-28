---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 171bbe28ce8f10ca4b213a94b23f8c049546e3bf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695714"
---
# <a name="selectz-operation"></a><span data-ttu-id="81a9e-102">SelectZ 操作</span><span class="sxs-lookup"><span data-stu-id="81a9e-102">SelectZ operation</span></span>

<span data-ttu-id="81a9e-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="81a9e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="81a9e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81a9e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81a9e-105">一种单一 $U $，它对索引状态 $ \ket{p} $ $p 上 $Z 的 qubits $</span><span class="sxs-lookup"><span data-stu-id="81a9e-105">A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$.</span></span> <span data-ttu-id="81a9e-106">也就是说，$ $ \begin{align} U\ket {p} \ 票证 {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="81a9e-106">That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$</span></span>

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="81a9e-107">输入</span><span class="sxs-lookup"><span data-stu-id="81a9e-107">Input</span></span>

### <a name="indexregister--littleendian"></a><span data-ttu-id="81a9e-108">indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="81a9e-108">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="81a9e-109">此寄存器的状态 $ \ket{p} $ 确定应用 $Z $ 的 qubit。</span><span class="sxs-lookup"><span data-stu-id="81a9e-109">The state $\ket{p}$ of this register determines the qubit on which $Z$ is applied.</span></span>


### <a name="targetregister--qubit"></a><span data-ttu-id="81a9e-110">targetRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="81a9e-110">targetRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="81a9e-111">注册应用 Pauli 运算符的 qubits。</span><span class="sxs-lookup"><span data-stu-id="81a9e-111">Register of qubits on which the Pauli operators are applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="81a9e-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="81a9e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

