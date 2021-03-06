---
title: 構造体 (C# プログラミング ガイド)
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 27d4b0d7edf1b5e89e84ac1df5783d68ebb4efe0
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259494"
---
# <a name="structs-c-programming-guide"></a>構造体 (C# プログラミング ガイド)

構造体は [struct](../../language-reference/keywords/struct.md) キーワードを使って定義します。次はその例です。  
  
[!code-csharp[csProgGuideObjects#39](./codesnippet/CSharp/structs_1.cs)]  
  
構造体の構文はクラスとほとんど同じです。 構造体の名前を、有効な C# の[識別子名](../inside-a-program/identifier-names.md)にする必要があります。 構造体は次の点でクラスよりも制限されています。  
  
- 構造体宣言内では、const または static と宣言されているフィールド以外は初期化できません。  
- 構造体では、既定のコンストラクター (パラメーターなしのコンストラクター) やファイナライザーを宣言できません。  
- 構造体は、割り当て時にコピーされます。 構造体を新しい変数に割り当てると、すべてのデータがコピーされ、新しいコピーを変更しても、元のコピーのデータは変更されません。 これは、`Dictionary<string, myStruct>` などの値の型のコレクションを使用する際に重要です。  
- 参照型であるクラスとは異なり、構造体は値型です。  
- クラスとは異なり、構造体は `new` 演算子を使用せずにインスタンス化できます。  
- 構造体は、パラメーターのあるコンストラクターを宣言できます。 
- 構造体は、他の構造体やクラスから継承できず、基本クラスになることはできません。 すべての構造体が <xref:System.ValueType> を直接継承し、System.ValueType は <xref:System.Object> を継承します。  
- 構造体は、インターフェイスを実装できます。  
- 構造体は、null 許容型として使うことができ、null 値を割り当てることができます。  
  
## <a name="related-sections"></a>関連項目  

詳細情報  
  
- [構造体の使用](using-structs.md)
- [コンストラクター](constructors.md)
- [Null 許容型](../nullable-types/index.md)
- [方法: メソッドに構造体を渡すこととクラス参照を渡すことの違いを理解する](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [方法: 構造体間にユーザー定義の変換を実装する](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a>関連項目

- [C# プログラミング ガイド](../index.md)
- [クラスと構造体](index.md)
- [クラス](classes.md)
- [識別子名](../inside-a-program/identifier-names.md)
