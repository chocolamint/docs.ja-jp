---
title: "IMetaDataAssemblyEmit::DefineAssembly メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 86002eb38d72ee628dbf54d0b5691f0816e6f996
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="28087-102">IMetaDataAssemblyEmit::DefineAssembly メソッド</span><span class="sxs-lookup"><span data-stu-id="28087-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="28087-103">作成、`Assembly`指定されたアセンブリのメタデータ含む構造体し、関連付けられたメタデータ トークンを返します。</span><span class="sxs-lookup"><span data-stu-id="28087-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28087-104">構文</span><span class="sxs-lookup"><span data-stu-id="28087-104">Syntax</span></span>  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28087-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="28087-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="28087-106">[in]アセンブリは厳密な名前いない場合は、アセンブリ、または NULL の発行者を識別する公開キー。</span><span class="sxs-lookup"><span data-stu-id="28087-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="28087-107">[in]バイト サイズ`pbPublicKey`です。</span><span class="sxs-lookup"><span data-stu-id="28087-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="28087-108">[in]Sha-1 アルゴリズムを指定するには、アセンブリ、または NULL でファイルの暗号化に使用するハッシュ アルゴリズムの識別子。</span><span class="sxs-lookup"><span data-stu-id="28087-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="28087-109">[in]アセンブリの人間が判読できるテキストの名前。</span><span class="sxs-lookup"><span data-stu-id="28087-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="28087-110">この値は 1024 文字を超えない必要があります。</span><span class="sxs-lookup"><span data-stu-id="28087-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="28087-111">[in]アセンブリのバージョン、プラットフォーム、およびロケール情報を格納している ASSEMBLYMETADATA インスタンスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="28087-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="28087-112">[in]組み合わせた[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)アセンブリの機能を記述する値。</span><span class="sxs-lookup"><span data-stu-id="28087-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="28087-113">[out]メタデータ トークンへのポインター。</span><span class="sxs-lookup"><span data-stu-id="28087-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28087-114">コメント</span><span class="sxs-lookup"><span data-stu-id="28087-114">Remarks</span></span>  
 <span data-ttu-id="28087-115">1 つだけ`Assembly`メタデータ構造体は、マニフェスト内で定義することができます。</span><span class="sxs-lookup"><span data-stu-id="28087-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28087-116">要件</span><span class="sxs-lookup"><span data-stu-id="28087-116">Requirements</span></span>  
 <span data-ttu-id="28087-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="28087-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28087-118">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28087-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28087-119">**ライブラリ:** MsCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="28087-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28087-120">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28087-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28087-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="28087-121">See Also</span></span>  
 [<span data-ttu-id="28087-122">IMetaDataAssemblyEmit インターフェイス</span><span class="sxs-lookup"><span data-stu-id="28087-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)