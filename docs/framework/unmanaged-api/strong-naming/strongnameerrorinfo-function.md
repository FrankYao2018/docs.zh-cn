---
title: "StrongNameErrorInfo 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameErrorInfo
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: StrongNameErrorInfo
helpviewer_keywords: StrongNameErrorInfo function [.NET Framework strong naming]
ms.assetid: e91bf8c3-7c26-4732-938e-2e5b04abfc99
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0fbe77f16ed022458a036b6627b82f80d194276c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="strongnameerrorinfo-function"></a><span data-ttu-id="b49b2-102">StrongNameErrorInfo 函数</span><span class="sxs-lookup"><span data-stu-id="b49b2-102">StrongNameErrorInfo Function</span></span>
<span data-ttu-id="b49b2-103">获取引发的强名称函数之一的最后一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="b49b2-103">Gets the last error code that was raised by one of the strong name functions.</span></span>  
  
 <span data-ttu-id="b49b2-104">此函数已弃用。</span><span class="sxs-lookup"><span data-stu-id="b49b2-104">This function has been deprecated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b49b2-105">语法</span><span class="sxs-lookup"><span data-stu-id="b49b2-105">Syntax</span></span>  
  
```  
HRESULT StrongNameErrorInfo ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="b49b2-106">返回值</span><span class="sxs-lookup"><span data-stu-id="b49b2-106">Return Value</span></span>  
 <span data-ttu-id="b49b2-107">设置由某一个强名称函数的最后一个 COM 错误代码。</span><span class="sxs-lookup"><span data-stu-id="b49b2-107">The last COM error code set by one of the strong name functions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b49b2-108">备注</span><span class="sxs-lookup"><span data-stu-id="b49b2-108">Remarks</span></span>  
 <span data-ttu-id="b49b2-109">大多数的强名称方法返回一个简单`true`或`false`成功完成的指示。</span><span class="sxs-lookup"><span data-stu-id="b49b2-109">Most of the strong name methods return a simple `true` or `false` indication of successful completion.</span></span> <span data-ttu-id="b49b2-110">使用`StrongNameErrorInfo`函数可检索指定生成的强名称函数的最后一个错误的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="b49b2-110">Use the `StrongNameErrorInfo` function to retrieve an HRESULT that specifies the last error generated by the strong name functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b49b2-111">要求</span><span class="sxs-lookup"><span data-stu-id="b49b2-111">Requirements</span></span>  
 <span data-ttu-id="b49b2-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b49b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b49b2-113">**标头：** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b49b2-113">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b49b2-114">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="b49b2-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b49b2-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b49b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b49b2-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b49b2-116">See Also</span></span>  
 [<span data-ttu-id="b49b2-117">强命名的全局静态函数</span><span class="sxs-lookup"><span data-stu-id="b49b2-117">Strong Naming Global Static Functions</span></span>](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)