# はじめての計算生物物理

## このノートについて

これは、名古屋大学[GSC MIRAI](http://nuqa.nagoya-u.ac.jp/miraigsc/)プロジェクト・セカンドステージ「コンピューターでタンパク質の構造・機能を探る」のガイド用に作成した文書です。

## はじめに

私達の生命活動はDNAの”設計図”に基づいて合成されたタンパク質に支えられています。２０種類のアミノ酸が紐状に結合したタンパク質はアミノ酸の配列に応じて固有の構造に折畳みます。タンパク質構造をアミノ酸配列から予測する問題は大変困難な課題として長らく知られたきました。そのため、タンパク質構造予測の理論的・技術的発展を目指し、タンパク質構造予測のコンテスト(CASP)が隔年で実施されてきました。
　一方、生物の脳を模したニューラルネットワークモデルは人工知能(AI)の発展に大きく寄与し、さらに深層学習の技術は社会生活のあらゆる面に浸透しはじめています。その一例として、AlphaFoldプログラムが挙げられます。このプログラムはCASPコンテストにおいて既存の手法を圧倒する好成績をみせています。最新版のAlphaFold2プログラムは、名大スパコンでも利用可能で、GPUを活用することで高速に動作することが確認されています。
 ただし、AlphaFold2も万能ではありません。たとえば、近年注目を集めている天然変性タンパク質（IDP)は特定の立体構造を持ちません。また、多量体タンパク質の会合体も、AlphaFold2にとってな困難な予測対象です。
 この実習では、立体構造データベースに未登録のアミノ酸配列から立体構造をAlphaFold2を用いて予測し、実験で決定された構造にどれだけ近い予測ができるかどうかを試すことを目的とします。 


## 予定
### 1日目：
#### 顔合わせ
#### プロジェクトの概要説明
#### その他

## SUPPORT

1. [名古屋大学情報基盤センター](https://icts.nagoya-u.ac.jp/ja/center/)
1. [片桐孝洋 先生] http://www.abc-lib.org/MyHTML/index-j.html
1. [大島聡史 先生] https://satoshiohshima.wordpress.com
1. [白井剛 先生] https://sird.nagahama-i-bio.ac.jp/blog/

## 参考
### Life

1. [研究室アクセス（理学館の５階です）](https://www.phys.nagoya-u.ac.jp/map/map.html)
1. [研究室周辺の生協店舗・食堂](https://www.nucoop.jp/coop/coop_332.html#s02)
1. [夏休み中の生協店舗・営業時間](https://www.nucoop.jp/shop/schedule_202207.html)
1. カフェ
1.1. [CAFE BLANC](https://www.instagram.com/cafe___blanc/)
1.1. [SEATTLE ESPPRESS 名古屋大学店](http://seattlecoffee.co.jp/?mode=f2)

### Computer

1. [Touch Typing] https://www.typingclub.com
1. [Python] https://kaityo256.github.io/python_zero/
1. [MarkDown text] https://www.markdown.jp

### Biology

1. [Translation of genetic information] https://dnalc.cshl.edu/resources/3d/15-translation-basic.html
