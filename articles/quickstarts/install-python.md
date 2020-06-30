---
title: 使用 Q# 和 Python 进行开发
author: bradben
ms.author: bradben
ms.date: 5/30/2020
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 6513acd5b9cdce15ce61ed2c0454f46e6a6d9bd0
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274021"
---
# <a name="develop-with-q-and-python"></a><span data-ttu-id="8fcd0-102">使用 Q# 和 Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="8fcd0-102">Develop with Q# and Python</span></span>

<span data-ttu-id="8fcd0-103">安装用于开发 Python 主机程序的 QDK 以调用 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="8fcd0-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="8fcd0-104">Prerequisites</span></span>

    - <span data-ttu-id="8fcd0-105">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="8fcd0-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="8fcd0-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="8fcd0-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="8fcd0-107">.NET Core SDK 3.1</span><span class="sxs-lookup"><span data-stu-id="8fcd0-107">.NET Core SDK 3.1</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)


1. <span data-ttu-id="8fcd0-108">安装 `qsharp` 包，这是一个可实现 Q# 和 Python 之间互操作的 Python 包。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```
    pip install qsharp
    ```

1. <span data-ttu-id="8fcd0-109">安装 IQ#，它是 Jupyter 和 Python 使用的内核，提供用于编译和执行 Q# 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

    > [!NOTE]
    > <span data-ttu-id="8fcd0-110">如果在 `dotnet iqsharp install` 步骤中遇到错误，请打开新的终端窗口，然后重试。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-110">If you get an error during the `dotnet iqsharp install` step, open a new terminal window and try again.</span></span>
    > <span data-ttu-id="8fcd0-111">如果仍有问题，请尝试查找安装的 `dotnet-iqsharp` 工具（在 Windows 上为 `dotnet-iqsharp.exe`）并运行：</span><span class="sxs-lookup"><span data-stu-id="8fcd0-111">If this still doesn't work, try locating the installed `dotnet-iqsharp` tool (on Windows, `dotnet-iqsharp.exe`) and running:</span></span>
    > ```
    > /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
    > ```
    > <span data-ttu-id="8fcd0-112">其中 `/path/to/dotnet-iqsharp` 应替换为文件系统中 `dotnet-iqsharp` 工具的绝对路径。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-112">where `/path/to/dotnet-iqsharp` should be replaced by the absolute path to the `dotnet-iqsharp` tool in your file system.</span></span>
    > <span data-ttu-id="8fcd0-113">通常，该工具在用户配置文件文件夹中的 `.dotnet/tools` 下。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-113">Typically this will be under `.dotnet/tools` in your user profile folder.</span></span>
  
1. <span data-ttu-id="8fcd0-114">虽然可以在任何 IDE 中结合使用 Q# 与 Python，但我们强烈建议为 Q# + Python 应用程序使用 Visual Studio Code (VS Code) IDE。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-114">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="8fcd0-115">使用 Visual Studio Code 和 QDK Visual Studio Code 扩展可访问更丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-115">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="8fcd0-116">安装 [VS Code](https://code.visualstudio.com/download)（Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="8fcd0-116">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="8fcd0-117">安装[适用于 VS Code 的 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-117">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="8fcd0-118">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="8fcd0-118">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="8fcd0-119">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="8fcd0-119">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="8fcd0-120">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="8fcd0-120">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="8fcd0-121">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="8fcd0-121">Run the program:</span></span>

        ```
        python hello_world.py
        ```

    - <span data-ttu-id="8fcd0-122">验证输出。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-122">Verify the output.</span></span> <span data-ttu-id="8fcd0-123">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="8fcd0-123">Your program should output the following lines:</span></span>

        ```
        Hello from quantum world!
        ```


> [!NOTE]
> * <span data-ttu-id="8fcd0-124">还可以使用 Python Jupyter 笔记本编写经典 Python 程序并从单元格中调用 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-124">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="8fcd0-125">Python 代码只是普通的 Python 程序。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-125">The Python code is just a normal Python program.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8fcd0-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8fcd0-126">Next steps</span></span>

<span data-ttu-id="8fcd0-127">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="8fcd0-127">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
