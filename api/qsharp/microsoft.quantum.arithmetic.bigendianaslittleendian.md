---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 5f5d7dc6e08a13fbdc45f9d11c93c29cfcf90bf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223623"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


`BigEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `LittleEndian` qubit 寄存器。

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>输入

### <a name="input--bigendian"></a>输入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Qubit 寄存器 `BigEndian` 。



## <a name="output--littleendian"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit 寄存器 `LittleEndian` 。