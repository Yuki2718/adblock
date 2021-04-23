## 広告ブロック FAQ

最終更新：2021/04/23

内容は記事執筆時点のものですのでご了承ください。脚注は少し詳しい方向けです。

### ブロッカー選択

#### Q1 AdBlockやAdblock Plus（ABP）ではダメなのですか？

<details>

<summary><strong>A1</strong></summary>

  それらでも大部分の広告は消えるでしょう。ですが、AdBlockで適用される日本語サイト用フィルタのABP Japanese filtersは2020年2月に更新が停止しており、不具合の修正等は期待できません（ABPでは既に削除され、日本用フィルタ不在です）。広告ブロッカーとは基本的にフィルタに書かれたルールを強制するためのプログラムであり、フィルタこそがその心臓部にあたります<sup>1</sup>。主要な日本語サイトの広告を大体除去するだけなら、100ほどのドメインをブロックするだけでもかなりの効果がありますが<sup>2</sup>、一部の厄介なサイトに対応するには特殊な文法で書かれたフィルタが必要です。そしてここからが重要なのですが、<strong>現在の主要な広告ブロッカーにはそれぞれ専用のフィルタ記法があり、それを無視して使うと十分な効果が得られません。</strong>今のところ、もちフィルタや豆腐フィルタといった主要な日本用フィルタが十分に性能を発揮できるのはuBlock Originだけであり、AdGuard（iOS版とコンテンツブロッカーを除く）が許容範囲といえる互換性を持っています<sup>3</sup>。日本用のフィルタでABPと互換性があるフィルタには280blockerさんのものとiOS向けAdGuard日本語フィルタがありますが、前者はモバイルサイトを対象としています。ほかに選択肢がないならともかく、より良い選択肢がある以上、わざわざAdBlockやABPを使う必要はありません。uBlock Originに変えたことで不具合が出たという方は、ABPでデフォルト無効のEasyPrivacyかPeter Lowe’s Ad and tracking server listが原因の可能性が高いです。

  詳しい方向け補足：ABPがダメな理由としてよく「控えめな広告の許可」が挙げられますが、これはオプションから無効にすれば信用面を除いて問題になりません。もちろん信用は大事ですが、機能面の話をほとんど見かけないため、少し補足します。ABPではuBlock Originでいうprocedural cosmetic filtersとスクリプトレットをまとめてスニペットと呼んでいますが、ABPのスニペットは、例えばhide-if-contains-image-hashのような、必要性がよくわからない非表示系に偏っています。その一方でuBlock Originのset.jsに相当するoverride-property-readなどは2020年8月にようやく実装される始末で、ブロックに役立つ機能は大きく後れをとっています。また、uBlock Originが、たとえほとんどのユーザーが気づかないレベルでもパフォーマンスに大変気を遣っているのに対し<sup>4</sup>、ABPは特定サイトのみにせよクライエントサイドで機械学習（TensorFlow）を走らせるなど、多少のパフォーマンス低下はやむを得ないと考えているように見えます（人間がカバーしきれない部分を機械学習で補う発想自体は悪くないと思いますが、ABPが対象としているFacebook等の特定サイトについてはカバー可能だと思います）。
  
  <sub>1: [Firefox版uBlock Origin公式ページ](https://addons.mozilla.org/ja/firefox/addon/ublock-origin/)より引用：「この拡張機能は、あらかじめ設定されているフィルターのリストが無ければ意味を成しません。ですので、何かしらの形で貢献したいと考えることがあった時は、これらのリストを無料で懸命に更新し続けている方々を思い出してください。」また、[AdGuardTeam/AdGuardFilters](https://github.com/AdguardTeam/AdguardFilters)（AdGuardのフィルタ専門レポジトリ）の副題："The place where ads are actually blocked"</sub>

  <sub>2: 280blockerさんがよいタイミングで[記事](https://280blocker.net/blog/20201004/2549/)を書いてくださっていました。この統計は、スマホ広告ブロック黎明期にFilterProxyやWeblockに手動でドメイン登録してブロックされていた方には納得できるのではないかと思います。他の方法で消える広告/消せない広告については私もデータがありませんが、URLによるブロックもドメインブロック同様、一部のルールは多くヒットし何千ものページで機能する一方、滅多にヒットしないルールが大部分を占めます。後述のCNAMEトラッカーなどは、誤爆を気にしなければたった２つのURLルールでかなりの部分がブロックできます。</sub>

  <sub>3: ABPでは+jsや:styleといった文法が機能しないのが致命的です。これらはページにスクリプトや特定のCSSを挿入するもので、アンチ広告ブロックや迂回広告などに対処するうえで強力な武器になります。実はスクリプトについてはABPも対応しているのですが、ABP用の文法で書く必要があります。</sub>

  <sub>4: uBlock Originのパフォーマンス追及は徹底しており、拡張機能だけでなくフィルタにも容赦なく改善を求めてきます。たとえばEasyListの[この変更](https://github.com/easylist/easylist/commit/eca8326d7ac0fd71d67b8264d13e91293376cf73)はuBlock Origin開発者の要求に基づくもので、彼がベンチマーク上のパフォーマンス劣化に気づいたことが発端となっています。</sub>

</details>

#### Q2 AdBlockとAdblock Plusの違いは？

<details>

<summary><strong>A2</strong></summary>

  歴史的な経緯についてはほかに優れた記事があるのでそちらに譲ります。現在はAdBlock（getadblock .com）のエンジンはAdblock Plusそのものであり、外装を付け替えただけです。小文字のAdblockについては知りません。

</details>

#### Q3 ブラウザ組込みのブロッカーはどうですか？

<details>

<summary><strong>A3</strong></summary>

  A1.を参照していただきたいのですが、豆腐フィルタやもちフィルタが採用しているuBlock Origin文法に対応した組込みブロッカーは、PCでは私の知る限りBraveのみです。しかし、Braveは今のところカスタムフィルタの購読ができません。Vivaldiはカスタムフィルタの購読ができますが、非表示や正規表現すらサポートしておらず、機能的にはAdblock PlusはおろかiOSのコンテンツブロッカーにも劣ります。

</details>

#### Q4 Chrome拡張機能のManifest V3移行で、広告ブロック拡張は使えなくなると聞きました。

<details>

<summary><strong>A4</strong></summary>

  まず、専門外ですので以下には間違った点があるかもしれません。<strong>広告ブロック拡張自体はManifest V3準拠のDeclarative Net Request APIでも可能です</strong>。V3移行で広告ブロック拡張が死ぬかのような主張は的外れです。しかし、現状のまま移行されるとuBlock Originのような[高度で柔軟な機能を持った拡張機能](https://twitter.com/gorhill/status/1316734012963119105)は死滅します。それ以上に、少数のボランティアに頼っている現在のフィルタコミュニティは大打撃を受けるでしょう<sup>5</sup>。既に（Manifest V3に近い）iOSは大きな負担となっています。広告ブロックコミュニティ側も、Manifest V3のすべてに反対しているわけではもちろんなく、ちゃんと意味のある制約は受け入れる意思を[示しています](https://github.com/uBlockOrigin/uBlock-issues/issues/338#issuecomment-534261690)。批判の要点は、プライバシー保護が目的というなら[筋違いではないか](https://www.eff.org/ja/deeplinks/2019/07/googles-plans-chrome-extensions-wont-really-help-security)という点と、広告ブロックコミュニティの実情を[理解していない](https://adguard.com/ja/blog/how-ad-blocking-is-done.html)という点が大きいのではないかと思います<sup>6</sup>。webRequest APIのうちブロック以外は残るため、Chromiumチームが挙げているような悪用はManifest V3でも可能で、プライバシー保護への直接的な効果はほぼありません。現状（2021年01月）ではV2がいつ切り捨てられるのか、V3がこのまま実装されるのか、企業向けに残されるというブロッキングwebRequest APIには誰がアクセス可能なのか等、不明なことが多すぎてあまりコメントできることはありません。ちなみに、[Ad Blocker Developer Summit 2020](https://adblockerdevsummit.com/)において、Mozillaも長期的にはwebRequest APIを切り捨て、Declarative Net Request APIに移行する予定であることが[示されました](https://www.youtube.com/watch?v=tpDFS-GUytg)。発表を行ったRob Wu氏にPeter Lowe氏が質問したところ、「Declarative Net Request APIが代替として十分なものになってからの話で、すぐではない」とのことですが。

  <sub>5: 機械学習を使えばいいという人もいますが、現状ではフィルタコミュニティの代替になるようなものではありません。Adblock Plusは既にFacebookのフィルタ作成用に[機械学習を使っています](https://gitlab.com/eyeo/adblockplus/adblockpluscore/-/issues/98)し、Braveが関与している[AdGraph](https://arxiv.org/abs/1805.09155)をはじめ、機械学習を広告やトラッキングのブロックに使った論文は多く出ています。</sub>

  <sub>6: 当初、Googleはパフォーマンスも理由に挙げていましたが、現行のAPIがパフォーマンス上まったく足かせになっていないデータが示されたためプライバシーに軸足を移しました。一方で、一般にはルール数の制約といったわかりやすい点ばかりが流布している気がします。ルール数は本題ではありません。そもそもuBlock Originが持つような高度な機能が必要となった背景には広告提供側とのいたちごっこが一因としてあります。Manifest V3に近いiOSではブロック側は圧倒的に不利な状況で、一部のアンチ広告ブロックや広告再挿入に対してはあきらめて広告を受け入れ、せいぜいそれがユーザーに目立たないよう誤魔化すのが精一杯です。幸い、日本ではそうしたサイトは比較的まれですが。</sub>

</details>

#### Q5 Nano Adblocker（+ Nano Defender）の方がよいと聞きました。

<details>

<summary><strong>A5</strong></summary>

  <strong>2020年10月17日追記：Nanoプロジェクト（Chrome版）はトルコの開発者に[売却され](https://github.com/NanoAdblocker/NanoCore/issues/362)、危険な機能が追加されたため[ストアから削除されました](https://github.com/jspenguin2017/Snippets/issues/2)。ChromeでNanoをご利用の方は速やかにアンインストールしてください。Firefox版は別の方がメンテナンスしているため大丈夫です。以下の内容は執筆当時のものです。</strong>

  目的と使い方によります。もし、アンチ広告ブロックを念頭に置いておられるのなら、uBlock Originで十分です。2020年時点で、Nanoに報告されるすべてのアンチ広告ブロックはuBlock filtersかuBlock filters - Annoyancesにて対処されています<sup>7</sup>。ただ、Nanoではコンテンツを妨害しないソフトアンチブロック（例：Outlook.com無料版で右側に出る「お願い」）もデフォルトで対処するのに対し、uBlock Originの場合はuBlock filters - Annoyancesの購読が必要になります。Nanoの最大の利点は強力だがリスクもあるスクリプトレットで一部の迷惑要素に対処できる点ですが<sup>8</sup>、Nano filters -  Annoyancesはほぼ海外向けです。日本語サイトを中心に見る人は、自分でルールを書くのでなければNanoを使うメリットはほぼありません。むしろ最新機能への追随が遅れることがあり<sup>9</sup>、使うフィルタによってはデメリットさえあります。ただ、NanoにはQuick reporterという問題報告ツールがあり、これは別の意味で大きなメリットといえます。アンチ広告ブロックは目立つため、初心者の方にはなにか特別な対処を要するものに思えてしまうのかもしれませんが、フィルタ作者にとって対処は容易です。しかしこれは評判が悪かったため、近年増えてきているのはブロッカーを検知してそれを迂回する広告を再挿入するパターンです（これもあまり成功していないようです。広告を見たくない人に無理やり見せるのだから当然ですが）。

  <sub>7: Nano Defenderには、あるタイプのアンチ広告ブロック全般に対処するgeneric solutionという仕組みもありますが、機能的にはuBlock Originでもほぼ同等のことは可能です。しかし、パフォーマンスや副作用への懸念などから[あえて避けています](https://github.com/uBlockOrigin/uAssets/issues/7468#issuecomment-635422293)。そもそもこれらのアンチ広告ブロックは対処が容易であり、最近の報告で増えているのはgeneric solutionが効かない独自実装によるものです。</sub>

  <sub>8: スクリプトレットにはもともとリスクがありますが、uBlock Originではあらかじめハードコードされたスクリプトのみを使うようにしてリスクを抑えています。この点はNanoも同じです。では何が違うかというと、uBlock Originの組込みスクリプトは最悪でもページの外見や機能を壊すくらいしかできないのに対し、Nanoのスクリプトにはたとえばクリックをシミュレーションするものがあり、これを使ったフィルタの存在を知っている攻撃者が対象サイトを乗っ取れば、マルウェアのリンクを自動クリックさせることもできます。ショッピングサイトなどであればもっと直接的な悪用もできるでしょう。このため、uBlock Originではこれらのスクリプトが広告やアンチ広告ブロックへの対処にどうしても必要となるまでは採用しないと決めています。</sub>

  <sub>9: DandelionSprout氏によると、domainオプションのワイルドカードサポートへの対応遅れが問題となったようです。</sub>

</details>

#### Q6 Nano Defenderの代わりはありますか/アンチ広告ブロック対策をどうすればいいですか？

<details>

<summary><strong>A6</strong></summary>

  A5で述べたように、Nanoはいらないと思います。uBlock Originに戻したことでアンチ広告ブロックが出るようになったという人は十中八九、フィルタ選択を間違えていると疑われます。まず、uBlock filtersが有効なことを確認し、それからほかのフィルタについても見直してみてください。初心者の方はフィルタを追加する方向に動いてしまいがちですが、AdGuardへの報告においてはむしろ過剰購読により惹起してしまっているケースが後を絶ちません。追加する前に、減らすか切り替えることをご検討ください。また、アンチ広告ブロックのテストページはuBlock filtersの対象外です<sup>10</sup>。テストページでブロッカーが検知されるからと言って、アンチ広告ブロック対策がされていないと早合点しないでください。それでもアンチ広告ブロックに遭遇してしまった場合<sup>11</sup>、[フィルタ作者に報告してください](https://www.reddit.com/r/firefox/comments/jbua53/nanoadblocker_nanodefender_is_malware_now/g8xrhct/)。フィルタで対処できないアンチ広告ブロックは知られておらず、サイト側がこちらの対策を監視していたちごっこにならない限りは必ず対処できます<sup>12</sup>。予防的な対処がしたいのであれば、一番簡単で効果的なのは「汎用的な要素隠蔽フィルターを無視する」にチェックを入れることです。ただし広告枠やテキスト広告、一部ポップアップが隠し切れなくなるなど副作用もあるため、中級者以上（ある程度自己対処できる方）向けです。どうしても標準のリストと日本用フィルタ以外にフィルタを追加したいのであれば、せいぜいAdGuard Baseくらいでしょう（uBlock Originの設定の、フィルター一覧 ＞ 広告にあるものを使ってください）。まれにuBlock filters未対応のアンチ広告ブロックに対応している場合もあります。ただし、uBlock Originで使うとそれなりに不具合もあり、逆にアンチ広告ブロックを起動してしまうこともあります（最近の[例](https://forums.lanik.us/viewtopic.php?f=62&t=45330)）。Fxxk Fxxkadblock（あえて伏字）は無駄が多く、作りもちょっと雑なためおすすめしませんし、uBlock filtersとBaseがあれば不要です<sup>13</sup>。Fanboy's problematic-sitesはA14で述べたFanboy's Enhanced Tracking Listのサブフィルタで、A14と同様の理由でおすすめしません。これらのフィルタで効果がある方は、もともとご利用のフィルタがアンチ広告ブロックのトリガーを引いてしまっている場合がほとんどです。一方、AdGuard AnnoyancesやuBlock filters - Annoyances、ついでにAdblock Warning Removal Listが対応するのはA5で述べたようにソフトアンチブロック、つまり邪魔にならないか×を押せば消せるようなものですので、これで悩む方はいないと思います。とくにAdblock Warning Removalはロシア語のマニアックなサイトを見る人以外には無意味といってよく、一時、uBlock Originでブラックリスト指定されていたほどです。アンチ広告ブロックは個別対応ではきりがないため、雪フィルタにおいてはトリガーをできるだけ丁寧に迂回して個別対策の必要性を減らしています。ほかの日本用フィルタと併用されるとこうした努力が水泡に帰す可能性があるため、やめてください。

  <sub>10: 雪フィルタでも対象外としていましたが、初心者の混乱を避けるため対応してみました。</sub> 

  <sub>11: 日本用フィルタでのみ惹起されるアンチ広告ブロックもあります。この場合uBlock filtersは対応しませんので、ご利用のフィルタ作者に報告してください。また、AdGuard日本語フィルタで対処されているアンチ広告ブロックは、原則としてuBlock filtersでは対処しません。同様の理屈でちょっと罠かもしれないのが、日本人利用者が多いと思われる違法コンテンツサイトやアダルトサイトの中に、たとえばスペイン/ポルトガル語のサイトがあります。この場合、uBlock Originではスペイン/ポルトガル語用のフィルタを購読するのが前提となりますが、実際にそうされている日本人利用者がどれほどいるか疑問です。そのため雪フィルタでは言語にこだわらず、日本人利用者がある程度いると思われるサイトは網羅的に対応しています（AdGuradにはフィルタの自動有効化機能があるためこうした問題は起きにくいですが、人によってはめったに訪れないサイトのフィルタを大量購読する結果になります）。</sub>

  <sub>12: uAssetsでcan't fixとなっているものは、いたちごっこの結果、対策が副作用をはらむものとなってしまったものです。一方、迂回広告やポップアップ、迷惑要素の中にはフィルタで対処できないものもあります。</sub>

  <sub>13: 同フィルタのソースのほとんどはuAssetsとAdGuardFiltersであり、uBlock filters, Base, または各言語用フィルタのいずれかで対処されます。しかしそれらと異なるフィルタ記法も多く、それらを購読している人には無駄になります。また、対象サイトの多くは頻繁に仕様を変えてくるのですが、同フィルタは廃れたルールを大量に含んでいます ~~掃除している様子はありません~~ （2021年4月20日訂正：してはいました。）。古いスクリプトレットルールはパフォーマンスの損失だけでなく不具合の原因ともなります（最近の[例](https://twitter.com/inkuringu_ika/status/1356507884993925120)）。加えて、多くの汎用非表示用が無効にされており、「汎用的な要素隠蔽フィルターを無視する」同様、枠残りなどの原因ともなります。</sub>

</details>

#### Q7 uBlock OriginもNanoのように売却されないか心配です。

<details>

<summary><strong>A7</strong></summary>

  確かなことは何も言えませんが、個人的な意見としては、Raymond Hill（uBlock Originの開発者、gorhill）は開発を中止することはあっても売却したり、その他ユーザーを危険にさらすことはないんじゃないかと思います。彼自身が今回の騒動で述べているように、現在の広告ブロック拡張機能は強大な権限を持っており、開発者を信用できなければ使うべきではありません。私はuBlock Originの前々身であるHttp Switchboardの誕生にも立ち会っている最初期ユーザーの一人で、そのころから何度か言葉を交わしていますが、ことセキュリティやプライバシーには厳格な人です。ほかの[悪質な拡張機能を見回ったり](https://www.bleepingcomputer.com/news/security/mozilla-removes-23-firefox-add-ons-that-snooped-on-users/)、パラメータの書換え機能などをセキュリティ上の問題で[却下したり](https://github.com/uBlockOrigin/uBlock-issues/issues/46#issuecomment-391303700)（同機能を採用したAdblock Plusは後に[脆弱性として指摘](https://forest.watch.impress.co.jp/docs/news/1180855.html)されることに）、例には事欠きません。また、お金に影響されるのを避けるため[寄付すら拒否](https://github.com/gorhill/uBlock/wiki/Why-don%27t-you-accept-donations%3F)しており、儲け話の誘いがあれば[さらし者にしています](https://twitter.com/gorhill/status/1293233244826218498)。実は一度、負担に耐え切れずuBlock Originの前身であるuBlockを新開発者に譲渡したことがあるのですが<sup>14</sup>、この時の失敗は氏にとって苦い経験だったようで、今でもときどきRedditなどで言及しています。

  <sub>14: 日本語では[こちらの記事](https://www.reddit.com/r/newsokur/comments/33wick/ublock%E3%82%AA%E3%83%AA%E3%82%B8%E3%83%8A%E3%83%AB%E3%81%AE%E4%BD%9C%E8%80%85%E3%81%8C%E7%8F%BE%E9%96%8B%E7%99%BA%E9%99%A3%E3%81%AE%E9%81%8B%E5%96%B6%E6%96%B9%E9%87%9D%E3%82%92%E7%96%91%E5%95%8F%E8%A6%96%E3%81%97%E7%8B%AC%E8%87%AA%E3%81%AB%E9%96%8B%E7%99%BA%E5%AD%98%E7%B6%9A%E3%82%92%E3%82%A2%E3%83%8A%E3%82%A6%E3%83%B3%E3%82%B9/)が詳しいです。ただし、uBlock Originの開発継続はもともとuBlockを委譲したときから決まっていました。</sub>

</details>

#### Q8 初心者におすすめのブロッカーを教えてください。

<details>

<summary><strong>A8</strong></summary>

  PCではブラウザ上のブロックで大抵の人は足りると思います。この場合、一番のおすすめはuBlock Originです。Macは使っていないのでわかりません。Androidだとアプリ内の広告もまれではないため、デバイス全体をカバーできた方がよいでしょう。AdGuard for Androidがもっともメジャーで、かつ機能的にも十分だと思います。[なんJ AdGuard部](https://wikiwiki.jp/nanj-adguard/)さんに記事がまとまっています<sup>15</sup>。iOSは2020年現在、広告ブロッカーへの制約が最も厳しい環境で、正直な話、厄介な広告再挿入などへの根本的な対処はできません（OSの問題で、ブロッカー開発者の技術でどうにかなるものではありません。文句はAxxleに）。日本語サイトを中心にみられる場合、280blockerがベストだと思います。最近の更新で、iOS14以上ならアプリ内広告にもある程度対応できるようになりました。少し詳しい人や海外サイトを本格的にみる人はいくつか選択肢がありますが、そういう人にはこんな導入記事は必要ないでしょう。ネットワーク全体をカバーするには、Pi-holeやAdGuard Homeを使う方法と、DNSキャッシュサーバーを広告ブロック機能のあるものにする簡易的な方法があります。AdGuard Homeについては280blockerさんがわかりやすい[記事](https://280blocker.net/blog/20181027/1254/)を書いてくださっています。ただしこれらはドメイン単位の「粗い」ブロックしかできないため、各デバイスのブロッカーを置き換えることはできません。

  <sub>15: 随所に当FAQの内容が反映されているようです。</sub>

</details>

#### Q9 ブロッカーを複数入れてもいいですか？

<details>

<summary><strong>A9</strong></summary>

  [やめて](https://twitter.com/gorhill/status/1033706103782170625)[ください](https://twitter.com/gorhill/status/1296122090026946567)。1.で述べたブロッカーとフィルタの区別が理解できれば、いかに無意味なことかわかるはずです。しかもuBlock Originのリソースリダイレクトルールを[無効にしてしまい](https://www.reddit.com/r/firefox/comments/l7xetb/network_priority_for_firefoxs_enhanced_tracking/gl9rn9n/)、いたずらに不具合やアンチ広告ブロックを引き起こしてしまいます。ブロックを強化したり、アンチ広告ブロックを除去したりしたいのでしたら、するべきことはブロッカーの複数使用ではなく、適切なフィルタの選択です（たくさん購読すればよいというものではない）。中級者以上の方であれば、ブラウザの広告ブロック拡張機能にhostsファイルあるいはネットワーク全体のブロック（たとえばPi-hole, AdGuard Home, UnboundなどによるDNSブラックホール）を組み合わせるのもありですし、Androidならブラウザ広告をuBlock Originで、その他のアプリをAdGuradでという対処も有効ですが、不具合への対処といった点から初心者にはおすすめしづらいものがあります<sup>16</sup>。また、目的が（少し）違う拡張機能、たとえばトラッキング対策のGhosteryやPrivacy Badgerなどを勧める人もいますが、これもほとんど意味がありません。[多くの論文](https://www.reddit.com/r/uBlockOrigin/comments/k6cezt/discussion_is_it_advisable_to_use_privacy_badger/gem3yds/)で、uBlock Origin（デフォルト設定）が最高レベルのトラッキング保護と高パフォーマンスを両立していることが実証されています。トラッキング対策を強化したいなら、やはりフィルタの選択が肝要です<sup>17</sup>。雪フィルタ単独でも日本のサイトにおいてはかなりのトラッカーをブロックしていますが、これにEasyPrivacyかAdGuard Tracking Protectionのどちらか（両方はほとんど無意味）を加えれば多くの人には十分以上です。これ以上を求めるなら、ブロッカーの併用などより[Medium mode](https://github.com/gorhill/uBlock/wiki/Blocking-mode:-medium-mode)といったデフォルト拒否の採用を考えるべきです。

  <sub>16: たまに、コンピュータのリソースを使わないからパブリックDNSでのブロックのほうが効率がよいと信じている人がいます。通信のフローを考えれば自明なはずですが、ブラウザ上でブロックすればそもそもDNSや広告サーバーへの通信自体が発生しないのに対し、パブリックDNSでのブロックはキャッシュがなければDNSの応答を待つ必要があります。ブラウザ組み込みのブロック機能を除けば、アプリケーション版AdGuardのみが、場合によりブラウザ拡張機能より先にブロックすることがありますが、これは一定のコストがかかる方法のため必ずしもパフォーマンス上ベターとはいえません。ただ、ブラウザ上でもブロックしている場合、[ブロック漏れにみえる]((https://www.reddit.com/r/uBlockOrigin/comments/kdz345/question_about_blocking/))おそれがあります。なお、Chromium拡張機能では[prefetchがブロックできず](https://www.reddit.com/r/uBlockOrigin/comments/lv47ac/dns_queries_can_be_seen_in_adguard_home_even_if/)、こちらはある意味本当の漏れですが、prefetchではハンドシェイクやTLSネゴシエーションまでしか行われないため、問題とみなすかは人によるでしょう。</sub>

  <sub>17: トラッカーは目に見えないためブロックしてもしなくてもほとんどのユーザーは気づかず、一方でしばしば不具合の原因となるため、フィルタ作者にとってモチベーションが上がりづらい対象です。実際、公開されているABP形式日本用ブロックフィルタで、トラッカーを独自解析して他リストにないエントリーを追加し続けているのは280blockerさんと当サイトくらいだと思います。</sub>

</details>

### uBlock Origin - 拡張機能

#### Q10 ブロックのカウンターが上がり続けます。/Adblock Plusの方がuBlock Originよりたくさんブロックしているようです。

<details>

<summary><strong>A10</strong></summary>

  カウンターの上昇は[何も問題](https://www.reddit.com/r/uBlockOrigin/comments/itw503/ubo_google_docs_high_cpu_spikes_and_blocked/g5l5yjd/)[ありません](https://www.reddit.com/r/uBlockOrigin/comments/j5cwdj/ubo_is_blocking_7k_xhr_requests_on_youtube_videos/g7sex8w/)。どういうわけか、カウンターが上がり続けるとパフォーマンスに悪影響があると信じている人が多いようです。確かに、ブロックされた場合にものすごい勢いでリクエストを送り続けるケースはあり、フリーズしたりCPU使用率が跳ね上がったりしますがこれはそのサイトの問題です。1秒に1つ程度のカウンター上昇なら何も影響ありません。どうしても信じられないなら、開発者ツールからパフォーマンスレコードをとって報告してください。証明できたらuBlock Origin史上初の発見です。また、逆にカウンターの数字が大きいほどたくさんブロックしてくれていると信じてアドオンやフィルタを比較する人もいますが、これも一概に言えません。Adblock PlusとuBlock Originではカウンターの仕様が異なりますし、HTMLフィルタで除去してしまえばカウンターの数字は上がりません。そもそもブロッカー検知用プローブ（アンチ広告ブロックとは無関係に、統計的情報を得るため使われることも多いです）などはブロックしない方がいいのですが、この点を理解されていない方も多そうです（[例](https://github.com/easylist/easylist/issues/6274)）。

</details>

### uBlock Origin - フィルタ

#### Q11 クラス名が毎回ランダムに変わる要素はどう消せばいいのでしょうか？/「要素をブロック」で消したものがすぐ復活します。

<details>

<summary><strong>A11</strong></summary>

  「要素をブロック」はフィルター作者のための補助ツールです。１つ２つならともかく、同機能で自動生成されたルールをたくさん作るのはおすすめしませんsup>18</sup>。クラス名が変わる場合、まずはクラス名以外で使える属性がないか、開発者ツールで見てみるのがよいと思います。もしなければ、該当要素の親や子孫で安定した属性を持つものや、使えそうなテキストを含むものがないか探します。そうしたものがあれば（必ずと言っていいほどあります）、あとは[Procedural cosmetic filters](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters)を使うだけです。初心者であれば`:has`, `:has-text`と`:upward`だけでも十分でしょう。

  <sub>18: スライダーの選び方にもよりますが、Youtubeのような複雑なサイトで下手にフィルタを作ると、のちに[問題に見舞われるケース](https://www.reddit.com/r/uBlockOrigin/comments/mblje3/cosmetic_filters_breaking_youtube_comments/gs1k0az/)もあります。基本的に、要素をブロックによる自動生成フィルタは一時しのぎ程度に使っていただくのが無難かと思います。そのための[エレメントザッパー](https://github.com/gorhill/uBlock/wiki/Element-zapper)もあります。

</details>

#### Q12 効率的なネットワークルールの書き方を教えてください。

<details>

<summary><strong>A12</strong></summary>

  [こちら](https://www.reddit.com/r/uBlockOrigin/comments/mdh9jz/order_of_complexity_for_network_filters/)に要点がまとまっています。大事なのは、
  1. 良質なトークンが抽出されるようにすること、すなわち、仕切られた7文字以内の語（できればbad tokenや一文字でない）をフィルタ中に確保する（正規表現フィルタは条件が複雑なので、ここでは割愛）
  2. それが難しいときは、タイプオプションやドメイン指定によりできるだけ限定する
  3. 1フィルタ中に二つ以上のワイルドカードを使うのはなるべく避ける

  効率的なフィルタは正しいフィルタの上に初めて成り立ちます。残念ながら、インターネット上に公開・共有されているフィルタには（ケアレスミスの範囲を超えて）間違ったものが少なくありません。たとえば、`||.example.com^`や`||*.example.com^`のようなフィルタは基本的に[間違い](https://www.wilderssecurity.com/threads/ublock-a-lean-and-fast-blocker.365273/page-207#post-2984667)です。これではドメインアンカーの意味がなく、誤爆の可能性が高まります。また、`/path/to/`が正規表現フィルタになってしまうことを理解していなさそうなもの、セパレータ`^`を「とにかくフィルタの最後につけるもの」と誤解しているようなケースも見受けられます。

</details>

#### Q13 効率的な非表示ルールの書き方を教えてください。

<details>

<summary><strong>A13</strong></summary>

  細かいTipsはありますが、一番大切なのは[最小マッチング](https://github.com/gorhill/uBlock/wiki/Procedural-cosmetic-filters#important)を意識することです。通常の非表示ルールでもそうですが、Procedural cosmetic filtersにおいては[とくに](https://github.com/uBlockOrigin/uAssets/commit/8fd12b060148cfde8e53e70012733b089abf65bc#commitcomment-39037147)[重要](https://www.reddit.com/r/uBlockOrigin/comments/j4ewg7/best_practice_hasx_or_xupward/)です（[実際に生じた問題の例](https://www.reddit.com/r/uBlockOrigin/comments/kg7224/youtube_homepage_loading_high_cpu/)）。

</details>

#### Q14 おすすめのフィルタ構成を教えてください。

<details>

<summary><strong>A14</strong></summary>

  フィルタ構成についてはこれが正解といえるものはなく、各自で調べて自身の好みに合うものを選択するしかありません。ただ、間違いといえるものはあります。フィルタを解釈して評価できる人はまれなため、インターネット上には主観的な使用感や信念にもとづいた「おすすめ」がたくさん転がっています。たとえば、Adblock Warning Removal Listは、最近になってようやく意味のないリストという認識が広まってきたようですが、数年前まであちこちでアンチ広告ブロック対策に推奨されていました。ここまでひどくはないものの、あまり正しく理解されていなさそうなリストとしてFanboy's Enhanced Tracking Listが挙げられます。このリストの最大部分は許可ルールによるブロッカー検知回避なのですが、ちょっと大雑把すぎて検知と関係ない広告スクリプトまで許可してしまっています。これらは基本的にイニシエイターで、最終的な広告は別のルールでブロックされますが、不要なスクリプトを走らせてまで一部の検知を回避することを、同リストの利用者が求めているかは疑問です<sup>19</sup>。残りの部分もすべてがトラッキング対策ではなく、迷惑要素なども含まれています。あまり意味のないリストについていえば、NoCoinが挙げられるでしょう。コインマイニング自体、絶滅してはいないものの下火ですが<sup>20</sup>、NoCoinでブロックされるものは（ほぼ？）すべてEasyPrivacy + uBlock filters - Resource abuseでカバーされています。

  一般的なアドバイスとしては、**初心者の方はともかく購読しすぎに注意することです**。日本用フィルタの複数購読、特定用途用フィルタの多重購読はおすすめしません。おそらく、**たくさん購読するとそれだけ多くブロックしてくれるという考えからなのでしょうが、これは必ずしも正しくありません**<sup>21</sup>。また、フィルタによる不具合は天災のようなもので、普段はあまり遭遇しませんが忘れたころにやってきます。多く購読すればするほど、メリットは薄くなっていき、不具合の確率ばかり高まります。それにいくらuBlock Originでも、Procedural cosmetic filtersやトークン化不能正規表現の無駄が積もればパフォーマンスに影響します。そもそもフィルタの購読は「なんとなく役に立ちそう」というあいまいな感覚ではなく、[実際に遭遇したニーズに基づいて行うべきです](https://www.reddit.com/r/uBlockOrigin/comments/jr6szm/suggestion_scoring_performance_of_filterlists/gbxu8i7/)。

  もう少し具体的に、PCの場合なら（あくまで参考程度にお願いします）
  - 内製フィルタ：最低でもuBlock filtersは維持することをおすすめします。ほかのフィルタに比べると不具合の率が少なく、日本語サイト利用者でもメリットは大きいです。Privacyはごくまれに誤爆することがあります。Badware risksやUnbreakは意味がわかっている人は外してもよいですが、維持しても問題はほとんどないと思います。
  - 広告：海外サイトをよく見る人はEasyListを維持。日本のサイトしか見ないなら、お好みで外してもよい
  - プライバシー：トラッキングを気にしない人、または雪フィルタ使用者は外してもよい。気にする人で、雪以外の日本語フィルタ使用または海外サイトをよく使うなら、平均的なブロック性能が高いが不具合も多いEasyPrivacyを維持するか、不具合は少ないが漏れも多いAdGuard Tracking Protectionから選択
  - マルウェアドメイン：お好みで。デフォルトのOnline Malicious URL Blocklistはブラウザのセキュリティ機能（Google Safe Browsing）とデータ共有しており、大部分はブラウザでブロックされます
  - 迷惑系：ソーシャルボタンを消したい人はAdGuard Social Mediaを追加してもよいでしょう。ただし、もちおさんが提供されている[ことりフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/kotori.html)やこちらで提供している[あられフィルタ](https://github.com/Yuki2718/adblock/blob/master/japanese/README-JP.md#yukis-ublock-japanese-filters---social%E3%81%82%E3%82%89%E3%82%8C%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF)も検討してみてください（あられはAdGuard Social Mediaとの互換性を意識して作っており、併用も可能です）。ほかの迷惑要素についても同じく、AdGuard Annoyances, [ねぎフィルタ](https://eeii0a5l.github.io/mochifilter_homepage/negi.html), [みぞれフィルタ](https://github.com/Yuki2718/adblock/blob/master/japanese/README-JP.md#yukis-ublock-japanese-filters---annoyances%E3%81%BF%E3%81%9E%E3%82%8C%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF)からの選択をおすすめします。ちょっと特殊なのがuBlock filters - Annoyancesで、これは主にソフトアンチ広告ブロックと右クリック/コピー禁止系への対策になりますが、Fanboy AnnoyanceおよびAdGuard Annoyancesの一部ルールがuBlock Origin上で無効化されてしまう場合の補完も兼ねています。EasyList Cookieを含むFanboy系は不具合の率が高く、初心者にはおすすめしません。クッキーの同意ダイアログのみ消したい方は[Sabre filters2](https://github.com/Yuki2718/adblock/blob/master/japanese/README-JP.md#sable-filters-2)もご検討ください。
  - 多目的：デフォルトのPeter Lowe'sはフィルタ数のわりに良い仕事を（主に海外サイトで）してくれているのですが、たまに誤爆することがあります。日本のサイトを中心に見るなら好みで外してもよいです。やや余談ですが、EasyListはよく訴訟の対象になり、その場合、対象ルールをEasyPrivacy（トラッキングも兼ねている場合）やPeter Lowe's（純粋な広告サーバー）に肩代わりしてもらうことがあります。
  - 地域、言語：英語、日本語以外のサイトをよく見る人はその言語のフィルタを追加。日本語については別途日本用フィルタを購読するのであればAdGuard Japaneseを外す
  - カスタム：お好みでもちフィルタ、豆腐フィルタ、雪フィルタの中から一つを追加（宣伝になってしまいますが、EasyListやEasyPrivacyを維持された方は誤爆やパフォーマンスの点から雪をおすすめします）

  フィルタ構成とは別に、中級者以上の方であれば「汎用的な要素隠蔽フィルターを無視する」はおすすめできるオプションです。パフォーマンスの向上に加え、誤爆やアンチ広告ブロックへの遭遇率を下げることもできます。その代わり広告枠やテキスト広告が隠し切れないケースも出てきます。

  <sub>19: 一般非表示が有効なら、結局検知されてしまうことが多いです。そもそも同リストで許可されている検知スクリプトは、多くがEasyListなどの主要フィルタ（雪も）で既にブロックから除外されています。</sub>

  <sub>20: coinhiveをはじめ主要なマイナーのほとんどがサービス終了しており、フィルタ作者ですら実際に機能しているマイニングに会うことは極めてまれです。</sub>

  <sub>21: 理由は大きく二つあります。まず、許可ルールが原則的にブロックルールに対して優先されるということがあります。ある程度の規模のフィルタリストであれば必ずといっていいほど不要になった許可ルールが含まれますし、リストによっては絞り込みが甘い許可ルールもあるかもしれません。こうした許可ルールによって広告が貫通するケースが報告されています（最近の[例](https://github.com/AdguardTeam/AdguardFilters/commit/3a0d2d14fe216b0d77f8462638ba2a0a4130758b)）。もう一つは広告再挿入です。これはアンチ広告ブロックと原理は同じで、ブロッカーを検知し、アンチ広告ブロックの派手な警告の代わりにブロッカーを迂回する広告を再挿入するものです。あるリストがせっかく再挿入を惹起しないようにしていても、他のリストが惹起してしまうと意味がありません。

</details>

#### Q15 EasyListやEasyPrivacyは不具合が多いと聞きます。

<details>

<summary><strong>A15</strong></summary>

  事実です。私もこれまでいろいろな形で、おそらく数十件は報告しています。なお、ルールが多いから不具合が多いわけではありません。80対20の法則ではありませんが、大部分のルールは不具合と無関係な一方、誤爆しやすいルールというのがあります。雪フィルタではこの点を逆手にとり、誤爆しやすいルールをなるべく外すことにしました<sup>22</sup>。またアンチ広告ブロックを惹起しやすいという議論も聞きます。これは間違ってはいませんが、「それほど違わない」という印象です。もっとも一般的なトリガーは非表示、とくに`##.adsbygoogle`ですが、これは主要な日本用フィルタすべてに含まれています。EasyList側も当然気づいており、[変更してみたり](https://github.com/easylist/easylist/commit/216979ef1f3643405c9d2dba077807e114def71c)（失敗）、uBlock Origin限定ですが`*##.adsbygoogle:style(width:1px!important;height:1px!important;)`を検討してみたり（レイアウトが崩れるケース有り、断念）<sup>23</sup>、その他のトリガーも含めて世界的なアンチブロックの潮流についてはむしろ日本用フィルタより対策が進んでいます。（EasyListで"Remove unused filter"というコメントで削除されているルールの多くは、私を含むフィルタ作者からのフィードバックに基づくアンチ広告ブロックのトリガーです）、逆に日本用フィルタでのみトリガーされるものも多くあり、とくに海外サイトではその傾向が強いです。ところで、不具合が多い理由の一つは日本のユーザーからの報告がほとんどないことです。EasyListでなくとも、日本では280blockerさんを唯一の例外として、フィルタ作者への報告自体がまばらな印象です。すべてのユーザーが不具合を自己修正できるとは思えないため、ブロックをそのサイトで無効にしたり、dynamic filteringの緑で上書きしたりといった対処をされている方が多いのではないかと思います。フィルタ作者はそういった「荒療治」より効果的な対処ができますし、あなたの報告がほかの多くのユーザーを助けるかもしれません。ぜひ積極的な報告をお願いします。なお、当サイトおよびしたらばの[簡易報告掲示板](https://jbbs.shitaraba.net/bbs/read.cgi/internet/25463/1598352715/)では、EasyList等外部フィルタ併用時の不具合も受けつけ、可能であれば関係先にフィードバックを送ります。

  2021年4月12日追記：EasyListは海外用と認識されている場合があるようですが、実際は全世界の広告ブロックのための標準フィルタです。当然、日本用のルールも多く含み、たとえば`##.res_ad`などはモバイル版5ちゃんねるくらいでしか使われていません。ABPのページに"Specialization: English"と書かれているのもそうした認識が広まった一因かもしれませんが、おそらく、これまでの日本用フィルタがEasyListの併用を前提としていなかったこともあると思います。

  <sup>22: imasdkなど、メリットとの兼ね合いから誤爆が多くても採用したルールもあります。ちなみにルール数というのは、せいぜい大雑把なメモリ消費量の目安にしかなりません。処理時間に影響しないのは随所で書きましたが、ルール数が多いほうがブロック性能が高いとも限りません。DandelionSprout氏のExtremely Condensed Adblocking Listが極端な例ですが、誤爆を気にせずルールを一般化すればルール数を減らしつつ高いブロック性能を実現できます（雪フィルタはこの逆で、なるべく一般化を避けているためルール数は多くなります）。メモリ消費についても、フィルタの書き方に左右されるのであくまで大雑把な目安です。ルール数ばかり気にする人がやたら多いので書かせていただきました。</sup>

  <sub>23: これはList Authors Chatという、国際的なフィルタ作者間の内部ディスカッション（雪フィルタ管理人もメンバーの一人）で検討されたため、公開可能なソースはありません。</sub>

</details>

#### Q16 ページをクリックすると発生するポップアップ/リダイレクトや「見えない広告」をなんとかしたいです

<details>

<summary><strong>A16</strong></summary>

  透明なオーバーレイを使用するケースはありますが、多くの場合、HTMLにクリックイベントが仕込まれているだけで「見えない広告」という表現はあまり適切ではありません。原因はケースバイケースで、シンプルなブロックルールで済む場合もあれば、スクリプトレットが必要な場合もあります。これらを用いるサイトの多くはアダルト、違法コンテンツ、または短縮プレミアムリンク系のサイトで、頻繁に仕様やドメインを変えてくるため個人フィルタでの十全な対応は困難です。これらのサイトを用いる方はEasyListとuBlock filtersの両方を有効にしてください。雪フィルタの場合はそれらと同期をとっており、また、日本語サイトの場合はまっさきに対応しています。たいていは同時にAdGuard Japaneseでも対応するので、AdGuardご利用の方、かつ日本語フィルタを切り替えた方で上記でお悩みでしたら公式ベース + 日本語フィルタもご検討ください。

</details>

### AdGuard

#### Q17 シェアボタンやツイートボタンが消えてしまいます

<details>

<summary><strong>A17</strong></summary>

  インストール時にソーシャルネットワーク・ウィジェット・フィルタのチェックを入れていたなら至極当然です。これらを表示するため、ブロックを（そのサイトで）オフにするのはとんでもない話です。対応は簡単で、設定 > フィルタから「SNSウィジェット」の項目を無効にしてください。インストール時のナビゲーションではデフォルトでチェックが入っているので、気づかずに有効にしてしまった方が多いのかもしれません。これに限らず、よくわからずにフィルタを有効にしてしまい、不具合に遭遇してブロッカーをオフにしてしまう方が多いようです。

  2021年4月7日追記：Androidで280blocker adblock filterをご利用の場合も同様のことが起こります。こちらについては誰にでもできる簡単な対処はちょっと思いつきません。購読フィルタを切り替えることぐらいでしょうか。

</details>

#### Q18 フィルタリストによるフィンガープリントが可能と聞きました。

<details>

<summary><strong>A18</strong></summary>

  理論上は可能ですが、心配するのはまったくの杞憂です。たとえば[このテストページ](https://browserleaks.com/proxy)で体験できますが、この程度では誤判定が多くとても実用にならないでしょう。それでいて、日常的にリクエストログをみているフィルタ作者にはリストのフィンガープリンティングを試みているのが手に取るようにわかります。精度を高めようとすればなおさら隠すのは難しくなりますし、各リストの変更に追随する手間もかかります。実際にリストのフィンガープリントが疑われる例の報告はありませんし、みたこともありません。そもそも、広告ブロックユーザーのみが対象で、かつ大多数のユーザーが標準リストを使っている<sup>24</sup>時点でフィンガープリントとしては使い物にならず、やるとしたら趣味にしかなりません。ブラウザベンダーがフィンガープリント制限への動きを強めているとはいえ、既存のフィンガープリントライブラリはこんなものとは比較にならないほど高精度の判別が可能なので、それを適当にリネームして使うほうがはるかに賢明です（実際そういう例はあります。ただし多くはリネームすらしておらず、EasyPrivacyや雪フィルタの汎用ルールでブロックできます）。

  <sub>24: 言語・地理による違いなどは、こんな手段を使わなくても判別できます。</sub>

</details>

#### Q19 アンチ広告ブロック（広告ブロック解除要求）への対処法を教えてください。

<details>

<summary><strong>A19</strong></summary>

  ご自身でフィルタを書ける人は別として、最良の対処はフィルタ作者に報告することです。uBlock Origin標準設定で出る場合は[こちら](https://jbbs.shitaraba.net/bbs/read.cgi/internet/25463/1618326670/)でも受けつけます。以下では、日本のサイトで比較的よくみるアンチ広告ブロックへの簡易的な対処をまとめました。内容的には、以前に「りぃのなんでも知恵袋」さんの[記事](https://mabidiary.blogspot.com/2019/01/2019.html)にコメントさせていただいたものの更新になります。`hoge.com`でアンチ広告ブロックが出たという仮定です。参考画像は一例で、バリエーションがあります。

  1. `antiblock.org`の場合
  
  以下のようなUIです。 
  
  ![antiblock_org_var1](https://user-images.githubusercontent.com/58900598/115898288-58660f80-a498-11eb-808a-c8f5300bd0d3.png)
  
  ![antiblock_org_var2](https://user-images.githubusercontent.com/58900598/115898305-5bf99680-a498-11eb-92ca-7f79b9932c4a.png)
  
  ![antiadblock_org_var3](https://user-images.githubusercontent.com/58900598/115898594-b0047b00-a498-11eb-8b5e-922e48b95855.png)

  uBlock Originでは`hoge.com##+js(acis, document.addEventListener, google_ad_client)`、AdGuard（iOSおよびAdGuardコンテンツブロッカーを除く）では`hoge.com#%#//scriptlet('abort-current-inline-script', 'document.addEventListener', 'google_ad_client')`をMyフィルター/ユーザールールに追加してみてください。たまに競合条件により安定して機能しない場合もあります。uBlock Originでは、Firefox上なら`hoge.com##^script:has-text(google_ad_client)`に切り替えてください。AdGuardでは`hoge.com$$script[wildcard="*load*google_ad_client*"][min-length="2000"][max-length="3000"]`に切り替えてみてください（一部のプラットフォームでは機能しません）。

  2. `BlockAdBlock`の場合
  
  以下のようなUIです。
  
  ![bab](https://user-images.githubusercontent.com/58900598/115764861-0615e780-a3e1-11eb-8ff8-88a083be4056.png)
  
  uBlock Originでは`hoge.com##+js(nosiif, visibility, 1000)`、AdGuardでは`hoge.com#%#//scriptlet("prevent-bab")`を追加してください。姉妹品にFuckAdBlockがありますが、日本のサイトでは最近ほぼみないため割愛します。

  3. Google Funding Choice Anti-adblockの場合

  UIはバリエーションが多いので割愛しますが、日本のサイトであれば日本語で解除を要求するのが一つの特徴といえるかもしれません。uBlock Originでは、uBlock filtersが有効ならよほどおかしな設定（過剰購読など）にしない限りみることはありません。AdGuardでは`hoge.com#$#body { overflow: visible !important; }`と`hoge.com#$#body div.fc-ab-root { display: none !important; }`を一行ずつ追加してください。

  4. それら以外
  
  アンチ広告ブロックプラグインにはほかにも多くのファミリーがあり、ここで網羅することはできません。また、独自実装のものも増えています。以下ではそうした場合にもしかしたら機能するかもしれない簡易的な対処をまとめます。

  uBlock Origin：まず、以下を追加
  ```
  *$image,redirect-rule=1x1.gif,domain=hoge.com
  *$script,redirect-rule=noop.js,domain=hoge.com
  ||googlesyndication.com/pagead/js/adsbygoogle.js$script,redirect-rule=googlesyndication_adsbygoogle.js:10,domain=hoge.com
  @@||hoge.com^$ghide
  ```
  ダメなら`||hoge.com^$inline-script`に切り替え、ただしサイトの機能を壊す可能性が高い。

  AdGuard：まず、以下を追加
  ```
  @@||hoge.com^$generichide
  ||googlesyndication.com/pagead/js/adsbygoogle.js$script,xmlhttprequest,redirect=googlesyndication-adsbygoogle,domain=hoge.com
  ```
  ダメなら`||hoge.com^$csp=script-src 'self' 'unsafe-eval' http: https:`に切り替え、ただしサイトの機能を壊す可能性が高い。

</details>

### 当サイトのフィルタ

#### Q20 雪フィルタの中を見ると、海外サイト用のルールが結構あります。どのようなサイトが対象なのでしょうか？

<details>

<summary><strong>A20</strong></summary>

  New York Timesなどの大手英語メディアや日本人利用者が多い海外マンガ、アニメ、あるいはポルノサイトに加え、以下のようなサイトを対象にしています：
  - 他の日本用フィルタで個別対応されているもの
  - 日本語のブログや記事などで紹介されている海外サイトで、ある程度トラフィックが高そうなもの
  - 特定のテーマに興味を持つ日本人が検索しそうな単語でGoogle検索したとき、検索上位に出てくるサイト
  - 上記に該当するサイトの姉妹/系列サイトや、直接リンクされているサイトの一部
  
  例外は短縮プレミアムリンク系です。日本でメジャーなものは`sh.*`, `shorten.*`, `ouo.*`などだと思いますが、目的地につくまでに様々な短縮リンクをたらい回しにされることがあるため、インターフェースが英語のものについてはある程度網羅的に対応しています。

  英語以外ではロシアと中国/広東語のサイトがやや多いですが、これらの言語をよく利用する方には到底足りません。EasyListや各言語用フィルタを使用してください。

</details>

#### Q21 雪フィルタでCNAMEトラッカー（ファーストパーティートラッカー）はブロックできますか？

<details>

<summary><strong>A21</strong></summary>

  2020年11月17日追記：[こちら](https://blog.apnic.net/2020/08/04/characterizing-cname-cloaking-based-tracking/)の論文を踏まえ、若干記述を修正しました。[First-party trackers host list](https://hostfiles.frogeye.fr/firstparty-only-trackers-hosts.txt)に含まれるものに関しては以前の記述で問題ないのですが、同リストでカバーされていないCNAMEトラッカーもまだたくさんあるようです。
  
  はい、かなりの程度ブロックされます。大雪併用ならほとんどといってもよいです。一部メディアが騒ぎ立てたため、CNAMEトラッカーをなにか特別なもののように思っている人がいるようですが、実際はEasyPrivacyなどは以前からとくに区別せずブロックしていました。日本では豆腐さんもgenieesspvのCNAMEトラッカーを以前よりブロックされています。Eulerianが少し厄介だったのはCNAMEの利用そのものではなく、CNAMEとランダムにみえるサブドメインの組合せでした<sup>25</sup>。多くのCNAMEトラッカーは、たとえば`smetrics`といった、決まったサブドメインを使います。そしてなにも`||smetrics.`のようなルールを使わずとも、一般ルールでほとんどがブロックできます（誤爆があるため雪では一部しか採用していません）。なお、ファーストパーティートラッカーという呼称が使われることもありますが、CNAMEトラッカーには純粋なサードパーティーのものも少なくないですし、一部メディアが書いたような「ファーストパーティーだとブロックしにくい」などということもありません<sup>26</sup>。ちなみに、`ad-cloud.jp`と`genieesspv.jp`の[CNAMEトラッカー](https://ln2.sync.com/dl/fa3ee4fc0/hbx7nuxm-u93hrvur-6pqd7ksx-4a43i6dq/view/text/10872149110008)[一覧](https://ln2.sync.com/dl/37297af50/view/text/10550679950008#qm9yf8hs-vk8m52pe-5ruzkqn9-ssa6cv2b)を公開しています（ここに含まれるすべてが実際に使われているわけではありません）。他に`a8.net`, `ebis.ne.jp`, `omtrdc.net`などのCNAMEトラッカー一覧もありますが、`sync.com`の共有リンク数制限により公開を取りやめました。ただしこれらはデータが少し古く、リストに含まれていないトラッカーも確認しています。

  <sub>25: ランダムドメインの利用もなんら新しいものではなく、Popadsなどで以前より使われています。Eulerian同様、正規表現でブロックできます。</sub>

  <sub>26: CNAMEトラッカーが騒ぎになったときからAレコードやAAAAレコードの利用が予測されていましたが、実際に2020年よりGoogleが[サーバーサイドタギング](https://developers.google.com/tag-manager/serverside?hl=ja)として提供しています。uBlock Originもこれに対応するため[strict3p](https://github.com/gorhill/uBlock/commit/bde3164eb445a4e74acca303ec9fa07f82ba1b1c)オプションを追加しました。このように、ブロッカーの迂回やその他"user hostile"な機能に真っ先に対応し続けているのもuBlock Originが信用されている理由の一つでしょう。</sub>

</details>

#### Q22 アクセス解析を独立したリストにわけてもらえませんか？

<details>

<summary><strong>A22</strong></summary>

  アクセス解析は気にする人とそうでない人がわかれるため、そうしたいところですがメンテナンスコストの点で難しいです。リストをわけると、非表示フィルタをメイン単独の場合とサブリストも購読する場合とでわけて考える必要がでてきます。既にみぞれでそういうケースは多数発生していますが、みぞれの場合はまだ限定的です。アクセス解析の場合だとアクセスカウンターやレコメンデーションエンジンを使用する多くのサイトでそうする必要がでてきます。また、広告と解析は常にきっぱりわけられるわけでもなく、現在の分類は正直に申し上げますと大雑把です。リストをわけるとなれば、判断に迷うケースや現実的に言って誤分類も出てきます。そして広告スクリプトを解析に誤分類してしまうと、広告漏れにもつながります。

</details>

#### Q23 雪フィルタの提供をやめてAdGuard Japaneseの強化に集中したほうが効率がよいのでは？

<details>

<summary><strong>A23</strong></summary>

  最初からAdGuardFiltersの書き込み権限があればそうしたかもしれません。とはいえ、方針も異なりますし、自己管理のフィルタだからできることもあります。たとえばuBlock Originに完全特化して専用機能・最新機能をふんだんに使うこと、トラッカーを即時ブロックすること（一定の不具合チェックはしています）などです。AdGuard公式フィルタにルールを追加する場合はどうしても慎重になりますし、チームの方針にしたがう必要もあります。とはいえ、フィルタの概念に気づいている広告ブロックユーザー自体が少なく、また、AdGuard JapaneseがuBlock OriginやBraveの標準リストでもあることから、これを改善していくのが最良と認識しています。ちなみに、雪を提供している理由の一つに、日本語ユーザーにおいて標準のフィルタリストを外し日本用フィルタ一本に絞るというのが割と行われているようだというのがあります。EasyList, EasyPrivacyの不具合の多さから理解はできますが、長期的には好ましくないと思っています<sup>27</sup>。不具合が多い最大の理由は、日本語ユーザーがあまり報告を行わない点にあると思われるため、雪を媒介に不具合報告を標準リストに反映させるという意味もあります。

  <sub>27: 10年前は日本のウェブ広告はネット上の孤島状態でしたが、今では日本のサイトでも海外の広告・解析サービスを利用することが珍しくなくなっています。また、翻訳の発達により日本人でも海外サイトを利用する方が増えている一方、広告のパーソナライズ化やA/Bテストの浸透が進み、Youtube広告などは個人メンテナーによる対応は不可能に近くなってきています（EasyListは汎用ルールで対応することが結構あり、サイト指定ルールのコピーでは不十分です）。</sub>

</details>

#### Q24 既に正規表現でブロックされていても広告ドメインを追加するのはなぜですか？

<details>

<summary><strong>A24</strong></summary>

  ほとんど好みの問題ですが、処理の重い正規表現チェックが入るリクエストを少しでも減らすためです。トークン化可能な一般ルールでブロックされている場合は原則として追加しません。雪フィルタは数か月ごとにデッドドメインのスキャンも行っているため、無駄になる心配もありません。

</details>

### その他一般

#### Q25 Youtubeで検索が機能しない、メニューが開けない、接続が途切れるなど不具合が出る

<details>

<summary><strong>A25</strong></summary>

  2021年3月22日追記：Twitterなどで同様の報告が後を絶たないようなので、ABP Japanese filtersを[ブラックリスト指定](https://github.com/uBlockOrigin/uAssets/issues/8738)させていただきました。

  ABP Japanese filtersが原因の可能性が高いです。同フィルタは更新が停止しており、既にAdblock PlusやuBlock Originの標準フィルタリストからは削除されていますが、昔インストールしてそのまま使っている場合は有効になっている場合があります。また、AdBlockでは今でもデフォルトで有効のようです。同フィルタを無効にして別の日本用フィルタに切り替えてください。なお、名前が似ていますがAdGuard Japaneseは問題ありません。

</details>


#### Q26 なにか言い残したことは？

<details>

<summary><strong>A26</strong></summary>

  AdGuardに関する某掲示板で私を指名するのはやめてください。ちゃんと報告していただければAdGuardチームの誰かが対処するはずです。私を含めチームの何名かはただの無償ボランティア<sup>28</sup>で、チームの誰かから依頼された場合は別として、空き時間で適当に目についた問題に対処しているだけです。ところで、スクリーンショットのみで説明がなく、何をしてほしいのか不明瞭な報告がたまにあります。大抵、チームから呼ばれて私がエスパーするはめになります。日本語で構いませんので（スクリーンショット中に日本語で説明を入れるのは控えてください）、一言、説明を加えてください。できればスクリーンショットにもマーキングをしていただけるとなおよいです。また、ご希望に添えない場合もあります。とくにDNS用のフィルタはブロックと不具合のバランスをとるのが難しいため、その傾向が強いです。
  
  <sub>28: 永久ライセンスはもらえますが、公式にある５件程度でいいというのはウソです。ライセンス目当てにContributorを目指すのはやめた方がいいでしょう。ですがContributorは欲しいです、切実に。</sub>

</details>

### 謝辞

このFAQの初版の作成に当たっては、@280blockerさんから貴重なご意見をいただきました。ここに感謝申し上げます。
（元々見ていただくことを想定していたわけではなく、たまたま別件で話していたときにタイミングがあったため、ご意見をいただくことができました。間違い等の文責はすべて@Yuki2718にあります）
