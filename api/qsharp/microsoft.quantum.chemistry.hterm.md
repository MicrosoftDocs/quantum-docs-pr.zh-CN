---
uid: Microsoft.Quantum.Chemistry.HTerm
title: HTerm 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851790"
---
# <a name="hterm-user-defined-type"></a>HTerm 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Chemistry)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


从 c # 传递到 Q # 以表示 Hamiltonian 的术语的数据格式。
表示的数据的含义取决于接收数据的算法。

```qsharp

newtype HTerm = (Int[], Double[]);
```

