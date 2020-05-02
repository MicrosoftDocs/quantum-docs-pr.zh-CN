---
title: 使用 Q# + Python 进行开发
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: e1b8a0c68b3ac0c059c6de6e478593321764ff88
ms.sourcegitcommit: db23885adb7ff76cbf8bd1160d401a4f0471e549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "82680151"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="aeeec-102">使用 Q# + Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="aeeec-102">Develop with Q# + Python</span></span>

<span data-ttu-id="aeeec-103">安装 QDK 以开发 Python 主机程序以调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="aeeec-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="aeeec-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="aeeec-104">Pre-requisites</span></span>

    - <span data-ttu-id="aeeec-105">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aeeec-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="aeeec-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="aeeec-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="aeeec-107">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="aeeec-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="aeeec-108">安装`qsharp`包，这是启用 Q # 和 Python 之间的互操作的 python 包。</span><span class="sxs-lookup"><span data-stu-id="aeeec-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="aeeec-109">安装 IQ #，Jupyter 和 Python 使用的内核，提供用于编译和执行 Q # 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="aeeec-109">Install IQ#, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="aeeec-110">尽管可以在任何 IDE 中将 Q # 与 Python 一起使用，但我们强烈建议对 Q # + Python 应用程序使用 Visual Studio Code （VS Code） IDE。</span><span class="sxs-lookup"><span data-stu-id="aeeec-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="aeeec-111">通过使用 Visual Studio Code 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="aeeec-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="aeeec-112">安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="aeeec-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="aeeec-113">[为 VS Code 安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="aeeec-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="aeeec-114">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="aeeec-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="aeeec-115">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="aeeec-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="aeeec-116">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="aeeec-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="aeeec-117">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="aeeec-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="aeeec-118">验证输出。</span><span class="sxs-lookup"><span data-stu-id="aeeec-118">Verify the output.</span></span> <span data-ttu-id="aeeec-119">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="aeeec-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="aeeec-120">你还可以使用 Python Jupyter 笔记本编写传统的 Python 程序并从单元格中调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="aeeec-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="aeeec-121">Python 代码只是一个普通的 Python 计划。</span><span class="sxs-lookup"><span data-stu-id="aeeec-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="aeeec-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="aeeec-122">What's next?</span></span>

<span data-ttu-id="aeeec-123">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="aeeec-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
