---
uid: Microsoft.Quantum.ErrorCorrection.TableLookupRecovery
title: TableLookupRecovery 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: TableLookupRecovery
qsharp.summary: For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.
ms.openlocfilehash: c56a9bbb1db72b5ba03ee9976e648a59f651aa16
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695465"
---
# <a name="tablelookuprecovery-function"></a><span data-ttu-id="f2200-102">TableLookupRecovery 函数</span><span class="sxs-lookup"><span data-stu-id="f2200-102">TableLookupRecovery function</span></span>

<span data-ttu-id="f2200-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="f2200-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="f2200-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f2200-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f2200-105">对于给定的 qubits 寄存器上的 Pauli 操作表，此函数返回一个类型为的对象，该对象 `RecoveryFn` 包含对给定的 Pauli 操作数组执行表查找解码所需的所有信息。</span><span class="sxs-lookup"><span data-stu-id="f2200-105">For a given table of Pauli operations on a given register of qubits, this function returns an object of type `RecoveryFn` which contains all information needed to perform a table-lookup decoding with respect to the given array of Pauli operations.</span></span>

```qsharp
function TableLookupRecovery (table : Pauli[][]) : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="input"></a><span data-ttu-id="f2200-106">输入</span><span class="sxs-lookup"><span data-stu-id="f2200-106">Input</span></span>

### <a name="table--pauli"></a><span data-ttu-id="f2200-107">table： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="f2200-107">table : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f2200-108">在给定的 qubit 注册上操作的 Pauli 操作表</span><span class="sxs-lookup"><span data-stu-id="f2200-108">Table of Pauli operations that operate on a given qubit register</span></span>



## <a name="output--recoveryfn"></a><span data-ttu-id="f2200-109">输出： [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="f2200-109">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="f2200-110">类型为的对象 `RecoveryFn` ，即， `Syndrome -> Pauli[]` 与给定症状数组关联的映射对应 Pauli 更正操作。</span><span class="sxs-lookup"><span data-stu-id="f2200-110">An object of type `RecoveryFn`, i.e., a map `Syndrome -> Pauli[]` that associates with a given syndrome array a corresponding Pauli correction operation.</span></span>