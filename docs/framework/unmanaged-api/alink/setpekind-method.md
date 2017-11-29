---
title: "SetPEKind メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a><span data-ttu-id="83577-102">SetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="83577-102">SetPEKind Method</span></span>
<span data-ttu-id="83577-103">ポータブル実行可能ファイルの種類、コンピューター固有またはコンピューターにもとらわれないのいずれかを判断します。</span><span class="sxs-lookup"><span data-stu-id="83577-103">Determines the portable executable type, either machine-specific or machine-agnostic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83577-104">構文</span><span class="sxs-lookup"><span data-stu-id="83577-104">Syntax</span></span>  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a><span data-ttu-id="83577-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83577-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="83577-106">アセンブリの ID です。</span><span class="sxs-lookup"><span data-stu-id="83577-106">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="83577-107">PE の種類を設定する対象のファイルのトークン。</span><span class="sxs-lookup"><span data-stu-id="83577-107">Token of file for which the PE type is to be set.</span></span> <span data-ttu-id="83577-108">場合、NULL を指定できます`AssemblyID`はバインドされていない netmodule を示しません。</span><span class="sxs-lookup"><span data-stu-id="83577-108">Can be NULL if `AssemblyID` does not indicate an unbound netmodule.</span></span>  
  
 `dwPEKind`  
 <span data-ttu-id="83577-109">によって示される、PE の種類、 [CorPEKind 列挙型](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)です。</span><span class="sxs-lookup"><span data-stu-id="83577-109">The type of PE, as indicated by the [CorPEKind Enumeration](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).</span></span>  
  
 `dwMachine`  
 <span data-ttu-id="83577-110">ターゲット コンピューターのアーキテクチャ、NT ヘッダーで指定されています。</span><span class="sxs-lookup"><span data-stu-id="83577-110">The target machine architecture, as indicated in the NT header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83577-111">戻り値</span><span class="sxs-lookup"><span data-stu-id="83577-111">Return Value</span></span>  
 <span data-ttu-id="83577-112">メソッドが成功した場合は、S_OK を返します。</span><span class="sxs-lookup"><span data-stu-id="83577-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83577-113">要件</span><span class="sxs-lookup"><span data-stu-id="83577-113">Requirements</span></span>  
 <span data-ttu-id="83577-114">Alink.h が必要です。</span><span class="sxs-lookup"><span data-stu-id="83577-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83577-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="83577-115">See Also</span></span>  
 [<span data-ttu-id="83577-116">GetPEKind メソッド</span><span class="sxs-lookup"><span data-stu-id="83577-116">GetPEKind Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [<span data-ttu-id="83577-117">IALink2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83577-117">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="83577-118">IALink インターフェイス</span><span class="sxs-lookup"><span data-stu-id="83577-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="83577-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="83577-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)