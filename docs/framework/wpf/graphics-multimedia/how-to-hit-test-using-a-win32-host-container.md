---
title: 如何：使用 Win32 宿主容器执行命中测试
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: 01c6a9dad6fccb38be4f240d0900727f776fd2b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33560503"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>如何：使用 Win32 宿主容器执行命中测试
你可以创建视觉对象中的[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]窗口是通过为可视对象提供宿主窗口容器。 若要为包含的视觉对象提供事件处理，需要处理传递到宿主窗口容器的消息筛选器循环的消息。 请参阅[教程： 在 Win32 应用程序中承载视觉对象](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)有关如何托管中的可视化对象的详细信息[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]窗口。  
  
## <a name="example"></a>示例  
 下面的代码演示如何设置鼠标事件处理程序[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]用作视觉对象的宿主容器的窗口。  
  
 [!code-csharp[VisualsHitTesting#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 下面的示例演示如何设置以捕获特定的鼠标事件的响应的命中测试。  
  
 [!code-csharp[VisualsHitTesting#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 <xref:System.Windows.Interop.HwndSource>对象代表[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]中的内容[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]窗口。 值<xref:System.Windows.Interop.HwndSource.RootVisual%2A>属性<xref:System.Windows.Interop.HwndSource>对象表示可视化树层次结构中的最顶层节点。  
  
 上的命中测试的完整示例对象使用 Win32 宿主容器，请参阅[命中测试的 Win32 间的互操作示例](http://go.microsoft.com/fwlink/?LinkID=159995)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Interop.HwndSource>  
 [可视化层中的命中测试](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)  
 [教程：在 Win32 应用程序中承载视觉对象](../../../../docs/framework/wpf/graphics-multimedia/tutorial-hosting-visual-objects-in-a-win32-application.md)
