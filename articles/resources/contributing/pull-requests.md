---
title: 打开拉取请求
description: 了解如何在准备好向 Microsoft Quantum Development Kit 提供代码或文档时提交 GitHub 拉取请求。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8e04e6502e0a6005dfdf0f93450bf3ffd5aaa672
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87866921"
---
# <a name="opening-pull-requests"></a>打开拉取请求 #

使用 Git 版本控制系统通过使用在 GitHub 上托管的多个存储库来管理量程开发工具包的所有文档。
通过将 Git 和 GitHub 结合使用，可以轻松地在量程开发工具包中轻松地进行协作。
特别是，可以对任何 Git 存储库进行克隆或分叉，以完全独立地复制该存储库。
这样，你就可以使用这些工具并按你喜欢的速度来处理你的内容。

准备就绪后，你可以使用 GitHub 的_拉取请求_功能向我们发送一个请求，以将你的内容包含在存储库中。
每个拉取请求的页面都包含有关所有更改的详细信息、有关发布内容的评论列表，以及社区的其他成员可用于提供反馈和建议的一组审阅工具。

> [!NOTE]
> 尽管 Git 的完整教程超出了本指南的范围，但我们可建议使用以下链接获取有关学习 Git 的更多资源：
>
> - [了解 git](https://www.atlassian.com/git)： Atlassian 中的一组 Git 教程。
> - [Visual Studio Code 中的版本控制](https://code.visualstudio.com/docs/editor/versioncontrol)：有关如何使用 Visual Studio Code 作为 GIT 的 GUI 的指南。
> - [GitHub 学习实验室](https://lab.github.com/)：一组用于使用 Git、GitHub 和相关技术的在线课程。
> - [可视化 git](https://git-school.github.io/visualizing-git/)：可视化 git 命令如何更改存储库状态的交互式工具。
> - [使用 git (EPQIS 2016) 进行版本控制](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes))：一个面向科学计算的 git 教程。
> - [了解 Git 分支](https://learngitbranching.js.org/)：一组交互式的分支和变基测验题，有助于了解新的 Git 功能。

## <a name="what-is-a-pull-request"></a>什么是拉取请求？ ##

说到前面说过，有必要花一些时间来指出拉取请求**是**什么。
使用 Git 时，任何更改都表示为_提交_，这些更改描述了这些更改在发生更改之前如何与存储库的状态相关。
我们经常会绘制一个图表，其中的提交以包含上一次提交的箭头的圆圈形式绘制。

假设已在_分支_中启动了一个名为的发布 `feature` 。
那么， **Microsoft/量子**的分叉可能如下所示：

![GitHub 中的工作分支](~/media/git-workflow-step0.png)

如果你在本地存储库中进行更改，则可以将另一个存储库中的更改_拉取_到你的存储库中，以捕获上游发生的任何更改。

![从上游存储库中提取和合并更改](~/media/git-workflow-step1.png)

拉取请求的工作方式相同，但反向：打开拉取请求时，请求上游存储库请求你的参与。

![请求将更改请求回原始存储库](~/media/git-workflow-step2.png)

当你打开某个存储库的拉取请求时，GitHub 将为社区中的其他人提供机会，以查看你的更改摘要、对这些更改进行评论，并为如何帮助做出更好的贡献提供建议。

![GitHub 中的拉取请求的屏幕截图](~/media/pull-request-header.png)

使用此过程可帮助我们使用 GitHub 功能提高贡献，并为量程编程社区维护高质量的产品。

## <a name="how-to-make-a-pull-request"></a>如何发出拉取请求 ##

可以通过两种主要方法来生成拉取请求。  
对于仅影响单个文件的小更改，可以使用 GitHub web 界面来完全联机请求拉取请求。 只需导航到要编辑的文件，然后使用编辑图标。  
对于更复杂的发布，通常会将存储库克隆到本地计算机，以便首先准备拉取请求。

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a>后续步骤 ##

恭喜你使用 Git 帮助你了解量程开发工具包社区！
若要了解有关如何编写代码的详细信息，请继续阅读下面的指南。

> [!div class="nextstepaction"]
> [了解如何编写代码](xref:microsoft.quantum.contributing.code)
