---
title: 数字库安装和验证 |Microsoft Docs
description: 数字库安装和验证
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.installation
ms.openlocfilehash: 8369a6f342ee8e6f56b69bd1f2ce3df40e4093aa
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184621"
---
# <a name="numerics-library-installation-and-validation"></a><span data-ttu-id="e4b47-103">数字库安装和验证</span><span class="sxs-lookup"><span data-stu-id="e4b47-103">Numerics Library Installation and Validation</span></span>

<span data-ttu-id="e4b47-104">量程开发工具包通过[`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet 包提供对数值型功能的支持。</span><span class="sxs-lookup"><span data-stu-id="e4b47-104">The Quantum Development Kit provides support for numerics functionality through the [`Microsoft.Quantum.Numerics`](https://www.nuget.org/packages/Microsoft.Quantum.Numerics) NuGet package.</span></span>

<span data-ttu-id="e4b47-105">**Visual Studio > = 2019：** 如果使用的是 Visual Studio 2019 或更高版本，则可以使用 NuGet 包管理器添加数字包。</span><span class="sxs-lookup"><span data-stu-id="e4b47-105">**Visual Studio >=2019:** If you are using Visual Studio 2019 or later, you can add the numerics package using the NuGet Package Manager.</span></span>
<span data-ttu-id="e4b47-106">为此，请选择 "管理 NuGet 包 ..."从 Visual Studio 中的 "项目" 菜单项。</span><span class="sxs-lookup"><span data-stu-id="e4b47-106">To do so, select "Manage NuGet Packages..." from the "Project" menu item in Visual Studio.</span></span>

<span data-ttu-id="e4b47-107">从 "浏览" 选项卡中，搜索包名称 ""。</span><span class="sxs-lookup"><span data-stu-id="e4b47-107">From the Browse tab, search for the package name "Microsoft.Quantum.Numerics"</span></span>

> [!NOTE]
> <span data-ttu-id="e4b47-108">请确保 "包括预发行版"</span><span class="sxs-lookup"><span data-stu-id="e4b47-108">Make sure to tick "Include prerelease"</span></span>

<span data-ttu-id="e4b47-109">这将列出可供下载的包。</span><span class="sxs-lookup"><span data-stu-id="e4b47-109">This will list the packages available for download.</span></span>
<span data-ttu-id="e4b47-110">如果将鼠标悬停在 ""，则会显示版本号右侧的向下箭头。</span><span class="sxs-lookup"><span data-stu-id="e4b47-110">Hovering over "Microsoft.Quantum.Numerics" reveals a downward-pointing arrow to the right of the version number.</span></span>
<span data-ttu-id="e4b47-111">单击箭头以便安装数字包。</span><span class="sxs-lookup"><span data-stu-id="e4b47-111">Click on the arrow in order to install the numerics package.</span></span>

<span data-ttu-id="e4b47-112">有关更多详细信息，请参阅[包管理器 UI 指南](https://docs.microsoft.com/nuget/tools/package-manager-ui)。</span><span class="sxs-lookup"><span data-stu-id="e4b47-112">For more details, see the [Package Manager UI guide](https://docs.microsoft.com/nuget/tools/package-manager-ui).</span></span>

<span data-ttu-id="e4b47-113">或者，你可以使用包管理器控制台通过命令行接口将数字库添加到你的项目。</span><span class="sxs-lookup"><span data-stu-id="e4b47-113">Alternatively, you can use the Package Manager Console to add the numerics library to your project via the command line interface.</span></span>

![](~/media/vs2017-nuget-console-menu.png)

<span data-ttu-id="e4b47-114">从包管理器控制台中，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="e4b47-114">From the package manager console, run the following:</span></span>

```
Install-Package Microsoft.Quantum.Numerics
```

<span data-ttu-id="e4b47-115">有关更多详细信息，请参阅[包管理器控制台指南](https://docs.microsoft.com/nuget/tools/package-manager-console)。</span><span class="sxs-lookup"><span data-stu-id="e4b47-115">For more details, see the [Package Manager Console guide](https://docs.microsoft.com/nuget/tools/package-manager-console).</span></span>

<span data-ttu-id="e4b47-116">**命令行或 Visual Studio Code：** 你可以使用命令行自己使用命令行，也可以从 Visual Studio Code 中，使用 `dotnet` 命令将 NuGet 包引用添加到你的项目：</span><span class="sxs-lookup"><span data-stu-id="e4b47-116">**Command line or Visual Studio Code:** Using the command line on its own or from within Visual Studio Code, you can use the `dotnet` command to add NuGet package reference to your project:</span></span>

```bash
dotnet add package Microsoft.Quantum.Numerics
```


## <a name="verifying-your-installation"></a><span data-ttu-id="e4b47-117">验证安装</span><span class="sxs-lookup"><span data-stu-id="e4b47-117">Verifying your installation</span></span>

<span data-ttu-id="e4b47-118">与量程开发工具包的其余部分一样，数字库附带了有助于尽快入门的示例。</span><span class="sxs-lookup"><span data-stu-id="e4b47-118">Like the rest of the Quantum Development Kit, the numerics library comes with samples that help you get started as quickly as possible.</span></span>
<span data-ttu-id="e4b47-119">若要使用这些示例测试安装，请克隆[主示例存储库](https://github.com/Microsoft/Quantum)，然后运行其中一个示例。</span><span class="sxs-lookup"><span data-stu-id="e4b47-119">To test your installation using these samples, clone the [main samples repository](https://github.com/Microsoft/Quantum) and then run one of the samples.</span></span>

<span data-ttu-id="e4b47-120">运行[`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd)示例：</span><span class="sxs-lookup"><span data-stu-id="e4b47-120">To run the [`CustomModAdd`](https://github.com/microsoft/Quantum/tree/master/Numerics/CustomModAdd) sample:</span></span>

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/Numerics/CustomModAdd
dotnet run
```