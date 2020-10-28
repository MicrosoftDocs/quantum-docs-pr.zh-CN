---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: e6831a8630c0a80c2abe7c4a720263f0de03edc4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695518"
---
# <a name="decodefromsteanecode-operation"></a><span data-ttu-id="07d34-102">DecodeFromSteaneCode 操作</span><span class="sxs-lookup"><span data-stu-id="07d34-102">DecodeFromSteaneCode operation</span></span>

<span data-ttu-id="07d34-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="07d34-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="07d34-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="07d34-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="07d34-105">一种反向编码操作，它将未编码的量程寄存器映射到⟦7，1，3⟧ Steane 量程代码下的编码的量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="07d34-105">An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.</span></span>

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a><span data-ttu-id="07d34-106">输入</span><span class="sxs-lookup"><span data-stu-id="07d34-106">Input</span></span>

### <a name="logicalregister--logicalregister"></a><span data-ttu-id="07d34-107">logicalRegister： [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span><span class="sxs-lookup"><span data-stu-id="07d34-107">logicalRegister : [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)</span></span>

<span data-ttu-id="07d34-108">表示已编码的 qubit 代码逻辑状态的 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="07d34-108">An array of qubits representing the encoded 5-qubit code logical state.</span></span>



## <a name="output--qubitqubit"></a><span data-ttu-id="07d34-109">Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) </span><span class="sxs-lookup"><span data-stu-id="07d34-109">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])</span></span>

<span data-ttu-id="07d34-110">长度为1的 qubit 数组，它表示第一个参数中未编码的状态，以及第二个参数中的辅助 qubits。</span><span class="sxs-lookup"><span data-stu-id="07d34-110">A qubit array of length 1 representing the unencoded state in the first parameter, together with auxiliary qubits in the second parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="07d34-111">注解</span><span class="sxs-lookup"><span data-stu-id="07d34-111">Remarks</span></span>

<span data-ttu-id="07d34-112">所选的解码器使用⟦7，1，3⟧ Steane 代码的 CSS 代码属性，即，它会单独更正 X 错误和 Z 错误。</span><span class="sxs-lookup"><span data-stu-id="07d34-112">The chosen decoder uses the CSS code property of the ⟦7, 1, 3⟧ Steane code, i.e., it corrects X errors and Z errors separately.</span></span> <span data-ttu-id="07d34-113">此代码的一个属性是，X 的位置分别是 x 的分别是 X 的3位编码，这是 X 的3位编码，被视为整数。</span><span class="sxs-lookup"><span data-stu-id="07d34-113">A property of the code is that the location of the X, respectively, Z correction to be applied is the 3-bit encoding of the X, respectively, Z syndrome when considered an integer.</span></span>

## <a name="references"></a><span data-ttu-id="07d34-114">参考</span><span class="sxs-lookup"><span data-stu-id="07d34-114">References</span></span>

- <span data-ttu-id="07d34-115">D.</span><span class="sxs-lookup"><span data-stu-id="07d34-115">D.</span></span> <span data-ttu-id="07d34-116">Gottesman、"稳定代码和量程错误纠正" 博士学位 Thesis，Caltech，1997; https://arxiv.org/abs/quant-ph/9705052</span><span class="sxs-lookup"><span data-stu-id="07d34-116">Gottesman, "Stabilizer Codes and Quantum Error Correction," Ph.D. Thesis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052</span></span>

## <a name="see-also"></a><span data-ttu-id="07d34-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d34-117">See Also</span></span>

- [<span data-ttu-id="07d34-118">ErrorCorrection. SteaneCodeEncoder</span><span class="sxs-lookup"><span data-stu-id="07d34-118">Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [<span data-ttu-id="07d34-119">ErrorCorrection. SteaneCodeDecoder</span><span class="sxs-lookup"><span data-stu-id="07d34-119">Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder</span></span>](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [<span data-ttu-id="07d34-120">ErrorCorrection. LogicalRegister</span><span class="sxs-lookup"><span data-stu-id="07d34-120">Microsoft.Quantum.ErrorCorrection.LogicalRegister</span></span>](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)