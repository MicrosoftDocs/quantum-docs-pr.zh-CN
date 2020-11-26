---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222773"
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