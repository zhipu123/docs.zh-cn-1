---
title: "CorGenericParamAttr 枚举"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorGenericParamAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorGenericParamAttr
helpviewer_keywords: CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e40613d790baed5bd89bee1e1f5ca57043bfe76a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="corgenericparamattr-enumeration"></a>CorGenericParamAttr 枚举
包含值，用于描述<xref:System.Type>对于泛型类型，为调用中使用的参数[imetadataemit2:: Definegenericparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,   
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,   
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`gpVarianceMask`|参数的方差仅适用于接口和委托的泛型参数。|  
|`gpNonVariant`|指示缺少变化。|  
|`gpCovariant`|指示协方差。|  
|`gpContravariant`|指示逆变。|  
|`gpSpecialConstraintMask`|特殊约束可应用于任何<xref:System.Type>参数。|  
|`gpNoSpecialConstraint`|指示没有约束应用于<xref:System.Type>参数。|  
|`gpReferenceTypeConstraint`|指示<xref:System.Type>参数必须是引用类型。|  
|`gpNotNullableValueTypeConstraint`|指示<xref:System.Type>参数必须是值类型，不能为 null 的值。|  
|`gpDefaultConstructorConstraint`|指示<xref:System.Type>参数必须具有默认公共构造函数不采用参数。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorHdr.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [Metadata 枚举](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
