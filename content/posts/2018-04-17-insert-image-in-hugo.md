---
title: "Insert Image in Hugo"
date: 2018-04-17T20:40:12+08:00
draft: false
showDate: true
tags: ["hugo"]
---

# 把圖片插入 hugo 中

<!--more-->

其實這個問題困擾我很久了，今天終於試出辦法來了

## 目前寫法

```
![IU](/blog/img/IU.jpg)
# http://localhost:1313/blog/img/IU.jpg
```

> 不過會是回傳 304，找不到原因，反正能顯示出來就好了，未來有機會再修改

## 資料夾結構

```
blog
├──static
   ├──img
      ├──IU.jpg
```

## 有沒有斜線的差異

```
# 兩者差在最前面的斜線

![IU](/blog/img/IU.jpg)
# http://localhost:1313/blog/img/IU.jpg

![IU](blog/img/IU.jpg)
# http://localhost:1313/blog/posts/2018-04-17-insert-image-in-hugo/blog/img/IU.jpg
```

沒有斜線就會抓取現在這篇文章的 path，並放在 URL 的最前面

## static 資料夾
文件放在 static 資料夾底下可以用 `/foo/bar.jpg` 來讀取，不用再加上 static 路徑了

```
.
├──static
   ├──foo
      ├──bar.jpg
```

## shortcode寫法

這是 shortcode 的寫法

{{< figure src="/blog/img/hugo_shortcode.png" >}}

因為用打的會直接變成圖片，所以就用圖片表示了

圖片置中的問題現在找不到辦法QQ
