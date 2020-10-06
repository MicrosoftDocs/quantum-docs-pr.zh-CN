---
title: 使用 Microsoft 数字 Q# 库
description: 了解有关 Microsoft 量程数字库中可用的类型和操作的信息。
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.usage
no-loc:
- Q#
- $$v
ms.openlocfilehash: dfcb8e9e5a15d0881750d67cf58d7ad47cbecd3a
ms.sourcegitcommit: 897ace8b506adb2331e911ee5633dceced566174
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "91764129"
---
# <a name="using-the-numerics-library"></a>使用数字库

## <a name="overview"></a>概述

数字库包括三个组件

1. 带有整数添加器和比较运算符的**基本整数算法**
1. 基于基本功能构建的**高级整数功能**;它包括乘法、除法、反转等。 对于有符号和无符号整数。
1. 固定点**算术功能**，具有定点初始化、加法、乘法、倒数、多项式计算和度量。

所有这些组件均可使用单个语句进行访问 `open` ：
```qsharp
open Microsoft.Quantum.Arithmetic;
```

## <a name="types"></a>类型

数字库支持以下类型

1. **`LittleEndian`**：表示整数的 qubit 数组 `qArr : Qubit[]` ，其中 `qArr[0]` 表示最小有效位。
1. **`SignedLittleEndian`**：与相同 `LittleEndian` ，只不过它表示以两个补码形式存储的带符号整数。
1. **`FixedPoint`**：表示包含 qubit 数组的实数 `qArr2 : Qubit[]` 和一个二进制点位置 `pos` ，该位置计算二进制点左侧的二进制位数。 `qArr2` 的存储方式与相同 `SignedLittleEndian` 。

## <a name="operations"></a>操作

上述三种类型的操作都可用：

1. **`LittleEndian`**
    - 加法
    - 比较
    - 乘法
    - 平方
    - 带有余数) 的相除 (

1. **`SignedLittleEndian`**
    - 加法
    - 比较
    - 反转模2的补码
    - 乘法
    - 平方

1. **`FixedPoint`**
    - 准备/初始化到传统值
    - 加法 (传统常量或其他量子固定点) 
    - 比较
    - 乘法
    - 平方
    - 对偶函数和奇数函数进行了特殊化计算
    - 倒数 (1/x) 
    -  (传统双) 度量值

有关这些操作的详细信息和详细信息，请参阅 Q# 库参考文档，网址为 [docs.microsoft.com](https://docs.microsoft.com/quantum)

## <a name="sample-integer-addition"></a>示例：整数加法

作为一个基本示例，请考虑操作 $ $ \ket x\ket y\mapsto \ket x\ket {x + y} $ $，也就是说，使用 n-qubit 整数 $x $，n 或 (n + 1) -qubit register $y $ 作为输入，后者映射到 sum $ (x + y) $。 请注意，如果 $y $ 存储在 $n $ 位寄存器中，则 sum 计算为 "2 ^ n $"。

使用量程开发工具包，可以按如下所示应用此操作：
```qsharp
operation TestMyAddition(xValue : Int, yValue : Int, n : Int) : Unit {
    using ((xQubits, yQubits) = (Qubit[n], Qubit[n]))
    {
        let x = LittleEndian(xQubits); // define bit order
        let y = LittleEndian(yQubits);
        
        ApplyXorInPlace(xValue, x); // initialize values
        ApplyXorInPlace(yValue, y);
        
        AddI(x, y); // perform addition x+y into y
        
        // ... (use the result)
    }
}
```

## <a name="sample-evaluating-smooth-functions"></a>示例：计算平滑函数

若要在量程计算机上评估平滑功能，如 $ \sin (x) $，其中 $x $ 是一个量程 `FixedPoint` 号，量子开发工具包数字库将提供操作 `EvaluatePolynomialFxP` 和 `Evaluate[Even/Odd]PolynomialFxP` 。

第一种是，可 `EvaluatePolynomialFxP` 计算 $ $ P (x) = a_0 + a_1x + a_2x ^ 2 + \cdots + a_dx ^ d，$ $ 其中 $d $ 表示 *度*的多项式。 为此，所需的全部都是多项式系数 `[a_0,..., a_d]` (类型 `Double[]`) 、输入 `x : FixedPoint` 和输出 `y : FixedPoint` (最初为零) ：
```qsharp
EvaluatePolynomialFxP([1.0, 2.0], x, y);
```
结果（$P (x) = 1 + 2x $）将存储在中 `yFxP` 。

第二个、 `EvaluateEvenPolynomialFxP` 和第三个 `EvaluateOddPolynomialFxP` 分别是偶函数和奇数函数的专用化。 也就是说，对于偶数/奇数函数 $f (x) $ 和 $ $ P_ {偶数} (x) = a_0 + a_1 x ^ 2 + a_2 x ^ 4 + \cdots + a_d x ^ {2d}，$ $ $f (x) $，$P _ {偶数} (x) $ 或 $P _ {奇} (x) ： = x\cdot P_ {偶数} (x) $，这二者都是近似的。
在中 Q# ，这两种情况可以按如下方式进行处理：
```qsharp
EvaluateEvenPolynomialFxP([1.0, 2.0], x, y);
```
这会计算 $P _ { (x) = 1 + 2x ^ 2 $，和
```qsharp
EvaluateOddPolynomialFxP([1.0, 2.0], x, y);
```
这会计算 $P _ {奇数} (x) = x + 2x ^ 3 $。

## <a name="more-samples"></a>更多示例

可以在 [主示例存储库](https://github.com/Microsoft/Quantum)中找到更多示例。

若要开始，请克隆存储库并打开 `Numerics` 子文件夹：

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/numerics
```

然后， `cd` 加入其中一个示例文件夹，并通过

```bash
dotnet run
```
