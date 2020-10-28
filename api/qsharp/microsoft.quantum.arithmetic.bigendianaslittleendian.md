---
uid: Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian
title: BigEndianAsLittleEndian 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndianAsLittleEndian
qsharp.summary: Converts a `BigEndian` qubit register to a `LittleEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 65074b74bcc952efc8b2a9473b2a010bdda42990
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699937"
---
# <a name="bigendianaslittleendian-function"></a>BigEndianAsLittleEndian 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


`BigEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `LittleEndian` qubit 寄存器。

```qsharp
function BigEndianAsLittleEndian (input : Microsoft.Quantum.Arithmetic.BigEndian) : Microsoft.Quantum.Arithmetic.LittleEndian
```


## <a name="input"></a>输入

### <a name="input--bigendian"></a>输入： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Qubit 寄存器 `BigEndian` 。



## <a name="output--littleendian"></a>输出： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit 寄存器 `LittleEndian` 。