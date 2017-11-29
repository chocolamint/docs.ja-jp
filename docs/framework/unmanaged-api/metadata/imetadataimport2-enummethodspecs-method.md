---
title: "IMetaDataImport2::EnumMethodSpecs メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.EnumMethodSpecs
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: db1968c73d5a1c6e0687bc86f249c70b6c21712c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a><span data-ttu-id="27046-102">IMetaDataImport2::EnumMethodSpecs メソッド</span><span class="sxs-lookup"><span data-stu-id="27046-102">IMetaDataImport2::EnumMethodSpecs Method</span></span>
<span data-ttu-id="27046-103">トークンの MethodSpec トークンが指定した MethodDef または MemberRef に関連付けられている配列の列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="27046-103">Gets an enumerator for an array of MethodSpec tokens associated with the specified MethodDef or MemberRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27046-104">構文</span><span class="sxs-lookup"><span data-stu-id="27046-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="27046-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="27046-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="27046-106">[入力、出力].列挙子へのポインター`rMethodSpecs`です。</span><span class="sxs-lookup"><span data-stu-id="27046-106">[in, out] A pointer to the enumerator for `rMethodSpecs`.</span></span>  
  
 `tk`  
 <span data-ttu-id="27046-107">[in]MethodSpec トークンは、列挙するメソッドを表す MemberRef または MethodDef トークンです。</span><span class="sxs-lookup"><span data-stu-id="27046-107">[in] The MemberRef or MethodDef token that represents the method whose MethodSpec tokens are to be enumerated.</span></span> <span data-ttu-id="27046-108">場合の値`tk`が 0 (ゼロ) のスコープ内のすべての MethodSpec トークンが列挙されます場合、。</span><span class="sxs-lookup"><span data-stu-id="27046-108">If the value of `tk` is 0 (zero), all MethodSpec tokens in the scope will be enumerated.</span></span>  
  
 `rMethodSpecs`  
 <span data-ttu-id="27046-109">[out]列挙する MethodSpec トークンの配列。</span><span class="sxs-lookup"><span data-stu-id="27046-109">[out] The array of MethodSpec tokens to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="27046-110">[in]配置するトークンの要求の最大数`rMethodSpecs`です。</span><span class="sxs-lookup"><span data-stu-id="27046-110">[in] The requested maximum number of tokens to place in `rMethodSpecs`.</span></span>  
  
 `pcMethodSpecs`  
 <span data-ttu-id="27046-111">[out]返されたトークンの数が内に配置`rMethodSpecs`です。</span><span class="sxs-lookup"><span data-stu-id="27046-111">[out] The returned number of tokens placed in `rMethodSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27046-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="27046-112">Return Value</span></span>  
  
|<span data-ttu-id="27046-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="27046-113">HRESULT</span></span>|<span data-ttu-id="27046-114">説明</span><span class="sxs-lookup"><span data-stu-id="27046-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="27046-115">`EnumMethodSpecs`正常に返されます。</span><span class="sxs-lookup"><span data-stu-id="27046-115">`EnumMethodSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="27046-116">`phEnum`メンバーの要素がありません。</span><span class="sxs-lookup"><span data-stu-id="27046-116">`phEnum` has no member elements.</span></span> <span data-ttu-id="27046-117">この場合、`pcMethodSpecs`は 0 (ゼロ) に設定します。</span><span class="sxs-lookup"><span data-stu-id="27046-117">In this case, `pcMethodSpecs` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27046-118">要件</span><span class="sxs-lookup"><span data-stu-id="27046-118">Requirements</span></span>  
 <span data-ttu-id="27046-119">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="27046-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27046-120">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27046-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27046-121">**ライブラリ:** MsCorEE.dll にリソースとして使用</span><span class="sxs-lookup"><span data-stu-id="27046-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27046-122">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27046-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27046-123">関連項目</span><span class="sxs-lookup"><span data-stu-id="27046-123">See Also</span></span>  
 [<span data-ttu-id="27046-124">IMetaDataImport2 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27046-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="27046-125">IMetaDataImport インターフェイス</span><span class="sxs-lookup"><span data-stu-id="27046-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)