---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: c3e48cb5dde36b694a5b16f25333cf0dad6c0f61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695729"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="ca5da-102">OptimizedBlockEncodingGeneratorSystem 函数</span><span class="sxs-lookup"><span data-stu-id="ca5da-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="ca5da-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ca5da-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ca5da-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca5da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca5da-105">将描述的 Hamiltonian 转换 `JWOptimizedHTerms` 为 `GeneratorSystem` Pauli 的表示形式 `GeneratorIndex` 。</span><span class="sxs-lookup"><span data-stu-id="ca5da-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ca5da-106">输入</span><span class="sxs-lookup"><span data-stu-id="ca5da-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="ca5da-107">数据： [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="ca5da-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="ca5da-108">格式的 Hamiltonian 说明 `JWOptimizedHTerms` 。</span><span class="sxs-lookup"><span data-stu-id="ca5da-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="ca5da-109">输出： [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ca5da-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="ca5da-110">Hamiltonian 的表示形式 `GeneratorSystem` 。</span><span class="sxs-lookup"><span data-stu-id="ca5da-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>