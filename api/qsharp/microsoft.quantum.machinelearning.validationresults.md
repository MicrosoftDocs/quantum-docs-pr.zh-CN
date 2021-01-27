---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 923fd80333b6bf77daeaac2bf205db620e61cfd0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846096"
---
# <a name="validationresults-user-defined-type"></a>ValidationResults 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


根据一组示例验证了分类器后得到的结果。

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a>命名项

### <a name="nmisclassifications--int"></a>NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)

验证期间观察到的 misclassifications 的数目。
### <a name="nvalidationsamples--int"></a>NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)

