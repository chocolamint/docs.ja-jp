---
title: '方法 : StatusStrip 内で Spring プロパティを対話的に使用する'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: 3319771cfcf671f5457bd3e95d264a694f9fa1c6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744191"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>方法 : StatusStrip 内で Spring プロパティを対話的に使用する
<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティを使用して、<xref:System.Windows.Forms.StatusStrip> コントロールに <xref:System.Windows.Forms.ToolStripStatusLabel> コントロールを配置できます。 <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティは、<xref:System.Windows.Forms.ToolStripStatusLabel> コントロールが <xref:System.Windows.Forms.StatusStrip> コントロールの使用可能な領域を自動的に入力するかどうかを決定します。  
  
## <a name="example"></a>例  
 次のコード例は、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティを使用して、<xref:System.Windows.Forms.StatusStrip> コントロールに <xref:System.Windows.Forms.ToolStripStatusLabel> コントロールを配置する方法を示します。 <xref:System.Windows.Forms.ToolStripItem.Click> イベント ハンドラーは、exclusive-or (XOR) 演算を実行して、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> プロパティの値を切り替えます。  
  
 このコード例を使用するコンパイルし、アプリケーションを実行し、をクリックし、**中間 (スプリング)** 上、<xref:System.Windows.Forms.StatusStrip>コントロールの値を切り替えます、<xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>プロパティ。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 この例で必要な要素は次のとおりです。  
  
-   System.Design、System.Drawing、および System.Windows.Forms の各アセンブリへの参照。  
  
 Visual Basic または Visual c# のコマンドラインからこの例の構築方法の詳細については、次を参照してください。 [、コマンドラインからビルドする](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)または[コマンド ライン ビルドで csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)します。 新しいプロジェクトにコードを貼り付けることによって、この例では、Visual Studio を構築することもできます。  「[方法: 完成した Windows フォーム コードの例を Visual Studio を使ってコンパイルして実行する](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))」も参照してください。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [ToolStrip コントロール](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
