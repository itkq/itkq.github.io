+++
categories = []
date = "2017-04-30T22:17:37+09:00"
description = ""
tags = ["Unix"]
title = "Unix の歴史と思想"
slug = "unix-history-and-principle"

+++

これは、自分がプログラミングを始めた頃に読みたかった（読むべきだった）というつもりの文章である。

<!--more-->

# Unix の歴史
Linux 登場までの歴史を簡単にまとめた。省いているところも多い。

## Unix の誕生
ベル研究所の Ken Tompson が、1969年に開発したゲーム用プラットフォームが起源である。当時はメインフレームで動く TSS が実験されていた (Multics) が、大規模で複雑なプロジェクトだった。
ベル研究所は Multics プロジェクトから脱退したが、彼らは対話的コンピューティングを必要としていた。その後ゲーム開発を可能にするプログラム（＝カーネル）が生み出された。これが **Unix** の元となった。Unix の語源は、Multics (Multiplexed information and computer system) を意識した **UN**iplexed **I**nformation and **C**omputer **S**ystem だと言われている。

ワードプロセッサをサポートする過程で、Unix OS が誕生した。初期の Unix OS はアセンブリ言語で書かれていたが、後に移植性を高めるためにC言語、つまり高水準言語で書き直された。
この頃は主に DEC (Degital Equipment Corporation) の PDP-7 というミニコンピュータで Unix は稼働していた。

1970年代に、Unix についての論文が ACM に投稿されたことで、世界中の研究機関が Unix に興味を持った。ベル研究所の親会社である AT&T は、電話と関係ない技術だったために、Unix のソースコードを配布することになった。

## BSD Unix
**ARPANET** は、インターネットの起源となった、複数の研究機関を接続したパケット交換ネットワークである。Unix と同時期の 1969年から開始された。当時 ARPANET は PDP-10 で稼働していたが、次世代の VAX シリーズ生産とともに淘汰されつつあった。そこで VAX 上の Unix で動作する TCP/IP プロトコルスタックの実装が必要になった。初期の Unix のネットワークサポートはごく貧弱だった。

Unix を拡張したり性能を向上させる研究をする大学は多数あった。そのうちカリフォルニア大学のバークレーキャンパスは、特に Unix 開発の中心的存在になっており、そこで開発されたソフトウェア郡は **BSD (Barkley Software Distribution)** として、1977年に最初にリリースされた。その開発成果はベル研究所にフィードバックされた。
ベル研究所では、改良を重ね "UNIX System" という名前でリリースしていた。
1979年にリリースされた Version 5 は、最も成功した Unix だった。

ARPANET の陣営は、1983年に BSD 4.2 とともにリリースされた TCP/IP 実装 (バークレーAPI) を最終的に採用した。この TCP/IP のおかげで、ARPANET は衰退を免れ、Unix もさらに広まることとなった。

## Unix 産業
1970年代、当時無名の企業だった **Microsoft** も Unix 産業に参入し、Xenix という商品を販売していたが、長くは続かなかった。1981年に **IBM** が開発した CP/M OS のクローンの1つを買収する歴史的に重要な契約を結んだ。この OS は後に **MS-DOS** (MicroSoft Disk Operating System) となり、IBM のハードウェアと独立して販売する契約もした。そして MS-DOS は、デスクトップコンピューティング市場を独占していった。

当時 UNIX System III のソースライセンスは4万ドルであったが、実際には裏で Unix のソースは流通しており、ベル研究所はそれを黙認していた。
**Sun Microsystems** は、ネットワーク機能を組み込んだ夢の Unix マシンを目標としており、ハードウェアとバークレーで開発された Unix を組み合わせた SunOS によってワークステーション産業を確立した。この商用化は、Unix System III のソースライセンス料を考えると、まだ良いことのように思えた。

また、1983年には AT&T で歴史的な分割が起きた。Unix の製品化を阻んできた裁判に勝利し、直ちに UNIX System V の商用化をした。ベル研究所や子会社は本体から分離された。

これらの Unix 商用化によって、初期の Unix の活力の原点であったソースコードの自由なやり取りは失われていった。また、Unix 市場への新規参入企業は、「差別化」による経営戦略をした。これは結果的に悪い影響を与え、Unix インターフェースはばらばらになり、互換性は失われ、Unix 市場は細分化された。
この頃 MIT 人工知能研究所では、Richard Stallman というプログラマが、Unix の完全フリーなクローンである **GNU** (GNU is Not Unix) OS を書き始めていた。

## Unix 戦争
それ以降の数年間、Unix コミュニティでは、UNIX System V と BSD Unix 間の標準化という、いわゆる Unix 戦争に没頭していた。
最終的に、1985年に発足した、IEEE が支援する **POSIX** (Portable operating system interface) で真剣な標準化が進められた。POSIX は、BSD と System V Release 3 の共通部分を取り、より優れている BSD のシグナル処理とジョブ制御、System V の端末制御を組み合わせている。
これ以降の Unix は POSIX に忠実に従っている。

1987年には GNU C コンパイラの最初のバージョンが登場し、GNU ツールセットの核となるエディタ、コンパイラ、デバッガ等の基本ツールが揃った。
また、グラフィックエンジンである X Window System は、開発者たちがライセンス無しでソースコードを公開したことが功を奏し、プロプライエタリなライバルを打ち破り、地位を確立していった。

AT&T と Sun を中心とした Unix International と、POSIX 標準化によって System V と BSD Unix の争いは最終的に終結した。しかし、その間に、IBM, DEC, Hewlett-Packard などの2番手ベンダーが OSF (Open Source Foundation) を結成し、Unix International と対抗する構えを見せたことにより、Unix vs Unix という第二次 Unix 戦争が始まった。

その間に Microsoft は Windows 3.0 をリリースし、その支配を確実にしていた。

## Linux の登場
当時の商用 Unix は高額で、学生が買えるものではなかった。フィンランドの Linus Torvalds は、大学の教材OS (Minix) を拡張して遊んでいたが、物足りなさを感じて1からモノリシックカーネルを作り始めた。そうして出来上がったのが後に **Linux** となるカーネルである。
Linux の開発は、電子メールや Usenet のニュースグループを中心にインターネット上で行われた。

また、1991年に開発された World Wide Web はインターネットのキラーアプリケーションとなり、Linux はインターネット機能と X の両方を持ったことで、インターネットの大衆消費市場が成立した。潜在開発者のプールは拡大し、開発のトランザクションコストは下がった。

その頃 Unix コミュニティでは、Unix からプロプライエタリなコードから解放することを目標としており、結果的に BSD 自体への影響は破壊的なものになってしまった。そして BSD コミュニティは分裂し、Linux に大きく遅れをとり、Unix コミュニティのトップの座を譲ることになった。

# Unix の思想
歴史的に、Unix は商業的な側面が強く、商標として認められているものは "UNIX" を名乗れるが、それ以外の派生は "Unix" のように書く。そういう意味で Linux もここでは "Unix" に含める。

## テキストインターフェース
基本的に Unix のプログラムはテキストインターフェースを持つ。
その理由は、テキストが最も「クリーン」なインターフェースだからである。
Unix 思想では、複雑なソフトウェアを書くために、全体の複雑性を下げる選択をする。
単純で小さいモジュールを組み合わせるために、適切なインターフェースが必要である。
バイナリは人間には読みづらいし、グラフィカルなインターフェースは接続が難しい。
また、クリーンであるために、余計な情報は出力しないほうが良いし、綺麗に表示する必要は無く、その出力は予想に反さないものであることが望ましい。


## 人間の時間を無駄にしない
マシンの値段が下がるにつれて、プログラマの時間は高価になる。
よって、プログラマは経済性を高めるために、時間を節約すべきである。手作業のハックを避け、自動化することが望ましい。

また、唯一の正解を探すことは生産性を下げる。プロトタイピングは美徳であり、途中でプロトタイプをすべて捨てるという勇気も必要である。


## まとめ
Unix 思想を一言でまとめると：

> Keep It Simple, Stupid!

# 参考文献
- それがぼくには楽しかったから 全世界を巻き込んだリナックス革命の真実
- The Art of UNIX Programming