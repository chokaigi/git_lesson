# Git勉強会であった質問のQA

## 1）Q.追加したファイルは１つでしたが、push時に表示される```Counting objects: 3, done.```の3というのは何の数ですか？

```
MacBookAir:myapp tt$ git push origin master
Counting objects: 3, done.
```

### A..git/objects/以下のファイルの更新された数かと思われます。詳しいアーキテクトは分かりませんが、ハッシュ化されたバイナリファイルのようです。  
補足：..git/objects/にinfoとpack以外のハッシュフォルダと内部にハッシュファイルができていてその個数になります。  
１ファイルだけなのにという話ですが操作に対して出てきます。  
上記の場合git addで1個、git commitの際に2個で合わせて3個になっています。  

## 2）Q.mergeとcherry-pickの違いはなんですか？

### A.margeはそのブランチのすべてのコミットがmerge先のブランチに適用されてしまいますが、cherry-pickはコミット単位で適用できて便利です。
