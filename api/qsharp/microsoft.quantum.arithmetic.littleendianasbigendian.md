---
uid: Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian
title: LittleEndianAsBigEndian 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndianAsBigEndian
qsharp.summary: Converts a `LittleEndian` qubit register to a `BigEndian` qubit register by reversing the qubit ordering.
ms.openlocfilehash: 8c2e6150a839bb0cd4c311c821b78a080288cd22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699833"
---
# <a name="littleendianasbigendian-function"></a>LittleEndianAsBigEndian 函数

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


`LittleEndian`通过反转 qubit 排序将 qubit 寄存器转换为 `BigEndian` qubit 寄存器。

```qsharp
function LittleEndianAsBigEndian (input : Microsoft.Quantum.Arithmetic.LittleEndian) : Microsoft.Quantum.Arithmetic.BigEndian
```


## <a name="input"></a>输入

### <a name="input--littleendian"></a>输入： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Qubit 寄存器 `LittleEndian` 。



## <a name="output--bigendian"></a>输出： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Qubit 寄存器 `BigEndian` 。