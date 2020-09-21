---
title: 用 QDK 设计自己的分类器
description: 了解为量子线路中心分类器设计线路模型的基本概念。
author: geduardo
ms.author: v-edsanc
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3515279dd4d03b2a512035af0b13e084dd91f9dc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835700"
---
# <a name="design-your-own-classifier"></a>设计自己的分类器

在本指南中，你将了解针对量程线路中心分类器的线路模型设计的基本概念。

与经典深度学习一样，没有用于选择特定体系结构的一般规则。 与其他体系结构相比，某些体系结构的性能更好。 但在设计线路时，有一些概念可能会很有用：

- 大量参数表示更灵活的模型，这种模型可能适用于绘制复杂的分类边界，但也可能更容易被过度拟合。

- Qubits 之间的 Entangling 入口对于捕获量程功能之间的相关性至关重要。

## <a name="how-to-build-a-classifier-with-q"></a>如何使用 Q 生成分类器\#

若要生成分类器，我们要将线路模型中的参数化控制旋转连接起来。 为此，我们可以使用 [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) 量程机器学习库中定义的类型。 此类型接受四个参数，这些参数可确定：目标 qubit 的索引、控件 qubits 的索引数组、旋转轴以及定义模型的参数数组中关联参数的索引。

让我们看一下分类器的示例。 在 [半部月亮示例](https://github.com/microsoft/Quantum/tree/main/samples/machine-learning/half-moons)中，可以找到在文件中定义的以下分类器 `Training.qs` 。

```qsharp
    function ClassifierStructure() : ControlledRotation[] {
        return [
            ControlledRotation((0, new Int[0]), PauliX, 4),
            ControlledRotation((0, new Int[0]), PauliZ, 5),
            ControlledRotation((1, new Int[0]), PauliX, 6),
            ControlledRotation((1, new Int[0]), PauliZ, 7),
            ControlledRotation((0, [1]), PauliX, 0),
            ControlledRotation((1, [0]), PauliX, 1),
            ControlledRotation((1, new Int[0]), PauliZ, 2),
            ControlledRotation((1, new Int[0]), PauliX, 3)
        ];
    }
 ```

此处定义的是一个函数，该函数返回一组 `ControlledRotation` 元素，这些元素与一组参数一起使用，而偏移将定义我们的 [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel) 。 此类型在量程机器学习库中是基本的，定义分类器。 上述函数中定义的线路是分类器的一部分，其中，数据集的每个示例都包含两个功能。 因此，我们只需要两个 qubits。 线路的图形表示形式为：

 ![线路模型示例](~/media/circuit_model_1.PNG)

请注意，默认情况下，量程机器学习库的操作测量寄存器的最后 qubit 以估计分类概率。 设计线路时，应记住这一点。

## <a name="use-the-library-functions-to-write-layers-of-gates"></a>使用库函数来编写入口层

假设每个实例有一个包含784功能的数据集，例如，MNIST 数据集的28×28像素的图像。 在这种情况下，该线路的宽度会变大，因此，每个单个门的书写可能会成为一项可能但不切实际的任务。 这就是量程机器学习库提供一组工具来自动生成参数化旋转层的原因。 例如，函数 [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) 返回沿给定轴不受控制的单 qubit 旋转的数组，并在寄存器中的每个 qubit 之间进行一次旋转，每个由不同的模型参数参数化。 例如， `LocalRotationsLayer(4, X)` 返回以下一组入口：

 ![本地旋转层](~/media/local_rotations_layer.PNG)

建议浏览 [量程机器学习库的 API 参考](xref:microsoft.quantum.machinelearning) ，以发现可用于简化线路设计的所有工具。

## <a name="next-steps"></a>后续步骤

 在示例提供的示例中，尝试使用不同的结构。 你是否看到了模型的性能发生了任何更改？ 在下一教程中， [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load) 你将学习如何加载数据集，以尝试和探索新的分类器体系结构。
