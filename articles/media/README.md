---
title: 媒体自述文件
description: 有关上传图像的提示
author: geduardo
ms.author: v-edsanc
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: bf28f57820e95bbbf81f5ac7ade582d89b945a26
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834527"
---
# <a name="readme"></a><span data-ttu-id="6f5fc-103">自述文件</span><span class="sxs-lookup"><span data-stu-id="6f5fc-103">README</span></span>
<span data-ttu-id="6f5fc-104">**重要提示**：若要使图像在暗色模式下正确呈现，必须避免使用透明胶片。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-104">**IMPORTANT**: to have the images rendering properly in dark mode you must avoid transparencies.</span></span>
- <span data-ttu-id="6f5fc-105">对于 .jpg 文件，不需要执行任何操作，因为文件格式不支持透明元素。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-105">For .jpg files you don't need to do anything since the file format doesn't support transparent elements.</span></span>
- <span data-ttu-id="6f5fc-106">对于 .png 文件，必须添加白色背景或将 alpha 通道的值更改为100。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-106">For .png files you must add a white background or change the value of the alpha channel to 100.</span></span> <span data-ttu-id="6f5fc-107">若要在 Windows 中执行此操作，最简单的方法是在 "画图" 中打开文件，并保存原始文件 overwritting。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-107">The easiest way to do this in Windows is by opening the file in Paint and saving, overwritting the original file.</span></span>
- <span data-ttu-id="6f5fc-108">对于 svg 文件，必须在最底层添加白色矩形。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-108">For .svg files you must add a white rectangle in the lowest layer.</span></span> <span data-ttu-id="6f5fc-109">可以通过 Inkscape 执行此操作：</span><span class="sxs-lookup"><span data-stu-id="6f5fc-109">You can do this with Inkscape:</span></span>
  - <span data-ttu-id="6f5fc-110">打开 svg 文件。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-110">Open the .svg file.</span></span>
  - <span data-ttu-id="6f5fc-111">选择 "方形 maker" 工具，并在原始图形顶部绘制一个白色矩形。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-111">Select the square maker tool and draw a white rectangle on top of the original figure.</span></span>
  - <span data-ttu-id="6f5fc-112">通过单击黑色箭头或按 F1，选择工具 "选择和转换对象"。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-112">Select the tool "Select and transform objects" by clicking in the dark arrow or pressing F1.</span></span>
  - <span data-ttu-id="6f5fc-113">选择矩形后，单击工具栏元素中的 "将选定内容减小 (结束) "。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-113">While having the rectangle selected, click in the toolbar element "Lower selection to bottom (End)".</span></span>
  - <span data-ttu-id="6f5fc-114">用鼠标或箭头键调整矩形。</span><span class="sxs-lookup"><span data-stu-id="6f5fc-114">Adjust the rectangle with the mouse or the arrow keys.</span></span>
