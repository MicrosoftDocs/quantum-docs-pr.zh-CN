---
title: 打开拉取请求
description: 了解如何在准备好向 Microsoft Quantum Development Kit 提供代码或文档时提交 GitHub 拉取请求。
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: contributor-guide
uid: microsoft.quantum.contributing.pulls
no-loc:
- Q#
- $$v
ms.openlocfilehash: a936283f3e51da9b97b8145bad3ab765b6423458
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858471"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="2539e-103">打开拉取请求</span><span class="sxs-lookup"><span data-stu-id="2539e-103">Opening Pull Requests</span></span> #

<span data-ttu-id="2539e-104">使用 Git 版本控制系统通过使用在 GitHub 上托管的多个存储库来管理量程开发工具包的所有文档。</span><span class="sxs-lookup"><span data-stu-id="2539e-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="2539e-105">通过将 Git 和 GitHub 结合使用，可以轻松地在量程开发工具包中轻松地进行协作。</span><span class="sxs-lookup"><span data-stu-id="2539e-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="2539e-106">特别是，可以对任何 Git 存储库进行克隆或分叉，以完全独立地复制该存储库。</span><span class="sxs-lookup"><span data-stu-id="2539e-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="2539e-107">这样，你就可以使用这些工具并按你喜欢的速度来处理你的内容。</span><span class="sxs-lookup"><span data-stu-id="2539e-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="2539e-108">准备就绪后，你可以使用 GitHub 的 _拉取请求_ 功能向我们发送一个请求，以将你的内容包含在存储库中。</span><span class="sxs-lookup"><span data-stu-id="2539e-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="2539e-109">每个拉取请求的页面都包含有关所有更改的详细信息、有关发布内容的评论列表，以及社区的其他成员可用于提供反馈和建议的一组审阅工具。</span><span class="sxs-lookup"><span data-stu-id="2539e-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="2539e-110">尽管 Git 的完整教程超出了本指南的范围，但我们可建议使用以下链接获取有关学习 Git 的更多资源：</span><span class="sxs-lookup"><span data-stu-id="2539e-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="2539e-111">[了解 git](https://www.atlassian.com/git)： Atlassian 中的一组 Git 教程。</span><span class="sxs-lookup"><span data-stu-id="2539e-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="2539e-112">[Visual Studio Code 中的版本控制](https://code.visualstudio.com/docs/editor/versioncontrol)：有关如何使用 Visual Studio Code 作为 GIT 的 GUI 的指南。</span><span class="sxs-lookup"><span data-stu-id="2539e-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="2539e-113">[GitHub 学习实验室](https://lab.github.com/)：一组用于使用 Git、GitHub 和相关技术的在线课程。</span><span class="sxs-lookup"><span data-stu-id="2539e-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="2539e-114">[可视化 git](https://git-school.github.io/visualizing-git/)：可视化 git 命令如何更改存储库状态的交互式工具。</span><span class="sxs-lookup"><span data-stu-id="2539e-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="2539e-115">[使用 git (EPQIS 2016) 进行版本控制 ](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes))：一个面向科学计算的 git 教程。</span><span class="sxs-lookup"><span data-stu-id="2539e-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="2539e-116">[了解 Git 分支](https://learngitbranching.js.org/)：一组交互式的分支和变基测验题，有助于了解新的 Git 功能。</span><span class="sxs-lookup"><span data-stu-id="2539e-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="2539e-117">什么是拉取请求？</span><span class="sxs-lookup"><span data-stu-id="2539e-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="2539e-118">说到前面说过，有必要花一些时间来指出拉取请求 **是** 什么。</span><span class="sxs-lookup"><span data-stu-id="2539e-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="2539e-119">使用 Git 时，任何更改都表示为 _提交_ ，这些更改描述了这些更改在发生更改之前如何与存储库的状态相关。</span><span class="sxs-lookup"><span data-stu-id="2539e-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="2539e-120">我们经常会绘制一个图表，其中的提交以包含上一次提交的箭头的圆圈形式绘制。</span><span class="sxs-lookup"><span data-stu-id="2539e-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="2539e-121">假设已在 _分支_ 中启动了一个名为的发布 `feature` 。</span><span class="sxs-lookup"><span data-stu-id="2539e-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="2539e-122">那么， **Microsoft/量子** 的分叉可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="2539e-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![GitHub 中的工作分支](~/media/git-workflow-step0.png)

<span data-ttu-id="2539e-124">如果你在本地存储库中进行更改，则可以将另一个存储库中的更改 _拉取_ 到你的存储库中，以捕获上游发生的任何更改。</span><span class="sxs-lookup"><span data-stu-id="2539e-124">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![从上游存储库中提取和合并更改](~/media/git-workflow-step1.png)

<span data-ttu-id="2539e-126">拉取请求的工作方式相同，但反向：打开拉取请求时，请求上游存储库请求你的参与。</span><span class="sxs-lookup"><span data-stu-id="2539e-126">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![请求将更改请求回原始存储库](~/media/git-workflow-step2.png)

<span data-ttu-id="2539e-128">当你打开某个存储库的拉取请求时，GitHub 将为社区中的其他人提供机会，以查看你的更改摘要、对这些更改进行评论，并为如何帮助做出更好的贡献提供建议。</span><span class="sxs-lookup"><span data-stu-id="2539e-128">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![GitHub 中的拉取请求的屏幕截图](~/media/pull-request-header.png)

<span data-ttu-id="2539e-130">使用此过程可帮助我们使用 GitHub 功能提高贡献，并为量程编程社区维护高质量的产品。</span><span class="sxs-lookup"><span data-stu-id="2539e-130">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="2539e-131">如何发出拉取请求</span><span class="sxs-lookup"><span data-stu-id="2539e-131">How to Make a Pull Request</span></span> ##

<span data-ttu-id="2539e-132">可以通过两种主要方法来生成拉取请求。</span><span class="sxs-lookup"><span data-stu-id="2539e-132">There are two main ways to make a pull request.</span></span>  
<span data-ttu-id="2539e-133">对于仅影响单个文件的小更改，可以使用 GitHub web 界面来完全联机请求拉取请求。</span><span class="sxs-lookup"><span data-stu-id="2539e-133">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span> <span data-ttu-id="2539e-134">只需导航到要编辑的文件，然后使用编辑图标。</span><span class="sxs-lookup"><span data-stu-id="2539e-134">Simply navigate to the file you want to edit and use the edit icon.</span></span>  
<span data-ttu-id="2539e-135">对于更复杂的发布，通常会将存储库克隆到本地计算机，以便首先准备拉取请求。</span><span class="sxs-lookup"><span data-stu-id="2539e-135">For more complicated contributions, it's most often easier to clone the repository to your local computer to prepare for a pull request first.</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="2539e-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2539e-136">Next steps</span></span> ##

<span data-ttu-id="2539e-137">恭喜你使用 Git 帮助你了解量程开发工具包社区！</span><span class="sxs-lookup"><span data-stu-id="2539e-137">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="2539e-138">若要了解有关如何编写代码的详细信息，请继续阅读下面的指南。</span><span class="sxs-lookup"><span data-stu-id="2539e-138">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="2539e-139">了解如何编写代码</span><span class="sxs-lookup"><span data-stu-id="2539e-139">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)
