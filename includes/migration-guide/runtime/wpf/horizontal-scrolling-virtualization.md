### <a name="horizontal-scrolling-and-virtualization"></a>水平方向スクロールと仮想化

|   |   |
|---|---|
|説明|この変更は、メインのスクロール方向と直交する方向で独自に仮想化を行う <xref:System.Windows.Controls.ItemsControl?displayProperty=name> に適用されます (代表的な例は、EnableColumnVirtualization=&quot;True&quot; である <xref:System.Windows.Controls.DataGrid?displayProperty=name> です)。  特定の水平方向スクロール操作の結果が変更され、比較可能な垂直操作の結果により類似した、より直感的な結果が生成されるようになりました。このような操作としては &quot;ここにスクロール&quot; や &quot;右端&quot; などがあり、水平スクロール バーを右クリックすると表示されるメニューから名前を使用することができます。  これらの両方の計算、候補オフセットと呼び出し<xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)>です。新しいオフセットの概念にスクロール後&quot;ここ&quot;または&quot;エッジを右&quot;の値を除外仮想化されたコンテンツが新しく変更されたために変更可能性がある<xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name>です。 .Net 4.6.2 では、前に、スクロール操作だけを使用して候補のオフセットができない場合でも&quot;ここ&quot;または、&quot;エッジを右&quot;かを確認します。  その結果、スクロールつまみの &quot;バウンス&quot; などの効果が得られます。次に例を示します。 たとえば、<xref:System.Windows.Controls.DataGrid?displayProperty=name> で ExtentWidth=1000 および Width=200 であるものとします。  &quot;右端&quot; へのスクロールでは、1000 - 200 = 800 という候補オフセットを使用します。  そのオフセットへのスクロール時に、新しい列が非仮想化されます。これらの列が非常に広いため、<xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> を 2000 に変更したとします。  スクロールは HorizontalOffset=800 で終了し、つまみはスクロールバーの中央付近 (正確には 800/2000 = 40%) に &quot;戻り&quot; ます。このような状況が発生した場合、変更は新しい候補オフセットを再計算し、再試行することになっています。 (垂直方向スクロールの動作は既にこのようになっています)。この変更により、エンド ユーザーにはより予測可能で直感的なエクスペリエンスが提供されるようになりますが、水平方向スクロール後の <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> の正確な値に依存するアプリに影響する可能性もあります。これは、エンド ユーザーによる呼び出しであるか、<xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset(System.Double)> の明示的な呼び出しであるかは関係ありません。|
|提案される解決策|<xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset?displayProperty=name> の予測値を使用するアプリを、非仮想化により <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> が変更される可能性のある水平方向スクロール後の実際の値 (および <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth?displayProperty=name> の値) を取得するように変更する必要があります。|
|スコープ|マイナー|
|Version|4.6.2|
|型|ランタイム|
|影響を受ける API|<ul><li><xref:System.Windows.Controls.Primitives.IScrollInfo?displayProperty=nameWithType></li></ul>|
