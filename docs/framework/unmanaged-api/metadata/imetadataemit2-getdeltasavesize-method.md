---
title: "IMetaDataEmit2::GetDeltaSaveSize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.GetDeltaSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::GetDeltaSaveSize
helpviewer_keywords:
- IMetaDataEmit2::GetDeltaSaveSize method [.NET Framework metadata]
- GetDeltaSaveSize method [.NET Framework metadata]
ms.assetid: 036db5e7-8211-4645-9a34-03d1a89be955
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 562b7be418a4a4e335350adf5131178e406b5a07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2getdeltasavesize-method"></a>IMetaDataEmit2::GetDeltaSaveSize 方法
获取一个值，该值元数据大小而导致的当前的编辑并继续会话中的任何更改。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetDeltaSaveSize (  
    [in]  CorSaveSize  fSave,  
    [out] DWORD        *pdwSaveSize  
);  
```  
  
#### <a name="parameters"></a>参数  
 `fSave`  
 [in]之一[CorSaveSize](../../../../docs/framework/unmanaged-api/metadata/corsavesize-enumeration.md)值，指示所需的精度的级别。 对于.NET Framework 2.0 版中，将忽略此参数。  
  
 `pdwSaveSize`  
 [out]中的元数据的大小的变化。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
