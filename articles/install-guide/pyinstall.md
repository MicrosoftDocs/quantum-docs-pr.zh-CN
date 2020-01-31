---
title: '用 Q # + Python 进行开发'
author: natke
ms.author: nakersha
ms.date: 9/30/2019
ms.topic: article
ms.custom: how-to
uid: microsoft.quantum.install.python
ms.openlocfilehash: 1e40c2dddeaf4fad41693c976493f10fffffa139
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76830995"
---
# <a name="develop-with-q--python"></a><span data-ttu-id="f8b6d-102">用 Q # + Python 进行开发</span><span class="sxs-lookup"><span data-stu-id="f8b6d-102">Develop with Q# + Python</span></span>

<span data-ttu-id="f8b6d-103">安装 QDK 以开发 Python 主机程序以调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-103">Install the QDK to develop Python host programs to call Q# operations.</span></span>

1. <span data-ttu-id="f8b6d-104">必备组件</span><span class="sxs-lookup"><span data-stu-id="f8b6d-104">Pre-requisites</span></span>

    - <span data-ttu-id="f8b6d-105">[Python](https://www.python.org/downloads/) 3.6 或更高版本</span><span class="sxs-lookup"><span data-stu-id="f8b6d-105">[Python](https://www.python.org/downloads/) 3.6 or later</span></span>
    - <span data-ttu-id="f8b6d-106">[PIP](https://pip.pypa.io/en/stable/installing) Python 包管理器</span><span class="sxs-lookup"><span data-stu-id="f8b6d-106">The [PIP](https://pip.pypa.io/en/stable/installing) Python package manager</span></span>
    - [<span data-ttu-id="f8b6d-107">.NET Core SDK 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="f8b6d-107">.NET Core SDK 3.1 or later</span></span>](https://www.microsoft.com/net/download)


1. <span data-ttu-id="f8b6d-108">安装 `qsharp` 包，这是一个允许在 Q # 和 Python 之间互操作的 Python 包。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-108">Install the `qsharp` package, a Python package that enables interop between Q# and Python.</span></span>

    ```bash
    pip install qsharp
    ```

1. <span data-ttu-id="f8b6d-109">安装 `iqsharp`，Jupyter 和 Python 使用的内核，提供用于编译和执行 Q # 操作的核心功能。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-109">Install `iqsharp`, a kernel used by Jupyter and Python that provides the core functionality for compiling and executing Q# operations.</span></span>

    ```bash
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```
  
1. <span data-ttu-id="f8b6d-110">尽管可以在任何 IDE 中将 Q # 与 Python 一起使用，但我们强烈建议对 Q # + Python 应用程序使用 Visual Studio Code （VS Code） IDE。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-110">While you can use Q# with Python in any IDE, we highly recommend using Visual Studio Code (VS Code) IDE for your Q# + Python applications.</span></span> <span data-ttu-id="f8b6d-111">通过使用 Visual Studio Code 和 QDK Visual Studio Code 扩展，你可以访问更丰富的功能。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-111">By using Visual Studio Code and the QDK Visual Studio Code extension you gain access to richer functionality.</span></span>

    - <span data-ttu-id="f8b6d-112">安装[VS Code](https://code.visualstudio.com/download) （Windows、Linux 和 Mac）</span><span class="sxs-lookup"><span data-stu-id="f8b6d-112">Install [VS Code](https://code.visualstudio.com/download) (Windows, Linux and Mac)</span></span>
    - <span data-ttu-id="f8b6d-113">[为 VS Code 安装 QDK 扩展](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode)。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-113">Install the [QDK extension for VS Code](https://marketplace.visualstudio.com/items?itemName=quantum.quantum-devkit-vscode).</span></span>

1. <span data-ttu-id="f8b6d-114">通过创建 `Hello World` 应用程序来验证安装</span><span class="sxs-lookup"><span data-stu-id="f8b6d-114">Verify the installation by creating a `Hello World` application</span></span>

    - <span data-ttu-id="f8b6d-115">通过创建名为 `Operation.qs` 的文件并向其添加以下代码来创建最小 Q# 操作：</span><span class="sxs-lookup"><span data-stu-id="f8b6d-115">Create a minimal Q# operation, by creating a file called `Operation.qs`, and adding the following code to it:</span></span>

        ```qsharp
        namespace HelloWorld {
            open Microsoft.Quantum.Intrinsic;
            open Microsoft.Quantum.Canon;

            operation SayHello() : Unit {
                Message("Hello from quantum world!");
            }
        }
        ```

    - <span data-ttu-id="f8b6d-116">创建名为 `hello_world.py` 的 Python 程序来调用 Q# `SayHello()` 操作：</span><span class="sxs-lookup"><span data-stu-id="f8b6d-116">Create a Python program called `hello_world.py` to call the Q# `SayHello()` operation:</span></span>

        ```python
        import qsharp

        from HelloWorld import SayHello

        SayHello.simulate()
        ```

    - <span data-ttu-id="f8b6d-117">运行该程序：</span><span class="sxs-lookup"><span data-stu-id="f8b6d-117">Run the program:</span></span>

        ```bash
        python hello_world.py
        ```

    - <span data-ttu-id="f8b6d-118">验证输出。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-118">Verify the output.</span></span> <span data-ttu-id="f8b6d-119">程序应输出以下行：</span><span class="sxs-lookup"><span data-stu-id="f8b6d-119">Your program should output the following lines:</span></span>

        ```bash
        Hello from quantum world!
       ```


> [!NOTE]
> * <span data-ttu-id="f8b6d-120">你还可以使用 Python Jupyter 笔记本编写传统的 Python 程序并从单元格中调用 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-120">You can also use Python Jupyter notebooks to write the classical Python program and call Q# operations from the cells.</span></span> <span data-ttu-id="f8b6d-121">Python 代码只是一个普通的 Python 计划。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-121">The Python code is just a normal Python program.</span></span>

## <a name="whats-next"></a><span data-ttu-id="f8b6d-122">还有什么？</span><span class="sxs-lookup"><span data-stu-id="f8b6d-122">What's next?</span></span>

<span data-ttu-id="f8b6d-123">在首选环境中安装量子开发工具包后，可以编写并运行[第一个量子程序](xref:microsoft.quantum.write-program)。</span><span class="sxs-lookup"><span data-stu-id="f8b6d-123">Now that you have installed the Quantum Development Kit in your preferred environment, you can write and run [your first quantum program](xref:microsoft.quantum.write-program).</span></span>
