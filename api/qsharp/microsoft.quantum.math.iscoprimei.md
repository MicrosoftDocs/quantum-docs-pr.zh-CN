---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700533"
---
# <a name="iscoprimei-function"></a>IsCoprimeI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


如果 $a $ 和 $b $ 是共同质数，则返回 true; 否则返回 false。

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

正在测试的 primality 的第一个数字


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

正在测试的 primality 的第二个数字



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

如果 $a $ 和 $b $ 是共同质数 (例如，其最大公因数为 1 ) ，则为 True; 否则为 false。