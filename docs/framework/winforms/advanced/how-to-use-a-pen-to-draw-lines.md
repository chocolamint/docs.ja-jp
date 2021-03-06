---
title: '方法 : ペンを使用して線を描画する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
ms.assetid: 0828c331-a438-4bdd-a4d6-3ef1e59e8795
ms.openlocfilehash: 6a728bcaf9946b2b92ce0ee97599f4c4fd0fea69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522986"
---
# <a name="how-to-use-a-pen-to-draw-lines"></a>方法 : ペンを使用して線を描画する
線を描画する必要があります、<xref:System.Drawing.Graphics>オブジェクトおよび<xref:System.Drawing.Pen>オブジェクト。 <xref:System.Drawing.Graphics>オブジェクトは、提供、<xref:System.Drawing.Graphics.DrawLine%2A>メソッド、および<xref:System.Drawing.Pen>オブジェクトは、線、色、太さなどの機能を格納します。  
  
## <a name="example"></a>例  
 次の例から行を描画する (20, 10) に (300, 100)。 最初のステートメントを使用して、<xref:System.Drawing.Pen.%23ctor%2A>黒のペンを作成するクラスのコンス トラクターです。 渡される 1 つの引数、<xref:System.Drawing.Pen.%23ctor%2A>コンス トラクターは、<xref:System.Drawing.Color>で作成されたオブジェクト、<xref:System.Drawing.Color.FromArgb%2A>メソッドです。 作成に使用される値、<xref:System.Drawing.Color>オブジェクト — (255, 0、0, 0): 色のアルファ、赤、緑、および青のコンポーネントに対応します。 これらの値は、不透明な黒のペンを定義します。  
  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 前の例は、Windows フォームで使用するために設計されていて、<xref:System.Windows.Forms.PaintEventArgs> イベント ハンドラーのパラメーターである `e`<xref:System.Windows.Forms.Control.Paint> を必要とします。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Drawing.Pen>  
 [ペンを使用した直線と図形の描画](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [GDI+ でのペン、直線、および四角形](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)
