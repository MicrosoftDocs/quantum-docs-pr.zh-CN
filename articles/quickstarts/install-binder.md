---
title: 使用 Q# 和 Binder 进行开发
description: 了解如何使用 Binder 创建 Q# 应用程序。
author: bradben
ms.author: v-benbra
ms.date: 9/03/2020
ms.topic: quickstart
uid: microsoft.quantum.install.binder
no-loc:
- Q#
- $$v
ms.openlocfilehash: f7e9b1ae67d6275ec7ba39ea411842dc537536c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856717"
---
# <a name="develop-with-no-locq-and-binder"></a><span data-ttu-id="14ded-103">使用 Q# 和 Binder 进行开发</span><span class="sxs-lookup"><span data-stu-id="14ded-103">Develop with Q# and Binder</span></span>

<span data-ttu-id="14ded-104">可以使用 Binder 联机运行和共享 Jupyter 笔记本。</span><span class="sxs-lookup"><span data-stu-id="14ded-104">You can use Binder to run and share your Jupyter Notebooks online.</span></span>

## <a name="use-binder-with-the-microsoft-qdk-samples"></a><span data-ttu-id="14ded-105">结合使用 Binder 和 Microsoft QDK 示例</span><span class="sxs-lookup"><span data-stu-id="14ded-105">Use Binder with the Microsoft QDK samples</span></span>

<span data-ttu-id="14ded-106">自动配置 Binder 以使用 Microsoft QDK 示例：</span><span class="sxs-lookup"><span data-stu-id="14ded-106">To configure Binder automatically to use the Microsoft QDK samples:</span></span>

1. <span data-ttu-id="14ded-107">打开浏览器并运行 https://aka.ms/try-qsharp 。</span><span class="sxs-lookup"><span data-stu-id="14ded-107">Open a browser and run https://aka.ms/try-qsharp.</span></span>
1. <span data-ttu-id="14ded-108">在“Quantum 开发工具包示例”登录页上，单击“Q#笔记本”，了解如何使用 IQ# 编写自己的量子应用程序笔记本。</span><span class="sxs-lookup"><span data-stu-id="14ded-108">On the **Quantum Development Kit Samples** landing page, click **Q# notebook** to learn how to use IQ# to write your own quantum application notebooks.</span></span>

![QDK 登录页](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a><span data-ttu-id="14ded-110">将 Binder 用于笔记本和存储库</span><span class="sxs-lookup"><span data-stu-id="14ded-110">Use Binder with your own notebooks and repository</span></span>

<span data-ttu-id="14ded-111">如果你在 GitHub 存储库中已有笔记本，可以将 Binder 配置为使用你的存储库：</span><span class="sxs-lookup"><span data-stu-id="14ded-111">If you already have notebooks in a GitHub repository, you can configure Binder to work with your repo:</span></span>

1. <span data-ttu-id="14ded-112">请确保在存储库的根目录中有一个名为 Dockerfile 的文件。</span><span class="sxs-lookup"><span data-stu-id="14ded-112">Ensure that there is a file named *Dockerfile* in the root of your repository.</span></span> <span data-ttu-id="14ded-113">文件必须至少包含以下行：</span><span class="sxs-lookup"><span data-stu-id="14ded-113">The file must contain at least the following lines:</span></span>

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > <span data-ttu-id="14ded-114">可以验证[发行说明](xref:microsoft.quantum.relnotes)中的最新 IQ# 版本。</span><span class="sxs-lookup"><span data-stu-id="14ded-114">You can verify the most current version of IQ# in the [Release Notes](xref:microsoft.quantum.relnotes).</span></span>

    <span data-ttu-id="14ded-115">有关创建 Dockerfile 的详细信息，请参阅 [Dockerfile 参考](https://docs.docker.com/engine/reference/builder/)。</span><span class="sxs-lookup"><span data-stu-id="14ded-115">For more information about creating a Dockerfile, see the [Dockerfile reference](https://docs.docker.com/engine/reference/builder/).</span></span>

2. <span data-ttu-id="14ded-116">将浏览器打开到 [mybinder.org](https://mybinder.org)。</span><span class="sxs-lookup"><span data-stu-id="14ded-116">Open a browser to [mybinder.org](https://mybinder.org).</span></span>
3. <span data-ttu-id="14ded-117">输入你的存储库名称作为 GitHub URL（例如 MyName/MyRepo），然后单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="14ded-117">Enter your repository name as the **GitHub URL** (for example *MyName/MyRepo*), and click **launch**.</span></span>

![MyBinder 窗体](~/media/mybinder.png)
    
## <a name="next-steps"></a><span data-ttu-id="14ded-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="14ded-119">Next steps</span></span>

<span data-ttu-id="14ded-120">现已设置 Binder 环境，接着可以编写并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。</span><span class="sxs-lookup"><span data-stu-id="14ded-120">Now that you have set up your Binder environment, you can write and run [your first quantum program](xref:microsoft.quantum.quickstarts.qrng).</span></span>
