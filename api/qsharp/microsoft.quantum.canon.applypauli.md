---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: b3557c6d8b5a90019f6d4cfa7b405475a3ab39fb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844740"
---
# <a name="applypauli-operation"></a>ApplyPauli 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定多 qubit Pauli 运算符，将相应的操作应用于寄存器。

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]

多 qubit Pauli 运算符，表示为单个 qubit Pauli 运算符的数组。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册以在上应用给定的 Pauli 操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

以下项是等效的：

```qsharp
ApplyPauli([PauliY, PauliZ, PauliX], target);
```

和

```qsharp
Y(target[0]);
Z(target[1]);
X(target[2]);
```