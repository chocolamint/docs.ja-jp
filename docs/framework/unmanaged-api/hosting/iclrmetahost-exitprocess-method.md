---
title: "ICLRMetaHost::ExitProcess メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.ExitProcess
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 10fb9bef99a90a76ea5bb1f4abe73cd756717285
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostexitprocess-method"></a><span data-ttu-id="c0218-102">ICLRMetaHost::ExitProcess メソッド</span><span class="sxs-lookup"><span data-stu-id="c0218-102">ICLRMetaHost::ExitProcess Method</span></span>
<span data-ttu-id="c0218-103">正常に読み込まれているすべてのランタイムをシャット ダウンしようとして、プロセスを終了します。</span><span class="sxs-lookup"><span data-stu-id="c0218-103">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="c0218-104">置き換えるソフトウェア更新プログラム、 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="c0218-104">Supersedes the [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0218-105">構文</span><span class="sxs-lookup"><span data-stu-id="c0218-105">Syntax</span></span>  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0218-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c0218-106">Parameters</span></span>  
 `iExitCode`  
 <span data-ttu-id="c0218-107">[in]プロセスの終了コード。</span><span class="sxs-lookup"><span data-stu-id="c0218-107">[in] The exit code for the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c0218-108">戻り値</span><span class="sxs-lookup"><span data-stu-id="c0218-108">Return Value</span></span>  
 <span data-ttu-id="c0218-109">このメソッドに値が戻りませんため、その戻り値が定義されていません。</span><span class="sxs-lookup"><span data-stu-id="c0218-109">This method never returns, so its return value is undefined.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0218-110">コメント</span><span class="sxs-lookup"><span data-stu-id="c0218-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0218-111">要件</span><span class="sxs-lookup"><span data-stu-id="c0218-111">Requirements</span></span>  
 <span data-ttu-id="c0218-112">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="c0218-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0218-113">**ヘッダー:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c0218-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c0218-114">**ライブラリ:** MSCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0218-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0218-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0218-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0218-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="c0218-116">See Also</span></span>  
 [<span data-ttu-id="c0218-117">ICLRMetaHost インターフェイス</span><span class="sxs-lookup"><span data-stu-id="c0218-117">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="c0218-118">ホスティング</span><span class="sxs-lookup"><span data-stu-id="c0218-118">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)