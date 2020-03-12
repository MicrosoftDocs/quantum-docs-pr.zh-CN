---
title: 媒体自述文件
description: 有关上传图像的提示
author: geduardo
ms.author: v-edsanc@microsoft.com
ms.date: 03/04/2020
ms.topic: readme
ms.openlocfilehash: a4922e28a8fc5ddfb4cbc80302e23869154234d8
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024179"
---
# <a name="readme"></a>自述文件
**重要提示**：若要使图像在暗色模式下正确呈现，必须避免使用透明胶片。
- 对于 .jpg 文件，不需要执行任何操作，因为文件格式不支持透明元素。
- 对于 .png 文件，必须添加白色背景或将 alpha 通道的值更改为100。 若要在 Windows 中执行此操作，最简单的方法是在 "画图" 中打开文件，并保存原始文件 overwritting。
- 对于 svg 文件，必须在最底层添加白色矩形。 可以通过 Inkscape 执行此操作：
  - 打开 svg 文件。
  - 选择 "方形 maker" 工具，并在原始图形顶部绘制一个白色矩形。
  - 通过单击黑色箭头或按 F1，选择工具 "选择和转换对象"。
  - 选择矩形时，单击工具栏元素 "将选定内容减小到底部（结束）"。
  - 用鼠标或箭头键调整矩形。
