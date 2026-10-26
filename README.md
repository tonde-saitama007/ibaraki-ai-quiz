# 茨城愛クイズ

動作する `tonde-saitama007/saitama-ai-quiz` の index.html（元のblob: 03c6c29edea8b1f1af21d3aba841d2933f8e66a3）をベースに作成。埼玉版は変更していません。

## 仕様
- 全30問から重複なしでランダム10問、4択、各問15秒
- 正解8点＋早押しボーナス（5秒以内2点、10秒以内1点）、100点満点
- 称号：90点以上「常陸の国マスター」、70点以上「茨城愛の達人」、50点以上「茨城通」、30点以上「茨城探検家」、それ未満「茨城ルーキー」
- 結果の操作は「画像を保存する」「シェア用リンクをコピー」「もう一度挑戦」の3つ
- 外部ライブラリ・APIキー不要。画像はブラウザ内でPNG生成
- 非公式のファン作品。称号は創作です。

## GitHub Pages
Settings → Pages → Build and deployment → Source: Deploy from a branch → main / (root) → Save

公開URL: https://tonde-saitama007.github.io/ibaraki-ai-quiz/

## 問題・解説の確認資料
問題順。文章は本クイズ向けに作成しました。
- Q1–4：[茨城県のプロフィール](https://www.pref.ibaraki.jp/doboku/doiji/kouhou/documents/03_ibarakinomichi2026_profile.pdf)、[県の概要](https://www.pref.ibaraki.jp/shiru/annai/index.html)
- Q5：[県広報紙ひばり・県民の日](https://www.pref.ibaraki.jp/bugai/koho/kenmin/hibari/hibari-site/hibari202211/11tokusyu1.html)
- Q6–9：[全国知事会・茨城県のシンボル](https://www.nga.gr.jp/pref_info/symbol/ibaragi.html)
- Q10：[農林水産省・納豆](https://www.maff.go.jp/j/keikaku/syokubunka/traditional-foods/menu/natto_ibaraki.html)
- Q11：[農林水産省・干し芋](https://www.maff.go.jp/j/keikaku/syokubunka/traditional-foods/menu/hosiimo.html)
- Q12：[観光いばらき・定番グルメ](https://www.ibarakiguide.jp/gourmet/ibaraki_major_food.html)
- Q13–17：[水戸市・千波湖と徳川家](https://www.city.mito.lg.jp/site/senbako/55226.html)、[偕楽園公式](https://ibaraki-kairakuen.jp/kairakuen/)、[観光いばらきガイドブック](https://www.ibarakiguide.jp/site/wp-content/uploads/2021/07/meister-guidebook2021_kantan_1p-25p.pdf)
- Q18–20：[国営ひたち海浜公園・みはらしの丘](https://www.hitachikaihin.jp/park_spot.php?code=4&mode=detail)
- Q21–23：[観光いばらき・つくば市](https://www.ibarakiguide.jp/site/ibaraki-map/south/tsukuba.html)
- Q24–25：[観光いばらき・袋田の滝](https://www.ibarakiguide.jp/spot.php?code=5&mode=detail)
- Q26：[牛久大仏公式](https://daibutu.net/)、上記ガイドブック
- Q27：[茨城県陶芸美術館・知る編](https://www.tougei.museum.ibk.ed.jp/viewer/info.html?id=125)
- Q28：[観光いばらき・結城紬](https://www.ibarakiguide.jp/special/unesco/yukitsumugi.html)
- Q29：[JAXA・筑波宇宙センター](https://www.jaxa.jp/about/centers/tksc/)
- Q30：[鹿嶋市・鹿島神宮](https://city.kashima.ibaraki.jp/site/karuta/15547.html)

## 検証
JavaScript構文検査、Edge（Playwright、390×844）で以下を確認：
- 全30問の一意性・4択・正解インデックス、100回の抽選で各回10問かつ重複なし
- 開始→全10問正解→100点・称号・結果の3ボタン
- 15秒経過で時間切れ、誤答で加点なし、正解の9点・8点加点
- 5段階称号、再挑戦、クリップボードの茨城版URL、PNGダウンロード
- JavaScript実行時エラーなし、スマホ幅の横はみ出しなし
- 開始画面・結果画面・生成PNGを目視確認

公開設定後のGitHub Pages上での動作は別途確認してください。
