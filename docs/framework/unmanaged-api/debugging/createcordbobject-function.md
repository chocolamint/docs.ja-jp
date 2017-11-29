---
title: "CreateCordbObject 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCoredbObject
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 06e08148e5526d65d82eca52ffe8db66a4e7df6e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="createcordbobject-function"></a><span data-ttu-id="aa5f1-102">CreateCordbObject 関数</span><span class="sxs-lookup"><span data-stu-id="aa5f1-102">CreateCordbObject Function</span></span>
<span data-ttu-id="aa5f1-103">デバッガー インターフェイスを作成します ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md))、リモート プロセスでマネージ デバッグ セッションをインスタンス化するための機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-103">Creates a debugger interface ([ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) that provides functionality for instantiating a managed debugging session on a remote process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa5f1-104">構文</span><span class="sxs-lookup"><span data-stu-id="aa5f1-104">Syntax</span></span>  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa5f1-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="aa5f1-105">Parameters</span></span>  
 `iDebuggerVersion`  
 <span data-ttu-id="aa5f1-106">[in] ターゲット プロセスのデバッガー バージョン。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-106">[in] Debugger version of the target process.</span></span> <span data-ttu-id="aa5f1-107">リモート デバッグの場合、このパラメーターは CorDebugVersion_2_0 である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-107">This parameter must be CorDebugVersion_2_0 for remote debugging.</span></span>  
  
 `ppCordb`  
 <span data-ttu-id="aa5f1-108">[out]キャストするオブジェクトへのポインターへのポインター、 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)インターフェイスし、が返されます。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-108">[out] Pointer to a pointer to an object that will be cast to an [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface and returned.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa5f1-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="aa5f1-109">Return Value</span></span>  
 <span data-ttu-id="aa5f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa5f1-110">S_OK</span></span>  
 <span data-ttu-id="aa5f1-111">プロセス内の CLR 数が正常に判別され、対応するハンドルとパスの配列が正しく入力されました。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-111">The number of CLRs in the process was successfully determined, and the corresponding handle and path arrays were properly filled.</span></span>  
  
 <span data-ttu-id="aa5f1-112">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="aa5f1-112">E_INVALIDARG</span></span>  
 <span data-ttu-id="aa5f1-113">`ppCordb` が null であるか、または `iDebuggerVersion` が CorDebugVersion_2_0 ではありません。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-113">`ppCordb` is null, or `iDebuggerVersion` is not CorDebugVersion_2_0.</span></span>  
  
 <span data-ttu-id="aa5f1-114">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="aa5f1-114">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="aa5f1-115">`ppCordb` 用に十分なメモリを割り当てることができません。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-115">Unable to allocate enough memory for `ppCordb`</span></span>  
  
 <span data-ttu-id="aa5f1-116">E_FAIL (またはその他の E_ リターン コード)</span><span class="sxs-lookup"><span data-stu-id="aa5f1-116">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="aa5f1-117">その他のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-117">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa5f1-118">コメント</span><span class="sxs-lookup"><span data-stu-id="aa5f1-118">Remarks</span></span>  
 <span data-ttu-id="aa5f1-119">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)で返されるインターフェイス`ppCordb`はすべてのマネージ デバッグ サービスの最上位レベルのデバッグ インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-119">The [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) interface that is returned in `ppCordb` is the top-level debugging interface for all managed debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa5f1-120">要件</span><span class="sxs-lookup"><span data-stu-id="aa5f1-120">Requirements</span></span>  
 <span data-ttu-id="aa5f1-121">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="aa5f1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa5f1-122">**ヘッダー:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="aa5f1-122">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="aa5f1-123">**ライブラリ:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="aa5f1-123">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="aa5f1-124">**.NET framework のバージョン:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="aa5f1-124">**.NET Framework Versions:** 3.5 SP1</span></span>