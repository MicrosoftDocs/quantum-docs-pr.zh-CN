---
title: 使用 Q# 和 .NET 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.cs
ms.openlocfilehash: 2b0b16bdd9fccc3b668036e6df2b20e11b32f8b6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274031"
---
# <a name="develop-with-q-and-net"></a><span data-ttu-id="111bf-102">使用 Q# 和 .NET 进行开发</span><span class="sxs-lookup"><span data-stu-id="111bf-102">Develop with Q# and .NET</span></span>

<span data-ttu-id="111bf-103">Q# 能够很好地与 C# 和 F# 等 .NET 语言配合运行。</span><span class="sxs-lookup"><span data-stu-id="111bf-103">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="111bf-104">在本指南中，我们将演示如何将 Q# 与采用 .NET 语言编写的主机程序结合使用。</span><span class="sxs-lookup"><span data-stu-id="111bf-104">In this guide, we'll demonstrate how to use Q# with a host program written in a .NET language.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="111bf-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="111bf-105">Prerequisites</span></span>

- <span data-ttu-id="111bf-106">安装 Quantum 开发工具包，以[用于 Q# 命令行项目](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="111bf-106">Install the Quantum Development Kit [for use with Q# command-line projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-q-library-and-a-net-host"></a><span data-ttu-id="111bf-107">创建 Q# 库和 .NET 主机</span><span class="sxs-lookup"><span data-stu-id="111bf-107">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="111bf-108">第一步是为 Q# 库以及将要调入到（Q# 库中定义的）操作和函数的 .NET 主机创建项目。</span><span class="sxs-lookup"><span data-stu-id="111bf-108">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

### <a name="visual-studio-2019"></a>[<span data-ttu-id="111bf-109">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="111bf-109">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="111bf-110">创建新的 Q# 库</span><span class="sxs-lookup"><span data-stu-id="111bf-110">Create a new Q# library</span></span>
  - <span data-ttu-id="111bf-111">转到“文件” -> “新建” -> “项目”  </span><span class="sxs-lookup"><span data-stu-id="111bf-111">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="111bf-112">在搜索框中键入“Q#”</span><span class="sxs-lookup"><span data-stu-id="111bf-112">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="111bf-113">选择 Q# 库</span><span class="sxs-lookup"><span data-stu-id="111bf-113">Select **Q# Library**</span></span>
  - <span data-ttu-id="111bf-114">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="111bf-114">Select **Next**</span></span>
  - <span data-ttu-id="111bf-115">为库选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="111bf-115">Choose a name and location for your library</span></span>
  - <span data-ttu-id="111bf-116">请确保未选中“将项目和解决方案置于同一目录中”</span><span class="sxs-lookup"><span data-stu-id="111bf-116">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="111bf-117">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="111bf-117">Select **Create**</span></span>
- <span data-ttu-id="111bf-118">创建新的 C# 或 F# 主机程序</span><span class="sxs-lookup"><span data-stu-id="111bf-118">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="111bf-119">转到“文件”→“新建”→“项目”  </span><span class="sxs-lookup"><span data-stu-id="111bf-119">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="111bf-120">选择适用于 C# 或 F# 的“控制台应用(.NET Core)”</span><span class="sxs-lookup"><span data-stu-id="111bf-120">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="111bf-121">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="111bf-121">Select **Next**</span></span>
  - <span data-ttu-id="111bf-122">在“解决方案”下，选择“添加到解决方案”</span><span class="sxs-lookup"><span data-stu-id="111bf-122">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="111bf-123">为主机程序选择一个名称</span><span class="sxs-lookup"><span data-stu-id="111bf-123">Choose a name for your host program</span></span>
  - <span data-ttu-id="111bf-124">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="111bf-124">Select **Create**</span></span>

### <a name="visual-studio-code-or-command-line"></a>[<span data-ttu-id="111bf-125">Visual Studio Code 或命令行</span><span class="sxs-lookup"><span data-stu-id="111bf-125">Visual Studio Code or Command Line</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="111bf-126">创建新的 Q# 库</span><span class="sxs-lookup"><span data-stu-id="111bf-126">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="111bf-127">创建新的 C# 或 F# 控制台项目</span><span class="sxs-lookup"><span data-stu-id="111bf-127">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="111bf-128">从主机程序添加 Q# 库作为参考</span><span class="sxs-lookup"><span data-stu-id="111bf-128">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="111bf-129">[可选] 为这两个项目创建解决方案</span><span class="sxs-lookup"><span data-stu-id="111bf-129">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

***

## <a name="calling-into-q-from-net"></a><span data-ttu-id="111bf-130">从 .NET 调用 Q#</span><span class="sxs-lookup"><span data-stu-id="111bf-130">Calling into Q# from .NET</span></span>

<span data-ttu-id="111bf-131">按照上述说明设置项目后，可从 .NET 控制台应用程序调用 Q#。</span><span class="sxs-lookup"><span data-stu-id="111bf-131">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="111bf-132">Q# 编译器将为每个 Q# 操作和函数创建 .NET 类，使你能够在模拟器上运行量子程序。</span><span class="sxs-lookup"><span data-stu-id="111bf-132">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="111bf-133">例如，[.NET 互操作性示例](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet)包含以下 Q# 操作的示例：</span><span class="sxs-lookup"><span data-stu-id="111bf-133">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/master/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="111bf-134">若要在量子模拟器上从 .NET 调用此操作，可以使用由 Q# 编译器生成的 `RunAlgorithm` .NET 类的 `Run` 方法：</span><span class="sxs-lookup"><span data-stu-id="111bf-134">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="111bf-135">C#</span><span class="sxs-lookup"><span data-stu-id="111bf-135">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="111bf-136">F#</span><span class="sxs-lookup"><span data-stu-id="111bf-136">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

***
    
## <a name="next-steps"></a><span data-ttu-id="111bf-137">后续步骤</span><span class="sxs-lookup"><span data-stu-id="111bf-137">Next steps</span></span>

<span data-ttu-id="111bf-138">现在，你已为 Q# 命令行程序和与 .NET 的互操作设置了 Quantum 开发工具包，接下来可以编写并运行你的[第一个量程程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="111bf-138">Now that you have Quantum Development Kit set up for both Q# command-line programs, and for interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
