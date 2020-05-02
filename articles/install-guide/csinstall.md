---
title: 使用 Q# + C# 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 5bcb036b0b32e64d43f90e9a068d9dcc237890ba
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680168"
---
# <a name="using-q-with-c-and-f"></a><span data-ttu-id="5421b-102">对 C\#和 F 使用 Q #\#</span><span class="sxs-lookup"><span data-stu-id="5421b-102">Using Q# with C\# and F\#</span></span>

<span data-ttu-id="5421b-103">Q # 旨在与 .NET 语言（如 c # 和 F #）一起正常运行。</span><span class="sxs-lookup"><span data-stu-id="5421b-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="5421b-104">在本指南中，我们将演示如何将 Q # 与用 .NET 语言编写的主机程序结合使用。</span><span class="sxs-lookup"><span data-stu-id="5421b-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5421b-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="5421b-105">Prerequisites</span></span>

- <span data-ttu-id="5421b-106">安装用于[Q # 命令行项目](xref:microsoft.quantum.install.standalone)的量程开发工具包。</span><span class="sxs-lookup"><span data-stu-id="5421b-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="5421b-107">创建 Q # 库和 .NET 主机</span><span class="sxs-lookup"><span data-stu-id="5421b-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="5421b-108">第一步是为你的 Q # 库创建项目，并为将调用到你的 Q # 库中定义的操作和函数的 .NET 主机创建项目。</span><span class="sxs-lookup"><span data-stu-id="5421b-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="5421b-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="5421b-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="5421b-110">创建新的 Q # 库</span><span class="sxs-lookup"><span data-stu-id="5421b-110">Create a new Q# library</span></span>
  - <span data-ttu-id="5421b-111">中转到 "**文件** -> " "**新建** -> **项目**"</span><span class="sxs-lookup"><span data-stu-id="5421b-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="5421b-112">在搜索框中键入 "Q #"</span><span class="sxs-lookup"><span data-stu-id="5421b-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="5421b-113">选择**Q # 库**</span><span class="sxs-lookup"><span data-stu-id="5421b-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="5421b-114">选择 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="5421b-114">Select **Next**</span></span>
  - <span data-ttu-id="5421b-115">选择库的名称和位置</span><span class="sxs-lookup"><span data-stu-id="5421b-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="5421b-116">请确保未**选中**"将项目和解决方案放在同一目录中"</span><span class="sxs-lookup"><span data-stu-id="5421b-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="5421b-117">选择**创建**</span><span class="sxs-lookup"><span data-stu-id="5421b-117">Select **Create**</span></span>
- <span data-ttu-id="5421b-118">创建新的 c # 或 F # 宿主程序</span><span class="sxs-lookup"><span data-stu-id="5421b-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="5421b-119">中转到**文件**→**新建**→**项目**</span><span class="sxs-lookup"><span data-stu-id="5421b-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="5421b-120">为 c # 或 F 选择 "控制台应用（.NET Core"） "#</span><span class="sxs-lookup"><span data-stu-id="5421b-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="5421b-121">选择 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="5421b-121">Select **Next**</span></span>
  - <span data-ttu-id="5421b-122">在 "*解决方案*" 下，选择 "添加到解决方案"</span><span class="sxs-lookup"><span data-stu-id="5421b-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="5421b-123">选择主机程序的名称</span><span class="sxs-lookup"><span data-stu-id="5421b-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="5421b-124">选择**创建**</span><span class="sxs-lookup"><span data-stu-id="5421b-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="5421b-125">Visual Studio Code 或命令行</span><span class="sxs-lookup"><span data-stu-id="5421b-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="5421b-126">创建新的 Q # 库</span><span class="sxs-lookup"><span data-stu-id="5421b-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="5421b-127">创建新的 c # 或 F # 控制台项目</span><span class="sxs-lookup"><span data-stu-id="5421b-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="5421b-128">添加你的 Q # 库作为主机程序的引用</span><span class="sxs-lookup"><span data-stu-id="5421b-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="5421b-129">可有可无为这两个项目创建解决方案</span><span class="sxs-lookup"><span data-stu-id="5421b-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="5421b-130">从 .NET 调入 Q #</span><span class="sxs-lookup"><span data-stu-id="5421b-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="5421b-131">按照上述说明设置项目后，可以从 .NET 控制台应用程序调入 Q #。</span><span class="sxs-lookup"><span data-stu-id="5421b-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="5421b-132">Q # 编译器将为每个 Q # 操作和函数创建 .NET 类，使你能够在模拟器上运行量程程序。</span><span class="sxs-lookup"><span data-stu-id="5421b-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="5421b-133">例如， [.net 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含以下 Q # 操作的示例：</span><span class="sxs-lookup"><span data-stu-id="5421b-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="5421b-134">若要在量程模拟器上从 .NET 调用此操作，可以使用由`Run` Q # 编译器`RunAlgorithm`生成的 .net 类的方法：</span><span class="sxs-lookup"><span data-stu-id="5421b-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="5421b-135">C#</span><span class="sxs-lookup"><span data-stu-id="5421b-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="5421b-136">果#</span><span class="sxs-lookup"><span data-stu-id="5421b-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="whats-next"></a><span data-ttu-id="5421b-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5421b-137">What's next?</span></span>

<span data-ttu-id="5421b-138">现在，你已为 Q # 命令行程序设置了量子开发工具包，并且为了与 .NET 互操作，你可以编写并运行[第一个量程程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="5421b-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
