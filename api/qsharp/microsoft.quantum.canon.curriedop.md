---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840766"
---
# <a name="curriedop-function"></a>CurriedOp 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回对两个输入的操作的扩充版本。

也就是说，假设有一个具有两个输入的操作，则此函数将应用咖喱的 isomorphism $f (x，y) \equiv f (x) # B4 y) $ 以返回一个输入的操作，该操作返回一个输入的操作。

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>输入

### <a name="op--tu--unit"></a>op： ( t，' U) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

其输入为成对的操作。



## <a name="output--t---u--unit"></a>输出：不 > "U => [单位](xref:microsoft.quantum.lang-ref.unit) 

一种操作，它接受对的第一个元素，并返回一个接受作为其输入的操作，该操作将原始操作的输入的第二个元素作为输入。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

成对定义的函数的第一个分量的类型。
### <a name="u"></a>' U

成对定义的函数的第二个分量的类型。

## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```