---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: fd2744a8372793ad01d1391c035c64de1264d2f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699841"
---
# <a name="littleendian-user-defined-type"></a>LittleEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


注册以小字节序顺序编码无符号整数。 带有索引的 qubit 对 `0` 无符号整数的最小位进行编码。

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a>注解

`LittleEndian`与 `LE` 文档中的缩写相同。