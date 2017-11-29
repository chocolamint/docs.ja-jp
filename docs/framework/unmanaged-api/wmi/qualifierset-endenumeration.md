---
title: "QualifierSet_EndEnumeration 関数 (アンマネージ API リファレンス)"
description: "QualifierSet_EndEnumeration 関数は、列挙を終了します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_EndEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_EndEnumeration
helpviewer_keywords: QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868a0c0ba5abb880af201ce73b35f5ffed6f223
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetendenumeration-function"></a><span data-ttu-id="83eb0-103">QualifierSet_EndEnumeration 関数</span><span class="sxs-lookup"><span data-stu-id="83eb0-103">QualifierSet_EndEnumeration function</span></span>
<span data-ttu-id="83eb0-104">呼び出しで開始された列挙の終了、 [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)関数。</span><span class="sxs-lookup"><span data-stu-id="83eb0-104">Terminates the enumeration begun with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="83eb0-105">構文</span><span class="sxs-lookup"><span data-stu-id="83eb0-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a><span data-ttu-id="83eb0-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="83eb0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="83eb0-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="83eb0-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="83eb0-108">[in]ポインター、 [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="83eb0-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="83eb0-109">戻り値</span><span class="sxs-lookup"><span data-stu-id="83eb0-109">Return value</span></span>

<span data-ttu-id="83eb0-110">この関数によって返される次の値がで定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができます、定数としてコードで定義します。</span><span class="sxs-lookup"><span data-stu-id="83eb0-110">The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:</span></span>

|<span data-ttu-id="83eb0-111">定数</span><span class="sxs-lookup"><span data-stu-id="83eb0-111">Constant</span></span>  |<span data-ttu-id="83eb0-112">値</span><span class="sxs-lookup"><span data-stu-id="83eb0-112">Value</span></span>  |<span data-ttu-id="83eb0-113">説明</span><span class="sxs-lookup"><span data-stu-id="83eb0-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | <span data-ttu-id="83eb0-114">0</span><span class="sxs-lookup"><span data-stu-id="83eb0-114">0</span></span> | <span data-ttu-id="83eb0-115">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="83eb0-115">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="83eb0-116">コメント</span><span class="sxs-lookup"><span data-stu-id="83eb0-116">Remarks</span></span>

<span data-ttu-id="83eb0-117">この関数への呼び出しをラップする、 [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="83eb0-117">This function wraps a call to the [IWbemQualifierSet::EndEnumeration](https://msdn.microsoft.com/library/aa391865(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="83eb0-118">この呼び出しは、推奨しますが、必要ありません。</span><span class="sxs-lookup"><span data-stu-id="83eb0-118">This call is recommended, but not required.</span></span> <span data-ttu-id="83eb0-119">すぐに、列挙体に関連付けられているリソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="83eb0-119">It immediately releases resources associated with the enumeration.</span></span>

## <a name="requirements"></a><span data-ttu-id="83eb0-120">要件</span><span class="sxs-lookup"><span data-stu-id="83eb0-120">Requirements</span></span>  

<span data-ttu-id="83eb0-121">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="83eb0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="83eb0-122">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="83eb0-122">**Header:** WMINet_Utils.idl</span></span>  
  
<span data-ttu-id="83eb0-123">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="83eb0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83eb0-124">関連項目</span><span class="sxs-lookup"><span data-stu-id="83eb0-124">See also</span></span>  
[<span data-ttu-id="83eb0-125">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="83eb0-125">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)