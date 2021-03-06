---
title: 複合型
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 8daeac8309434b3c4e090d8e75f2de02d63e8b11
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756814"
---
# <a name="complex-type"></a>複合型
A*複合型*豊富な構造化されたプロパティを定義するためのテンプレートです[エンティティ型](../../../../docs/framework/data/adonet/entity-type.md)またはその他の複合型。 各テンプレートには、以下が含まれています。  
  
-   一意の名前  (必須)  
  
    > [!NOTE]
    >  複合型の名前は、同じ名前空間のエンティティ型の名前と同じにすることはできません。  
  
-   1 つまたは複数の形式でデータ[プロパティ](../../../../docs/framework/data/adonet/property.md)です。 (省略可能)   
  
    > [!NOTE]
    >  複合型のプロパティには、別の複合型を使用することができます。  
  
 複合型は、プリミティブ型のプロパティまたはその他の複合型の形式でデータ ペイロードを伝達できる点がエンティティ型と似ています。 ただし、複合型とエンティティ型の間にはいくつかの重要な違いがあります。  
  
-   複合型には ID がないため、独立して存在することができません。 複合型は、エンティティ型またはその他の複合型のプロパティとしてのみ存在できます。  
  
-   複合型には参加できません[アソシエーション](../../../../docs/framework/data/adonet/association-type.md)です。 アソシエーションの end にも複雑な型であることができ、したがって[ナビゲーション プロパティ](../../../../docs/framework/data/adonet/navigation-property.md)複合型で定義することはできません。  
  
## <a name="example"></a>例  
 [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)概念スキーマ定義言語と呼ばれるドメイン固有言語 (DSL) を使用して ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 概念モデルを定義します。 次の CSDL は、`StreetAddress`、`City`、`StateOrProvince`、`Country`、および `PostalCode` のプリミティブ型のプロパティの複合型 Address を定義しています。  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 エンティティ型のプロパティとして複合型 `Address` (上の図) を定義するには、エンティティ型の定義にプロパティの型を宣言する必要があります。 次の CSDL は、エンティティ型 (Publisher) に複合型として `Address` プロパティを宣言しています。  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>関連項目  
 [Entity Data Model キーの概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
