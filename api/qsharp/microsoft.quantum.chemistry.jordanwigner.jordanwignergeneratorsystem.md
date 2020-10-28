---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 30da4129278f83633c2cc76489c7c81304a1f565
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695742"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="efd4f-102">JordanWignerGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="efd4f-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="efd4f-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="efd4f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="efd4f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="efd4f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="efd4f-105">将描述的 Hamiltonian 转换 `JWOptimizedHTerms` 为用 `GeneratorSystem` `GeneratorIndex` 此文件中定义的约定表示的。</span><span class="sxs-lookup"><span data-stu-id="efd4f-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="efd4f-106">输入</span><span class="sxs-lookup"><span data-stu-id="efd4f-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="efd4f-107">数据： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="efd4f-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="efd4f-108">格式的 Hamiltonian 说明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="efd4f-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="efd4f-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="efd4f-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="efd4f-110">Hamiltonian 的表示形式 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="efd4f-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>