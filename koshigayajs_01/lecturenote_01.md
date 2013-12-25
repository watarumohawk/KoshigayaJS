# #KoshigayaJS #1
---
##■簡単なHTMLを書いてみる。

まず好きなディレクトリ(フォルダ)に新規のファイルを作って(作らなくても良い)、テキストエディタで「新規作成」したスクリプトを「index.html」の名前で保存。

index.htmlに以下のコードをそのまま真似して書いてみよう。

	<!DOCTYPE html>
	<html lang="ja">
	<head>
		<meta charset="utf8">
	</head>
	<body>
		<h1>はじめてのプログラミング</h1>
		<p>Hello World</p>
	</body>
	</html>
htmlはタグ呼ばれる文字列で囲う。

	<!DOCTYPE html>
これはおまじない的な感じで、書かなくちゃいけないので毎回書く。

タグには始まりと終わりがあり、終わりのタグにはスラッシュ(/)が入る。
始まりのタグは必ずあるが、終わりタグの無いものもある。

	<meta charset="utf8">
は文字化けしないために書いてます。これも毎回書きましょう。

ページに表示したいものをbodyタグの中に書いていく。
	
	<h1></h1>
のhは見出しを意味するheadingの略。
	
	<p></p>

pはparagraphの略で段落を意味する。

書き終わったら保存。保存のショートカットは ⌘+S

####書き終わったスクリプトを表示してみる。
index.htmlのファイルをダブルクリック、もしくはブラウザのURLの入力する欄にドラッグ・アンド・ドロップ。
そうするとタグは見えずに文字だけ表示される筈です。

---
##■JavaScriptを書いてみる

htmlスクリプト内にJavaScriptのコードを書く場合はheadかbodyの中に書いていく。僕の好みで今回はbody内に書く。

	<!DOCTYPE html>
	<html lang="ja">
	<head>
		<meta charset="utf8">
	</head>
	<body>
		<h1>はじめてのプログラミング</h1>
		<p>Hello World</p>
		<script type="text/javascript">
			alert("Hello World");
		</script>
	</body>
	</html>
書いて保存したら、webブラウザで再読み込み。そうすると小さなウインドウが表示された筈です。

JavaScriptのコードはhtml内にも書いていけるけど、コードは増えていくと見づらいしメンテナンスしづらいので、htmlとJavaScriptは別々に書いていく。

テキストエディタで新規ファイル作成し、ファイル名を「index.js」にしましょう。（ファイル名は好みで）

	#index.js(書くスクリプトを指していてこれは書かない。以下この説明は省略)
	
	alert("Hello World");
次にhtmlを以下のように変更

	#index.html
	
	<!DOCTYPE html>
	<html lang="ja">
	<head>
		<meta charset="utf8">
		<script type="text/javascript" src="index.js"></script>
	</head>
	<body>
		<h1>はじめてのプログラミング</h1>
		<p>Hello World</p>
	</body>
	</html>

2つ書いたら保存して、ページをリロードすると同じように"Hello World"の文字が出た筈です。

今回はJavaScriptのファイル(index.js)を読み込んで実行してます。JavaScriptのファイルを読み込む時は

	<script type="text/javascript" src="index.js"></script>
	
と書き、srcの後ろのダブルクオートの中にファイル名を書きます。(正確に言えば、ファイルへのパス)

---
##■変数
	var 変数名 = 値;

変数という言葉は数学で聞いたことあるだろうから、説明は省く。気になる人はググッて下さい。

変数が持てる値は1つだけで、値を代入していくと上書きされる。

####変数に数値を代入

以下のコードを書いてみましょう。

	#index.js
	
	var num = 1;
	console.log(num);

変数を宣言するときは「var」の後に変数名を書きます。

今は、変数numの中に1が代入されています。

一つの処理が終わったら必ず「セミコロン(;)」を付けます。

今回はalertではなくconsoleで確認します(いちいちalertを消すのが面倒なので)。

console.log( ) のカッコ内に表示したいものを入れます。今回は変数numの中を表示。

Chromeでコンソールを見るには「表示>開発/管理>JavaScriptコンソール」で見れます。ショートカットは「⌘ + option + J」です。

コンソールで確認すると「1」と表示されます。

(もし表示されなかったら、webブラウザのリロードをし忘れてるか、テキストエディタで保存し忘れかセミコロンを付け忘れかな。)

####変数に文字を代入

	#index.js
	
	var elm = "hello world";
	console.log(elm);
	

ページをリロードしてコンソールで見ると、「hello world」と表示されます。

数字を入れる時はダブルクオート( " " )は入りませんが、文字を入れる時は文字列をブルクオート( " " )でくくります。

console.log(num) のnumは変数ですが、一回varを付けて宣言してるので、ここで更にvarをつける必要はありません。


####四則演算
*足し算
	
	var num = 1 + 1;
	console.log(num); //結果は2

*引き算
	
	var num = 2 - 1;
	console.log(num); //1
	
*掛け算

掛け算では「×」ではなく「*」を使います。

	var num = 2 * 2;
	console.log(num); //4

*割り算

割り算では「÷」ではなく「/」を使います。
	
	var num = 4 / 2;
	console.log(num); //2
	
---	
##■配列
	var 配列名 = [要素1, 要素2, 要素3];

複数の変数を1つにまとめたものが配列です。

	#配列
	
	var 配列名 = [要素1, 要素2, 要素3];
以下のコードを書いてみよう。	

	#index.js
	
	var array = [10, 20, 30, 40];
	console.log(array);
	
配列は変数と同じく「var」で宣言し、[ ]の中に値を入れていきます(中身はカンマで区切る)。

コンソールでは

	[10, 20, 30, 40] 
	
と表示されます。

文字を入れる時はさっきと同じく、ダブルクオート( " " )でくくります。

####要素の参照
	配列名[インデックス]
配列の中身を全部見るのではなく、特定のものだけを見たい時には要素のインデックスを指定します。
配列の[ ]の中は、順に「0番目」、「1番目」「2番目」、…と数えます。
なので、一番頭にあるもの(今の場合10)を参照する場合は

	array[0];
	
と指定します。

実際に以下のコードを書いてみましょう。

	#index.js
	
	var array = [10, 20, 30, 40];
	console.log(array[0]);
	
1つ前のコードだと配列の中身がすべて見えてましたが、今回は10だけ表示されます。

前から2番目の20を表示したい場合は

	console.log(array[1]);
	
とインデックスを書き換えれば20が表示されます。


####要素への代入
	配列名[インデックス] = 値;

20を100に書き換えましょう。

	#index.js
	
	var array = [10, 20, 30, 40];
	array[1] = 100;
	console.log(array);

var arrayで宣言した配列の2番目の20はarray[1]で指定でき、それに100を代入しています。

そうすると、配列全部を表示してみると
	
	[10, 100, 30, 40] 

と20が100に置き換わった配列が表示されます。

####要素数の取得
	配列名.length
以下のコードを書いてみよう。

	#index.js
	
	var array = [10, 20, 30, 40];
	console.log(array.length);

配列名.length とすると配列の要素の数が取得出来ます。

---
##■連想配列
他のプログラミング言語ではハッシュと呼ばれたりする。

配列と名前が似てますが、配列はさっきインデックスで要素を指定したように順番がありますが、連想配列には順番がありません。

	var 連想配列名 = {key1:value1, key2:value2, key3:value3};
	
連想配列は、キーとバリューがセットになったものです。

以下のコードを書いてみよう。(keyとvalueは好きなものでも)
	
	#index.js

	var wataru = {"age": 23, "job": "student", "city": "Koshigaya", "language": "Japanese"};
	console.log(wataru);

####※注意
連想配列の中に文字を入れる時は必ずダブルクオートでくくる。そうしないと文字列が変数だと解釈される。

####要素の取得
	連想配列名.key

配列では要素のインデックスを指定して値を取得したが、連想配列では順番は関係ないので、valueに紐付いたkeyを使って要素を取得する。

	#index.js
	
	var wataru = {"age": 23, "job": "student", "city": "Koshigaya", "language": "Japanese"};
	console.log(wataru.age); //23
	console.log(wataru.city); //Koshigaya

連想配列wataruのkeyであるageとcityで、それぞれのvalueを取得している。

---
##■for文
	for(初期化式; 継続条件; 増減式){
		繰り返す処理
	}
for文は繰り返しの処理を行う時に使います。

####for文を使わずに計算
for文を使わずに1~10を足してみる

	#index.js
	
	var num = (1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10);
	console.log(num); //計算結果は55

(計算式にカッコを使わなくても大丈夫ですが、見た目的にカッコ使ってます。)

####for文を使って計算

	#index.js
	
	var num = 0; //numを初期化
	for(var i = 0; i <= 10; i++){
		num = num + i;
	}
	console.log(num); //結果は55

となり、for文を使わずに計算と同じ結果になる。

このコードは以下の様にも書ける。

	#index.js
	
	var num = 0; //numを初期化
	for(var i = 0; i <= 10; i++){
		num += i;
	}
	console.log(num); //結果は55

足し算の時に説明しませんでしたが

	a += b;
	
で「aとbを足したものを、aに足す」という意味で 「a = a + b」と同値です。

他の演算でも同様に書けます。

	a *= b;
	a -=b;
	a /=b;

####for文の説明
1つ目のコードを使って説明。
	
	#index.js
	
	var num = 0; //numを初期化
	for(var i = 0; i <= 10; i++){
		num = num + i;
	}
	console.log(num); //結果は55

forの丸カッコの中は「iが0~10(以下)まで、iを1ずつ増やしていく。」という意味です。

#####1周目

まず変数numに0を代入。

変数numに「0を代入したnum」と変数 i = 0 を足したものを代入。

iを1増やす。

#####2周目

変数numに、1周目のnumとi = 1を代入。

iを1増やす。

以下、iが10以下の間グルグル回る。

---
##■while文

 	while(継続条件){
 		繰り返す処理
 	}
 
for文では「初期化式」「継続条件式」「増減式」の3つを( )の中に書きましたが、while文は「継続条件式」だけです。

	#index.js
	
	var a = 1;
	while(a<=100){
		a += 2;
		console.log(a);
	}

aが100以下であれば、aに2を毎回足していきます。


---
##■if文

	if(条件式){
		条件を満たす場合に実行する処理
	} else {
		条件を満たさない場合に実行する処理
	}

サンプル

	#index.js
	//『スラスラわかるJavaScript』p111より
	
	var color = "青";
	if(color == "青"){
		console.log("進む");
	}else{
		console.log("止まる");
	}
ifの( )の中で、変数colorの中身が青かどうかを判断しています。青が入ってるので、consoleに「進む」と表示されます。

これを以下のように書き換えてみると

	var color = "赤";
	if(color == "青"){
		console.log("進む");
	}else{
		console.log("止まる");
	}
変数colorの中は青では無く赤なので、「止まる」と表示されます。

また、

	color !== "青"
と条件文を書き換えると「変数colorが青ではない」という条件になります。

---
##■宿題
###問1
以下の配列の「88」をconsoleに表示してみよう。
	
	var numbers = [ [10, 50], [48, 40, 88], [39,77] ];



###問2
1以上100以下の数字で3の倍数はfizz、5の倍数はbuzz、15の倍数はfizzbuzzと表示してみよう。

[ヒント]
今回の講義ではやらなかった演算子「%」を使う。割り算の余りを求めることが出来る。
	
	(e.g.)
	
	10 % 3 //結果は1


	

