---
title: 使用 Q# 和 .NET 进行开发
description: 了解如何使用 .NET 语言创建 Q# 应用程序。
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.cs
no-loc:
- Q#
- $$v
ms.openlocfilehash: de79c361331766572f5608c341be766e071e01b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844307"
---
# <a name="develop-with-no-locq-and-net"></a><span data-ttu-id="68e77-103">使用 Q# 和 .NET 进行开发</span><span class="sxs-lookup"><span data-stu-id="68e77-103">Develop with Q# and .NET</span></span>

<span data-ttu-id="68e77-104">Q# 能够很好地与 C# 和 F# 等 .NET 语言配合运行。</span><span class="sxs-lookup"><span data-stu-id="68e77-104">Q# is built to play well with .NET languages such as C# and F#.</span></span>
<span data-ttu-id="68e77-105">在本指南中，我们将演示如何将 Q# 与采用 .NET 语言编写的主机程序结合使用。</span><span class="sxs-lookup"><span data-stu-id="68e77-105">In this guide, we demonstrate how to use Q# with a host program written in a .NET language.</span></span>

<span data-ttu-id="68e77-106">首先，我们将创建 Q# 应用程序和 .NET 主机，然后演示如何从主机调用 Q#。</span><span class="sxs-lookup"><span data-stu-id="68e77-106">First we create the Q# application and .NET host, and then demonstrate how to call to Q# from the host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="68e77-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="68e77-107">Prerequisites</span></span>

- <span data-ttu-id="68e77-108">安装 Quantum 开发工具包，将它[用于 Q# 项目](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="68e77-108">Install the Quantum Development Kit [for use with Q# projects](xref:microsoft.quantum.install.standalone).</span></span>

## <a name="creating-a-no-locq-library-and-a-net-host"></a><span data-ttu-id="68e77-109">创建 Q# 库和 .NET 主机</span><span class="sxs-lookup"><span data-stu-id="68e77-109">Creating a Q# library and a .NET host</span></span>

<span data-ttu-id="68e77-110">第一步是为 Q# 库以及将要调入到（Q# 库中定义的）操作和函数的 .NET 主机创建项目。</span><span class="sxs-lookup"><span data-stu-id="68e77-110">The first step is to create projects for your Q# library, and for the .NET host that will call into the operations and functions defined in your Q# library.</span></span>

<span data-ttu-id="68e77-111">按照你的开发环境所对应的选项卡中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="68e77-111">Follow the instructions in the tab corresponding to your development environment.</span></span>
<span data-ttu-id="68e77-112">如果使用的是编辑器而不是 Visual Studio 或 VS Code，只需按照命令提示符步骤操作即可。</span><span class="sxs-lookup"><span data-stu-id="68e77-112">If you are using an editor other than Visual Studio or VS Code, simply follow the command prompt steps.</span></span>

### <a name="visual-studio-code-or-command-prompt"></a>[<span data-ttu-id="68e77-113">Visual Studio Code 或命令提示符</span><span class="sxs-lookup"><span data-stu-id="68e77-113">Visual Studio Code or command prompt</span></span>](#tab/tabid-cmdline)

- <span data-ttu-id="68e77-114">创建新的 Q# 库</span><span class="sxs-lookup"><span data-stu-id="68e77-114">Create a new Q# library</span></span>

  ```dotnetcli
  dotnet new classlib -lang Q# -o quantum
  ```

- <span data-ttu-id="68e77-115">创建新的 C# 或 F# 控制台项目</span><span class="sxs-lookup"><span data-stu-id="68e77-115">Create a new C# or F# console project</span></span>

  ```dotnetcli
  dotnet new console -lang C# -o host  
  ```

- <span data-ttu-id="68e77-116">从主机程序添加 Q# 库作为参考</span><span class="sxs-lookup"><span data-stu-id="68e77-116">Add your Q# library as a reference from your host program</span></span>

  ```dotnetcli
  cd host
  dotnet add reference ../quantum/quantum.csproj
  ```

- <span data-ttu-id="68e77-117">[可选] 为这两个项目创建解决方案</span><span class="sxs-lookup"><span data-stu-id="68e77-117">[Optional] Create a solution for both projects</span></span>

  ```dotnetcli
  dotnet new sln -n quantum-dotnet
  dotnet sln quantum-dotnet.sln add ./quantum/quantum.csproj
  dotnet sln quantum-dotnet.sln add ./host/host.csproj
  ```

### <a name="visual-studio-2019"></a>[<span data-ttu-id="68e77-118">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="68e77-118">Visual Studio 2019</span></span>](#tab/tabid-vs2019)

- <span data-ttu-id="68e77-119">创建新的 Q# 库</span><span class="sxs-lookup"><span data-stu-id="68e77-119">Create a new Q# library</span></span>
  - <span data-ttu-id="68e77-120">转到“文件” -> “新建” -> “项目”  </span><span class="sxs-lookup"><span data-stu-id="68e77-120">Go to **File** -> **New** -> **Project**</span></span>
  - <span data-ttu-id="68e77-121">在搜索框中键入“Q#”</span><span class="sxs-lookup"><span data-stu-id="68e77-121">Type "Q#" in the search box</span></span>
  - <span data-ttu-id="68e77-122">选择“Q# 库”</span><span class="sxs-lookup"><span data-stu-id="68e77-122">Select **Q# Library**</span></span>
  - <span data-ttu-id="68e77-123">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="68e77-123">Select **Next**</span></span>
  - <span data-ttu-id="68e77-124">为库选择名称和位置</span><span class="sxs-lookup"><span data-stu-id="68e77-124">Choose a name and location for your library</span></span>
  - <span data-ttu-id="68e77-125">请确保未选中“将项目和解决方案置于同一目录中”</span><span class="sxs-lookup"><span data-stu-id="68e77-125">Make sure that "place project and solution in same directory" is **unchecked**</span></span>
  - <span data-ttu-id="68e77-126">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="68e77-126">Select **Create**</span></span>
- <span data-ttu-id="68e77-127">创建新的 C# 或 F# 主机程序</span><span class="sxs-lookup"><span data-stu-id="68e77-127">Create a new C# or F# host program</span></span>
  - <span data-ttu-id="68e77-128">转到“文件”→“新建”→“项目”  </span><span class="sxs-lookup"><span data-stu-id="68e77-128">Go to **File** → **New** → **Project**</span></span>
  - <span data-ttu-id="68e77-129">选择适用于 C# 或 F# 的“控制台应用(.NET Core)”</span><span class="sxs-lookup"><span data-stu-id="68e77-129">Select "Console App (.NET Core")" for either C# or F#</span></span>
  - <span data-ttu-id="68e77-130">选择“下一步”</span><span class="sxs-lookup"><span data-stu-id="68e77-130">Select **Next**</span></span>
  - <span data-ttu-id="68e77-131">在“解决方案”下，选择“添加到解决方案”</span><span class="sxs-lookup"><span data-stu-id="68e77-131">Under *solution*, select "add to solution"</span></span>
  - <span data-ttu-id="68e77-132">为主机程序选择一个名称</span><span class="sxs-lookup"><span data-stu-id="68e77-132">Choose a name for your host program</span></span>
  - <span data-ttu-id="68e77-133">选择“创建”</span><span class="sxs-lookup"><span data-stu-id="68e77-133">Select **Create**</span></span>

<span data-ttu-id="68e77-134">\*\*_</span><span class="sxs-lookup"><span data-stu-id="68e77-134">\*\*_</span></span>

## <a name="calling-into-no-locq-from-net"></a><span data-ttu-id="68e77-135">从 .NET 调用 Q#</span><span class="sxs-lookup"><span data-stu-id="68e77-135">Calling into Q# from .NET</span></span>

<span data-ttu-id="68e77-136">按照上述说明设置项目后，可从 .NET 控制台应用程序调用 Q#。</span><span class="sxs-lookup"><span data-stu-id="68e77-136">Once you have your projects set up following the above instructions, you can call into Q# from your .NET console application.</span></span>
<span data-ttu-id="68e77-137">Q# 编译器将为每个 Q# 操作和函数创建 .NET 类，使你能够在模拟器上运行量子程序。</span><span class="sxs-lookup"><span data-stu-id="68e77-137">The Q# compiler will create .NET classes for each Q# operation and function that allow you to run your quantum programs on a simulator.</span></span>

<span data-ttu-id="68e77-138">例如，[.NET 互操作性示例](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet)包含以下 Q# 操作的示例：</span><span class="sxs-lookup"><span data-stu-id="68e77-138">For example, the [.NET interoperability sample](https://github.com/microsoft/Quantum/tree/main/samples/interoperability/dotnet) includes the following example of a Q# operation:</span></span>

:::code language="qsharp" source="~/quantum/samples/interoperability/dotnet/qsharp/Operations.qs" range="67-75":::

<span data-ttu-id="68e77-139">若要在量子模拟器上从 .NET 调用此操作，可以使用由 Q# 编译器生成的 `RunAlgorithm` .NET 类的 `Run` 方法：</span><span class="sxs-lookup"><span data-stu-id="68e77-139">To call this operation from .NET on a quantum simulator, you can use the `Run` method of the `RunAlgorithm` .NET class generated by the Q# compiler:</span></span>

### <a name="c"></a>[<span data-ttu-id="68e77-140">C#</span><span class="sxs-lookup"><span data-stu-id="68e77-140">C#</span></span>](#tab/tabid-csharp)

:::code language="csharp" source="~/quantum/samples/interoperability/dotnet/csharp/Host.cs" range="4-":::

### <a name="f"></a>[<span data-ttu-id="68e77-141">F#</span><span class="sxs-lookup"><span data-stu-id="68e77-141">F#</span></span>](#tab/tabid-fsharp)

:::code language="fsharp" source="~/quantum/samples/interoperability/dotnet/fsharp/Host.fs" range="4-":::

<span data-ttu-id="68e77-142">_\*\*</span><span class="sxs-lookup"><span data-stu-id="68e77-142">_\*\*</span></span>
    
## <a name="next-steps"></a><span data-ttu-id="68e77-143">后续步骤</span><span class="sxs-lookup"><span data-stu-id="68e77-143">Next steps</span></span>

<span data-ttu-id="68e77-144">现在，你已为 Q# 应用程序和与 .NET 的互操作设置了 Quantum 开发工具包，接下来可编写并运行你的[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="68e77-144">Now that you have the Quantum Development Kit set up for both Q# applications and interoperability with .NET, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
