---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: c89288e1eb421fd5abd8fcd5d9c12049aa47ac89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843077"
---
# <a name="littleendianasbigendian-function"></a>LittleEndianAsBigEndian 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


`LittleEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `BigEndian` qubit 寄存器。

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a>输入

### <a name="input--littleendian"></a>输入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit 寄存器 `LittleEndian` 。



## <a name="output--bigendian"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Qubit 寄存器 `BigEndian` 。