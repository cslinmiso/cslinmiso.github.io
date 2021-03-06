---
title: WD My book 8TB as internal drive
date: 2018-02-23 23:39:17
categories:
- PC
tags:
- PC
- WD
- 8T
- harddrive
---

  此篇說明如何將WD My book 8TB外接硬碟的硬碟在一般PC上使用
  
 <!--more-->
 
## Teardown

首先要先拆出硬碟，從[家用佳选 — WD 西部数据 My Book 8TB 外置硬盘 使用评测](https://post.smzdm.com/p/558309/) 中得知從底部先撬開並往內壓。
將卡榫推進殼內後，再從上方往外撬開，由下往上推，則可抽出硬碟架，按圖操作成功取出硬碟後，用六星起子將硬碟解下。

開心的裝上電腦測試，發現根本沒抓到，看了一下才發現硬碟沒通電，緊張的上網找了一下發現國外有人整理出WD外接盒硬碟規格以及支援的POWER等等。

[wd_easystore_8tb_compendium](https://www.reddit.com/r/DataHoarder/comments/7fx0i0/wd_easystore_8tb_compendium/)
[3.3v_pin_reset_directions_d](https://www.reddit.com/r/DataHoarder/comments/7g2v9o/33v_pin_reset_directions_d/)

整理出來有幾種作法：

- 改SATA線
- 貼膠帶

## ** 最終解決方法 **

> 將SATA接頭前三個pin用膠帶貼起來就可以惹！

什麼？就這麼簡單。`沒錯，這是最無痛而且隨時可以復原的作法！`如果要還原只需要將膠帶拆下，一點問題都不會造成。

原理如下，HGST系列硬碟的第三條PIN是`Power Disable Mode(PWDIS)`的開關，使其不島通來告訴硬碟可以開啟電源，反之如果導通則關閉電源，也就是我一開始遇到的情況。

![][HGST-Power-Disable-Pin-TB]

`那為什麼要把前兩個一起貼起來？`因為那兩個是3.3v電源，也不會用到，所以乾脆一起貼起來。

![材料們][Step1]

如果使用一般電氣絕緣膠帶(黑貼布)可能會太厚，所以我拿了`耐熱絕緣膠帶(Kapton Tape)`來貼，因為這種膠帶既薄又黏剛好可以達成我們想要的效果。

![Kapton Tape][Step2]

`記得膠帶務必將SATA頭整個貼住，最好包覆到背面沒有PIN腳的位置，以確保不會因為插拔而脫落。`

![完成][Step3]

就這樣，真的就可以用了。而且沒有後遺症啊！`但是切記不要蓋到第四條PIN....`


## Reference:

[wd_easystore_8tb_compendium](https://www.reddit.com/r/DataHoarder/comments/7fx0i0/wd_easystore_8tb_compendium/)
[3.3v_pin_reset_directions_d](https://www.reddit.com/r/DataHoarder/comments/7g2v9o/33v_pin_reset_directions_d/)

[HGST-Power-Disable-Pin-TB]: https://i.imgur.com/s2EF0Df.png
[Step1]: /img/WD_MyBook_8TB_As_Internal_Drive/Step1.jpg
[Step2]: /img/WD_MyBook_8TB_As_Internal_Drive/Step2.jpg
[Step3]: /img/WD_MyBook_8TB_As_Internal_Drive/Step3.jpg
