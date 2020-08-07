---
title: 使用其他 Q# 库
description: 了解如何将其他 Q# 库添加到量程应用程序。
author: cgranade
ms.author: chgranad
ms.date: 06/30/2020
ms.topic: article
uid: microsoft.quantum.libraries.using
no-loc:
- Q#
- $$v
ms.openlocfilehash: ef88ca765a394a7092eb0a60bf6f3615c082ef6a
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869573"
---
# <a name="using-additional-no-locq-libraries"></a><span data-ttu-id="a7d2b-103">使用其他 Q# 库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-103">Using Additional Q# Libraries</span></span>

<span data-ttu-id="a7d2b-104">量程开发工具包通过可添加到项目中的_NuGet 包_提供附加的特定于域的功能 Q# 。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-104">The Quantum Development Kit provides additional domain-specific functionality through _NuGet packages_ that can be added to your Q# projects.</span></span>

| <span data-ttu-id="a7d2b-105">Q#类库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-105">Q# Library</span></span>  | <span data-ttu-id="a7d2b-106">NuGet 程序包</span><span class="sxs-lookup"><span data-stu-id="a7d2b-106">NuGet package</span></span> | <span data-ttu-id="a7d2b-107">说明</span><span class="sxs-lookup"><span data-stu-id="a7d2b-107">Notes</span></span> |
|---------|---------|--------|
| [<span data-ttu-id="a7d2b-108">Q#标准库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-108">Q# standard library</span></span>](xref:microsoft.quantum.libraries.standard.intro) | [<span data-ttu-id="a7d2b-109">**Microsoft 量子. 标准版**</span><span class="sxs-lookup"><span data-stu-id="a7d2b-109">**Microsoft.Quantum.Standard**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Standard) | <span data-ttu-id="a7d2b-110">默认包括</span><span class="sxs-lookup"><span data-stu-id="a7d2b-110">Included by default</span></span> |
| [<span data-ttu-id="a7d2b-111">量子化学库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-111">Quantum chemistry library</span></span>](xref:microsoft.quantum.chemistry.concepts.intro) | [<span data-ttu-id="a7d2b-112">**Microsoft.Quantum.Chemistry**</span><span class="sxs-lookup"><span data-stu-id="a7d2b-112">**Microsoft.Quantum.Chemistry**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) | |
| [<span data-ttu-id="a7d2b-113">量子数字库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-113">Quantum numerics library</span></span>](xref:microsoft.quantum.numerics.intro) | [<span data-ttu-id="a7d2b-114">**Microsoft. 量子**</span><span class="sxs-lookup"><span data-stu-id="a7d2b-114">**Microsoft.Quantum.Numerics**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) | |
| [<span data-ttu-id="a7d2b-115">量子机器学习库</span><span class="sxs-lookup"><span data-stu-id="a7d2b-115">Quantum machine learning library</span></span>](xref:microsoft.quantum.libraries.machine-learning.intro) | [<span data-ttu-id="a7d2b-116">**Microsoft.Quantum.MachineLearning**</span><span class="sxs-lookup"><span data-stu-id="a7d2b-116">**Microsoft.Quantum.MachineLearning**</span></span>](https://www.nuget.org/packages/Microsoft.Quantum.MachineLearning) | |

<span data-ttu-id="a7d2b-117">一旦您安装了用于您喜欢的环境和主机语言的量程开发工具包，就可以轻松地将库添加到各个 Q# 项目，而无需进行任何进一步的安装。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-117">Once you have installed the Quantum Development Kit for use with your preferred environment and host language, you can easily add libraries to individual Q# projects without any further installation.</span></span>

> [!NOTE]
> <span data-ttu-id="a7d2b-118">某些 Q# 库可以很好地与你的 Q# 程序或与主机应用程序集成的其他工具一起工作。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-118">Some Q# libraries may work well with additional tools that work alongside your Q# programs, or that integrate with your host applications.</span></span>
> <span data-ttu-id="a7d2b-119">例如，[化学库安装说明](xref:microsoft.quantum.chemistry.concepts.installation)介绍了如何将 NWChem [ **Microsoft.Quantum.Chemistry**包](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry)与计算化学平台一起使用，以及如何安装 `qdk-chem` 用于处理量程化学数据的命令行工具。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-119">For example, the [chemistry library installation instructions](xref:microsoft.quantum.chemistry.concepts.installation) describe how to use the [**Microsoft.Quantum.Chemistry** package](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) together with the NWChem computational chemistry platform, and how to install the `qdk-chem` command-line tools for working with quantum chemistry data.</span></span>

## <a name="no-locq-command-line-applications-or-net-interopability"></a>[<span data-ttu-id="a7d2b-120">Q#命令行应用程序或 .NET interopability</span><span class="sxs-lookup"><span data-stu-id="a7d2b-120">Q# command-line applications or .NET interopability</span></span>](#tab/tabid-csproj)

<span data-ttu-id="a7d2b-121">**命令行或 Visual Studio Code：** 你可以使用命令行自己使用命令行，也可以从 Visual Studio Code 中，使用 `dotnet` 命令将 NuGet 包引用添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-121">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add a NuGet package reference to your project.</span></span>
<span data-ttu-id="a7d2b-122">例如，若要添加[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)包，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-122">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package, run the following command:</span></span>

```dotnetcli
dotnet add package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a7d2b-123">**Visual Studio：** 如果你使用的是 Visual Studio 2019 或更高版本，则可以 Q# 使用 NuGet 包管理器添加其他包。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-123">**Visual Studio:** If you are using Visual Studio 2019 or later, you can add additional Q# packages using the NuGet Package Manager.</span></span>
<span data-ttu-id="a7d2b-124">若要加载包：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-124">To load a package:</span></span> 
1. <span data-ttu-id="a7d2b-125">在 Visual Studio 中打开项目后，从 "**项目**" 菜单中选择 "**管理 NuGet 包 ...** "。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-125">With a project open in Visual Studio, select **Manage NuGet Packages...** from the **Project** menu.</span></span>

2. <span data-ttu-id="a7d2b-126">单击 "**浏览**"，选择 "**包括预发行**版"，然后搜索包名称 ""。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-126">Click **Browse**, select **Include prerelease** and search for the package name "Microsoft.Quantum.Numerics".</span></span> <span data-ttu-id="a7d2b-127">这将列出可供下载的包。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-127">This will list the packages available for download.</span></span>

3. <span data-ttu-id="a7d2b-128">将鼠标悬停在 **"..." 上，** 并单击版本号右侧的向下箭头，以安装数字包。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-128">Hover over **Microsoft.Quantum.Numerics** and click the downward-pointing arrow to the right of the version number to install the numerics package.</span></span>

<span data-ttu-id="a7d2b-129">有关更多详细信息，请参阅[包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-129">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="a7d2b-130">或者，你可以使用包管理器控制台通过命令行接口将数字库添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-130">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![在命令行中使用程序包管理器控制台](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="a7d2b-132">从包管理器控制台中，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-132">From the Package Manager Console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a7d2b-133">有关更多详细信息，请参阅[包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-133">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

## <a name="ino-locq-notebooks"></a>[<span data-ttu-id="a7d2b-134">我的 Q# 笔记本</span><span class="sxs-lookup"><span data-stu-id="a7d2b-134">IQ# Notebooks</span></span>](#tab/tabid-notebook)

<span data-ttu-id="a7d2b-135">你可以 Q# 使用[ `%package` 魔棒命令](xref:microsoft.quantum.iqsharp.magic-ref.package)使其他包可用于我的笔记本。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-135">You can make additional packages available for use in an IQ# Notebook by using the [`%package` magic command](xref:microsoft.quantum.iqsharp.magic-ref.package).</span></span>
<span data-ttu-id="a7d2b-136">例如，若要添加[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)包以便在 I 笔记本中使用 Q# ，请在笔记本单元中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-136">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following command in a notebook cell:</span></span>

```
%package Microsoft.Quantum.Numerics
```

<span data-ttu-id="a7d2b-137">在此命令之后，包可用于笔记本中的任何单元。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-137">Following this command, the package is available to any cells within the notebook.</span></span>
<span data-ttu-id="a7d2b-138">若要使包可从 Q# 当前工作区中的代码使用，请在添加包后重新加载工作区：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-138">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```
%workspace reload
```

## <a name="python-interoperability"></a>[<span data-ttu-id="a7d2b-139">Python 互操作性</span><span class="sxs-lookup"><span data-stu-id="a7d2b-139">Python interoperability</span></span>](#tab/tabid-python)


<span data-ttu-id="a7d2b-140">可以通过使用方法，使其他包在 Python 主机程序中可供使用 [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) 。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-140">You can make additional packages available for use in a Python host program by using the [`qsharp.packages.add`](https://docs.microsoft.com/python/qsharp/qsharp.packages.packages) method.</span></span>
<span data-ttu-id="a7d2b-141">例如，若要添加要在 I 笔记本中使用的[**Microsoft 量子**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics)包 Q# ，请运行以下 Python 代码：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-141">For example, to add the [**Microsoft.Quantum.Numerics**](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) package for use in an IQ# Notebook, run the following Python code:</span></span>

```python
import qsharp
qsharp.packages.add("Microsoft.Quantum.Numerics")
```

<span data-ttu-id="a7d2b-142">执行此命令后，包将可供 Q# 使用编译的任何代码使用 `qsharp.compile` 。</span><span class="sxs-lookup"><span data-stu-id="a7d2b-142">Following this command, the package will be made available to any Q# code compiled using `qsharp.compile`.</span></span>
<span data-ttu-id="a7d2b-143">若要使包可从 Q# 当前工作区中的代码使用，请在添加包后重新加载工作区：</span><span class="sxs-lookup"><span data-stu-id="a7d2b-143">To make the package available from Q# code in the current workspace, reload the workspace after adding your package:</span></span>

```python
qsharp.reload()
```

***
