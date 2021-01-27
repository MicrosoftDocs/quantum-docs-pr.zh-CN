---
uid: Microsoft.Quantum.Arithmetic.PhaseLittleEndian
title: PhaseLittleEndian 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: PhaseLittleEndian
qsharp.summary: >-
  Little-endian unsigned integers in QFT basis.

  For example, if $\ket{x}$ is the little-endian encoding of the integer $x$ in the computational basis, then $\operatorname{QFTLE} \ket{x}$ is the encoding of $x$ in the QFT basis.
ms.openlocfilehash: 59df1db31090f875ccd261fe6cc43995ba57b963
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843001"
---
# <a name="phaselittleendian-user-defined-type"></a>PhaseLittleEndian 用户定义的类型

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


QFT 基础中的小字节端无符号整数。

例如，如果 $ \ket{x} $ 为计算基础中的整数 $x $ 的小 endian 编码，则 $ \operatorname{QFTLE} \ket{x} $ 是 QFT 中 $x $ 的编码。

```qsharp

newtype PhaseLittleEndian = (Qubit[]);
```



## <a name="remarks"></a>备注

`PhaseLittleEndian`与 `PhaseLE` 文档中的缩写相同。

## <a name="see-also"></a>另请参阅

- [Canon. QFT](xref:Microsoft.Quantum.Canon.QFT)
- [Canon. QFTLE](xref:Microsoft.Quantum.Canon.QFTLE)