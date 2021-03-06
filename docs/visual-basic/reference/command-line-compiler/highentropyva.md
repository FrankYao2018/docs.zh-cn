---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fef3f922d3089eaca1762ffe35fa38cfe94baf22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656306"
---
# <a name="-highentropyva-visual-basic"></a>-highentropyva (Visual Basic)
指示是否 64 位可执行文件或可执行文件标记的[/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md)编译器选项支持高熵地址空间布局随机化 (ASLR)。  
  
## <a name="syntax"></a>语法  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a>自变量  
 `+` &#124; `-`  
 可选。 选项默认处于关闭状态，或如果你指定`-highentropyva-`。 如果你指定的选项位于`-highentropyva`或`-highentropyva+`。  
  
## <a name="remarks"></a>备注  
 如果指定此选项时，Windows 内核的兼容版本可以使用更高程度的熵时内核的 ASLR 一部分随机进程的地址空间布局。 如果内核使用更高程度的平均信息量，可以将更多的地址分配到例如堆栈或堆的内存区域。 因此，猜测特定内存区域的位置会更加困难。  
  
 选项上时，目标可执行文件和任何模块上它依赖于它必须是能够处理这些模块作为 64 位进程运行时会大于 4 千兆字节 (GB) 的指针值。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
