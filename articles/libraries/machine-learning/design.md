---
title: 用 QDK 设计自己的分类器
description: 了解为量子线路中心分类器设计线路模型的基本概念。
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 02/17/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.design
ms.openlocfilehash: 4899336f437c1b7712a7831b97fd6ec1431b59a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909715"
---
# <a name="design-your-own-classifier"></a><span data-ttu-id="b72bc-103">设计自己的分类器</span><span class="sxs-lookup"><span data-stu-id="b72bc-103">Design your own classifier</span></span>

<span data-ttu-id="b72bc-104">在本指南中，你将了解针对量程线路中心分类器的线路模型设计的基本概念。</span><span class="sxs-lookup"><span data-stu-id="b72bc-104">In this guide you will learn the basic concepts behind the design of circuit models for the quantum circuit centric classifier.</span></span>

<span data-ttu-id="b72bc-105">与经典深度学习一样，没有用于选择特定体系结构的一般规则。</span><span class="sxs-lookup"><span data-stu-id="b72bc-105">As in classical deep learning, there is no general rule for choosing a specific architecture.</span></span> <span data-ttu-id="b72bc-106">与其他体系结构相比，某些体系结构的性能更好。</span><span class="sxs-lookup"><span data-stu-id="b72bc-106">Depending on the problem some architectures will perform better than others.</span></span> <span data-ttu-id="b72bc-107">但在设计线路时，有一些概念可能会很有用：</span><span class="sxs-lookup"><span data-stu-id="b72bc-107">But, there are some concepts that might be useful when designing the circuit:</span></span>

- <span data-ttu-id="b72bc-108">大量参数表示更灵活的模型，这种模型可能适用于绘制复杂的分类边界，但也可能更容易被过度拟合。</span><span class="sxs-lookup"><span data-stu-id="b72bc-108">A large number of parameters implies a more flexible model, which may be suitable to draw complicated classification boundaries but which may also be more susceptible to overfitting.</span></span>

- <span data-ttu-id="b72bc-109">Qubits 之间的 Entangling 入口对于捕获量程功能之间的相关性至关重要。</span><span class="sxs-lookup"><span data-stu-id="b72bc-109">Entangling gates between qubits are essential to capture the correlations between the quantum features.</span></span>

## <a name="how-to-build-a-classifier-with-q"></a><span data-ttu-id="b72bc-110">如何使用 Q\# 生成分类器</span><span class="sxs-lookup"><span data-stu-id="b72bc-110">How to build a classifier with Q\#</span></span>

<span data-ttu-id="b72bc-111">若要生成分类器，我们要将线路模型中的参数化控制旋转连接起来。</span><span class="sxs-lookup"><span data-stu-id="b72bc-111">To build a classifier we are going to concatenate parametrized controlled rotations in our circuit model.</span></span> <span data-ttu-id="b72bc-112">为此，我们可以使用量程机器学习库中定义[`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation)类型。</span><span class="sxs-lookup"><span data-stu-id="b72bc-112">To do it we can use the type [`ControlledRotation`](xref:microsoft.quantum.machinelearning.controlledrotation) defined in the Quantum Machine Learning library.</span></span> <span data-ttu-id="b72bc-113">此类型接受四个参数，这些参数可确定：目标 qubit 的索引、控件 qubits 的索引数组、旋转轴以及定义模型的参数数组中关联参数的索引。</span><span class="sxs-lookup"><span data-stu-id="b72bc-113">This type accepts four arguments that determine: the index of the target qubit, the array of indices of the control qubits, the axis of rotation, and index of the associated parameter in the array of parameters defining the model.</span></span>

<span data-ttu-id="b72bc-114">让我们看一下分类器的示例。</span><span class="sxs-lookup"><span data-stu-id="b72bc-114">Let's see an example of a classifier.</span></span> <span data-ttu-id="b72bc-115">在[半部月亮示例](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons)中，可以找到在文件 `Training.qs`中定义的以下分类器。</span><span class="sxs-lookup"><span data-stu-id="b72bc-115">In the [half-moons sample](https://github.com/microsoft/Quantum/tree/master/samples/machine-learning/half-moons), we can find the following classifier defined in the file `Training.qs`.</span></span>

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

<span data-ttu-id="b72bc-116">此处定义的是一个函数，该函数返回 `ControlledRotation` 元素的数组，这些元素与一组参数一起使用，而偏差将定义我们的[`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel)。</span><span class="sxs-lookup"><span data-stu-id="b72bc-116">What we are defining here is a function that returns an array of `ControlledRotation` elements, that together with an array of parameters and a bias will define our [`SequentialModel`](xref:microsoft.quantum.machinelearning.sequentialmodel).</span></span> <span data-ttu-id="b72bc-117">此类型在量程机器学习库中是基本的，定义分类器。</span><span class="sxs-lookup"><span data-stu-id="b72bc-117">This type is fundamental in the Quantum Machine Learning library and defines the classifier.</span></span> <span data-ttu-id="b72bc-118">上述函数中定义的线路是分类器的一部分，其中，数据集的每个示例都包含两个功能。</span><span class="sxs-lookup"><span data-stu-id="b72bc-118">The circuit defined in the function above is part of a classifier in which each sample of the dataset contains two features.</span></span> <span data-ttu-id="b72bc-119">因此，我们只需要两个 qubits。</span><span class="sxs-lookup"><span data-stu-id="b72bc-119">Therefore we only need two qubits.</span></span> <span data-ttu-id="b72bc-120">线路的图形表示形式为：</span><span class="sxs-lookup"><span data-stu-id="b72bc-120">The graphical representation of the circuit is:</span></span>

 ![线路模型示例](~/media/circuit_model_1.PNG)

## <a name="use-the-library-functions-to-write-layers-of-gates"></a><span data-ttu-id="b72bc-122">使用库函数来编写入口层</span><span class="sxs-lookup"><span data-stu-id="b72bc-122">Use the library functions to write layers of gates</span></span>

<span data-ttu-id="b72bc-123">假设每个实例有一个包含784功能的数据集，例如，MNIST 数据集的28×28像素的图像。</span><span class="sxs-lookup"><span data-stu-id="b72bc-123">Suppose we have a dataset with 784 features per instance, e.g. images of 28×28 pixels like the MNIST dataset.</span></span> <span data-ttu-id="b72bc-124">在这种情况下，该线路的宽度会变大，因此，每个单个门的书写可能会成为一项可能但不切实际的任务。</span><span class="sxs-lookup"><span data-stu-id="b72bc-124">In this case, the width of the circuit becomes large enough so that writing by hand each individual gate becomes a possible but impractical task.</span></span> <span data-ttu-id="b72bc-125">这就是量程机器学习库提供一组工具来自动生成参数化旋转层的原因。</span><span class="sxs-lookup"><span data-stu-id="b72bc-125">This is why the Quantum Machine Learning library provides a set of tools to automatically generate layers of parametrized rotations.</span></span> <span data-ttu-id="b72bc-126">例如，函数[`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer)返回沿给定轴不受控制的 qubit 旋转的数组，并在寄存器中的每个 qubit 之间进行一次旋转，每个由不同的模型参数参数化。</span><span class="sxs-lookup"><span data-stu-id="b72bc-126">For instance, the function [`LocalRotationsLayer`](xref:microsoft.quantum.machinelearning.localrotationslayer) returns an array of uncontrolled single-qubit rotations along a given axis, with one rotation for each qubit in the register, each parametrized by a different model parameter.</span></span> <span data-ttu-id="b72bc-127">例如，`LocalRotationsLayer(4, X)` 返回以下一组入口：</span><span class="sxs-lookup"><span data-stu-id="b72bc-127">For example, `LocalRotationsLayer(4, X)` returns the following set of gates:</span></span>

 ![本地旋转层](~/media/local_rotations_layer.PNG)

<span data-ttu-id="b72bc-129">建议您浏览[量程机器学习库的 API referenece](xref:microsoft.quantum.machinelearning) ，以发现可用于简化线路设计的所有工具。</span><span class="sxs-lookup"><span data-stu-id="b72bc-129">We recommend you to explore the [API referenece of the Quantum Machine Learning library](xref:microsoft.quantum.machinelearning) to discover all the tools available to streamline the circuit design.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b72bc-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b72bc-130">Next steps</span></span>

 <span data-ttu-id="b72bc-131">在示例提供的示例中，尝试使用不同的结构。</span><span class="sxs-lookup"><span data-stu-id="b72bc-131">Try different structures in the examples provided by the samples.</span></span> <span data-ttu-id="b72bc-132">你是否看到了模型的性能发生了任何更改？</span><span class="sxs-lookup"><span data-stu-id="b72bc-132">Do you see any changes in the performance of the model?</span></span> <span data-ttu-id="b72bc-133">在下一教程[`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load)中，你将学习如何加载数据集，以尝试和探索新的分类器体系结构。</span><span class="sxs-lookup"><span data-stu-id="b72bc-133">In the next tutorial, [`Load your own datasets`](xref:microsoft.quantum.libraries.machine-learning.load), you will learn how to load datasets to try and explore new architectures of classifiers.</span></span>
