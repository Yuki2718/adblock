## お知らせ（2020年11月10日）

Youtubeの白（または黒）い「広告をスキップ」画面および広告すり抜けについて：まず、uBlock Originでの対策方法は[公式ページ](https://github.com/gorhill/uBlock/releases)から1.30.9b12以降の開発者ビルドをインストールすることです。この新しいタイプのYoutube広告（新スキーム）では、fetchと組込みのBody.json()パーサーが用いられており、これまでのjson-pruneフィルタでは対処できませんでした（[参照](https://github.com/gorhill/uBlock/commit/13f92756befaa9a8d3ba1615bd7abc7075758c67)）。また、旧スキームは特定アカウントでサインイン中に限り広告が配信されていた（そのため、アカウント切り替えやサインアウトで対処できた）のに対し、新スキームは（旧スキームもこれからは？）サインアウト状態でも配信されることがあります。ただしクッキー削除後の初訪問時に表示されることはなく、リロードかページ遷移後に表示されるようです。念のため述べると、旧スキームも依然として用いられており、このフィルタのおかげで多くの人は広告を目にせず済んでいます。どちらのスキームにせよ、広告表示には何らかの条件があり、フィルタ作者側もuBlockチームのgwarser氏がほんの数時間、およびEasyListのFanboyNZ氏が再現できたほかは新スキーム広告を再現できていません。

### Yuki's uBlock Japanese filters （雪フィルタ）

日本語サイト閲覧者がPCで遭遇する広告・解析のほとんどを除去できる、uBlock Origin用<sup>1</sup>フィルタです。

- AdGuardなど他のプラットフォームでは機能しないルールがあるため、使用はおすすめしません<sup>2</sup>。uBlock-for-firefox-legacyもサポートしません。
- モバイルサイトは対象外です。280blockerさんの[フィルタ](https://280blocker.net/download/)やもちおさんの[たまごフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/tamago.html)など、モバイル用のフィルタを使用してください。
- 他所では広告ブロックフィルタでブロックしていても、当サイトでは迷惑要素に分類している場合もあります。たとえば、AdGuard日本語フィルタがブロックするブログロール系、uBlock filtersがカットする不要な待ち時間などです。ブロックに不足を感じられたら、Annoyancesの購読もご検討ください。

<strong>ガイドライン（PC広告）：</strong>広告ブロック初心者の方は、まずuBlock Origin（[Firefox用](https://addons.mozilla.org/ja/firefox/addon/ublock-origin/)/[Chrome用](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)）をインストールしてください（名前の似たまがいものに注意！）。豆腐フィルタやもちフィルタなど、<strong>主要な日本用のフィルタが性能をフルに発揮できるのは、uBlock Originだけです</strong><sup>3</sup>。その上でまず、もちおさんが提供なさっている[もちフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/mochi.html)を試してみることをおすすめします。もしそれで十分でないと感じられた場合、同サイトで提供されているサブフィルタを追加するか、あるいは長年、日本の広告ブロックを代表されてきた[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)に切り替えるという方法があります。もちフィルタよりやや不具合（誤爆と呼ばれる）が増えたり、パフォーマンスが落ちたりするかもしれませんが<sup>4</sup>、2020年7月末より大幅な改修がなされており、十分おすすめできると思います。雪フィルタ系が適しているのは以下のような方です。

- とにかく徹底的にブロックしたい
- オンラインのアクセス解析、行動追跡が気になる
- 既にEasyListなど海外用のフィルタを購読している
- 広告ばかりでなくソーシャルボタンやページ内ポップアップなどの迷惑要素もブロックしたいが、既存のソーシャル/迷惑系フィルタでは満足できない/誤爆が多い
- 低スペック端末だが速度・効率とブロック力を両立させたい
- 広告を目にしないことより、通信量の削減が第一
- ある程度は悪質サイトやコインマイナーもブロックしてほしい

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt&title=Yuki's%20uBlock%20Japanese%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt)

#### 特徴

<details>
<summary><strong>網羅性</strong></summary>

日本語サイト<sup>5</sup>のPC用公開フィルタとして、2020年7月現在メンテナンスされているものの中で最高のブロック性能を持ちます。とくにアクセス解析については他の日本用フィルタではおまけ程度にしか扱われていませんが、当フィルタはできるだけブロックします。そのため不具合も多いかもしれません<sup>6</sup>。

</details>

<details>
<summary><strong>ブロック優先</strong></summary>

ブロック可能な対象はできる限りブロックします。これは当然のことではなく、他のフィルタではブロック可能でも非表示で済ましているケースが多数あります<sup>7,8</sup>。ブロックが困難な場合、Firefox上ではHTMLフィルタリングにより除去を試みています。ブロックさえできればよいという方は「汎用的な要素隠蔽フィルターを無視する」にチェックを入れてください。表示崩れや多少の広告漏れと引き換えに、パフォーマンスを高めることができます。Yuki's uBlock Japanese filtersファミリーは、その場合でもある程度の性能を維持できます<sup>9</sup>。

<strong>初心者向け補足：</strong>広告ブロックには、ブロックと非表示という２種類の方法があります。ブロックはそのままの意味ですが、非表示とは広告を見えなくすることです。広告自体は読み込まれているため、通信量やコンピュータのリソースを消費しますし、悪質広告（Malvertising）の防御もできません。それでも非表示を使わなければならない理由はいろいろありますが、どこまで使うかはフィルタによってまちまちです。当フィルタは世界的に見てもブロックに極振りしたフィルタです。

</details>

<details>
<summary><strong>高効率</strong></summary>

uBlock Originはトークン化という仕組みにより高速処理を実現しています<sup>10</sup>。ルールがトークン化可能なら、ルール数は[処理時間に](https://www.wilderssecurity.com/threads/ublock-a-lean-and-fast-blocker.365273/page-155#post-2831026)[影響しません](https://twitter.com/i/web/status/1289255976198123520)<sup>11</sup>。当フィルタはできるだけトークン化を意識したルールを心がけており（例外あり）<sup>12</sup>、また非表示フィルタについても[最小マッチング](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters#important)の原則を満たしつつ、できるだけ高速で誤爆の少ないセレクタを使うよう心がけているつもりです。

</details>

<details>
<summary><strong>併用可</strong></summary>

ブロック対象に違いがなく、パフォーマンスや誤爆の観点から問題がない場合、[EasyList](https://easylist.to/easylist/easylist.txt), [EasyPrivacy](https://easylist.to/easylist/easyprivacy.txt), [Peter Lowe's Ad and tracking server list](https://pgl.yoyo.org/adservers/serverlist.php), [uBlock 内製フィルター](https://github.com/uBlockOrigin/uAssets), [AdGuard Base](https://kb.adguard.com/en/general/adguard-ad-filters#english), [AdGuard Tracking Protection](https://kb.adguard.com/en/general/adguard-ad-filters#privacy), [Fanboy Enhanced Tracking](https://www.fanboy.co.nz/enhancedstats.txt), [280blocker 広告ドメインリスト](https://280blocker.net/download/)など、併用されることが多そうなフィルタとルールを統一しています<sup>13</sup>。これにより重複が排除され、フィルター一覧でのフィルタ有効数<sup>14</sup>が正しく表示されるだけでなく、非表示フィルタの多重適用も回避できます。つまり単独で使えるばかりでなく、上述の各種フィルタと併用した場合でも無駄がありません<sup>15</sup>。また、標準リストで発生する不具合が当該リストで修正されない場合、こちらで修正いたします。つまり標準リストに対する不具合修正フィルタとしても機能します。なお、280blocker 広告ドメインリスト以外の日本用フィルタとの併用はおすすめしません。不具合やアンチ広告ブロック起動の原因となりえます。

</details>

#### 対象
- 広告、アフィリエイトリンク
- 一部のプロモーションコンテンツ（ネイティブ広告）<sup>16</sup>
- 侵襲性の高いセルフプロモーション
- アクセス解析、行動追跡、ヒートマップ
- バグレポート
- サードパーティーまたはスクリプトを伴うアクセスカウンター
- 主に上記をブロックしたため生じた枠や不要なスペース
- アンチ広告ブロック
- 迷惑・有害なポップアップ、ポップアンダー、リダイレクト
- 一部の詐欺・悪質サイト（セキュリティーソフトの代わりにはなりません）
- 一部のコインマイナー

#### 対象外
- サイトの内容と強く関連しており（例：具体的な商品のレビュー）、かつ量が過剰でなくユーザーに不利益・不快感を与えない広告<sup>17</sup>（「ゲームのブログだからゲームの広告」程度では強く関連しているとみなしません。ただしあるテーマのまとめサイトなどで潜在的な有用性がある場合、画像のみブロックしリンクは残すことがあります）
- 運営母体の系列サイトへのリンクバナーで、それほど不快でないもの<sup>18</sup>
- アフィリエイトリンクの一般非表示（280blockerさんと同様の[理由](https://280blocker.net/advanced-settings/)に加え、多くは誤って踏んでもStrict blockingできる）
- ファーストパーティーの単純なCGI/SSIアクセスカウンターで、広範に使われているもの以外
- Google Safe Browsingでカバーされている、またはモバイル限定の悪質サイト

### Yuki's uBlock Japanese filters - Paranoid　（大雪フィルタ）

Yuki's uBlock Japanese filtersに追加できるフィルタで、多少の不具合を覚悟でより強固にブロックします。<strong>自己責任で使用してください</strong>。トラッキングパラメータを含むリンクからの移動もブロックします。この場合、<strong>「uBlock Origin は、このページの読み込みをブロックしました」画面で右側の虫眼鏡アイコンをクリックすると、トラッキングパラメータを除いたURLが（場合によってはいくつか）表示され、そのままクリックできます。</strong>ただし、ブロックするとあまりに煩雑になる場合はブロックしません（例：記事の大部分にトラッキングパラメータを付与しているサイト、utm_sourceなど広範に使われるパラメータの一般ブロック）。1.30.9b5から`$queryprune`が追加されパラメータの直接除去が可能になりましたが、`$rewrite`と違い完全な置き換えができないこと、また無条件に除去するとプロモーションや割引が受けられない場合もあることから、Strict blockingによる除去はこれまで通り続け、`$queryprune`は除去して問題のないことが十分確認されたトラッキングパラメータやSSAI対策に限定するつもりです。なお、このフィルタの一部のルールはgwarser氏の[Block access to LAN](https://github.com/gwarser/filter-lists/blob/master/lan-block.txt)フィルタによるものです。

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
- 一部のソーシャルログイン
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

広告以外の迷惑要素をブロックするフィルタで、Yuki's uBlock Japanese filtersとの併用を前提とします。一部、[Fanboy's Annoyance List](https://easylist.to/easylist/fanboy-annoyance.txt), [AdGuard Annoyances](https://kb.adguard.com/en/general/adguard-ad-filters#annoyances), [uBlock filters – Annoyances](https://github.com/uBlockOrigin/uAssets/blob/master/filters/annoyances.txt), および[Web Annoyances Ultralist](https://github.com/yourduskquibbles/webannoyances)から取られたルールもあります。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Annoyances">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances.txt)

#### 対象

- サイト内ポップアップ、モダルウィンドウ等
- プッシュ通知を中心とした、有益性の低い通知
- スマホアプリの宣伝バナーで大画像を伴うか、広い面積を占有するもの
- ブログロール、相互RSSの類（そのブログ自身の更新通知は除く）
- ブラウザチェックとIE用スクリプト
- クッキーやプライバシーポリシーの同意バナー
- ランキングボタンやその他の不要なブログパーツ
- 広告や行動解析を伴う、または不快なレコメンド（追尾型など）
- 一部のセルフプロモーションバナー
- メールマガジン購読やサブスクリプションを促すバナー
- 不要な待ち時間（多くの場合、広告の類を見せるために使われる）
- 楽天のデフォルトでチェックされているメールマガジン配信チェックボックス（アンチェックします）
- Twitterのおすすめトピック（おすすめユーザーはコメントアウト：必要な方は先頭の`!`を除いたものをMyフィルターにコピー＆ペーストしてください）
- その他多くのユーザーにとって迷惑・不要と思われるもの

#### 対象外

- 上記対象に該当するが潜在的に、または人によっては有用なもの
- ログインサイトで、デフォルトで無効のプッシュ通知（ニコニコなど）
- 右クリック防止やコピープロテクトの類（すべての利用者に著作権を遵守していただけるならよいのですが、その保証がない以上あえてブロックしません）
- 開発者ツールの妨害スクリプト
- ペイウォール（クッキーを参照して「無料で読める記事はあと〇〇」と警告するタイプのものは対応する場合もあります）
- ポップアップやクッキーバナーの内、クリックが必須のもの（セキュリティ上の理由により、uBlock Originではあえて対応するスクリプトを採用していません）
- モバイルブラウザチェックとiPhone, Android用スクリプト（モバイルも限定的にサポートするため）
- レーティングウィジェット
- ブログ以外のブックマークボタン、クリップ系
- チャットウィジェット
- コロナウイルス関係で、一般的な通知ブロックで防げないもの（一時的なものなので）

モバイルサイトは対象外にしたかったのですが、当サイトで以前より公開しているサブフィルタがモバイルに対応してしまっているため、限定的な対応ということにします（メインはあくまでPCです）。モバイルで使用する場合、拡張機能に対応したブラウザにuBlock Originを入れてご利用ください（この場合、Yuki's uBlock Japanese filtersの併用は不要です。モバイル用のフィルタと併用してください）<sup>19</sup>。迷惑度のとくに高いものはYuki's uBlock Japanese filtersでブロックすることもあります。たとえば忍者レコメンドは当初Annoyancesに入れていましたが、動画中に画像を挿入するケースなどが散見されたため方針を変えました。

<details>
<summary><strong>みぞれフィルタのサブフィルタ</strong></summary>

### Sable filters 2

当サイトで以前から公開しているフィルタで、クッキーの同意バナーを除去します。<strong>Yuki's uBlock Japanese filters - Annoyancesに含まれており、これを購読しているなら必要ありません（AdGuard for Androidを除く）</strong>。一方でYuki's uBlock Japanese filters - Annoyancesと異なり、AdGuardとも完全な互換性があります。

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt&title=Sabre%20filters%202">購読 する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt)


### Yuki's Blog parts filters

Sable filters 2と同じく、以前から公開しているYuki's uBlock Japanese filters - Annoyancesのサブフィルタで、ランキングボタン等のブログパーツをブロックします。こちらも他のプラットフォームでご利用可能です。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt&title=Yuki's%20Blog%20parts%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt)

### Yuki's Blog parts filters - Adult

Yuki's Blog parts filtersのアダルトサイト版です。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt&title=Yuki's%20Blog%20parts%20filters%20-%20Adult">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt)

</details>

### 280blocker AdblockPlus形式 悪質サイト対策強化パッチ（AdGuard for AndroidおよびuBlock Origin専用）

280blockerさんは、2020年8月2日の更新で悪質サイト対策のルールを大幅に追加されました。できるだけ多くのプラットフォームをサポートしたいという280blockerさんの願いにより、280blocker AdblockPlus形式フィルタは正規表現などの高度な文法を避け、互換性の高い記法で書かれています。一方で、AdGuardやuBlock Originなど高度な文法をサポートするモダンブロッカーにとっては、この記法による悪質サイト対策にはいくつかの限界があります。

1. 誤爆の恐れが高まります（海外サイトですが、[実例](https://www.fullhdfilmcehennemi8.live/)）
2. AdGuardでは悪質サイトへのアクセス自体はブロックされません
3. uBlock Originではパフォーマンスが悪いです（質の低いトークンしか引き出せないため）

また、重要ではないですが

4. これらのブロッカーの機能を使えばサイトそのものをブロックしなくて済む場合でも、ブロックされています

当パッチは280blocker AdblockPlus形式のビジターアンケート詐欺用ルールを、iOSの280blockerで使われているものにより近い（厳密に同じではありません）正規表現に置き換え、適切なオプションを指定することで上記1-3を解決しています。4については安全性をとるならサイトごとブロックするに越したことはないため、ルールの置き換えまではしていません。また、Yuki's uBlock Japanese filtersから悪質サイト用のルールをさらに追加しています。本来ならこうしたことは[なんj改修フィルター](https://wikiwiki.jp/nanj-adguard/%E3%81%AA%E3%82%93J%E6%94%B9%E4%BF%AE%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC)・[なんJ拡張フィルター](https://wikiwiki.jp/nanj-adguard/%E3%81%AA%E3%82%93J%E6%8B%A1%E5%BC%B5%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC)で行われるべきなのかもしれません。ただ、多数のデッドルールが放置されるなどメンテナンスが続いているのか怪しい状態ですし、私がそれをやるなら自分のレポジトリで公開したほうが今後の調整が楽なため、そのようにさせていただきました。

<strong>2020年8月現在、「信頼するフィルタ」のチェックは必須ではありません。ただ、今後信頼するフィルタ用の機能を使う可能性はあるので、チェックを推奨します。</strong>

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt&title=280blocker%20AdblockPlus%E5%BD%A2%E5%BC%8F%20%E6%82%AA%E8%B3%AA%E3%82%B5%E3%82%A4%E3%83%88%E5%AF%BE%E7%AD%96%E5%BC%B7%E5%8C%96%E3%83%91%E3%83%83%E3%83%81">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt)

公益の観点から、このフィルタのみ[CC0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)で提供しています。

#### 対象外

- Google Safe Browsingで既にブロックされているもの（AdGuardのブラウジングセキュリティはGoogle Safe Browsingをソースの一部としており、またuBlock Originが利用可能なモバイルブラウザもGoogle Safe Browsingをサポートしているものが多いため）

## 不具合、ブロック漏れの報告

原則としてGithubのIssueを通してのみ受けつけます。どうしてもアカウント作成が手間だという方用に[掲示板](https://jbbs.shitaraba.net/internet/25463/)も用意しましたが、報告基準はここと同じです。URLも環境も示さない報告は大きな負担となりますので、絶対にやめてください。報告前に一度、<strong>新しいブラウザプロファイルを作り、uBlock OriginをクリーンインストールしてYuki's uBlock Japanese filters (+ Paranoid/Social/Annoyances）のみを購読した状態で問題が再現できるか</strong>を確認してください。また、ネットワークの別の部分でブロックしていないか（例: AdGuard Home, 280blocker DNS）も確かめてください。報告される方は、<strong>必ず以下の項目をすべて記入してください（テンプレートを用意してありますのでご利用ください）。</strong>海外サイトの不具合は、AdGuard Japaneseを除くuBlock Origin標準のフィルタ（+ 英語以外の場合、その言語の標準フィルタ）を併用しても再現する場合のみ対応いたします。

1. 問題が起こるサイトの完全なURL（URLの前後に`をつけてください）: 検索エンジンの場合は検索語もお願いします。
2. 現象の説明: 言葉による説明とスクリーンショットを両方含めてください。
3. 現象の再現方法: そのサイトに行くだけで100%再現できる場合でも、順を追って記述してください。例えばYoutube広告では新しいタブで開いたか、ページ内遷移したかで広告の出方が違います。そのサービスにログインした状態か否かも必ず記述してください。
4. 環境と設定: OS、ブラウザ、uBlock Originの種類とバージョン、また購読しているフィルタの一覧（スクリーンショット可）は必須です。Firefox上でのみ問題が発生する場合、GoogleかCloudflareのDNSで現象が再現できるかも確かめていただけると助かります。

注意： ログインが必要なサイトでの不具合や広告漏れにつきましては、ログや開発者ツールのスクリーンショット等、こちらがログインせずとも現象や解決を確認できる手段の提供をお願いすることがあります。

## ブロックおよびメンテナンス方針

- ルールの追加・削除については問題の検証を必須とします。他のフィルタが採用しているからというだけの理由、またはユーザー様の自己報告だけに基づく追加・削除は原則として行いません。

- 誤爆かどうかの判定が難しいケースもあります。そのような場合、そのサイトを日常的に使う人を想定するため、たまたま訪れた人には判定が甘い（広告漏れ）ように映るかもしれません。できるだけ最大公約数をとるように努力しますが、そもそも万人向けのフィルタなどなく、私が私用フィルタと公開フィルタをわけているのもそうした理由です。可能でしたら、適宜`$badfilter`, `$important`や例外などで対応してください。

- 他フィルタとルールを統一する場合を除き一般ルールの使用を最小限に抑えています。ルールを一般化するのは原則、1) 少なくとも3か所以上で使われており、2) 他の場所でも使われる見込みが高く、3)かつ、誤爆する見込みが低い場合のみです。逆に、1つでも既知の誤爆がある場合は極力避けています。

- デッドドメインや不要になったルールは見つけ次第取り除く方針です。デッドドメインでもリクエストは発生するため、見かけ上ほかのフィルタよりブロックが少なく見えることがあり得ます。

- 問題報告がGithubのみなのは、あまり気軽に報告できてしまうと質の低い報告が増えるという懸念もあるためです。必ず所定の手順を守ってください。

- 正直なところ、既に公開しているフィルタの維持と主要フィルタへの報告だけでも限界に近く、長期的にメンテナンスできるかはわかりません。他のフィルタ作者さんはご自身で使われているケースが多いようですが、こちらでは私用フィルタと公開フィルタは別です。元々、当時更新が停滞していた[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)のフォークを考えていたのですが、許可が下りなかったためオリジナルフィルタを企画しました。その間に豆腐さんも更新を再開されたようです。オリジナルとはいえ豆腐フィルタを参考にした部分は多々あり、ここに感謝申し上げます。

- 当フィルタの方針に同意いただけ、かつフィルタを作成する技能のある方の貢献は歓迎いたします。興味がおありの方はプルリクエストやIssueを通じて声をおかけください。それが面倒くさい方は、CC BY-SA 4.0の範囲において自由に改変、再配布も可能です。識別のために私の名前を入れたものの、本来はチームによる共同管理が望ましいと考えています。

## その他

[よくある質問](/japanese/FAQ.md)

<details>
<summary>註</summary>

<sub>1: Nano Adblockerでもご利用いただけますが、当フィルタでuBlock Originの最新機能を利用した場合、一時的にその機能が利用できない可能性があります。Nanoの本質的な違いは、専用のスクリプトレットによりある種の迷惑要素に対処できるという点です。アンチ広告ブロックについては、Nano Defenderも不要です。強いて言えばuBlock OriginではuBlock filters - Annoyancesの購読が必要な「控えめな」アンチブロック（×ボタンで消せるか、コンテンツを妨害しないもの）が、Nanoではデフォルトでブロックされているくらいの違いです（古いアンチ広告ブロックで、uBlock Origin未対応のものがある可能性は否定できませんが）。ただ、Quick reporterはフィルタ作者としてありがたい機能なのですが。[2020年10月16日追記] Chrome版Nanoは売却され、新開発者がスパイウェアらしきコードを追加しました。ご利用の方は速やかにアンインストールすることをおすすめします。Firefox版はメンテナーが別のため大丈夫ですが、前述のようにNanoを使うメリット自体あまりありません。</sub>

<sub>2: AdGuardで使用する場合、最大の問題はspecific-genericとdenyallowでしょう。とくに後者は大幅な書き直しが必要です。PCでAdGuardをご利用の場合、もちフィルタを使用するか、あるいは海外サイトも閲覧するのであればAdGuardベース + 日本語フィルタの組合せも悪くないと思います。AdGuard日本語フィルタはかつて不評でしたが、近年大きく改善されてきています。豆腐フィルタはAdGuardで機能しないルールが増えてきたため、おすすめできません。</sub>

<sub>3: AdGuardならスクリプトレットに互換性があるので許容範囲です。困ったことに、IT関係者の方でAdBlockやAdblock Plusを勧められる方がおられます。これらでも大体の広告は消えますが、フィルタ設定の如何にかかわらず不具合や広告漏れの確率が格段に高まります。</sub>

<sub>4: 主に処理負荷の高いprocedural cosmetic filtersとspecific-genericの組合せによるものですが、よほどの低スペック端末でない限り体感に影響するほどではないと思います（[参考1](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters) [参考2](https://github.com/uBlockOrigin/uBlock-issues/issues/803#issuecomment-586712831)）。
</sub>

<sub>5: いくつかの日本用フィルタと同様、日本語話者がよく利用すると思われる海外サイトにも対応しています。</sub>

<sub>6: 後述のようにEasyListやEasyPrivacyなどから多くのルールを取り入れているものの、誤爆率の高いルールは除外しています。また私の知るこれらのフィルタによる誤爆で、未報告または報告済みだが未対処のものにも対応しています。一方、EasyPrivacyなどに含まれていないアクセス解析も（誤爆率の高そうなもの以外）多く盛り込んでいます。なお、当フィルタは誤爆を重く受けとめており、利用者が修正してしかるべきとは考えておりません。あくまで個人管理の限界により、上記のような断りを入れさせていただいております。</sub>

<sub>7: 「要素をブロック」機能でMyフィルターを作っている人も同様です。画像についてはブロックしてくれることもありますが、イニシエイターとなるスクリプトはお手上げです。非表示についても質の低いルールが多いです。同機能は[あくまで補助であり](https://github.com/uBlockOrigin/uBlock-issues/issues/1058#issuecomment-631459847)、過剰に頼るべきではありません。</sub>

<sub>8: uBlock Originポップアップパネルの目玉アイコンをクリックして×印をつけると、ブロックされていない広告が浮かび上がってきます。元に戻すにはもう一度クリックして×印を外してください。</sub>

<sub>9: 当サイトのフィルタは[specific-generic](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic)を利用したおそらく最初の公開フィルタです。なお、汎用非表示フィルタの数はパフォーマンスに[影響しません](https://github.com/uBlockOrigin/uBlock-issues/issues/738#issuecomment-619450820)。パフォーマンスを高めたいなら、完全に切る他ありません。</sub>

<sub>10: 簡単に言うと、リクエストとルールそれぞれから抽出したトークンを使ってマッチする見込みがありそうなルールを絞り込んでいます。一般的なリクエストに対して大部分のルールは無いも同然であり、計算量のオーダーはルール数に依存しません。検索エンジンの転置インデックスに近いです。</sub>

<sub>11: 実測するのが早いです（レイテンシの影響が大きいのでキャッシュは維持してください）。[こちら](https://brave.com/improved-ad-blocker-performance/)はBraveがuBlock Originの方式を導入した時の記事ですが、16,000個ルールを追加しても個々のリクエスト処理にかかる時間は1μsも変わらないことがわかります。メモリ消費はルール数に応じて増えますが、PCで問題になる量ではありません。逆にいうと非効率なルールが増えるほど遅くなるため、そうしたルールは対象を絞り込む必要があります。</sub>

<sub>12: ABP文法と異なり、[単語境界を意識](https://github.com/gorhill/uBlock/issues/1065)する必要があります。たとえば`/example`というルールは、（他の部分でトークンマッチが起きない限り）`/example1`というリクエストをブロックしません。明示的に`*`を追加するとブロックするようになりますが（`/example*`）、これは`example`のトークン化を妨げます。主要な[bad token](https://github.com/gorhill/uBlock/blob/381498daa2a9ce089a69d044760190b1dd14b5ac/src/js/static-net-filtering.js#L2062)（トークン化されない文字列）も覚えた方がよいでしょう。一般に遅いとされる正規表現ルールも[条件](https://github.com/gwarser/filter-lists/blob/master/lan-block.txt#L8)を満たせばトークン化可能なので、とくに正規表現ルールの作り方は大事です。</sub>

<sub>13: 当フィルタはCC BY-SA 4.0のもとに配布しており、こればuBlock 内製フィルターと280blocker以外を正しく継承（デュアルライセンス、バージョン違い）しています。uBlock内製フィルターはGPLv3ですが、AdGuardなどと比較して癖のないルールであり、一般的なフィルタ作者が思いつく範囲だと思います（スクリプトレットルールを比較していただくとわかるように、実際に有効なルール以外は採用していません。古いスクリプトルールは不要になったものが多く、適宜報告しています。さらに言えば、もともと私が提案ないしプルリクエストしたルールもあります）。280blockerはライセンス指定なしですが、参考にしているのはドメインリストのみであり、これは書き方がほぼ一意に決まってしまうため問題ないと考えます。また一部、[EasyList China](http://abpchina.org/forum/forum.php), [RU AdList](https://forums.lanik.us/viewforum.php?f=102), [Brave Unbreak](https://github.com/brave/adblock-lists)（MITライセンス）からとられたルールがある他、[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)を参考にしたルールが少なからずあります（著作権上、そのままの使用はなるべく避けましたが、どうしても同じになってしまったものもあります）。</sub>

<sub>14: 有効数には優先順位がありませんので、Yuki's uBlock Japanese filtersの内どれだけ使われているか知りたい場合、一度Yuki's uBlock Japanese filtersのチェックを外して他のフィルタを更新し、再度チェックを入れてください。なお、この方法で真の有効数がわかるのはYuki's uBlock Japanese filtersならではであり、ほかのフィルタではメモリに載るルール数までしかわかりません。同じブロック対象をまったく別のルールでターゲットにするケースが多数生じるためで、この場合、優先順位の低いトークン化可能ブロックルールは「死んだルール」（メモリのみ消費）、トークン化不能ブロックルールやProcedural cosmetic filters、スクリプトレットルール等はパフォーマンス上の損失となります。</sub>

<sub>15: これらのフィルタによる誤爆をより網羅的に修正していることもあり、既にEasyList等を併用されている方にはもっともおすすめできる日本用フィルタと言ってよいでしょう。逆に、既存の日本用フィルタとこれらの併用は無駄が多く、Braveの日本用フィルタに採用されなかった[一因](https://github.com/brave/adblock-lists/issues/355#issuecomment-609680337)となっています。ちなみに、日本以外の国や地域ではEasyListに各言語用のフィルタを追加して使うのが普通であり、各言語用フィルタはEasyListの併用を前提としたものとなっています。</sub>

<sub>16: 有用性などを鑑み、すべてはブロックしません。大まかには、記事リストの間に挿入されるもの、ネイティブ広告としての性質が強いものなどを中心にブロックしています。</sub>

<sub>17: 今のところ実際には、スポンサー記事でない、一般的なブログにおける商品かサービスについてのレビューに付随するAmazonや楽天へのリンクで、量が過剰でなく、他の関係ない商品やサービスへのリンクを含まないものに限定しています。280blockerさんの[おっしゃるように](https://280blocker.net/advanced-settings/)これらを消すと文章が不自然になるケースもありますし、消したい方は「要素をブロック」で簡単に消せるものがほとんどです。他の日本用フィルタでも、もちフィルタさんが`amazon-adsystem.com`のウィジェットをブロックされている以外はせいぜい汎用非表示にとどまっています。そのもちフィルタさんも、`ssl-images-amazon.com`や`ecx.images-amazon.com`はコメントアウトされている（ブロックしていない）ことから苦心の跡がうかがえます。この辺りはすべてのフィルタ作者の悩みの種です。</sub>

<sub>18: こちらも基本、他の日本用フィルタでもブロックされていません。そもそも広告でなく、画像付きのリンクに過ぎませんが、侵襲性が高いものについては（ときにAnnoyancesで）ブロックする場合もあります。</sub>

<sub>19: Yuki's uBlock Japanese filtersと比べてAdGuardで機能しないルールは減っています。uBlock Originでの使用を推奨しますが、このフィルタについてはAdGuardでの使用も今のところ許容範囲です。<strong>ただしAdGuard for Androidでご利用の場合、Sabre filters2などのサブフィルタを別途購読してください</strong>。AdGuardブラウザ拡張機能ではその必要はなさそうです。AdGuardコンテンツブロッカーでの使用はおすすめしません。</sub>

</details>