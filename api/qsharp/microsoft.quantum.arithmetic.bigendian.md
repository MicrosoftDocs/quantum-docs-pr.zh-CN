---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 64590606f7c36e0598a9d29c5c6a7ba6d6451aa1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699945"
---
# <a name="bigendian-user-defined-type"></a>BigEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


注册以大字节序顺序编码无符号整数。 带有索引的 qubit 对 `0` 无符号整数的最高位进行编码。

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a>注解

`BigEndian`与 `BE` 文档中的缩写相同。