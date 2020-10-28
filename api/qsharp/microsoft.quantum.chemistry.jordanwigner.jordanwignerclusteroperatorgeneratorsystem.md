---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: c75dcd655dafb7048f61f4b07b852cc5f437275d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695752"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a><span data-ttu-id="87825-102">JordanWignerClusterOperatorGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="87825-102">JordanWignerClusterOperatorGeneratorSystem function</span></span>

<span data-ttu-id="87825-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="87825-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="87825-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87825-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87825-105">将描述的 Hamiltonian 转换 `JWOptimizedHTerms` 为用 `GeneratorSystem` `GeneratorIndex` 此文件中定义的约定表示的。</span><span class="sxs-lookup"><span data-stu-id="87825-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="87825-106">输入</span><span class="sxs-lookup"><span data-stu-id="87825-106">Input</span></span>

### <a name="data--jordanwignerinputstate"></a><span data-ttu-id="87825-107">数据： [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span><span class="sxs-lookup"><span data-stu-id="87825-107">data : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]</span></span>

<span data-ttu-id="87825-108">格式的 Hamiltonian 说明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="87825-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="87825-109">输出： [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="87825-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="87825-110">Hamiltonian 的表示形式 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="87825-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>