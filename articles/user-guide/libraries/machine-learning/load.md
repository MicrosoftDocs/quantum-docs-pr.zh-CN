---
title: 正在加载传统数据
description: 了解如何加载自己的数据集，以便使用 Microsoft Quantum Development Kit (QDK) 训练分类器模型。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 26ba7411c9ade1d6c4b606e8c12c10ade18fc584
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868825"
---
# <a name="load-and-classify-your-own-datasets"></a>对你自己的数据集进行加载和分类

在本快速教程中，我们将学习如何加载自己的数据集，以便使用量程开发工具包 (QDK) 来训练分类器模型。

我们强烈建议使用标准化的序列化格式（如[JSON 文件](https://en.wikipedia.org/wiki/JSON)）来存储数据。
此类格式提供与 Python 和 .NET 生态系统等不同框架的高兼容性。
具体而言，我们建议使用模板来加载数据，以便直接从示例中复制和粘贴代码。

## <a name="template-for-loading-your-datasets"></a>用于加载数据集的模板

假设我们有一个定型数据集 $ (x，y) $ of $N = $2，其中，_i $ 的每个实例 $x $x $ 有三个功能： $x _ {i1} $，$x _ {i2} $，$x _ {i3} $。
验证数据集具有相同的结构。
这些下可由类似于以下内容的 `data.json` 文件表示：

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>使用模板的示例

假设我们有一个小型数据集，其中包含不同猫和狗的高度和权重。 此数据集非常小，不能定型模型，但足以显示加载数据集的过程。

| 高度 (m)  | 重量 (千克)  | 动物 |
|-----------|------------|--------|
| 0.54      | 30         | 狗    |
| 0.30      | 8          | Cat    |
| 0.91      | 44         | 狗    |
| 0.86      | 31          | 狗    |
| 0.32      | 5         | Cat    |
| 0.25      | 4          | Cat    |

过程如下：

- 首先，我们需要将数据集分成定型和验证。 在这种情况下，我们可以使用前三个示例进行训练，使用其他示例进行验证。 通常，为避免定型数据中不需要的偏差，随机采样是一种很好的做法。
- 其次，需要为每个类指定一个数字标签。 请注意，QML 库只 admits 二元分类问题。 因此，我们会将标签0分配给类 `Dog` ，将编号1分配给类 `Cat` 。
- 最后，我们使用数据集中的数据填充模板。 请注意，对于大型数据集，您应该构建一个小脚本，以根据您的特定数据集自动生成模板。 此脚本将取决于数据集的原始格式。

对于我们的数据集， `data.json` 文件为：

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>加载数据

将数据序列化为 JSON 文件后，可以将其加载到使用宿主所选语言提供的 JSON 库中。

### <a name="python"></a>[Python](#tab/tabid-python)

Python 提供了用于处理 JSON 序列化数据的[内置 `json` 包](https://docs.python.org/3.7/library/json.html)：

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

.NET Core 平台提供了用于处理 JSON 序列化数据的[ `System.Text.Json` 包](https://www.nuget.org/packages/System.Text.Json)：

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>后续步骤

现在，你已准备好开始运行你自己的数据集的试验。 尝试不同的分类器和数据集，并向社区提供共享结果的社区！
