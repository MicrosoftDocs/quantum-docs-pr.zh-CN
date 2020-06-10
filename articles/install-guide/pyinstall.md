---
title: '用 Q # 和 Python 进行开发'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1ae208e7047cb040fb44945a59c3cc6508a09723
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630282"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="7764e-102">用 Q # 和 Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="7764e-102">Develop with Q# and Python</span></span>

<span data-ttu-id="7764e-103">安装 QDK 以开发 Python 主机程序以调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="7764e-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="7764e-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="7764e-104">Prerequisites</span></span>

    - <span data-ttu-id="7764e-105">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7764e-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="7764e-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="7764e-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="7764e-107">.NET Core SDK 3。1</span><span class="sxs-lookup"><span data-stu-id="7764e-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="7764e-108">安装 `qsharp` 包，这是启用 Q # 和 Python 之间的互操作的 python 包。</span><span class="sxs-lookup"><span data-stu-id="7764e-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="7764e-109">安装 IQ #，Jupyter 和 Python 使用的内核，提供用于编译和执行 Q # 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="7764e-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="7764e-110">如果在此步骤中遇到错误 `dotnet iqsharp install` ，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="7764e-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="7764e-111">如果这仍不起作用，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上 `dotnet-iqsharp.exe` ）并运行：</span><span class="sxs-lookup"><span data-stu-id="7764e-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="7764e-112">其中 `/path/to/dotnet-iqsharp` 应替换为 `dotnet-iqsharp` 文件系统中的工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="7764e-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="7764e-113">通常，这会在 `.dotnet/tools` 用户配置文件文件夹下。</span><span class="sxs-lookup"><span data-stu-id="7764e-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="7764e-114">尽管可以在任何 IDE 中将 Q # 与 Python 一起使用，但我们强烈建议对 Q # + Python 应用程序使用 Visual Studio Code （VS Code） IDE。</span><span class="sxs-lookup"><span data-stu-id="7764e-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="7764e-115">通过使用 Visual Studio Code 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="7764e-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="7764e-116">安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="7764e-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="7764e-117">[为 VS Code 安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="7764e-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="7764e-118">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="7764e-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="7764e-119">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="7764e-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="7764e-120">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="7764e-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="7764e-121">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="7764e-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="7764e-122">验证输出。</span><span class="sxs-lookup"><span data-stu-id="7764e-122">Verify the output.</span></span> <span data-ttu-id="7764e-123">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="7764e-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="7764e-124">你还可以使用 Python Jupyter 笔记本编写传统的 Python 程序并从单元格中调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="7764e-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="7764e-125">Python 代码只是一个普通的 Python 计划。</span><span class="sxs-lookup"><span data-stu-id="7764e-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7764e-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7764e-126">Next steps</span></span>

<span data-ttu-id="7764e-127">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="7764e-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
