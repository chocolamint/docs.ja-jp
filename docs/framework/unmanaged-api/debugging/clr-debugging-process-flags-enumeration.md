---
title: "CLR_DEBUGGING_PROCESS_FLAGS 列挙体"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CLR_DEBUGGING_PROCESS_FLAGS
api_location: mscordbi.dll
api_type: COM
f1_keywords: CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords: CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5040b1e1eb7ec4bd814329de156fcdfeb9c383c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="d44fe-102">CLR_DEBUGGING_PROCESS_FLAGS 列挙体</span><span class="sxs-lookup"><span data-stu-id="d44fe-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="d44fe-103">によって使用されている値を提供、 [iclrdebugging::openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="d44fe-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d44fe-104">構文</span><span class="sxs-lookup"><span data-stu-id="d44fe-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d44fe-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="d44fe-105">Members</span></span>  
  
|<span data-ttu-id="d44fe-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="d44fe-106">Member</span></span>|<span data-ttu-id="d44fe-107">説明</span><span class="sxs-lookup"><span data-stu-id="d44fe-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="d44fe-108">このランタイムには、送信する非 catch アップ マネージ デバッガー イベントがあります。</span><span class="sxs-lookup"><span data-stu-id="d44fe-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="d44fe-109">キャッチアップおよび非 catch アップ イベントを区別する「解説」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d44fe-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="d44fe-110">保留中であるマネージ イベントは、<xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType>要求します。</span><span class="sxs-lookup"><span data-stu-id="d44fe-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d44fe-111">コメント</span><span class="sxs-lookup"><span data-stu-id="d44fe-111">Remarks</span></span>  
 <span data-ttu-id="d44fe-112">キャッチアップ イベントには、プロセス、アプリケーション ドメイン、アセンブリ、モジュール、および現在の状態には、プロセスにアタッチした後、デバッガーになるスレッドの作成の通知が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d44fe-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="d44fe-113">示される非 catch アップ イベント、`CLR_DEBUGGING_MANAGED_EVENT_PENDING`すべて他のデバッガー イベント、例外などが含まれて、マネージ デバッグ アシスタント (MDA) 通知フラグを設定します。</span><span class="sxs-lookup"><span data-stu-id="d44fe-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="d44fe-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`フラグ終了例外とキャンセル可能なマネージ デバッガーをアタッチ要求を区別するためにランタイムを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d44fe-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d44fe-115">要件</span><span class="sxs-lookup"><span data-stu-id="d44fe-115">Requirements</span></span>  
 <span data-ttu-id="d44fe-116">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="d44fe-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d44fe-117">**ヘッダー:** Metahost.idl、Metahost.h</span><span class="sxs-lookup"><span data-stu-id="d44fe-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="d44fe-118">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d44fe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d44fe-119">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d44fe-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d44fe-120">関連項目</span><span class="sxs-lookup"><span data-stu-id="d44fe-120">See Also</span></span>  
 [<span data-ttu-id="d44fe-121">列挙体のデバッグ</span><span class="sxs-lookup"><span data-stu-id="d44fe-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="d44fe-122">デバッグ</span><span class="sxs-lookup"><span data-stu-id="d44fe-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)