---
title: ICorDebugMergedAssemblyRecord 接口
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793060"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>ICorDebugMergedAssemblyRecord 接口
提供有关合并的程序集的信息。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetCulture 方法](icordebugmergedassemblyrecord-getculture-method.md)|获取程序集的区域性名称字符串。|  
|[GetIndex 方法](icordebugmergedassemblyrecord-getindex-method.md)|获取程序集的前缀索引。|  
|[GetPublicKey 方法](icordebugmergedassemblyrecord-getpublickey-method.md)|获取程序集的公钥。|  
|[GetPublicKeyToken 方法](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|获取程序集的公钥标记。|  
|[GetSimpleName 方法](icordebugmergedassemblyrecord-getsimplename-method.md)|获取程序集的简单名。|  
|[GetVersion 方法](icordebugmergedassemblyrecord-getversion-method.md)|获取程序集的版本信息。|  
  
## <a name="remarks"></a>备注  
  
> [!NOTE]
> 此接口仅适用于 .NET Native。 如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试接口](debugging-interfaces.md)
- [调试](index.md)
