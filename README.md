# おもてなしwebapp
このリポジトリはHTML共有専用です。  
Vueの環境が整い次第撤去します。撤去する際はslackでアナウンスするので、push漏れがないかご確認ください。

【撤去予定日：2018.06.19 24:00:00】


## HTMLファイルについて
`/public`の中に順次上げていってください


## cssの形式について
CSSの構成案はFLOCSS。スタイルシート言語はSCSSを使います。


### セレクタの命名規則のルール
[セレクタの命名規則についてはこちらを参照しました:BEM(MindBEMding)によるCSS設計](https://github.com/manabuyasuda/styleguide/blob/master/how-to-bem.md)

#### レイアウトの構造(layout.scssに記述するセレクタ)について
layout.scssに記載するセレクタの先頭は`l-`から始まるものではなくIDをつかう。  
なので、このファイルにあるセレクタは全て＃始まりとし、`#element{ ... }`という構造になる。
-----

#### リストタグの命名規則について
要素については基本的に`sass/object/project/`に格納されるセレクタの場合`p-要素名`、`sass/object/component/`に格納されるcomponentの場合`c-要素名`、`sass/object/utility/`に格納されるutilityの場合`u-要素名`といったように必ず先頭にレイヤー名の頭文字を指定してください。

ただし、ul-liタグに限り、通常の命名規則とは異なる命名法則にします。

FLOCSSのセレクタの命名規則はBEM(Block/Element/Modifier)を採用しています。  
しかし、従来の形式でマークアップをすると冗長になってしまうので、上コードのように単語が重複している場合は親のitemを複数形にし、子に当たるelementは単数形にしています。

例えば以下のような構造になっているとして、

``` question.html line:23~
<nav class="p-global-nav">
	<ul class="p-gloval-nav__items">
		<li class="p-gloval-nav__item">
			<a href="#" class="p-gloval-nav__item__link">
				<img src="#" alt="質問ページ">
			</a>
		</li>
		<li class="p-gloval-nav__item">
			<a href="#" class="p-gloval-nav__item__link">
				<img src="#" alt="メール">
			</a>
		</li>

		<< 以下略 >>
	</ul>
</nav>
```

上コードの場合、`.p-gloval-nav__items`の子要素は`.p-gloval-nav__item`のようにsを抜いて名前をつけています。

----

#### インライン要素について
`<img ~ >`や`<span> ~ </span>`などにクラスは基本当てないでください。  
ただしblock要素が含まれる可能性のあるアンカータグは例外となります。





### CSSの書き方について
- エレメントごとに&でネストする。
- 繰り返し使う値は`foundation/variable.scss`に記述する