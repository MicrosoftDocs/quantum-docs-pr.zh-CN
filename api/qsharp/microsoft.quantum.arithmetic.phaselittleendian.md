---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: f1f792d62004a2765d4e63870f5a41a4377b0d34
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696599"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


QFT 基础中的小字节端无符号整数。

例如，如果 $ \ket{x} $ 为计算基础中的整数 $x $ 的小 endian 编码，则 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 中 $x $ 的编码。

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>注解

`PhaseLittleEndian`与 `PhaseLE` 文档中的缩写相同。

## <a name="see-also"></a>另请参阅

- [Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)