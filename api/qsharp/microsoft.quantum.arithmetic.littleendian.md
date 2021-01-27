---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846568"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


注册以小字节序顺序编码无符号整数。 带有索引的 qubit 对 `0` 无符号整数的最小位进行编码。

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>备注

`LittleEndian`与 `LE` 文档中的缩写相同。