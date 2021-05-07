# [VsCode中使用Emmet神器快速编写HTML代码](https://www.cnblogs.com/summit7ca/p/6944215.html)

## 一、Emmet简述[#](https://www.cnblogs.com/summit7ca/p/6944215.html#idx_0)

Emmet (前身为 Zen Coding) 是一个能大幅度提高前端开发效率的一个工具. 在前端开发的过程中，一大部分的工作是写 HTML、CSS 代码。特别是手动编写 HTML 代码的时候，效率会特别低下，因为需要敲打很多尖括号，而且很多标签都需要闭合标签等。于是，就有了 Emmet，它可以极大的提高代码编写的效率，它提供了一种非常简练的语法规则，然后立刻生成对应的 HTML 结构或者 CSS 代码，同时还有多种实用的功能帮助进行前端开发。
VsCode内置了Emmet语法,在后缀为.html/.css中输入缩写后按Tab键即会自动生成相应代码

> 请注意在VsCode新版本中按Tab不再默认启用Emmet展开缩写!需要在首选项配置中将emmet.triggerExpansionOnTab设置为true值!

语法基本规则如下:

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_0" title="复制代码">Copy</div><code class="hljs coffeescript" id="copy_target_0">E 代表HTML标签。
E<span class="hljs-comment">#id 代表id属性。</span>
E.<span class="hljs-keyword">class</span> 代表<span class="hljs-class"><span class="hljs-keyword">class</span>属性。</span>
E[attr=foo] 代表某一个特定属性。
E{foo} 代表标签包含的内容是foo。
E>N 代表N是E的子元素。
E+N 代表N是E的同级元素。
E^N 代表N是E的上级元素。
</code></pre>

> 本文仅介绍了在Html使用Emmet,
> 如果想Css缩写的语法请参考这里[https://docs.emmet.io/css-abbreviations/](https://docs.emmet.io/css-abbreviations/)

---

## 二、基础用法[#](https://www.cnblogs.com/summit7ca/p/6944215.html#idx_1)

* **元素(Elements)**
  您可以使用元素的名称，如div或p来生成HTML标签。Emmet没有一组可用的标签名称，可以写任何单词并将其转换为标签。也就是只要知道元素的缩写,Emmet会自动转换成对应标签.
  形如:

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_1" title="复制代码">Copy</div><code class="hljs xml" id="copy_target_1">div => <span class="hljs-tag"><<span class="hljs-name">div</span>></span> <span class="hljs-tag"></<span class="hljs-name">div</span>></span>
foo => <span class="hljs-tag"><<span class="hljs-name">foo</span>></span> <span class="hljs-tag"></<span class="hljs-name">foo</span>></span>
html:5 => 将生成html5标准的包含body为空基本dom
html:xt => 生成XHTML过渡文档类型,DOCTYPE为XHTML
html:4s => 生成HTML4严格文档类型,DOCTYPE为HTML 4.01
a:mail          => <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"mailto:"</span>></span><span class="hljs-tag"></<span class="hljs-name">a</span>></span>
a:link          => <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"http://"</span>></span><span class="hljs-tag"></<span class="hljs-name">a</span>></span>
base            => <span class="hljs-tag"><<span class="hljs-name">base</span> <span class="hljs-attr">href</span>=<span class="hljs-string">""</span>></span>
br              => <span class="hljs-tag"><<span class="hljs-name">br</span>></span>
link            => <span class="hljs-tag"><<span class="hljs-name">link</span> <span class="hljs-attr">rel</span>=<span class="hljs-string">"stylesheet"</span> <span class="hljs-attr">href</span>=<span class="hljs-string">""</span>></span>
script:src      => <span class="hljs-tag"><<span class="hljs-name">script</span> <span class="hljs-attr">src</span>=<span class="hljs-string">""</span>></span><span class="hljs-tag"></<span class="hljs-name">script</span>></span>
form:get        => <span class="hljs-tag"><<span class="hljs-name">form</span> <span class="hljs-attr">action</span>=<span class="hljs-string">""</span> <span class="hljs-attr">method</span>=<span class="hljs-string">"get"</span>></span><span class="hljs-tag"></<span class="hljs-name">form</span>></span>
label           => <span class="hljs-tag"><<span class="hljs-name">label</span> <span class="hljs-attr">for</span>=<span class="hljs-string">""</span>></span><span class="hljs-tag"></<span class="hljs-name">label</span>></span>
input           => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"text"</span>></span>
inp             => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"text"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span>
input:hidden    => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"hidden"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span>></span> input:h亦可
input:email     => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"email"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span>
input:password  => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"password"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span>
input:checkbox  => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"checkbox"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span>
input:radio     => <span class="hljs-tag"><<span class="hljs-name">input</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"radio"</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span>
select          => <span class="hljs-tag"><<span class="hljs-name">select</span> <span class="hljs-attr">name</span>=<span class="hljs-string">""</span> <span class="hljs-attr">id</span>=<span class="hljs-string">""</span>></span><span class="hljs-tag"></<span class="hljs-name">select</span>></span>
option          => <span class="hljs-tag"><<span class="hljs-name">option</span> <span class="hljs-attr">value</span>=<span class="hljs-string">""</span>></span><span class="hljs-tag"></<span class="hljs-name">option</span>></span>
bq              => <span class="hljs-tag"><<span class="hljs-name">blockquote</span>></span><span class="hljs-tag"></<span class="hljs-name">blockquote</span>></span>
btn             => <span class="hljs-tag"><<span class="hljs-name">button</span>></span><span class="hljs-tag"></<span class="hljs-name">button</span>></span>
btn:s           => <span class="hljs-tag"><<span class="hljs-name">button</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"submit"</span>></span><span class="hljs-tag"></<span class="hljs-name">button</span>></span>
btn:r           => <span class="hljs-tag"><<span class="hljs-name">button</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"reset"</span>></span><span class="hljs-tag"></<span class="hljs-name">button</span>></span>
</code></pre>

* **文本操作符(Text)**
  如果想在生成元素的同时添加文本内容可以使用{}

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_2" title="复制代码">Copy</div><code class="hljs xml" id="copy_target_2">div{这是一段文本}
<span class="hljs-tag"><<span class="hljs-name">div</span>></span>这是一段文本<span class="hljs-tag"></<span class="hljs-name">div</span>></span>
a{点我点我}
<span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">""</span>></span>点我点我<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
</code></pre>

* **属性操作符(Attribute operators)**
  属性运算符用于修改输出元素的属性.

  * Id和Class (elem#id and elem.class )

  <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_3" title="复制代码">Copy</div><code class="hljs x86asm" id="copy_target_3"><span class="hljs-keyword">div</span><span class="hljs-number">.</span><span class="hljs-keyword">test</span>  => <<span class="hljs-keyword">div</span> class=<span class="hljs-string">"test"</span>></<span class="hljs-keyword">div</span>>
  <span class="hljs-keyword">div</span>#pageId => <<span class="hljs-keyword">div</span> id=<span class="hljs-string">"pageId"</span>></<span class="hljs-keyword">div</span>>
  </code></pre>

  隐式标签则会自动联想生成对应元素,根据配置规则不同生成的结果也是不同的.

  <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_4" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_4">.class
  =>
  <span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span> <span class="hljs-attr">class</span>></span><span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
  em>.class
  =>
  <span class="xml"><span class="hljs-tag"><<span class="hljs-name">em</span>></span><span class="hljs-tag"><<span class="hljs-name">span</span> <span class="hljs-attr">class</span>></span><span class="hljs-tag"></<span class="hljs-name">span</span>></span><span class="hljs-tag"></<span class="hljs-name">em</span>></span></span>
  table>.row>.col
  =>
  <span class="xml"><span class="hljs-tag"><<span class="hljs-name">table</span>></span>
      <span class="hljs-tag"><<span class="hljs-name">tr</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"row"</span>></span>
          <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"col"</span>></span><span class="hljs-tag"></<span class="hljs-name">td</span>></span>
      <span class="hljs-tag"></<span class="hljs-name">tr</span>></span>
  <span class="hljs-tag"></<span class="hljs-name">table</span>></span></span>
  </code></pre>

  绑定多个类名用.符号连续起来即可

  <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_5" title="复制代码">Copy</div><code class="hljs x86asm" id="copy_target_5"><span class="hljs-keyword">div</span><span class="hljs-number">.</span>test1<span class="hljs-number">.</span>test2<span class="hljs-number">.</span>test3
  =>
  <<span class="hljs-keyword">div</span> class=<span class="hljs-string">"test1 test2 test3"</span>></<span class="hljs-keyword">div</span>>
  </code></pre>

  * 自定义属性使用 [attr1='' attr2='']

  <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_6" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_6">a[href=<span class="hljs-string">'#'</span> data-title=<span class="hljs-string">'customer'</span> target=<span class="hljs-string">'_blank'</span>]
  =>
  <span class="xml"><span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"#"</span> <span class="hljs-attr">data-title</span>=<span class="hljs-string">"customer"</span> <span class="hljs-attr">target</span>=<span class="hljs-string">"_blank"</span>></span><span class="hljs-tag"></<span class="hljs-name">a</span>></span></span>
  </code></pre>
* **嵌套操作符(Nesting operators)**
  嵌套操作符用于将缩写元素放置在生成的树中,是否应放置在上下文元素的内部或附近.

  * 子级:>
    通过>标识元素可以生成嵌套子级元素,可以配合元素属性进行连写
    <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_7" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_7">div#pageId>ul><span class="hljs-function"><span class="hljs-params">li</span>
    =></span>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span> <span class="hljs-attr">id</span>=<span class="hljs-string">"pageId"</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
    </code></pre>
  * 同级:+
    +字符表示生成兄弟级元素.
    <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_8" title="复制代码">Copy</div><code class="hljs x86asm" id="copy_target_8"><span class="hljs-keyword">div</span>#pageId+<span class="hljs-keyword">div</span><span class="hljs-number">.</span>child
    =>
    <<span class="hljs-keyword">div</span> id=<span class="hljs-string">"pageId"</span>></<span class="hljs-keyword">div</span>>
    <<span class="hljs-keyword">div</span> class=<span class="hljs-string">"child"</span>></<span class="hljs-keyword">div</span>>
    </code></pre>
  * 父级:^
    ^用于生成父级元素的同级元素,从这个^ 字符所在位置开始,查找左侧最近的元素的父级元素并生成其兄弟级元素.
    <pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_9" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_9">div>p.parent>span.child^ul.brother><span class="hljs-function"><span class="hljs-params">li</span>
    =></span>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">p</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"parent"</span>></span><span class="hljs-tag"><<span class="hljs-name">span</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"child"</span>></span><span class="hljs-tag"></<span class="hljs-name">span</span>></span><span class="hljs-tag"></<span class="hljs-name">p</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">ul</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"brother"</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
    </code></pre>
* **分组操作符(Grouping)**
  分组使用()来实现缩写的分离.比如这个例子,如果不加括号那么a将作为span的子级元素生成.加上括号a将于()内的元素同级.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_10" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_10">div>(ul>li+span)><span class="hljs-function"><span class="hljs-params">a</span>
=></span>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">span</span>></span><span class="hljs-tag"></<span class="hljs-name">span</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">""</span>></span><span class="hljs-tag"></<span class="hljs-name">a</span>></span>
<span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
</code></pre>

* **乘法(Multiplication)**
  使用*N即可自动生成重复项.N是一个正整数.在使用时请注意* N所在位置,位置不同生成的结果不同.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_11" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_11">ul>li*<span class="hljs-number">3</span>
=>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
<span class="hljs-tag"></<span class="hljs-name">ul</span>></span></span>
</code></pre>

* **自动计数(numbering)**
  这个功能挺方便的对于生成重复项时增加一个序号,只需要加上$符号即可.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_12" title="复制代码">Copy</div><code class="hljs xml" id="copy_target_12">ul>li.item${item number:$}*3
<span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item1"</span>></span>item number:1<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item2"</span>></span>item number:2<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item3"</span>></span>item number:3<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
<span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
</code></pre>

如果生成两位数则使用两个连续的$$,更多位数以此类推...
使用@修饰符，可以更改编号方向（升序或降序）和基数（例如起始值）.注意这个操作符在$之后添加
@-表示降序,@+表示升序,默认使用升序.
@N可以改变起始值.需要注意的是如果配合升降序使用的话N是放到+-符后.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_13" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_13">ul>li.item$@-*<span class="hljs-number">3</span>
=>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item3"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item2"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item1"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
<span class="hljs-tag"></<span class="hljs-name">ul</span>></span></span>
---------------------------
ul>li.item$@-<span class="hljs-number">10</span>*<span class="hljs-number">3</span>
=>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item12"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item11"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">li</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item10"</span>></span><span class="hljs-tag"></<span class="hljs-name">li</span>></span>
<span class="hljs-tag"></<span class="hljs-name">ul</span>></span></span>
</code></pre>

上述的操作是可以搭配使用进而得出酷炫的效果,使用时请注意空格的问题,缩写代码不要有空格否则是不会进行转换的.
另外如果你的编辑器中已经有了一些html智能提示代码段,比如我的VsCode还装了HTML Snippets插件,这个与Emmet语法有部分冲突,使用Tab键时会优先使用插件的代码提示,建议禁用.
组合起来看看效果:

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_14" title="复制代码">Copy</div><code class="hljs apache" id="copy_target_14"><span class="hljs-attribute">table</span>.table-row[role='table']>(thead>tr>td{item $@<span class="hljs-number">120</span>}*<span class="hljs-number">5</span>)+(tbody>tr>(td.item$$@-)lorem<span class="hljs-number">10</span>*<span class="hljs-number">5</span>)
</code></pre>

这段目的在于生成一个类名为table-row,且自定义了属性role的table标签,内部包含了thead与tbody,分别生成5个td.
thead中td的内容是item加上自增序号,自增序号基数从120开始.
tbody中td拥有一个名为item加降序自增符号类名,且每个td内容随机填充10个单词.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_15" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_15"><table <span class="hljs-class"><span class="hljs-keyword">class</span></span>=<span class="hljs-string">"table-row"</span> role=<span class="hljs-string">"table"</span>>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">thead</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">tr</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>item 120<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>item 121<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>item 122<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>item 123<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>item 124<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
        <span class="hljs-tag"></<span class="hljs-name">tr</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">thead</span>></span></span>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">tbody</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">tr</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item05"</span>></span>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Odit, assumenda.<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item04"</span>></span>Magnam possimus molestias ipsum animi rem placeat, ut obcaecati laudantium.<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item03"</span>></span>Consequuntur, labore ad optio cupiditate iusto dolores fugit quidem officiis.<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item02"</span>></span>Veniam, explicabo consequuntur blanditiis at dicta fuga ratione eos beatae.<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">td</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">td</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"item01"</span>></span>Fuga voluptatum illo quis ducimus ad eveniet non. Saepe, eveniet.<span class="hljs-tag"></<span class="hljs-name">td</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">td</span>></span>
        <span class="hljs-tag"></<span class="hljs-name">tr</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">tbody</span>></span></span>
</table>
</code></pre>

再来个配合嵌套元素和计数的大栗子.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_16" title="复制代码">Copy</div><code class="hljs smalltalk" id="copy_target_16">div.nav>(nav<span class="hljs-symbol">#navbar</span>>(ul>li>(a[href=<span class="hljs-comment">"/xxx/product/$"</span> data-index=<span class="hljs-string">$]</span>>lorem4)*<span class="hljs-number">5</span>))+div.btn[type=<span class="hljs-string">'button'</span>]>span{--}^^div<span class="hljs-symbol">#main</span>

</code></pre>

这个有点复杂,看下效果:

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_17" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_17"><div <span class="hljs-class"><span class="hljs-keyword">class</span></span>=<span class="hljs-string">"nav"</span>>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">nav</span> <span class="hljs-attr">id</span>=<span class="hljs-string">"navbar"</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
            <span class="hljs-tag"><<span class="hljs-name">li</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"/xxx/product/1"</span> <span class="hljs-attr">data-index</span>=<span class="hljs-string">"1"</span>></span>Lorem ipsum dolor sit.<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"/xxx/product/2"</span> <span class="hljs-attr">data-index</span>=<span class="hljs-string">"2"</span>></span>Dolor vel, quia quas.<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"/xxx/product/3"</span> <span class="hljs-attr">data-index</span>=<span class="hljs-string">"3"</span>></span>Qui hic, corrupti eum!<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"/xxx/product/4"</span> <span class="hljs-attr">data-index</span>=<span class="hljs-string">"4"</span>></span>Necessitatibus perspiciatis, corrupti. Praesentium!<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
                <span class="hljs-tag"><<span class="hljs-name">a</span> <span class="hljs-attr">href</span>=<span class="hljs-string">"/xxx/product/5"</span> <span class="hljs-attr">data-index</span>=<span class="hljs-string">"5"</span>></span>Nostrum quos, voluptate. Velit!<span class="hljs-tag"></<span class="hljs-name">a</span>></span>
            <span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">nav</span>></span></span>
    <span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span> <span class="hljs-attr">class</span>=<span class="hljs-string">"btn"</span> <span class="hljs-attr">type</span>=<span class="hljs-string">"button"</span>></span><span class="hljs-tag"><<span class="hljs-name">span</span>></span>--<span class="hljs-tag"></<span class="hljs-name">span</span>></span><span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
</div>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">div</span> <span class="hljs-attr">id</span>=<span class="hljs-string">"main"</span>></span><span class="hljs-tag"></<span class="hljs-name">div</span>></span></span>
</code></pre>

## 三、进阶高级用法[#](https://www.cnblogs.com/summit7ca/p/6944215.html#idx_2)

* **模拟文本/随机文本**
  在开发时经常要填充一些文本内容占位,Emmet内置了Lorem Ipsum功能来实现.loremN或者lipsumN,N表示生成的单词数,正整数.可以不填.

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_18" title="复制代码">Copy</div><code class="hljs javascript" id="copy_target_18">lorem
=> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Suscipit quia commodi vero sint omnis fugiat excepturi reiciendis necessitatibus totam asperiores, delectus saepe nulla consequuntur nostrum! Saepe suscipit recusandae repellendus assumenda.

p><span class="hljs-function"><span class="hljs-params">lorem4</span>
=></span>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">p</span>></span>Lorem ipsum dolor sit.<span class="hljs-tag"></<span class="hljs-name">p</span>></span></span>

(p>lorem4)*<span class="hljs-number">3</span>
=>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">p</span>></span>Lorem ipsum dolor sit.<span class="hljs-tag"></<span class="hljs-name">p</span>></span></span>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">p</span>></span>Labore aperiam, consequuntur architecto.<span class="hljs-tag"></<span class="hljs-name">p</span>></span></span>
<span class="xml"><span class="hljs-tag"><<span class="hljs-name">p</span>></span>Quidem nisi, cum odio!<span class="hljs-tag"></<span class="hljs-name">p</span>></span></span>
</code></pre>

* **包装文本**
  听起来可能有点绕,通俗点解释就是把一段指定的文本包装成我们想要的结构.注意这个功能需要编辑器的支持,举个大栗子:
  比如PM给了这样一段文本

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_19" title="复制代码">Copy</div><code class="hljs xml" id="copy_target_19">首页
产品介绍
相关案例
关于我们
联系我们
而我们预期的效果是这样
<span class="hljs-tag"><<span class="hljs-name">nav</span>></span>
    <span class="hljs-tag"><<span class="hljs-name">ul</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span>首页<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span>产品介绍<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span>相关案例<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span>关于我们<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
        <span class="hljs-tag"><<span class="hljs-name">li</span>></span>联系我们<span class="hljs-tag"></<span class="hljs-name">li</span>></span>
    <span class="hljs-tag"></<span class="hljs-name">ul</span>></span>
<span class="hljs-tag"></<span class="hljs-name">nav</span>></span>
</code></pre>

1. 选中文本,按下`ctrl+shift+p`打开命令窗口输入ewrap
2. 选择`Emmet:使用缩写进行包装(Wrap with Abbreviation)`选项
   ![](https://images2015.cnblogs.com/blog/648483/201706/648483-20170605122055715-1250857112.png)
3. 输入缩写字符`nav>ul>li*`按下回车键即可看到效果.
   当然也可以在菜单=>编辑=>Emmet(M)..然后输入.

> 这里需要的注意的地方是输入的缩写代码中*所在位置不同得到的效果也是不同的.

另外如果给的文本带有序号的情况,我们也是可以通过缩写来处理,而不是手动删除,主要用的是`|t`来处理.
比如:

<pre><div class="esa-clipboard-button" data-clipboard-target="#copy_target_20" title="复制代码">Copy</div><code class="hljs yaml" id="copy_target_20">    <span class="hljs-number">1</span><span class="hljs-string">.首页</span>
    <span class="hljs-number">2</span><span class="hljs-string">.产品介绍</span>
    <span class="hljs-number">3</span><span class="hljs-string">.相关案例</span>
    <span class="hljs-number">4</span><span class="hljs-string">.关于我们</span>
    <span class="hljs-number">5</span><span class="hljs-string">.联系我们</span>
    <span class="hljs-string">输入包装字符命令</span>
    <span class="hljs-string">nav>ul>li*|t</span>
    <span class="hljs-string">即可看到生成的html中自动去掉了序号</span>
</code></pre>

针对上边说的几种情况来演示一下.
![](https://images2015.cnblogs.com/blog/648483/201706/648483-20170605122015012-1752202759.gif)
利用好Emmet来快速编写html代码,能提升工作效率不用在一个个敲闭合标签,简直是我等偷懒党神器.赶快去耍耍吧.
