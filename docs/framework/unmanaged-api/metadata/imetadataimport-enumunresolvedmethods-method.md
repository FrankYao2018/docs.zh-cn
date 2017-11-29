---
title: "IMetaDataImport::EnumUnresolvedMethods 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUnresolvedMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3c7709180e5b7811379c25977f8a8d23b91adb3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="4b5a2-102">IMetaDataImport::EnumUnresolvedMethods 方法</span><span class="sxs-lookup"><span data-stu-id="4b5a2-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="4b5a2-103">枚举表示当前元数据范围内未解析的方法的 MemberDef 标记。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b5a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b5a2-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b5a2-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b5a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4b5a2-106">[在中，out]枚举数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4b5a2-107">这必须在首次调用此方法为 NULL。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="4b5a2-108">[out]用于存储 MemberDef 标记的数组。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4b5a2-109">[in] `rMethods` 数组的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4b5a2-110">[out]在中返回的 MemberDef 标记数`rMethods`。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b5a2-111">返回值</span><span class="sxs-lookup"><span data-stu-id="4b5a2-111">Return Value</span></span>  
  
|<span data-ttu-id="4b5a2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b5a2-112">HRESULT</span></span>|<span data-ttu-id="4b5a2-113">描述</span><span class="sxs-lookup"><span data-stu-id="4b5a2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4b5a2-114">`EnumUnresolvedMethods`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4b5a2-115">没有要枚举的标记。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4b5a2-116">在这种情况下，`pcTokens`为零。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b5a2-117">备注</span><span class="sxs-lookup"><span data-stu-id="4b5a2-117">Remarks</span></span>  
 <span data-ttu-id="4b5a2-118">无法解析的方法是指已声明但未实现。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="4b5a2-119">如果标记的方法，枚举中包括的一种方法`miForwardRef`和任一`mdPinvokeImpl`或`miRuntime`设置为零。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="4b5a2-120">换而言之，无法解析的方法是标记的类方法`miForwardRef`但其不在 （通过 PInvoke 到达） 的非托管代码中实现也不会由运行时本身在内部实现</span><span class="sxs-lookup"><span data-stu-id="4b5a2-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="4b5a2-121">在枚举排除在模块作用域 （全局） 或在接口或抽象类定义的所有方法。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b5a2-122">要求</span><span class="sxs-lookup"><span data-stu-id="4b5a2-122">Requirements</span></span>  
 <span data-ttu-id="4b5a2-123">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b5a2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b5a2-124">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4b5a2-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b5a2-125">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4b5a2-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b5a2-126">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b5a2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b5a2-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b5a2-127">See Also</span></span>  
 [<span data-ttu-id="4b5a2-128">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="4b5a2-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="4b5a2-129">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="4b5a2-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)