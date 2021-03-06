---
title: ImportTypes2 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51c696679626a598be422376e9dc89b5add1773d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400486"
---
# <a name="importtypes2-method"></a>ImportTypes2 方法
启动导入的类型。 调用此方法可开始从通过导入每个作用域导入类型[ImportFile 方法](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 要导入到其中的程序集的 ID。  
  
 `FileToken`  
 要从中导入到的文件 ID。  
  
 `dwScope`  
 要从中导入的从零开始作用域。  
  
 `phEnum`  
 接收给定范围中的类型的枚举器句柄。  
  
 `ppImportScope`  
 （可选） 接收[IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)接口。  
  
 `pdwCountOfTypes`  
 （可选） 指定范围内接收的类型的计数。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h  
  
## <a name="see-also"></a>请参阅  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
