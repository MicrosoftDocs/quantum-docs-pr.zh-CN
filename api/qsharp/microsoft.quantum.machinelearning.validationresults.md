---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696715"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


根据一组示例验证了分类器后得到的结果。

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>命名项

### <a name="nmisclassifications--int"></a>NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)

验证期间观察到的 misclassifications 的数目。
### <a name="nvalidationsamples--int"></a>NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)

