---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695741"
---
# <a name="jordanwignerinputstate-user-defined-type"></a><span data-ttu-id="41930-102">JordanWignerInputState 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="41930-102">JordanWignerInputState user defined type</span></span>

<span data-ttu-id="41930-103">命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="41930-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="41930-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41930-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41930-105">从 c # 传递到 Q # 以表示初始状态准备的数据的格式由所表示的数据的含义决定。</span><span class="sxs-lookup"><span data-stu-id="41930-105">Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.</span></span>

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```
