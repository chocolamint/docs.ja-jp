---
title: Skip While 句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: a3c0749560d8cea1e46d96298347ce54f0bf9185
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863375"
---
# <a name="skip-while-clause-visual-basic"></a>Skip While 句 (Visual Basic)
指定された条件が `true` である限り、コレクションの要素をバイパスし、残りの要素を返します。  
  
## <a name="syntax"></a>構文  
  
```  
Skip While expression  
```  
  
## <a name="parts"></a>指定項目  
  
|用語|定義|  
|---|---|  
|`expression`|必須。 要素をテストするための条件を表す式。 式を返す必要があります、`Boolean`値またはそれと同等の機能など、`Integer`として評価される、`Boolean`します。|  
  
## <a name="remarks"></a>Remarks  
 `Skip While`句まで、指定されたクエリ結果の先頭から要素をバイパスする`expression`返します`false`します。 後`expression`返します`false`クエリは、残りのすべての要素を返します。 `expression`残りの結果は無視されます。  
  
 `Skip While`句とは異なります、`Where`句を`Where`を特定の条件を満たさないクエリからすべての要素を除外する句を使用できます。 `Skip While`句は、条件が満たされていませんが、初めてまでのみ要素を除外します。 `Skip While`句は、順序付けられたクエリ結果を使用しているときに最も役立ちます。  
  
 使用してクエリ結果の先頭からの結果の特定の数をバイパスできる、`Skip`句。  
  
## <a name="example"></a>例  
 次のコード例では、`Skip While`米国から最初の顧客が見つかるまで、結果をバイパスする句。  
  
 [!code-vb[VbSimpleQuerySamples#3](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-while-clause_1.vb)]  
  
## <a name="see-also"></a>関連項目  
 [Visual Basic における LINQ の概要](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [クエリ](../../../visual-basic/language-reference/queries/index.md)  
 [Select 句](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 句](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Skip 句](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take While 句](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [WHERE 句](../../../visual-basic/language-reference/queries/where-clause.md)
