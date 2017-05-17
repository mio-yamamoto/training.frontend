# 2017/04/26

## HTML

4 HTMLの要素（https://momdo.github.io/html5/semantics.html#semantics）を覚える。

## CSS

### セレクタ

子孫セレクタ
    .class .class

子セレクタ（親要素の一つ下の要素にのみ）
    ul > li, ol > li
    dl > dt, dl > dd
    table > tbody > tr > td

隣接セレクタ
    section + section
    
    ex）
        ul > li + li {
            margin-top: 40px;
        }


### float

ul > li {
    float: left;
}

    clear: both;

ul.after {
    content: '';
    display: block;
    clear: both;
}

ul（class="cf"） => .cf:after {.....}

ul {
    overflow: hidden;   /* あまりよくない */
}


### 要素の横並び

1. float

2. display: inline-block;
    ブラウザが改行を認識してしまい、隙間（半角スペース）ができてしまう。
    **解決法**
    1. 改行をなくす
    2. 親要素にfont-size: 0;を付与し、元の要素に元のfont-sizeを返す（あまりよくない）

3. table
ul {
    display: table;
}
ul > li {
    display: table-cell;
}

横並びにした要素の高さが同じになる

4. flex-box
横並びにしたい要素の親要素にかける
ul {
    display: flex;
}
    CSSプロパティ...対応ブラウザを確認
    IE10以上であれば使うと非常に楽。

### paddingとmarginの使い方

コーディング規約

#### paddingとmarginをかける方向
top / left にかけるのが普通
cf）隣接セレクタ


## OOCSS

## scriptを読み込む場所を考える

scriptを頭に書くと、その処理が終わるまでそれ以降のHTMLなどが読み込まれなくなってしまう
<body>タグ直下の一番下