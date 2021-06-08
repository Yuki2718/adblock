### お知らせ（2021年05月15日）

（2021年6月6日追記）EasyList作者がwikiを作ったので[リンク](https://github.com/easylist/easylist/wiki/Youtube-Issues)

（2021年05月24日追記）状況は変わりませんが、Youtubeの規約変更に伴いネット上で話題になった結果、誤情報が飛び交っています。標準設定で用いていれば、プログラムのバグでもない限り、**本稿執筆時点でPCではAdblock Plus/AdBlock, AdGuard, Brave, uBlock Originの間でYoutube広告のブロック性能に違いはありません！（注3）** たしかにAdblock Plus/AdBlockはブロック機能においてAdGuardやuBlock Originに劣りますが、それとこれとは話が別です。ブロッカーやブラウザを変えて改善したとしても、それはたまたまか、広告配信条件にブラウザ（UA）が絡んでいるかのどちらかと思われます。実際、同じセットアップでもブラウザを変えて改善したケースは報告されています。当サイトでは随所で述べていますが、Youtubeの広告は人によって、デバイスによって、さらにほかの条件によっても出方がまったく違います。iOSではスマートフォンとタブレットで異なるルールが必要なことがわかっており、さらにこれらのルールはPCでは不具合を起こすようです。**現状ではすり抜けの原因はわかっておらず、上記のどれを使ってもすり抜けるときはすり抜けるようです**。また、**Youtube用の広告ブロック拡張を入れたり、フィルタを追加したりしても無駄（効果が出てもプラセボ）です**（もともとのフィルタがまずかった場合を除く）。前者は既にuBlock Origin等で行っているブロックにせいぜいスキップの自動クリックを追加しただけです。後者も、本校執筆時点で新型広告（？）に有効なフィルタは（そもそもフィルタで対処可能なのかも）、誰にも知られていません。ちなみに3月にも大規模なすり抜けが起きており、この時の原因はYoutubeがfetchを使い始めたことで、フィルタでは対処できないものでした。

Youtubeの動画内広告について：各所で、また動画内広告がすり抜けてきたという報告が上がっています。一部では再生不具合も起こっているようです。今のところ、フィルター作者間（注1）ではEasyListメンテナーの一人がごく短時間不具合を再現したほかは再現しておらず、原因はわかりません。もしこの新型広告（？）の対象になってしまった場合、現状ではブラウザやアカウントを切り替える、ログアウトする等が最善かと思います。同じアカウントでも時間がたつと自然に回復（？）することもあるようです。ただし、これまでのすり抜け報告の大部分はフィルターや設定の問題、またはほかの拡張機能による干渉でした。まずはフィルター設定を見直し、uBlock Origin以外の広告・追跡ブロック拡張機能はすべて無効にしてください。またBlocktubeなどYoutube用のいくつかの拡張機能はuBlock filtersと干渉することが知られていますので、無効にしてください。Yuki's uBlock Japanese filtersとYuki's uBlock Japanese filters - Paranoidでは（注2）、すり抜けと再生不具合に対し実験的なフィルタを既に導入していますが、効果があるかはわかりません。なお、FAQでも[述べました](https://github.com/Yuki2718/adblock/blob/master/japanese/FAQ.md#q28-youtube%E3%81%A7%E6%A4%9C%E7%B4%A2%E3%81%8C%E6%A9%9F%E8%83%BD%E3%81%97%E3%81%AA%E3%81%84%E3%83%A1%E3%83%8B%E3%83%A5%E3%83%BC%E3%81%8C%E9%96%8B%E3%81%91%E3%81%AA%E3%81%84%E6%8E%A5%E7%B6%9A%E3%81%8C%E9%80%94%E5%88%87%E3%82%8C%E3%82%8B%E3%81%AA%E3%81%A9%E4%B8%8D%E5%85%B7%E5%90%88%E3%81%8C%E5%87%BA%E3%82%8B)が、Youtubeの広告はアカウントや諸条件により出方が違うため、「うちはこの設定で出ない」といった話の多くは当てになりません（丁寧に条件を分析した方からのフィードバックは歓迎いたします）。

<sub>注1：Adblock Plus, AdGuard, EasyList, uBlock Origin, 各言語用フィルタの作者間では毎日活発に情報交換しており、Youtubeの広告などは共同で解析することもあります。</sub>

<sub>注2：Paranoidの実験フィルタが効果を発揮するには、「ウェブサイトのオフライン作業用データ」を削除していただくか、`about:debugging#/runtime/this-firefox`または`chrome://inspect/#service-workers`からYoutubeのWorkerを解除していただく必要があります。なお、Fanboy Annoyanceにもほぼ同じ実験フィルタが含まれています。</sub>

<sub>注3：これらの内、AdBlockは今でもABP Japanese filtersをデフォルトで有効にしており、Youtubeで接続の問題など様々な不具合を引き起こします。これはYoutubeの広告ブロック対策などではなく、単なるフィルタの誤爆です。</sub>

## Yuki's uBlock Japanese filters （雪フィルタ）

日本語サイト閲覧者がPCで遭遇する広告・解析のほとんどを除去できる、**uBlock Origin専用**フィルタです。AdBlock, Adblock Plus, AdGuard, uBlock-for-firefox-legacy, Vivaldiなどでは**使わないで**ください<sup>1</sup>！

- モバイルサイトは対象外です。各ブロッカー標準のフィルタ、または280blockerさんの[フィルタ](https://280blocker.net/download/)やもちおさんの[たまごフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/tamago.html)など、モバイル用のフィルタを使用してください。
- 他所では広告ブロックフィルタでブロックしていても、当サイトでは迷惑要素に分類している場合もあります。ブロックに不足を感じられたら、Annoyancesの購読もご検討ください。

<strong>ガイドライン（PC広告）：</strong>初心者の方は、まずuBlock Origin（[Firefox用](https://addons.mozilla.org/ja/firefox/addon/ublock-origin/)/[Chrome用](https://chrome.google.com/webstore/detail/ublock-origin/cjpalhdlnbpafiamejdnhcphjbkeiagm)）をインストールしてください。豆腐フィルタやもちフィルタなど、<strong>主要な日本用のフィルタが性能をフルに発揮できるのは、uBlock Originだけです</strong><sup>2</sup>。その上でまず、もちおさんが提供なさっている[もちフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/mochi.html)を試してみることをおすすめします。これから広告ブロックを導入される方は「多少の広告は許せるし、行動追跡と言われてもよくわからないけど、下品な広告やコンテンツを妨害するものはイヤ」という方が多いと思います。その場合、もちフィルタなら主要な日本語サイトにおいて十分な効果がありますし、日本用フィルタの中では比較的、不具合やアンチ広告ブロック（広告ブロック解除要求）の起動率が少ないです。もしそれで不足を感じられた場合、同サイトで提供されている目的別フィルタを追加するか、あるいは[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)に切り替えるという方法もあります。もちフィルタよりやや不具合（誤爆と呼ばれる）やアンチ広告ブロックへの遭遇率は上がりますが、とくにサブカル系に強いです。Yuki's uBlock Japanese filtersファミリーが適しているのは以下のような方です。

- とにかく徹底的にブロックしたい
- オンラインのアクセス解析、行動追跡が気になる
- 専門サイト、あるいは他人に言えないサイトをよく利用する
- ほかの日本用フィルタではアンチ広告ブロックに遭遇してしまう
- uBlock Origin標準のリストを購読している
- ソーシャルボタンやページ内ポップアップなどの迷惑要素もブロックしたいが、既存のソーシャル/迷惑系フィルタでは満足できない/誤爆が多い
- 速度・効率とブロック力を両立させたい
- 広告を目にしないことより、通信量の削減が第一
- ある程度は悪質サイトやコインマイナーもブロックしてほしい

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt&title=Yuki's%20uBlock%20Japanese%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-filters.txt)

#### 特徴

<details>
<summary><strong>網羅性</strong></summary>

日本語サイト<sup>3</sup>のPC用公開フィルタリストとして、2021年4月現在メンテナンスされているものの中で最高のブロック性能を持ちます。とくにアクセス解析については他の日本用フィルタではおまけ程度にしか扱われていませんが、当フィルタはできるだけブロックします<sup>4</sup>。アンチ広告ブロックについても、日本用フィルタのなかで最も先進的な対策を取り入れています。また、当フィルタの管理人は国際的な広告ブロックコミュニティと連携しているため、YoutubeやFacebookなど個人での対応が困難なサイトにもある程度対応できます。これらのサイトの広告は特定条件でしか出なかったり、人によって出方が違ったりするため、コミュニティでの議論や情報を反映させていただいています。

</details>

<details>
<summary><strong>ブロック優先</strong></summary>

ブロック可能な対象はできる限りブロックします。これは当然ではなく、他のフィルタではブロック可能でも非表示で済ましているケースが多数あります<sup>5,6</sup>。ブロックが困難な場合、HTMLフィルタリングによる除去を試みています（これは広告を根こそぎ取り除きますがEdgeやChrome上で使えず、Firefoxでもいつも可能なわけではありません）。ブロックさえできればよいという中級者以上の方は「汎用的な要素隠蔽フィルターを無視する」にチェックを入れてください。表示崩れや多少の広告漏れと引き換えに、パフォーマンスを高めることができます。Yuki's uBlock Japanese filtersファミリーは、その場合でもある程度の性能を維持できます<sup>7</sup>。

<strong>初心者向け補足：</strong>広告ブロックには、ブロックと非表示という２種類の方法があります。ブロックはそのままですが、非表示とは広告を見えなくすることです。広告自体は読み込まれているため、通信量やコンピュータのリソースを消費しますし、悪質広告（Malvertising）の防御もできないことがあります。それでも非表示を使う理由はいろいろありますが、どこまで使うかはフィルタによってまちまちです。当フィルタは世界的に見てもブロックに極振りしたフィルタです。

</details>

<details>
<summary><strong>高効率</strong></summary>

ほとんどのルールがuBlock Originに最適化された、現状唯一の日本用フィルタです。uBlock Originはトークン化という仕組みにより高速処理を実現しています<sup>8</sup>。ルールがトークン化可能なら、ルール数は[処理時間に](https://www.wilderssecurity.com/threads/ublock-a-lean-and-fast-blocker.365273/page-155#post-2831026)[影響しません](https://twitter.com/i/web/status/1289255976198123520)。uBlock Originにおける限り、ルールが多いと重くなるという議論は[ナイーブな直感に基づいた完全な誤りです](https://www.wilderssecurity.com/threads/ublock-a-lean-and-fast-blocker.365273/page-204#post-2975580)<sup>9</sup>。当フィルタはできるだけトークン化を意識したルールを心がけており<sup>10</sup>、非表示フィルタについても[最小マッチング](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters#important)の原則を満たしつつ、できるだけ高速で誤爆の少ないフィルタを使うよう心がけているつもりです。さらに、数か月ごとに冗長なルールとデッドドメインのチェックを行い無駄を省いているほか、スクリプトレットフィルタについてはプロパティや関数のチェックをできる限り行い、不要なルールを追加しないようにしています。

</details>

<details>
<summary><strong>併用可</strong></summary>

日本人作者によるフィルタリストとして初、かつ現状唯一、EasyListなど標準フィルタリストとの併用を考慮しています。具体的にはブロック対象に違いがなく、パフォーマンスや誤爆の観点から問題がない場合、[EasyList](https://easylist.to/easylist/easylist.txt), [EasyPrivacy](https://easylist.to/easylist/easyprivacy.txt), [Peter Lowe's Ad and tracking server list](https://pgl.yoyo.org/adservers/serverlist.php), [uBlock 内製フィルター](https://github.com/uBlockOrigin/uAssets), [AdGuard Base](https://filters.adtidy.org/extension/ublock/filters/2_without_easylist.txt), [AdGuard Tracking Protection](https://filters.adtidy.org/extension/ublock/filters/3.txt), [AdGuard URL Tracking filter](https://filters.adtidy.org/extension/ublock/filters/17.txt), [Fanboy Enhanced Tracking](https://www.fanboy.co.nz/enhancedstats.txt), [280blocker domain filter](https://280blocker.net/download/)など、標準リストおよび併用されることが多そうなリストとルールを統一しています<sup>11</sup>。これにより重複が排除され、フィルター一覧でのフィルタ有効数<sup>12</sup>が正しく表示されるだけでなく、非表示フィルタの多重適用も回避できます。つまり単独でもご利用可能ですが、上述の各種リストと併用した場合でも無駄がありません<sup>13</sup>。逆にAdGurad Japaneseを除く他の日本用リストは標準リストとの併用が考慮されておらず、パフォーマンス上の影響に加え、まれに競合して不具合やアンチ広告ブロックの原因となることもあり<sup>14</sup>、Braveの日本用フィルタに採用されなかった[一因](https://github.com/brave/adblock-lists/issues/355#issuecomment-609680337)となっています。また、標準リストで発生する不具合が当該リストで修正されない場合、こちらで修正いたします。以下に主要なフィルタリストとYuki's uBlock Japanese filtersファミリーとの互換性をまとめました（同系統、たとえばAdGuard AnnoyancesならYuki's uBlock Japanese filters - Annoyancesを購読した場合です）。

| リスト名 | 互換性 | 説明 |
|:---|:---:|:---:|
| uBlock内製フィルター, EasyList, EasyPrivacy, Peter Lowe’s Ad and tracking server list, AdGuard Base, 280blocker domain filter, AdGuard Social Media, uBlock filters – Annoyances | ◎ | 互換性が最大限考慮されており、併用しても無駄はほとんど生じない |
| AdGuard Chinese/EasyList China, RU AdList, Fanboy Enhanced Tracking, AdGuard Annoyances, EasyList Cookie, Fanboy’s Annoyance, Fanboy’s Social | ○ | 互換性がある程度考慮されており、多少の無駄は生じるがあまり問題ない（Fanboy系は互換性低め） |
| もちフィルタ, もち拡張フィルタ, いちごフィルタ, ことりフィルタ, ねぎフィルタ, AdGuard Japanese | △ | 併用すると大量の無駄が生じるが、問題が生じるかは未確認 |
| 豆腐フィルタ, 280blocker adblock filter | × | 大量の無駄だけでなく、実際に問題が生じるため併用は非推奨 |

</details>

#### 対象
- 広告、アフィリエイトリンク
- 一部のプロモーションコンテンツ（ネイティブ広告）<sup>15</sup>
- 侵襲性の高いセルフプロモーション<sup>16</sup>
- アクセス解析、行動追跡、ヒートマップ、バグレポート
- サードパーティーまたはスクリプトを伴うアクセスカウンター
- 一部のトラッキングパラメータ
- 主に上記をブロックしたため生じた枠や不要なスペース
- アンチ広告ブロック
- 迷惑・有害なポップアップ、ポップアンダー、リダイレクト
- 一部の詐欺・悪質サイトや知恵袋の偽サイト（セキュリティーソフトの代わりにはなりません）
- コインマイニングなど、ユーザーの同意を得ずにコンピュータのリソースを浪費するもの
- uBlock Origin標準フィルタリストで生じる不具合の修正

#### 対象外
- サイトの内容と強く関連しており（例：具体的な商品のレビュー）、かつ量が過剰でなくユーザーに不利益・不快感を与えない広告<sup>17</sup>（「ゲームのブログだからゲームの広告」程度では強く関連しているとみなしません。ただしあるテーマのまとめサイトなどで潜在的な有用性がある場合、画像のみブロックしリンクは残すことがあります）
- 運営母体の系列サイトへのリンクバナーで、それほど不快でないもの<sup>18</sup>
- アフィリエイトリンクの一般非表示（280blockerさんと同様の[理由](https://280blocker.net/advanced-settings/)）
- 広告ブロッカー検知用の罠スクリプト
- ファーストパーティーの単純なCGI/SSIアクセスカウンターで、広範に使われているもの以外
- Google Safe Browsingでカバーされている、またはモバイル限定の悪質サイト
- デッドドメイン

## Yuki's uBlock Japanese filters - Paranoid （大雪フィルタ）

Yuki's uBlock Japanese filtersに追加できるフィルタで、多少の不具合を覚悟でより強固にブロックします。<strong>自己責任で使用してください</strong>。トラッキングパラメータも除去するほか、一部、トラッキングパラメータを含むリンクからの移動もブロックします。この場合、<strong>「uBlock Origin は、このページの読み込みをブロックしました」画面で右側の虫眼鏡アイコンをクリックすると、トラッキングパラメータを除いたURLが（場合によってはいくつか）表示され、そのままクリックできます。</strong>ただし、ブロックするとあまりに煩雑になる場合はブロックしません。また、gwarser氏の[Block access to LAN](https://github.com/gwarser/filter-lists/blob/master/lan-block.txt)フィルタによるLANへの攻撃を防ぐルールも含みます。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Paranoid">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-paranoid.txt)

## Yuki's uBlock Japanese filters - Social （あられフィルタ）

ソーシャル要素をブロックするフィルタです。[AdGuard Social media filter](https://kb.adguard.com/en/general/adguard-ad-filters#social)との互換性を重視しており、一部、共通のルールがあります。ブロック優先主義のため、非表示にしかできないものは迷惑度が高いものを除き無視します。また、ブロックできても他の要素まで巻き込んでしまう場合はブロックしません。これらも非表示にしたい方や、海外のサイトもご覧になる方はAdGuard Social mediaを併用してください。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Social">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-social.txt)

#### 対象

- シェアボタン
- FeedlyとTumblrのフォローボタン
- Lineのいいね/友だち追加ボタン
- 有益性の低い一部のソーシャルウィジェット
- ごく一部のソーシャルログイン
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


## Yuki's uBlock Japanese filters - Annoyances （みぞれフィルタ）

広告以外の迷惑要素をブロックするフィルタで、Yuki's uBlock Japanese filtersとの併用を前提とします。一部、[Fanboy's Annoyance List](https://easylist.to/easylist/fanboy-annoyance.txt), [AdGuard Annoyances](https://kb.adguard.com/en/general/adguard-ad-filters#annoyances), [uBlock filters – Annoyances](https://github.com/uBlockOrigin/uAssets/blob/master/filters/annoyances.txt), および[Web Annoyances Ultralist](https://github.com/yourduskquibbles/webannoyances)と共通のルールもあります。AdGuard AnnoyancesおよびuBlock filters – Annoyancesとの互換性を意識していますが、Socialの場合ほどではありません（併用可能ですが、多少の無駄が生じます）。

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
- 一部のセルフプロモーションや、プロモーション広告
- メールマガジン購読やサブスクリプションを促すバナー
- 不要な待ち時間（多くの場合、広告の類を見せるために使われる）
- 楽天の、デフォルトでチェックされているメールマガジン配信チェックボックス（アンチェックします）
- Twitterのおすすめトピック、おすすめユーザー、おすすめツイート、「タイムラインにトピックも表示しましょう」、新しいリストを見つける
- 迷惑度の高いチャットウィジェット（大型ポップアップなど）
- その他多くのユーザーにとって迷惑・不要と思われるもの

#### 対象外

- 上記対象に該当するが潜在的に、または人によっては有用なもの
- ログインサイトで、デフォルトで無効のプッシュ通知（ニコニコなど）
- 右クリック防止やコピープロテクトの類（すべての利用者に著作権を遵守していただけるならよいのですが、その保証がない以上あえてブロックしません）
- 開発者ツールの妨害スクリプト
- ペイウォール（クッキーを参照して「無料で読める記事はあと〇〇」と警告するタイプのものは対応する場合もあります）
- ポップアップやクッキーバナーの内、クリックが必須のもの（セキュリティ上の理由により、uBlock Originではあえて対応するスクリプトを採用していません）
- モバイルブラウザチェック（モバイルも限定的にサポートするため）
- レーティングウィジェット
- ブログ以外のブックマークボタン、クリップ系
- 一般のチャットウィジェット
- コロナウイルス関係で、一般的な通知ブロックで防げないもの（一時的なものなので）

モバイルサイトは限定的に対応します、メインはPCです。モバイルで使用する場合、拡張機能に対応したブラウザにuBlock Originを入れてご利用ください（この場合、モバイル用のフィルタと併用してください。ただし、一定の無駄は生じます）<sup>19</sup>。迷惑度のとくに高いものはYuki's uBlock Japanese filtersでブロックすることもあります。たとえば忍者レコメンドは当初、Annoyancesに入れていましたが、動画中に画像を挿入するケースなどが散見されたため方針を変えました。

<details>
<summary><strong>みぞれフィルタのサブフィルタ</strong></summary>

### Sable filters 2

クッキーの同意バナーを除去します。<strong>Yuki's uBlock Japanese filters - Annoyancesに含まれており、これを購読しているなら必要ありません（AdGuard for Androidを除く）</strong>。一方でYuki's uBlock Japanese filters - Annoyancesと異なり、AdGuardとも完全な互換性があります。

<a href="https://subscribe.adblockplus.org/?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt&title=Sabre%20filters%202">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/sabre-filters2.txt)


### Yuki's Blog parts filters

ランキングボタン等のブログパーツをブロックします。こちらも他のプラットフォームでご利用可能です。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt&title=Yuki's%20Blog%20parts%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts.txt)

### Yuki's Blog parts filters - Adult

Yuki's Blog parts filtersのアダルトサイト版です。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt&title=Yuki's%20Blog%20parts%20filters%20-%20Adult">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blog-parts-adult.txt)

### Yuki's Blogroll filters

ブログロール、相互RSSの類をブロックします。uBlock Origin専用で、Yuki's uBlock Japanese filtersとの併用を前提としています。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blogroll.txt&title=Yuki's%20Blog%20parts%20filters">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/blogroll.txt)

</details>

## Yuki's uBlock Japanese filters - Annoyances Plus （ひょうフィルタ）

人によって要否がわかれる、微妙な迷惑要素をブロックするフィルタです。対象をよく見て、必要な人だけ購読してください。

#### 対象

- Youtubeで一部の動画に表示される「プロモーションを含みます」
- 侵襲的ではないが、必要性も低そうなチャットウィジェット
- グランブルーファンタジー左側のバー

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances-plus.txt&title=Yuki's%20uBlock%20Japanese%20filters%20-%20Annoyances%2B">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/jp-annoyances-plus.txt)

## Anti Anti-adblock Enhancer for AdGuard （AdGuard アンチ広告ブロック対策強化パッチ）

<strong>「信頼するフィルタ」のチェックが必要です。また、DNSフィルタリングが有効の場合、効果が半減します（リソースリダイレクトの問題）。とはいえDNSフィルタリングにはメリットもあるため、各自の優先項目に応じて総合的に判断してください</strong>

AdGuard for Windows, AdGuard for Android, AdGuard for Mac, AdGuardブラウザ拡張機能専用です。AdGuard for Safari, AdGuard for iOS, AdGuardコンテンツブロッカーではあまり機能しません。AdGuardのアンチ広告ブロック対策機能を汎用フィルタで底上げします。個別対策はしませんので、対応漏れはこちらではなくAdGuard公式に報告してください（表示崩れなどの不具合報告は受けつけます）。一部アダルトサイト、違法コンテンツサイト、短縮リンクなどでよくみられる悪質ポップアップも軽減します。AdGuard標準フィルタリストへの追加を想定していますが、280blocker adblock filterなどほかのリストに追加してもある程度の効果はあると思います。uBlock filtersから取られたルールが多いため、ライセンスはGPLv3としています。

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/anti-antiadb.txt&title=Anti%20Anti-adblock%20Enhancer%20for%20AdGuard">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/adguard/anti-antiadb.txt)

## 280blocker adblock filter 悪質サイト対策強化パッチ

**AdGuard for AndroidおよびuBlock Origin専用**

280blocker adblock filterは、できるだけ多くのプラットフォームをサポートしたいという280blockerさんの願いにより、正規表現などの高度な文法を避け、互換性の高い記法で書かれています。ただ、このためにアプリの280blockerではブロック可能なビジターアンケート詐欺などの悪質サイトが完全にはブロックされません。当パッチはAdGuardとuBlock Originの高度な機能を使い、この点を補強します。また、ほかにも多くの悪質サイトを登録しています。AdGuardおよびuBlock Origin標準のフィルターリストに追加しても効果はありますが、Yuki's uBlock Japanese filtersご利用の場合は不要です。

<strong>2021年5月現在、「信頼するフィルタ」のチェックは必須ではありません。ただ、今後信頼するフィルタ用の機能を使う可能性はあるので、当サイトを信頼していただけるならチェックを推奨します。AdGuardの場合、信頼されたフィルタはページに様々なスクリプトを挿入することが可能になるため、本当に信頼できるのでなければチェックすべきではありません。</strong>

<a href="https://subscribe.adblockplus.org?location=https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt&title=280blocker%20AdblockPlus%E5%BD%A2%E5%BC%8F%20%E6%82%AA%E8%B3%AA%E3%82%B5%E3%82%A4%E3%83%88%E5%AF%BE%E7%AD%96%E5%BC%B7%E5%8C%96%E3%83%91%E3%83%83%E3%83%81">購読する</a>
[中身を見る](https://raw.githubusercontent.com/Yuki2718/adblock/master/japanese/280-patch.txt)

公益の観点から、このフィルタのみ[CC0](https://creativecommons.org/publicdomain/zero/1.0/deed.ja)で提供しています。

#### 対象外

- Google Safe Browsingで既にブロックされているもの

## 不具合、ブロック漏れの報告

GithubのIssueか[掲示板](https://jbbs.shitaraba.net/internet/25463/)を通して受けつけます。報告前に一度、<strong>新しいブラウザプロファイルを作り、uBlock OriginをクリーンインストールしてYuki's uBlock Japanese filters (+ Paranoid/Social/Annoyances）のみを購読した状態で問題が再現できるか</strong>を確認してください。また、ネットワークの別の部分でブロックしていないか（例: AdGuard Home, 280blocker DNS）も確かめてください。報告される方は、<strong>必ず以下の項目をすべて記入してください（Githubではテンプレートを用意してありますのでご利用ください）。</strong>海外サイトの不具合は、AdGuard Japaneseを除くuBlock Origin標準のフィルタ（+ 英語以外の場合、その言語の標準フィルタ）を併用しても再現する場合のみ対応いたします。

1. 問題が起こるサイトの完全なURL: 検索エンジンの場合は検索語もお願いします。
2. 現象の説明: 言葉による説明とスクリーンショットを両方含めてください。
3. 現象の再現方法: そのサイトに行くだけで100%再現できる場合でも、順を追って記述してください。例えばYoutube広告では新しいタブで開いたか、ページ内遷移したかで広告の出方が違います。そのサービスにログインした状態か否かも必ず記述してください。
4. 環境と設定: OS、ブラウザ、uBlock Originの種類とバージョン、また購読しているフィルタの一覧（スクリーンショット可）は必須です。Firefox上でのみ問題が発生する場合、GoogleかCloudflareのDNSで現象が再現できるかも確かめていただけると助かります。

注意： ログインが必要なサイトでの不具合や広告漏れにつきましては、ログや開発者ツールのスクリーンショット等、こちらがログインせずとも現象や解決を確認できる手段の提供をお願いすることがあります。

### ブロックおよびメンテナンス方針

- ルールの追加・削除については問題の検証を必須とします。他のフィルタが採用しているからというだけの理由、またはユーザー様の自己報告だけに基づく追加・削除は原則として行いません。

- 誤爆かどうかの判定が難しいケースもあります。そのような場合、そのサイトを日常的に使う人を想定するため、たまたま訪れた人には判定が甘い（広告漏れ）ように映るかもしれません。できるだけ最大公約数をとるように努力しますが、そもそも万人向けのフィルタなどありません。可能でしたら、適宜`$badfilter`, `$important`や例外などで対応してください。

- 他フィルタとルールを統一する場合を除き、一般ルールの使用を最小限に抑えています。ルールを一般化するのは原則、1) 少なくとも3か所以上で使われており、2) 他の場所でも使われる見込みが高く、3)かつ、誤爆する見込みが低い場合のみです。１つでも既知の誤爆がある場合は極力避けています。

- デッドドメインや不要になったルールは見つけ次第取り除く方針です。デッドドメインでもリクエストは発生するため、ほかのフィルタよりブロックが少なく見えることがあり得ます。

- ブロッカー検知用の罠スクリプトは意図的にブロックから除外しています。初心者の方にはこれがブロック漏れにみえるようです（[例1](https://github.com/easylist/easylist/issues/6407)、[例2](https://github.com/AdguardTeam/AdguardFilters/issues/67785)）。報告は実際の問題に対して行うか、せめてスクリプトの内容を確認してからにしてください。

- 正直なところ、長期的にメンテナンスできるかはわかりません。元々、当時更新が停滞していた[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)のフォークを考えていたのですが、許可が下りなかったためオリジナルフィルタを企画しました（わざわざフィルタを公開するからには、理由は他にもあります）。その間に豆腐さんも更新を再開されたようです。オリジナルとはいえ豆腐フィルタを参考にした部分は多々あり、ここに感謝申し上げます。

- 当フィルタの方針に同意いただけ、かつフィルタを作成する技能のある方の貢献は歓迎いたします。興味がおありの方はプルリクエストやIssueを通じて声をおかけください。それが面倒な方は、CC BY-SA 4.0の範囲において自由に改変、再配布も可能です。識別のために管理人の名前を入れたものの、本来はチームによる共同管理が望ましいと考えています。

## その他

[よくある質問](/japanese/FAQ.md)

### お断り

当サイト（レポジトリ）管理人および貢献者は、当サイトのフィルタやルールによって生じたいかなる損害についても責任を負いません。また、事前の予告なく公開を中止する可能性があります。

### 管理人について

EasyListなどの国際的な広告ブロックコミュニティにボランティアとして一年以上貢献を続けており、uBlock内製フィルタおよびAdGuard公式フィルタの共同管理者でもあります。280blockerさん、もちフィルタさん、豆腐フィルタさんなどにも問題報告をすることがあります。

<details>
<summary>註</summary>

<sub>1: AdGuardで使用する場合、最大の問題はspecific-generic（[解決予定](https://github.com/AdguardTeam/CoreLibs/issues/1437)）, redirect-rule, domain=のワイルドカード, script以外のHTMLフィルタでしょう。また、json-pruneの互換性によりYoutubeで問題が生じます。ほかにもAdGuard - uBlock Origin間にはスクリプトレットやProcedural cosmetic filtersの仕様の違いがいろいろあり、気づき次第報告していますが今後もそうしたことが起こるかもしれません。PC/MacでAdGuardをご利用の場合、AdGuard標準のフィルタリストに@hirorpt氏による[こなゆきフィルタ](https://github.com/hirorpt/filters#%E3%81%93%E3%81%AA%E3%82%86%E3%81%8D%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF-%E6%A8%99%E6%BA%96%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF1%E3%81%AE%E4%B8%8D%E5%85%B7%E5%90%88%E4%BF%AE%E6%AD%A3)を追加していただくのが最善と思います。AdGuard日本語フィルタはかつて不評でしたが、近年大きく改善されてきています。</sub>

<sub>2: AdGuardならスクリプトレットに互換性があるので許容範囲です。</sub>

<sub>3: いくつかの日本用フィルタと同様、日本語話者がよく利用すると思われる海外サイトにも対応しています（[FAQ A23](https://github.com/Yuki2718/adblock/blob/master/japanese/FAQ.md#q23-%E9%9B%AA%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%81%AE%E4%B8%AD%E3%82%92%E8%A6%8B%E3%82%8B%E3%81%A8%E6%B5%B7%E5%A4%96%E3%82%B5%E3%82%A4%E3%83%88%E7%94%A8%E3%81%AE%E3%83%AB%E3%83%BC%E3%83%AB%E3%81%8C%E7%B5%90%E6%A7%8B%E3%81%82%E3%82%8A%E3%81%BE%E3%81%99%E3%81%A9%E3%81%AE%E3%82%88%E3%81%86%E3%81%AA%E3%82%B5%E3%82%A4%E3%83%88%E3%81%8C%E5%AF%BE%E8%B1%A1%E3%81%AA%E3%81%AE%E3%81%A7%E3%81%97%E3%82%87%E3%81%86%E3%81%8B)）。</sub>

<sub>4: 後述のようにEasyListやEasyPrivacyなどから多くのルールを取り入れているものの、誤爆率の高いルールは除外しています。EasyPrivacyではレコメンドウィジェットやプッシュ通知などもブロックしていますが、これには異論もあるためこちらではAnnoyancesに分類しています。また私の知るこれらのフィルタによる誤爆で、未報告または報告済みだが未対処のものにも対応しています。一方、EasyPrivacyなどに含まれていないアクセス解析も（誤爆率の高そうなもの以外）多く盛り込んでいます。</sub>

<sub>5: 「要素をブロック」機能でMyフィルターを作っている人も同様です。画像についてはブロックしてくれることもありますが、イニシエイターはお手上げです。非表示についても質の低いルールが多いです。同機能は[あくまで補助であり](https://github.com/uBlockOrigin/uBlock-issues/issues/1058#issuecomment-631459847)、過剰に頼るべきではありません。</sub>

<sub>6: uBlock Originポップアップパネルの目玉アイコンをクリックして×印をつけると、ブロックされていない広告が見えてきます。元に戻すにはもう一度クリックして×印を外してください。</sub>

<sub>7: 当サイトのフィルタは[specific-generic](https://github.com/gorhill/uBlock/wiki/Static-filter-syntax#specific-generic)を利用したおそらく最初の公開フィルタです。なお、汎用非表示フィルタの数はパフォーマンスに[影響しません](https://github.com/uBlockOrigin/uBlock-issues/issues/738#issuecomment-619450820)。</sub>

<sub>8: 簡単に言うと、リクエストとルールそれぞれから抽出したトークンを使ってマッチする見込みがありそうなルールを絞り込んでいます。一般的なリクエストに対して大部分のルールは無いも同然であり、計算量のオーダーはルール数に依存しません。検索エンジンの転置インデックスに近いです。</sub>

<sub>9: 実測するのが早いです（レイテンシの影響が大きいのでキャッシュは維持してください。また、当然ですが有効数字や交絡要因に注意してください）。[こちら](https://brave.com/improved-ad-blocker-performance/)はBraveがuBlock Originの方式を導入した時の記事ですが、16,000個ルールを追加しても個々のリクエスト処理にかかる時間は1μsも変わらないことがわかります。メモリ消費はルール数に応じて増えますが、PCで問題になる量ではありません。ブロック漏れ（非表示含む）による消費のほうが大きいでしょう。逆に、非効率なルールが増えると遅くなるため、対象を絞り込むなどの対策が必要です。Twitterや個人ブログなどでルールを公開する人は多いですが、それらの中には問題のあるものも少なくありません。</sub>

<sub>10: ABP文法と異なり、[単語境界を意識](https://github.com/gorhill/uBlock/issues/1065)する必要があります。たとえば`/foo`というルールは、（他の部分でトークンマッチが起きない限り）`/foo1`というリクエストをブロックしません。明示的に`*`を追加するとブロックするようになりますが（`/foo*`）、これは`foo`のトークン化を妨げます（細かく言うと、８文字以上だと[話が別になります](https://github.com/gorhill/uBlock/issues/3011#issuecomment-329140908)）。主要な[bad token](https://github.com/gorhill/uBlock/blob/381498daa2a9ce089a69d044760190b1dd14b5ac/src/js/static-net-filtering.js#L2062)（原則、トークン化されない文字列）も覚えた方がよいでしょう。一般に遅いとされる正規表現ルールも条件を満たせばトークン化可能です。</sub>

<sub>11: 当フィルタはCC BY-SA 4.0のもとに配布しており、これはuBlock内製フィルターと280blocker以外を正しく継承（デュアルライセンス、バージョン違い）しています。uBlock内製フィルターはGPLv3ですが、AdGuardなどと比較して癖のないルールであり、一般的なフィルタ作者が思いつく範囲だと思います（管理人はuBlock内製フィルターのメンテナーでもあるため、自ら追加したルールも多数あります）。280blockerはライセンス指定なしですが、参考にしているのはドメインリストのみであり、これは書き方がほぼ一意に決まってしまうため問題ないと考えます。また一部、[EasyList China](http://abpchina.org/forum/forum.php), [RU AdList](https://forums.lanik.us/viewforum.php?f=102), [Brave Unbreak](https://github.com/brave/adblock-lists)（MITライセンス）からとられたルールがある他、[豆腐フィルタ](http://tofukko.r.ribbon.to/abp.html)を参考にしたルールが少なからずあります（著作権上、そのままの使用はなるべく避けましたが、どうしても同じになってしまったものもあります）。</sub>

<sub>12: 有効数には優先順位がありませんので、Yuki's uBlock Japanese filtersの内どれだけ使われているか知りたい場合、一度Yuki's uBlock Japanese filtersのチェックを外して他のフィルタを更新し、再度チェックを入れてください。なお、この方法で真の有効数がわかるのはYuki's uBlock Japanese filtersならではであり、ほかのフィルタではわかりません。同じブロック対象を別のルールでターゲットにするケースが多数生じるためで、この場合、優先順位の低いトークン化可能ブロックルールは「死んだルール」（メモリのみ消費）、トークン化不能ブロックルールやProcedural cosmetic filters、スクリプトレットルール等はパフォーマンス上の損失となります。フィルター一覧の使用数は実際に使われるフィルタ数ではないということです。</sub>

<sub>13: これらのフィルタによる誤爆をより網羅的に修正していることもあり、既にEasyList等を併用されている方にはもっともおすすめできる日本用フィルタと言ってよいでしょう。ちなみに、日本以外の国や地域ではEasyListに各言語用のフィルタを追加して使うのが普通であり、各言語用フィルタはEasyListの併用を前提としたものとなっています。中国ではEasyList Liteというのを用意しており、中国語サイトを中心にみる場合はEasyListの代わりにこれを使ってもよいとされています。Yuki's uBlock Japanese filtersも、日本のサイトを中心に見るなら10万以上のルール数におよぶ標準リストの代わりに使えるものとして提供していますが、標準リストとの併用も可能としている点が異なります。実は、標準リストの変更に追随していくのが一番大変な作業です。</sub>

<sub>14: 主に汎用ルールやスクリプトレットの不一致によるもので、海外アダルトサイトなどで顕著です。</sub>

<sub>15: 有用性などを鑑み、すべてはブロックしません。大まかには、記事リストの間に挿入されるもの、ネイティブ広告としての性質が強いものなどを中心にブロックしています。</sub>

<sub>16: セルフプロモーションは悩ましい対象です。AdGuardなどにもしばしば広告として報告する方が来られますが、基本的に迷惑要素として対処しています。Yuki's uBlock Japanese filtersの基準はこれより厳しく、記事中に挿入されるバナーなど侵襲性が高いものや、冗長なものなどはブロックすることがあります。とはいえ、ブロックしすぎと思われるものがあればご報告ください。</sub>

<sub>17: 実際には、1. 一般的なブログにおける商品かサービスについてのレビューに付随するAmazonや楽天へのリンクで、量が過剰でなく、他の関係ない商品やサービスへのリンクを含まないもの、2. そのサイトの管理者による著作物などの紹介、に限定しています。280blockerさんの[おっしゃるように](https://280blocker.net/advanced-settings/)これらを消すと文章が不自然になるケースもありますし、消したい方は「要素をブロック」で簡単に消せるものがほとんどです。他の日本用フィルタでも、もちフィルタさんが`amazon-adsystem.com`のウィジェットをブロックされている以外はせいぜい汎用非表示にとどまっています。そのもちフィルタさんも、`ssl-images-amazon.com`や`ecx.images-amazon.com`はコメントアウトされている（ブロックしていない）ことから苦心の跡がうかがえます。この辺りはすべてのフィルタ作者の悩みの種です。</sub>

<sub>18: こちらも基本、他の日本用フィルタでもブロックされていません。そもそも広告でなく、画像付きのリンクに過ぎませんが、侵襲性が高いものについては（ときにAnnoyancesで）ブロックする場合もあります。</sub>

<sub>19: Yuki's uBlock Japanese filtersと比べてAdGuardで機能しないルールは減っています。uBlock Originでの使用を推奨しますが、このフィルタについてはAdGuardでの使用も今のところ許容範囲です。<strong>ただしAdGuard for Androidでご利用の場合、Sabre filters2などのサブフィルタを別途購読してください</strong>。AdGuardブラウザ拡張機能ではその必要はなさそうです。AdGuardコンテンツブロッカーでの使用はおすすめしません。</sub>

</details>