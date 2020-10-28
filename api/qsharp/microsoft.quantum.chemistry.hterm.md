---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 7a18db539e55e4c1086b3d83725e3d4ba87f0117
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695868"
---
# <a name="hterm-user-defined-type"></a>HTerm 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

软件包 [](https://nuget.org/packages/)


从 c # 传递到 Q # 以表示 Hamiltonian 的术语的数据格式。
表示的数据的含义取决于接收数据的算法。

```qsharp

newtype HTerm = (Int[], Double[]);
```

