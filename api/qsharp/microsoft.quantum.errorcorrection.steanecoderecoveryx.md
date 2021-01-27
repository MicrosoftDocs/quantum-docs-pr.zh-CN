---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: c90eac291ebe718d10377399184ad705bb51673e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98824695"
---
# <a name="steanecoderecoveryx-function"></a><span data-ttu-id="36113-102">SteaneCodeRecoveryX 函数</span><span class="sxs-lookup"><span data-stu-id="36113-102">SteaneCodeRecoveryX function</span></span>

<span data-ttu-id="36113-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="36113-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="36113-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="36113-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="36113-105">⟦7，1，3⟧ Steane 量程代码的稳定的 X 部分的解码器。</span><span class="sxs-lookup"><span data-stu-id="36113-105">Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a><span data-ttu-id="36113-106">输入</span><span class="sxs-lookup"><span data-stu-id="36113-106">Input</span></span>

### <a name="syndrome--syndrome"></a><span data-ttu-id="36113-107">症状： [症状](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span><span class="sxs-lookup"><span data-stu-id="36113-107">syndrome : [Syndrome](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)</span></span>

<span data-ttu-id="36113-108">从测量稳定的 X 部分获得的症状数组。</span><span class="sxs-lookup"><span data-stu-id="36113-108">A syndrome array obtained from measuring the X-part of the stabilizer.</span></span>



## <a name="output--pauli"></a><span data-ttu-id="36113-109">Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="36113-109">Output : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="36113-110">一组 Pauli 操作，当应用于已编码的量程系统时，它会更正对应于的错误 `syndrome` 。</span><span class="sxs-lookup"><span data-stu-id="36113-110">An array of Pauli operations which, when applied to the encoded quantum system corrects the error corresponding to `syndrome`.</span></span>

## <a name="remarks"></a><span data-ttu-id="36113-111">备注</span><span class="sxs-lookup"><span data-stu-id="36113-111">Remarks</span></span>

<span data-ttu-id="36113-112">所选的解码器使用⟦7，1，3⟧ Steane 代码的 CSS 代码属性，即，它会单独更正 X 错误和 Z 错误。</span><span class="sxs-lookup"><span data-stu-id="36113-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="36113-113">此代码的一个属性是，X 的位置分别是 x 的分别是 X 的3位编码，这是 X 的3位编码，被视为整数。</span><span class="sxs-lookup"><span data-stu-id="36113-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="36113-114">参考</span><span class="sxs-lookup"><span data-stu-id="36113-114">References</span></span>

- <span data-ttu-id="36113-115">D.</span><span class="sxs-lookup"><span data-stu-id="36113-115">D.</span></span> <span data-ttu-id="36113-116">Gottesman、"稳定代码和量程错误纠正" 博士学位 Thesis，Caltech，1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="36113-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="36113-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36113-117">See Also</span></span>

- [<span data-ttu-id="36113-118">ErrorCorrection. SteaneCodeRecoveryX</span><span class="sxs-lookup"><span data-stu-id="36113-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [<span data-ttu-id="36113-119">ErrorCorrection. SteaneCodeRecoveryFns</span><span class="sxs-lookup"><span data-stu-id="36113-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)