# Regular Expression

## [Java - Regular Expression - \b 與 \B 在regex中的分別](https://ithelp.ithome.com.tw/articles/10229585)
\b
解釋說明:
比對「文字/數字的邊界」，包括underscore ( _ ) 。

\B
解釋說明:
比對非「文字/數字的邊界」，包括空格及特別字元。

以下用詳細例子解釋:
首先將s定義為

```
sentence= "martinis himartin goo goomartingoo";
```
例子1: 每個詞的開始位置

```
result = sentence.replace(/\bmartin/g, "KK");
```
最後改變成為 "KKis himartin goo goomartingoo"

例子2: 每個詞的尾部位置

```
result = sentence.replace(/martin\b/g, "KK");
```
最後改變成為 "martinis hiKK goo goomartingoo"

例子3: 不在每個詞的開始位置

```
result = sentence.replace(/\Bmartin/g, "KK");
```
最後改變成為 "martinis hiKK goo gooKKgoo"

例子4: 不在每個詞的尾部位置

```
result = sentence.replace(/martin\B/g, "KK");
```
最後改變成為 "KKis himartin goo gooKKgoo"

例子5: 不在每個詞的尾部或開始的位置

```
result = sentence.replace(/\Bmartin\B/g, "KK");
```
最後改變成為 "martinis himartin goo gooKKgoo"

## string_to_tag
-string_to_tag
	change string to tag, e.g. abc=><abc></abc>
