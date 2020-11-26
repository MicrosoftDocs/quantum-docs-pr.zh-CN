---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 8ea1aefa46a7224ef199baf68f2d6ab2d563e3a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223657"
---
# <a name="bigendian-user-defined-type"></a>BigEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


注册以大字节序顺序编码无符号整数。 带有索引的 qubit 对 `0` 无符号整数的最高位进行编码。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>备注

`BigEndian`与 `BE` 文档中的缩写相同。