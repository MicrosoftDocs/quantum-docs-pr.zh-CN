---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: JordanWignerInputState 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837692"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>JordanWignerInputState 用户定义的类型

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


从 c # 传递到 Q # 以表示初始状态准备的数据的格式由所表示的数据的含义决定。

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

