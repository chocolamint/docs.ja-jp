---
title: "StrongNameSignatureSize 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureSize
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureSize
helpviewer_keywords: StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7944763f1c1379228e715b18b563e7aa776fedac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="4b9f9-102">StrongNameSignatureSize 関数</span><span class="sxs-lookup"><span data-stu-id="4b9f9-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="4b9f9-103">厳密な名前の署名のサイズを返します。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="4b9f9-104">`StrongNameSignatureSize`遅延署名アセンブリを作成するときに、ファイルに予約する領域の量を決定するコンパイラで通常に使用されます。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="4b9f9-105">この関数は廃止されました。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-105">This function has been deprecated.</span></span> <span data-ttu-id="4b9f9-106">使用して、 [iclrstrongname::strongnamesignaturesize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)メソッド代わりにします。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b9f9-107">構文</span><span class="sxs-lookup"><span data-stu-id="4b9f9-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b9f9-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="4b9f9-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="4b9f9-109">[in]型の構造体[PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)厳密な名前の署名を生成するためのキー ペアの公開部分を格納しています。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="4b9f9-110">[in]サイズをバイト単位での`pbPublicKeyBlob`します。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="4b9f9-111">[in]厳密な名前の署名を格納するために必要なバイト数。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b9f9-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="4b9f9-112">Return Value</span></span>  
 <span data-ttu-id="4b9f9-113">`true`正常に終了します。それ以外の場合、`false`です。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b9f9-114">コメント</span><span class="sxs-lookup"><span data-stu-id="4b9f9-114">Remarks</span></span>  
 <span data-ttu-id="4b9f9-115">場合、`StrongNameSignatureSize`関数が正常に完了、呼び出すしていない、 [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)最後に生成されたエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b9f9-116">要件</span><span class="sxs-lookup"><span data-stu-id="4b9f9-116">Requirements</span></span>  
 <span data-ttu-id="4b9f9-117">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b9f9-118">**ヘッダー:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4b9f9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4b9f9-119">**ライブラリ:** MsCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="4b9f9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b9f9-120">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b9f9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9f9-121">関連項目</span><span class="sxs-lookup"><span data-stu-id="4b9f9-121">See Also</span></span>  
 [<span data-ttu-id="4b9f9-122">StrongNameSignatureSize メソッド</span><span class="sxs-lookup"><span data-stu-id="4b9f9-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [<span data-ttu-id="4b9f9-123">ICLRStrongName インターフェイス</span><span class="sxs-lookup"><span data-stu-id="4b9f9-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)