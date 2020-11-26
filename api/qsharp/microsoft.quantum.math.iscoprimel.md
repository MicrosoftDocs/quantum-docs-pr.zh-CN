---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: c78e995801f67822cf98104a7319093d853b6afe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228128"
---
# <a name="iscoprimel-function"></a>IsCoprimeL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果 $a $ 和 $b $ 是共同质数，则返回 true; 否则返回 false。

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

正在测试的 primality 的第一个数字


### <a name="b--bigint"></a>b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

正在测试的 primality 的第二个数字



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果 $a $ 和 $b $ 是共同质数 (例如，其最大公因数为 1 ) ，则为 True; 否则为 false。