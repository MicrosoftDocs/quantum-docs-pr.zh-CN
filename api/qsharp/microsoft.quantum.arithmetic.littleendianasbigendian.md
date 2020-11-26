---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 3cdcd18f06bf43d109c9f5e69f319f9d33b96bfc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222739"
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