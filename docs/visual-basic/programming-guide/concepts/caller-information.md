---
title: "调用方信息 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: 15d556eb-4d0c-4497-98a3-7f60abb7d6a1
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9a4b63fb424ad6aef9d1bd56f43ccccd79f0b9b3
ms.lasthandoff: 03/13/2017

---
# <a name="caller-information-visual-basic"></a>调用方信息 (Visual Basic)
通过使用调用方信息特性，可获取有关方法的调用方的信息。 可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。 此信息有助于跟踪、调试和创建诊断工具。  
  
 若要获取此信息，可以使用应用于可选参数的特性，每个特性都具有默认值。 下表列出了在中定义的调用方信息特性<xref:System.Runtime.CompilerServices?displayProperty=fullName>命名空间︰</xref:System.Runtime.CompilerServices?displayProperty=fullName>  
  
|特性|描述|类型|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|包含调用方的源文件的完整路径。 这是编译时的文件路径。|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|源文件中调用方法的行号。|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|调用方的方法或属性名称。 请参阅[成员名称](#MEMBERNAMES)本主题中更高版本。|`String`|  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用调用方信息特性。 每次调用 `TraceMessage` 方法时，调用方信息将替换为可选参数的变量。  
  
```vb  
Private Sub DoProcessing()  
    TraceMessage("Something happened.")  
End Sub  
  
Public Sub TraceMessage(message As String,  
        <System.Runtime.CompilerServices.CallerMemberName> Optional memberName As String = Nothing,  
        <System.Runtime.CompilerServices.CallerFilePath> Optional sourcefilePath As String = Nothing,  
        <System.Runtime.CompilerServices.CallerLineNumber()> Optional sourceLineNumber As Integer = 0)  
  
    System.Diagnostics.Trace.WriteLine("message: " & message)  
    System.Diagnostics.Trace.WriteLine("member name: " & memberName)  
    System.Diagnostics.Trace.WriteLine("source file path: " & sourcefilePath)  
    System.Diagnostics.Trace.WriteLine("source line number: " & sourceLineNumber)  
End Sub  
  
' Sample output:  
'   message: Something happened.  
'   member name: DoProcessing  
'   source file path: C:\Users\username\Documents\Visual Studio 2012\Projects\CallerInfoVB\CallerInfoVB\Form1.vb  
'   source line number: 15  
```  
  
## <a name="remarks"></a>备注  
 你必须为每个可选参数指定显式默认值。 不能将调用方信息特性应用于未指定为可选的参数。  
  
 调用方信息特性不会使参数成为可选参数。 相反，它们会在忽略此参数时影响传入的默认值。  
  
 在编译时，调用方信息值将作为文本传入中间语言 (IL)。 与不同的结果<xref:System.Exception.StackTrace%2A>例外情况之外，结果的属性不受模糊处理。</xref:System.Exception.StackTrace%2A>  
  
 你可显式提供可选参数来控制调用方信息或隐藏调用方信息。  
  
###  <a name="MEMBERNAMES"></a>成员名称  
 可以使用 `CallerMemberName` 特性来避免将成员名称指定为所调用的方法的 `String` 参数。 通过使用此方法，可以避免此问题，**重命名重构**不会更改`String`值。 此好处对于以下任务特别有用：  
  
-   使用跟踪和诊断例程。  
  
-   实现<xref:System.ComponentModel.INotifyPropertyChanged>接口绑定数据时。</xref:System.ComponentModel.INotifyPropertyChanged> 此接口允许对象的属性通知绑定控件该属性已更改，以便此控件能够显示更新的信息。 如果没有 `CallerMemberName` 特性，则必须将属性名称指定为文本。  
  
 以下图表显示在使用 `CallerMemberName` 特性时返回的成员名称。  
  
|调用发生中|成员名称结果|  
|-------------------------|------------------------|  
|方法、属性或事件|从中发起调用的方法、属性或事件的名称。|  
|构造函数|字符串“.ctor”|  
|静态构造函数|字符串“.cctor”|  
|析构函数|字符串“Finalize”|  
|用户定义的运算符或转换|为成员生成的名称，例如，“op_Addition”。|  
|特性构造函数|要应用特性的成员的名称。 如果该特性是成员中的任何元素（如参数、返回值或泛型参数），则此结果是与该元素关联的成员的名称。|  
|无包含的成员（例如，程序集级别或应用于类型的特性）|可选参数的默认值。|  
  
## <a name="see-also"></a>另请参阅  
 [特性 (Visual Basic)](../../../visual-basic/language-reference/attributes.md)   
 [公共特性 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)   
 [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [编程概念 (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)