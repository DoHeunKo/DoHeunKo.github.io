---
layout: single
title:  "start"
date:   2022-03-11 08:41:41 +0900
categories: 
- Computer Science
- Algorithm Concepts
comments : true
---

# 컴퓨터 알고리즘(1주차)

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/



*bold*

_bold_

__bold__

---

* itme1

* item2

* item3

1. item1

2. item2


~~~
int main() {
   print("Hello world\n");
   return 0;
~~~

바나나 포스트는 '_post' 폴더 밑에 있다.  
가나다라

abcd\
efg

link: [이건 링크입니다](https://naver.com)  
image: ![](https://upload.wikimedia.org/wikipedia/commons/4/47/PNG_transparency_demonstration_1.png)

{% if page.comments%}

{%include disqus_comments.html %}

{% endif %}  