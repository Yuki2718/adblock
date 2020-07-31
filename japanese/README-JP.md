### Yuki's uBlock Japanese filters （雪フィルタ）

<strong>Youtubeの動画内広告について：2020年7月現在、誰にも不具合を起こさず広告だけを確実にブロックする方法は知られていません（[参考](https://www.reddit.com/r/uBlockOrigin/comments/ht4o9h/youtube_adserrors_solutions/)）。当フィルタでは不具合を起こしにくそうなルールのみ採用し、リスクのあるルールはParanoidに入れています。また、この広告は特定のアカウントでのみ表示され、対象の動画やログインしているか否か、さらに閲覧方法によっても違うようです。広告が出てしまった場合、Paranoidを有効にしてみてください。</strong>

日本語サイト閲覧者がPCで遭遇する広告・解析のほとんどを除去できる、uBlock Origin用フィルタです（上級者向け）。

- AdGuardなど他のプラットフォームでは機能しないルールがあるため、使用はお勧めしません<sup>1</sup>。uBlock-for-firefox-legacyもサポートしません。
- モバイルサイトは対象外です。280blockerさんの[フィルタ](https://280blocker.net/download/)やもちおさんの[たまごフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/tamago.html)など、モバイル用のフィルタを使用してください。
- ログインが必要なサイトは原則、対象外です。これらのサイトでの不具合や広告漏れにつきましては、ログや開発者ツールのスクリーンショット等、こちらがログインせずとも現象や解決を確認できる手段の提供をお願いすることがあります。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt&title=Yuki's%20uBlock%20Japanese%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt)

1: AdGuardで使用する場合、最大の問題となるのはspecific-genericとdenyallowでしょう。前者は簡単に対応できますが、後者は大幅な書き直しが必要なため私はやりません。

#### 特徴

<details>
<summary><strong>網羅性</strong></summary>

日本語サイト<sup>2</sup>のPC用公開フィルタとして、2020年7月現在メンテナンスされているものの中で最高のブロック性能（非表示ではない）を持ちます。とくにアクセス解析については他の日本用フィルタではおまけ程度にしか扱われていませんが、当フィルタはできるだけブロックします。そのため不具合（誤爆と呼ばれる）も多いと思われ<sup>3</sup>、例外フィルタの扱いに長けた上級者向けのフィルタです。広告ブロック初心者の方は、もちおさんが提供なさっている[もちフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/mochi.html)も検討してみてください。

2: いくつかの日本用フィルタと同様、日本語話者がよく利用すると思われる海外サイトにも対応しています。

3: 後述のようにEasyListやEasyPrivacyから多くのルールを取り入れているものの、誤爆率の高いルールは除外しています。また私の知るこれらのフィルタによる誤爆で、未報告または報告済みだが未対処のものにも対応しています。一方、EasyPrivacyなどに含まれていないアクセス解析も（誤爆率の高そうなもの以外）多く盛り込んでいます。利用者様からの不具合報告が十分集まれば、将来的に上級者向けという断りを外すかもしれません。

</details>

<details>
<summary><strong>ブロック優先</strong></summary>

ブロック可能な対象はできる限りブロックします。これは当然のことではなく、他のフィルタではブロック可能でも非表示で済ましているケースが多数あります<sup>4,5</sup>。ブロックが困難な場合、Firefox上ではHTMLフィルタリングにより除去を試みています（不可能な場合もあります）。ブロックさえできればよいという方は「汎用的な要素隠蔽フィルターを無視する」にチェックを入れてください。表示崩れや多少の広告漏れと引き換えに、パフォーマンスを高めることができます。Yuki's uBlock Japanese filtersファミリーは、その場合でもある程度の性能を維持できます<sup>6</sup>。

4: 「要素をブロック」機能でMyフィルターを作っている人も同様です。画像についてはブロックしてくれることもありますが、イニシエイターとなるスクリプトまではお手上げです。非表示についても質の低いルールが多いです。同機能は[あくまで補助であり](https://github.com/uBlockOrigin/uBlock-issues/issues/1058#issuecomment-631459847)、過剰に頼るべきではありません。

5: uBlock Originポップアップパネルの目玉アイコンをクリックして×印をつけると、ブロックされていない広告が浮かび上がってきます。元に戻すにはもう一度クリックして×印を外してください。

6: 当サイトのフィルタは[specific-generic](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic)を利用したおそらく最初の公開フィルタです。なお、汎用非表示フィルタの数はパフォーマンスに[影響しません](https://github.com/uBlockOrigin/uBlock-issues/issues/738#issuecomment-619450820)。パフォーマンスを高めたいなら、完全に切る他ありません。

</details>

<details>
<summary><strong>高効率</strong></summary>

uBlock Originはトークン化という仕組みにより高速処理を実現しています<sup>7</sup>。ルールがトークン化可能なら、ルール数は処理時間に[影響しません](https://www.wilderssecurity.com/threads/ublock-a-lean-and-fast-blocker.365273/page-155#post-2831026)<sup>8</sup>。当フィルタはできるだけトークン化を意識したルールを心がけており（例外あり）<sup>9</sup>、また非表示フィルタについても[最小マッチング](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters#important)の原則を満たしつつ、できるだけ高速で誤爆の少ないセレクタを使うよう心がけているつもりです。

7: 簡単に言うと、リクエストとルールそれぞれから抽出したトークンを使ってマッチする見込みがありそうなルールを絞り込んでいます。一般的なリクエストに対して大部分のルールは無いも同然であり、計算量のオーダーはルール数に依存しません。検索エンジンの転置インデックスに近いです。

8: 実測するのが早いです（レイテンシの影響が大きいのでキャッシュは維持してください）。[こちら](https://brave.com/improved-ad-blocker-performance/)はBraveがuBlock Originの方式を導入した時の記事ですが、16,000個ルールを追加しても個々のリクエスト処理にかかる時間は1μsも変わらないことがわかります。メモリ消費はルール数に応じて増えますが、PCで問題になる量ではありません。逆にいうと非効率なルールが増えるほど遅くなるため、そうしたルールは対象を絞り込む必要があります。

9: ABP文法と異なり、[単語境界を意識](https://github.com/gorhill/uBlock/issues/1065)する必要があります。たとえば`/example`というルールは、（他の部分でトークンマッチが起きない限り）`/example1`というリクエストをブロックしません。明示的に`*`を追加するとブロックするようになりますが（`/example*`）、これは`example`のトークン化を妨げます。主要な[bad token](https://github.com/gorhill/uBlock/blob/381498daa2a9ce089a69d044760190b1dd14b5ac/src/js/static-net-filtering.js#L2062)（トークン化されない文字列）も覚えた方がよいでしょう。

</details>

<details>
<summary><strong>併用可</strong></summary>

ブロック対象に違いがなく、パフォーマンスや誤爆の観点から問題がない場合、[EasyList](https://easylist.to/easylist/easylist.txt), [EasyPrivacy](https://easylist.to/easylist/easyprivacy.txt), [Peter Lowe's Ad and tracking server list](https://pgl.yoyo.org/adservers/serverlist.php), [uBlock 内製フィルター](https://github.com/uBlockOrigin/uAssets), [AdGuard Base](https://kb.adguard.com/en/general/adguard-ad-filters#english), [AdGuard Tracking Protection](https://kb.adguard.com/en/general/adguard-ad-filters#privacy), [Fanboy Enhanced Tracking](https://www.fanboy.co.nz/enhancedstats.txt), [280blocker 広告ドメインリスト](https://280blocker.net/files/280blocker_domain_ag.txt)など、併用されることが多そうなフィルタとルールを統一しています<sup>10</sup>。これによりフィルター一覧でのフィルタ有効数<sup>11</sup>が正しく表示されるだけでなく、非表示フィルタの多重適用も回避できます。つまり単独で使えるばかりでなく、上述の各種フィルタと併用した場合でも無駄がありません<sup>12</sup>。なお、280blocker 広告ドメインリスト以外の日本用フィルタとの併用はお勧めしません。

10: 当フィルタはCC BY-SA 4.0のもとに配布しており、こればuBlock 内製フィルターと280blocker以外を正しく継承（デュアルライセンス、バージョン違い）しています。uBlock内製フィルターはGPLv3ですが、AdGuardなどと比較して癖のないルールであり、一般的なフィルタ作者が思いつく範囲だと思います（スクリプトレットルールを比較していただくとわかるように、実際に有効なルール以外は採用していません。古いスクリプトルールは不要になったものが多く、適宜報告しています。さらに言えば、もともと私が提案ないしプルリクエストしたルールもあります）。280blockerはCC BY-NC-NDですが、参考にしているのはドメインリストのみであり、これは書き方がほぼ一意に決まってしまうため問題ないと考えます。また一部、[EasyList China](http://abpchina.org/forum/forum.php)および[RU AdList](https://forums.lanik.us/viewforum.php?f=102)からとられたルールがある他、[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)を参考にしたルールが少なからずあります（著作権上、そのままの使用はなるべく避けましたが、どうしても同じになってしまったものもあります）。

11: 有効数には優先順位がありませんので、Yuki's uBlock Japanese filtersの内どれだけ使われているか知りたい場合、一度Yuki's uBlock Japanese filtersのチェックを外して他のフィルタを更新し、再度チェックを入れてください。

12: これらのフィルタによる誤爆をより網羅的に修正していることもあり、既にEasyList等を併用されている方にはもっともおすすめできる日本用フィルタと言ってよいでしょう。逆に、既存の日本用フィルタとこれらの併用は無駄が多く、Braveの日本用フィルタに採用されなかった[一因](https://github.com/brave/adblock-lists/issues/355#issuecomment-609680337)となっています。

</details>

#### 対象
- 広告、アフィリエイトリンク
- 一部のプロモーションコンテンツ（ネイティブ広告）
- アクセス解析、行動追跡、ヒートマップ
- バグレポート
- サードパーティーまたはスクリプトを伴うアクセスカウンター
- 主に上記をブロックしたため生じた枠や不要なスペース
- アンチ広告ブロック
- 迷惑・有害なポップアップ、ポップアンダー、リダイレクト
- 一部の悪質サイト（ビジターアンケート詐欺など）
- トラッキングパラメータを含むリンクからの移動<sup>13</sup>

13: <strong>「uBlock Origin は、このページの読み込みをブロックしました」画面で右側の虫眼鏡アイコンをクリックすると、トラッキングパラメータを除いたURLが表示され、そのままクリックできます。</strong>

#### 対象外
- サイトの内容と強く関連しており（例：具体的な商品のレビュー）、かつ量が過剰でなくユーザーに不利益・不快感を与えない広告（「ゲームのブログだからゲームの広告」程度では強く関連しているとみなしません）
- 画像を伴わないアフィリエイトリンクの一般非表示（個別に対応）
- ファーストパーティーの単純なCGI/SSIアクセスカウンターで、広範に使われているもの以外

### Yuki's uBlock Japanese filters - Paranoid　（大雪フィルタ）

Yuki's uBlock Japanese filtersに追加できるフィルタで、多少の不具合を覚悟でより強固にブロックします。自己責任で使用してください。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Paranoid">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt)

### Yuki's uBlock Japanese filters - Social　（あられフィルタ）

ソーシャル要素をブロックするフィルタです。一部、[AdGuard Social media filter](https://kb.adguard.com/en/general/adguard-ad-filters#social)と共通のルールがあります。ブロック優先主義のため、非表示にしかできないものは迷惑度が高いものを除き無視します。また、ブロックできても他の要素まで巻き込んでしまう場合はブロックしません。これらも非表示にしたい方や、海外のサイトもご覧になる方はAdGuard Social mediaなどを併用してください。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Social">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt)

#### 対象

- シェアボタン
- FeedlyとTumblrのフォローボタン
- Lineのいいね/友だち追加ボタン
- 有益性の低い一部のソーシャルウィジェット
- ソーシャルログイン
- 一部対象外に該当するが、とくに迷惑なもの


#### 対象外

- Feedly, Tumblr以外のフォローボタンやInstagramバッジ
- Facebook/Twitter動画
- Twitterタイムラインウィジェット
- Facebook、Twitter等の更新情報ウィジェット
- Pinterestの写真ウィジェット（しばしば記事の一部）
- 記事に対するソーシャルメディア上の反応が閲覧できるもの、その他潜在的に有用なもの
- 対象に入るが、ブロックすると対象外まで巻き込むもの
- 対象に入るが、非表示にしかできず、かつ一定の基準を満たさないもの


### Yuki's uBlock Japanese filters - Annoyances　（みぞれフィルタ）

広告以外の迷惑要素をブロックするフィルタで、Yuki's uBlock Japanese filtersとの併用を前提とします。一部、[Fanboy's Annoyance List](https://easylist.to/easylist/fanboy-annoyance.txt)や[AdGuard Annoyances](https://kb.adguard.com/en/general/adguard-ad-filters#annoyances)から取られたルールもあります。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Annoyances">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt)

#### 対象

- サイト内ポップアップ、モダルウィンドウ等
- プッシュ通知を中心とした、有益性の低い通知
- スマホアプリの宣伝バナーで大画像を伴うもの
- ブログロール、相互RSSの類（そのブログ自身の更新通知は除く）
- ブラウザチェックとIE用スクリプト
- クッキーやプライバシーポリシーの同意バナー
- ランキングボタンやその他の不要なブログパーツ
- 広告や行動解析を伴う、または不快なレコメンド（追尾型など）
- メールマガジン購読やサブスクリプションを促すバナー
- 不要な待ち時間（多くの場合、広告の類を見せるために使われる）
- その他多くのユーザーにとって迷惑・不要と思われるもの

#### 対象外

- 上記対象に該当するが潜在的に、または人によっては有用なもの
- 右クリック防止やコピープロテクトの類（すべての利用者に著作権を遵守していただけるならよいのですが、その保証がない以上あえてブロックしません）
- 開発者ツールの妨害スクリプト
- ペイウォール（クッキーを参照して「無料で読める記事はあと〇〇」と警告するタイプのものは対応する場合もあります）
- ポップアップやクッキーバナーの内、クリックが必須のもの（セキュリティ上の理由により、uBlock Originではあえて対応するスクリプトを採用していません）
- モバイルブラウザチェックとiPhone, Android用スクリプト（モバイルも限定的にサポートするため）
- レーティングウィジェット
- ブログ以外のブックマークボタン、クリップ系
- チャットウィジェット
- コロナウイルス関係で、一般的な通知ブロックで防げないもの（一時的なものなので）

モバイルサイトは対象外にしたかったのですが、当サイトで以前より公開しているサブフィルタがモバイルに対応してしまっているため、限定的な対応ということにします（メインはあくまでPCです）。モバイルで使用する場合、拡張機能に対応したブラウザにuBlock Originを入れてご利用ください（この場合、Yuki's uBlock Japanese filtersの併用は不要です。モバイル用のフィルタと併用してください）。迷惑度のとくに高いものはYuki's uBlock Japanese filtersでブロックすることもあります。たとえば忍者レコメンドは当初Annoyancesに入れていましたが、動画中に画像を挿入するケースなどが散見されたため方針を変えました。


### Sable filters 2

当サイトで以前から公開しているフィルタで、クッキーの同意バナーを除去します。<strong>Yuki's uBlock Japanese filters - Annoyancesに含まれており、これを購読しているなら必要ありません</strong>。一方でYuki's uBlock Japanese filters - Annoyancesと異なり、AdGuardなど他のプラットフォームでもSable filters 2は使うことができます。

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt&title=Sabre%20filters%202">購読 する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt)


### blog-parts.txt

Sable filters 2と同じく、以前から公開しているYuki's uBlock Japanese filters - Annoyancesのサブフィルタで、ランキングボタン等のブログパーツをブロックします。こちらも他のプラットフォームでご利用可能です。

### blog-parts-adult.txt

blog-parts.txtのアダルトサイト版です。


## 不具合、ブロック漏れの報告

原則としてGithubのIssueを通してのみ受けつけます。報告前に一度、<strong>新しいブラウザプロファイルを作り、uBlock OriginをクリーンインストールしてYuki's uBlock Japanese filters (+ Paranoid/Social/Annoyances）のみを購読した状態で問題が再現できるか</strong>を確認してください。また、ネットワークの別の部分でブロックしていないか（例: AdGuard Home, 280blocker DNS）も確かめてください。テンプレートは用意していませんが、報告される方は、<strong>必ず以下の項目をすべて記入してください。</strong>海外サイトの不具合は、AdGuard Japaneseを除くuBlock Origin標準のフィルタ（+ 英語以外の場合、その言語の標準フィルタ）を併用しても再現する場合のみ対応いたします。

1. 問題が起こるサイトの完全なURL（URLの前後に`をつけてください）: 検索エンジンの場合は検索語もお願いします。
2. 現象の説明: 言葉による説明とスクリーンショットを両方含めてください。
3. 現象の再現方法: そのサイトに行くだけで100%再現できる場合でも、順を追って記述してください。例えば最近のYoutube広告では新しいタブで開いたか、ページ内遷移したかで広告の出方が違います。そのサービスにログインした状態か否かも必ず記述してください。
4. 環境と設定: OS、ブラウザ、uBlock Originの種類とバージョン、また購読しているフィルタの一覧（スクリーンショット可）は必須です。Firefox上でのみ問題が発生する場合、GoogleかCloudflareのDNSで現象が再現できるかも確かめていただけると助かります。

<strong>同じURLにアクセスすればみんな同じように広告や不具合が出ると思っている人がいますが、間違いです。必ず上記手順を守ってください。</strong>また、迅速な対応はお約束しかねます。

## ブロックおよびメンテナンス方針

- ルールの追加・削除については問題の検証を必須とします。他のフィルタが採用しているからというだけの理由、またはユーザー様の自己報告だけに基づく追加・削除は原則として行いません。

- 誤爆かどうかの判定が難しいケースもあります。そのような場合、そのサイトを日常的に使う人を想定するため、たまたま訪れた人には判定が甘い（広告漏れ）ように映るかもしれません。できるだけ最大公約数をとるように努力しますが、そもそも万人向けのフィルタなどなく、私が私用フィルタと公開フィルタをわけているのもそうした理由です。上級者向けですので、適宜`$badfilter`, `$important`や例外などで対応してください。

- 誤爆の観点から、他フィルタとルールを統一する場合を除き一般ルールの使用を最小限に抑えています。ルールを一般化するのは原則、1) 少なくとも3か所以上で使われており、2) 他の場所でも使われる見込みが高く、3)かつ、誤爆する見込みが低い場合のみです。

- デッドドメインや不要になったルールは見つけ次第取り除く方針です。そのため、見かけ上ほかのフィルタよりブロックが少なく見えることがあり得ます。

- 問題報告がGithubのみなのは、あまり気軽に報告できてしまうと質の低い報告が増えるという懸念もあるためです。必ず所定の手順を守ってください。

- 正直なところ、既に公開しているフィルタの維持と主要フィルタへの報告だけでも限界に近く、長期的にメンテナンスできるかはわかりません。他のフィルタ作者さんはご自身で使われているケースが多いようですが、こちらでは私用フィルタと公開フィルタは別です。元々、当時更新が停滞していた[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)のフォークを考えていたのですが、許可が下りなかったためオリジナルフィルタを企画しました。その間に豆腐さんも更新を再開されたようです。オリジナルとはいえ豆腐フィルタを参考にした部分は多々あり、ここに感謝申し上げます。

- 当フィルタの方針に同意いただけ、かつフィルタを作成する技能のある方の貢献は歓迎いたします。興味がおありの方はプルリクエストやIssueを通じて声をおかけください。それが面倒くさいという方は、CC BY-SA 4.0の範囲において自由に改変、再配布も可能です。識別のために私の名前を入れたものの、本来はチームによる共同管理が望ましいと考えています。その場合、雪フィルタ等を正式名称に格上げするかもしれません。
