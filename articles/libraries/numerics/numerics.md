---
title: 使用数字库 |Microsoft Docs
description: 使用数字库
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
ms.openlocfilehash: ca24ff60cd9ae5077c7f4bae0012fe1180d7e6d4
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821025"
---
# <a name="using-the-numerics-library"></a>使用数字库

## <a name="overview"></a>概述

数字库包括三个组件

1. 带有整数添加器和比较运算符的**基本整数算法**
1. 基于基本功能构建的**高级整数功能**;它包括乘法、除法、反转等。 对于有符号和无符号整数。
1. 固定点**算术功能**，具有定点初始化、加法、乘法、倒数、多项式计算和度量。

所有这些组件均可使用单个 `open` 语句进行访问：
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>类型

数字库支持以下类型

1. **`LittleEndian`** ：表示整数的 qubit 数组 `qArr : Qubit[]`，其中 `qArr[0]` 表示最小有效位。
1. **`SignedLittleEndian`** ：与 `LittleEndian` 相同，不同之处在于，它表示存储在两个补码中的带符号整数。
1. **`FixedPoint`** ：表示包含 qubit 数组的实数 `qArr2 : Qubit[]` 和一个二进制点位置 `pos`，这将计算二进制点左端的二进制位数。 `qArr2` 的存储方式与 `SignedLittleEndian`相同。

## <a name="operations"></a>Operations

上述三种类型的操作都可用：

1. **`LittleEndian`**
    - 加
    - 比较
    - 乘
    - 平方
    - 相除（含余数）

1. **`SignedLittleEndian`**
    - 加
    - 比较
    - 反转模2的补码
    - 乘
    - 平方

1. **`FixedPoint`**
    - 准备/初始化到传统值
    - 加法（古典常量或其他量子固定点）
    - 比较
    - 乘
    - 平方
    - 对偶函数和奇数函数进行了特殊化计算
    - 互惠（1/x）
    - 度量值（古典双精度值）

有关这些操作的详细信息和详细信息，请参阅 Q # 库参考文档，网址为[docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>示例：整数加法

作为一个基本示例，请考虑操作 $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是说，使用 n-qubit 整数 $x $，n 或（n + 1）-qubit register $y $ 作为输入，后者映射到 sum $ （x + y） $。 请注意，如果 $y $ 存储在 $n $ 位寄存器中，则 sum 计算为 "2 ^ n $"。

使用量程开发工具包，可以按如下所示应用此操作：
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        x = LittleEndian(xQubits); // define bit order
        y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>示例：计算平滑函数

若要在量程计算机上评估平滑功能，如 $ \sin （x） $，其中 $x $ 是量程 `FixedPoint` 号，量子开发工具包数字库提供操作 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP`。

第一个 `EvaluatePolynomialFxP`允许对 $ $ P （x） = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ （其中 $d $ 表示*度数*）进行求值。 为此，所需的全部都是多项式系数 `[a_0,..., a_d]` （类型 `Double[]`）、输入 `x : FixedPoint` 和输出 `y : FixedPoint` （最初为零）：
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
结果（$P （x） = 1 + 2x $）将存储在 `yFxP`中。

第二个、`EvaluateEvenPolynomialFxP`和第三个 `EvaluateOddPolynomialFxP`是专用于偶函数和奇数函数的专用化。 也就是说，对于偶数/奇数函数 $f （x） $ 和 $ $ P_ {偶数} （x） = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f （x） $ 近似 $P _ {偶} （x） $ 或 $P _ {奇} （x）： = x\cdot P_ {偶} （x） $。
在 Q # 中，可以按如下所示处理这两种情况：
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
计算 $P _ {偶数} （x） = 1 + 2x ^ 2 $，和
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
这会计算 $P _ {奇数} （x） = x + 2x ^ 3 $。

## <a name="more-samples"></a>更多示例

可以在[主示例存储库](https://github.com/Microsoft/Quantum)中找到更多示例。

若要开始，请克隆存储库并打开 `Numerics` 子文件夹：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics
```

然后，`cd` 到其中一个示例文件夹，并通过

```bash
dotnet run
```
