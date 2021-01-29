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
# <a name="develop-with-no-locq-and-binder"></a>使用 Q# 和 Binder 进行开发

可以使用 Binder 联机运行和共享 Jupyter 笔记本。

## <a name="use-binder-with-the-microsoft-qdk-samples"></a>结合使用 Binder 和 Microsoft QDK 示例

自动配置 Binder 以使用 Microsoft QDK 示例：

1. 打开浏览器并运行 https://aka.ms/try-qsharp 。
1. 在“Quantum 开发工具包示例”登录页上，单击“Q#笔记本”，了解如何使用 IQ# 编写自己的量子应用程序笔记本。

![QDK 登录页](~/media/binder-install.png)

## <a name="use-binder-with-your-own-notebooks-and-repository"></a>将 Binder 用于笔记本和存储库

如果你在 GitHub 存储库中已有笔记本，可以将 Binder 配置为使用你的存储库：

1. 请确保在存储库的根目录中有一个名为 Dockerfile 的文件。 文件必须至少包含以下行：

    ```bash
    FROM mcr.microsoft.com/quantum/iqsharp-base:0.12.20082513
    
    USER root
    COPY . ${HOME}
    RUN chown -R ${USER} ${HOME}
    
    USER ${USER}
    ```

    > [!NOTE]
    > 可以验证[发行说明](xref:microsoft.quantum.relnotes)中的最新 IQ# 版本。

    有关创建 Dockerfile 的详细信息，请参阅 [Dockerfile 参考](https://docs.docker.com/engine/reference/builder/)。

2. 将浏览器打开到 [mybinder.org](https://mybinder.org)。
3. 输入你的存储库名称作为 GitHub URL（例如 MyName/MyRepo），然后单击“启动”。

![MyBinder 窗体](~/media/mybinder.png)
    
## <a name="next-steps"></a>后续步骤

现已设置 Binder 环境，接着可以编写并运行[你的第一个量子程序](xref:microsoft.quantum.quickstarts.qrng)。
