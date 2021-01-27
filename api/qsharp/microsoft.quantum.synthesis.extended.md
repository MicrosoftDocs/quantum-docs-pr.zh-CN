---
uid: Microsoft.Quantum.Synthesis.Extended
title: 扩展函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855471"
---
# <a name="extended-function"></a>扩展函数

命名空间 [：](xref:Microsoft.Quantum.Synthesis)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


通过反转系数扩展色谱

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>输入

### <a name="spectrum--int"></a>色谱： [Int](xref:microsoft.quantum.lang-ref.int)[]

Spectral 系数



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

系数，后跟倒副本

## <a name="example"></a>示例

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```