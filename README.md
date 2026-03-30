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

## [What does (?: do in a regular expression](https://stackoverflow.com/a/14138202)
It's a non-capture group, which essentially is the same as using (...), but the content isn't retained (not available as a back reference).

If you're doing something like this: (abc)(?:123)(def) You'll get abc in $1 and def in $2, but 123 will only be matched.
https://regexr.com/8leu2

## [RegExp 應用： lookahead , lookbehind](https://darkk6.blogspot.com/2017/03/regexp-lookahead-lookbehind.html)
例如： 12345 XD Hi12345678ab666666cd987654321

要找出： 12345678 和 666666；但不可以找出 987654321 中的 98765432 或者 87654321

於是我第一個想到的東西就是 Lookahead 和 lookbehind。

先來看一下如果直接使用 \d{6,8} 會取出什麼：[RegExr: Learn, Build, & Test RegEx](https://regexr.com/8leue).  
可以看到，直接使用 \d{6,8} 是會連後方的 987654321 取出來。

最後我給的的解法是：(?<!\d)\d{6,8}(?!\d)，結果：[RegExr: Learn, Build, & Test RegEx](https://regexr.com/8leuh).  
重點就在前面的 (?<!\d) 和後面的 (?!\d) 這兩個表示法，他們分別代表的是  
negative lookbehind 和 negative lookahead

## string_to_tag
-string_to_tag
	change string to tag, e.g. abc=><abc></abc>
