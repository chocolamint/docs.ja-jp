---
title: 方法 :デザイナーを使って ToolBar ボタンのアイコンを定義する
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- buttons [Windows Forms], images
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: d848f38e-67f2-49d4-8e88-01c845c06c02
ms.openlocfilehash: f26e21d824420fc4ff0480de21f260309c5c2e11
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856609"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button-using-the-designer"></a>方法 :デザイナーを使って ToolBar ボタンのアイコンを定義する
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip> コントロールは、<xref:System.Windows.Forms.ToolBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ToolBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。  
  
 <xref:System.Windows.Forms.ToolBar> ボタンは、ユーザーがそれらに含まれるを簡単に識別のアイコンを表示できません。 これは画像を追加することによって実現、<xref:System.Windows.Forms.ImageList>コンポーネントと関連付けること、<xref:System.Windows.Forms.ToolBar>コントロール。  
  
 次の手順が必要です、 **Windows アプリケーション**プロジェクトが含まれているフォームを<xref:System.Windows.Forms.ToolBar>コントロールと<xref:System.Windows.Forms.ImageList>コンポーネント。 このようなプロジェクトの設定の詳細については、次を参照してください。[方法: Windows アプリケーション プロジェクトを作成](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)と[方法: Windows フォームにコントロールを追加](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)します。  
  
> [!NOTE]
>  実際に画面に表示されるダイアログ ボックスとメニュー コマンドは、アクティブな設定またはエディションによっては、ヘルプの説明と異なる場合があります。 設定を変更するには、 **[ツール]** メニューの **[設定のインポートとエクスポート]** をクリックします。 詳細については、「[Visual Studio IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」を参照してください。  
  
### <a name="to-set-an-icon-for-a-toolbar-button-at-design-time"></a>デザイン時にツール バー ボタンのアイコンを設定するには  
  
1.  イメージを追加、<xref:System.Windows.Forms.ImageList>コンポーネント。 詳細については、次を参照してください。[方法: デザイナーを使って ImageList イメージを追加または](../../../../docs/framework/winforms/controls/how-to-add-or-remove-imagelist-images-with-the-designer.md)します。  
  
2.  選択、<xref:System.Windows.Forms.ToolBar>フォーム上のコントロール。  
  
3.  **プロパティ**ウィンドウで、設定、<xref:System.Windows.Forms.ToolBar>コントロールの<xref:System.Windows.Forms.ToolBar.ImageList%2A>プロパティを<xref:System.Windows.Forms.ImageList>コンポーネント。  
  
4.  をクリックして、<xref:System.Windows.Forms.ToolBar>コントロールの<xref:System.Windows.Forms.ToolBar.Buttons%2A>プロパティを選択し、省略記号ボタンをクリックします (![VisualStudioEllipsesButton スクリーン ショット](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) ボタンを**ツールバー ・ ボタン コレクション エディター**します。  
  
5.  使用して、**追加**にボタンを追加するボタン、<xref:System.Windows.Forms.ToolBar>コントロール。  
  
6.  **プロパティ**ウィンドウの右側にあるペインに表示される、**ツールバー ・ ボタン コレクション エディター**、設定、<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>一覧で、値の 1 つは、各ツール バー ボタンのプロパティを追加したイメージの描画、<xref:System.Windows.Forms.ImageList>コンポーネント。  
  
## <a name="see-also"></a>関連項目  
 <xref:System.Windows.Forms.ToolBar>  
 [方法: ツール バー ボタンのメニュー イベントをトリガーする](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)  
 [ToolBar コントロール](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)  
 [ImageList コンポーネント](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
