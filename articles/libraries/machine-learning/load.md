---
title: 正在加载传统数据
description: 了解如何加载您自己的数据集，以便使用 Microsoft Quantum Development Kit （QDK）为分类器模型定型。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/16/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.load
ms.openlocfilehash: efa4a65a489446cbef48507d0b02a932da74c71c
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327656"
---
# <a name="load-and-classify-your-own-datasets"></a><span data-ttu-id="f10e0-103">对你自己的数据集进行加载和分类</span><span class="sxs-lookup"><span data-stu-id="f10e0-103">Load and classify your own datasets</span></span>

<span data-ttu-id="f10e0-104">在本快速教程中，我们将学习如何加载自己的数据集，以便使用量程开发工具包（QDK）为分类器模型定型。</span><span class="sxs-lookup"><span data-stu-id="f10e0-104">In this short tutorial, we are going to learn how to load your own dataset to train a classifier model with the Quantum Development Kit (QDK).</span></span>

<span data-ttu-id="f10e0-105">我们强烈建议使用标准化的序列化格式（如[JSON 文件](https://en.wikipedia.org/wiki/JSON)）来存储数据。</span><span class="sxs-lookup"><span data-stu-id="f10e0-105">We highly recommend the use of a standardized serialization format such as [JSON files](https://en.wikipedia.org/wiki/JSON) to store your data.</span></span>
<span data-ttu-id="f10e0-106">此类格式提供与 Python 和 .NET 生态系统等不同框架的高兼容性。</span><span class="sxs-lookup"><span data-stu-id="f10e0-106">Such formats offer high compatibility with different frameworks like Python and the .NET ecosystem.</span></span>
<span data-ttu-id="f10e0-107">具体而言，我们建议使用模板来加载数据，以便直接从示例中复制和粘贴代码。</span><span class="sxs-lookup"><span data-stu-id="f10e0-107">In particular, we recommend using our template for loading the data, so that you can copy-paste the code directly from the samples.</span></span>

## <a name="template-for-loading-your-datasets"></a><span data-ttu-id="f10e0-108">用于加载数据集的模板</span><span class="sxs-lookup"><span data-stu-id="f10e0-108">Template for loading your datasets</span></span>

<span data-ttu-id="f10e0-109">假设我们有一个 $N = $2 的定型数据集 $ （x，y） $，其中每个实例 $x $x $ 的 _i $ 包含三个功能： $x _ {i1} $、$x _ {i2} $ 和 $x _ {i3} $。</span><span class="sxs-lookup"><span data-stu-id="f10e0-109">Suppose we have a training dataset $(x, y)$ of size $N=2$ where each instance $x_i$ of $x$ has three features: $x_{i1}$, $x_{i2}$ and $x_{i3}$.</span></span>
<span data-ttu-id="f10e0-110">验证数据集具有相同的结构。</span><span class="sxs-lookup"><span data-stu-id="f10e0-110">The validation dataset has the same structure.</span></span>
<span data-ttu-id="f10e0-111">这些下可由类似于以下内容的 `data.json` 文件表示：</span><span class="sxs-lookup"><span data-stu-id="f10e0-111">These datsets can be represented by a `data.json` file similar to the following:</span></span>

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

### <a name="example-using-the-template"></a><span data-ttu-id="f10e0-112">使用模板的示例</span><span class="sxs-lookup"><span data-stu-id="f10e0-112">Example using the template</span></span>

<span data-ttu-id="f10e0-113">假设我们有一个小型数据集，其中包含不同猫和狗的高度和权重。</span><span class="sxs-lookup"><span data-stu-id="f10e0-113">Suppose we have a small dataset with the heights and weights of different cats and dogs.</span></span> <span data-ttu-id="f10e0-114">此数据集非常小，不能定型模型，但足以显示加载数据集的过程。</span><span class="sxs-lookup"><span data-stu-id="f10e0-114">This dataset is very small to train a model but will be enough to show the process of loading a dataset.</span></span>

| <span data-ttu-id="f10e0-115">高度（m）</span><span class="sxs-lookup"><span data-stu-id="f10e0-115">Height (m)</span></span> | <span data-ttu-id="f10e0-116">重量（千克）</span><span class="sxs-lookup"><span data-stu-id="f10e0-116">Weight (kg)</span></span> | <span data-ttu-id="f10e0-117">动物</span><span class="sxs-lookup"><span data-stu-id="f10e0-117">Animal</span></span> |
|-----------|------------|--------|
| <span data-ttu-id="f10e0-118">0.54</span><span class="sxs-lookup"><span data-stu-id="f10e0-118">0.54</span></span>      | <span data-ttu-id="f10e0-119">30</span><span class="sxs-lookup"><span data-stu-id="f10e0-119">30</span></span>         | <span data-ttu-id="f10e0-120">狗</span><span class="sxs-lookup"><span data-stu-id="f10e0-120">Dog</span></span>    |
| <span data-ttu-id="f10e0-121">0.30</span><span class="sxs-lookup"><span data-stu-id="f10e0-121">0.30</span></span>      | <span data-ttu-id="f10e0-122">8</span><span class="sxs-lookup"><span data-stu-id="f10e0-122">8</span></span>          | <span data-ttu-id="f10e0-123">Cat</span><span class="sxs-lookup"><span data-stu-id="f10e0-123">Cat</span></span>    |
| <span data-ttu-id="f10e0-124">0.91</span><span class="sxs-lookup"><span data-stu-id="f10e0-124">0.91</span></span>      | <span data-ttu-id="f10e0-125">44</span><span class="sxs-lookup"><span data-stu-id="f10e0-125">44</span></span>         | <span data-ttu-id="f10e0-126">狗</span><span class="sxs-lookup"><span data-stu-id="f10e0-126">Dog</span></span>    |
| <span data-ttu-id="f10e0-127">0.86</span><span class="sxs-lookup"><span data-stu-id="f10e0-127">0.86</span></span>      | <span data-ttu-id="f10e0-128">31</span><span class="sxs-lookup"><span data-stu-id="f10e0-128">31</span></span>          | <span data-ttu-id="f10e0-129">狗</span><span class="sxs-lookup"><span data-stu-id="f10e0-129">Dog</span></span>    |
| <span data-ttu-id="f10e0-130">0.32</span><span class="sxs-lookup"><span data-stu-id="f10e0-130">0.32</span></span>      | <span data-ttu-id="f10e0-131">5</span><span class="sxs-lookup"><span data-stu-id="f10e0-131">5</span></span>         | <span data-ttu-id="f10e0-132">Cat</span><span class="sxs-lookup"><span data-stu-id="f10e0-132">Cat</span></span>    |
| <span data-ttu-id="f10e0-133">0.25</span><span class="sxs-lookup"><span data-stu-id="f10e0-133">0.25</span></span>      | <span data-ttu-id="f10e0-134">4</span><span class="sxs-lookup"><span data-stu-id="f10e0-134">4</span></span>          | <span data-ttu-id="f10e0-135">Cat</span><span class="sxs-lookup"><span data-stu-id="f10e0-135">Cat</span></span>    |

<span data-ttu-id="f10e0-136">过程如下：</span><span class="sxs-lookup"><span data-stu-id="f10e0-136">The process is:</span></span>

- <span data-ttu-id="f10e0-137">首先，我们需要将数据集分成定型和验证。</span><span class="sxs-lookup"><span data-stu-id="f10e0-137">First we need to separate the dataset into training and validation.</span></span> <span data-ttu-id="f10e0-138">在这种情况下，我们可以使用前三个示例进行训练，使用其他示例进行验证。</span><span class="sxs-lookup"><span data-stu-id="f10e0-138">In this case we can just take the first three samples for training and the rest of samples for validation.</span></span> <span data-ttu-id="f10e0-139">通常，为避免定型数据中不需要的偏差，随机采样是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="f10e0-139">In general it is a good practice to sample randomly the training and validation dataset to avoid unwanted biases in the training data.</span></span>
- <span data-ttu-id="f10e0-140">其次，需要为每个类指定一个数字标签。</span><span class="sxs-lookup"><span data-stu-id="f10e0-140">Secondly, we need to assign a numeric label to each class.</span></span> <span data-ttu-id="f10e0-141">请注意，QML 库只 admits 二元分类问题。</span><span class="sxs-lookup"><span data-stu-id="f10e0-141">Note that, for the moment, the QML library only admits binary classification problems.</span></span> <span data-ttu-id="f10e0-142">因此，我们会将标签0分配给类 `Dog` ，将编号1分配给类 `Cat` 。</span><span class="sxs-lookup"><span data-stu-id="f10e0-142">So we will assign the label 0 to the class `Dog` and the number 1 to the class `Cat`.</span></span>
- <span data-ttu-id="f10e0-143">最后，我们使用数据集中的数据填充模板。</span><span class="sxs-lookup"><span data-stu-id="f10e0-143">Finally, we fill the template using the data from our dataset.</span></span> <span data-ttu-id="f10e0-144">请注意，对于大型数据集，您应该构建一个小脚本，以根据您的特定数据集自动生成模板。</span><span class="sxs-lookup"><span data-stu-id="f10e0-144">Note that for big datasets you should build a small script to automatically generate the template from your specific dataset.</span></span> <span data-ttu-id="f10e0-145">此脚本将取决于数据集的原始格式。</span><span class="sxs-lookup"><span data-stu-id="f10e0-145">This script will depend on the original format of your dataset.</span></span>

<span data-ttu-id="f10e0-146">对于我们的数据集， `data.json` 文件为：</span><span class="sxs-lookup"><span data-stu-id="f10e0-146">For our dataset the `data.json` file is:</span></span>

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

## <a name="loading-the-data"></a><span data-ttu-id="f10e0-147">加载数据</span><span class="sxs-lookup"><span data-stu-id="f10e0-147">Loading the data</span></span>

<span data-ttu-id="f10e0-148">将数据序列化为 JSON 文件后，可以将其加载到使用宿主所选语言提供的 JSON 库中。</span><span class="sxs-lookup"><span data-stu-id="f10e0-148">Once you have your data serialized as a JSON file, you can load it in using JSON libraries provided with your host language of choice.</span></span>

### <a name="python"></a>[<span data-ttu-id="f10e0-149">Python</span><span class="sxs-lookup"><span data-stu-id="f10e0-149">Python</span></span>](#tab/tabid-python)

<span data-ttu-id="f10e0-150">Python 提供了用于处理 JSON 序列化数据的[内置 `json` 包](https://docs.python.org/3.7/library/json.html)：</span><span class="sxs-lookup"><span data-stu-id="f10e0-150">Python provides the [built-in `json` package](https://docs.python.org/3.7/library/json.html) for working with JSON-serialized data:</span></span>

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[<span data-ttu-id="f10e0-151">C#</span><span class="sxs-lookup"><span data-stu-id="f10e0-151">C#</span></span>](#tab/tabid-csharp)

<span data-ttu-id="f10e0-152">.NET Core 平台提供了用于处理 JSON 序列化数据的[ `System.Text.Json` 包](https://www.nuget.org/packages/System.Text.Json)：</span><span class="sxs-lookup"><span data-stu-id="f10e0-152">The .NET Core platform provides the [`System.Text.Json` package](https://www.nuget.org/packages/System.Text.Json) for working with JSON-serialized data:</span></span>

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a><span data-ttu-id="f10e0-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f10e0-153">Next steps</span></span>

<span data-ttu-id="f10e0-154">现在，你已准备好开始运行你自己的数据集的试验。</span><span class="sxs-lookup"><span data-stu-id="f10e0-154">Now you are ready to start running your own experiments with your own datasets.</span></span> <span data-ttu-id="f10e0-155">尝试不同的分类器和数据集，并向社区提供共享结果的社区！</span><span class="sxs-lookup"><span data-stu-id="f10e0-155">Try different classifiers and dataset and contribute to the community sharing your results!</span></span>
