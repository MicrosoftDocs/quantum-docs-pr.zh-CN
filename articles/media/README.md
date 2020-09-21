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
# <a name="readme"></a>自述文件
**重要提示**：若要使图像在暗色模式下正确呈现，必须避免使用透明胶片。
- 对于 .jpg 文件，不需要执行任何操作，因为文件格式不支持透明元素。
- 对于 .png 文件，必须添加白色背景或将 alpha 通道的值更改为100。 若要在 Windows 中执行此操作，最简单的方法是在 "画图" 中打开文件，并保存原始文件 overwritting。
- 对于 svg 文件，必须在最底层添加白色矩形。 可以通过 Inkscape 执行此操作：
  - 打开 svg 文件。
  - 选择 "方形 maker" 工具，并在原始图形顶部绘制一个白色矩形。
  - 通过单击黑色箭头或按 F1，选择工具 "选择和转换对象"。
  - 选择矩形后，单击工具栏元素中的 "将选定内容减小 (结束) "。
  - 用鼠标或箭头键调整矩形。
