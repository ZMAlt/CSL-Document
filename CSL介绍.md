[TOC]

# CSL介绍

## 前言

`CSL`是一种基于`XML`的开放的语言，用来描述引用和参考文献的格式。对CSL更加技术和详细的描述见`CSL 1.0.1 规范`。

## CSL 是什么

如果你写过论文的话，你可能在其中引用了别人的论文。参考文献在学术交流中很重要，因为它可以提供引用的来源，并且可以把已经发表的研究联系到一起。但是，手动设置引用格式和参考文献目录非常耗时，而且不同的期刊有自己的引用格式。

参考文献管理软件可以解决上面的问题。像`Zotero、Mendeley、Papers`等软件不仅能帮助你管理参考文献，而且可以自动的生成引用的参考文献目录。为了设置特定的引用格式，这些软件需要能识别的对引用格式的描述，这种描述就是`Citation Style Language(CSL)`。

## 引用格式

引用格式有很多很多种，我们最常用的就是国标（信息与文献 参考文献著录规则），最新的国标代号是`(GB/T 7714-2015)`。大多数的引用格式都属于级个基本类别，如下。

### In-text Styles

引用格式可以分为两个主要的类型。第一种就是`in-text styles`，正文种的引用直接指向参考文献目录中的一个或者多个条目。`in-text styles`还可以细分为`author-date,author,numeric和label`格式。

在`CSL`中，每个单独的`pointer`称为一个引用。例如，引文`“(Doe et al. 2002, Smith 1997)”`包含两个引用：一个是`Doe et al.`在2002年发表的文献，另外一个是`Smith`1997年发表的文献。

#### “author-date” 和 “author” 格式

###### 例

#### “numeric”格式

###### 例

#### 标签格式

###### 例

### Note Styles

## CSL 生态

## 理解 CSL 格式

```xml
<?xml version="1.0" encoding="utf-8"?>
<style xmlns="http://purl.org/net/xbiblio/csl" version="1.0" default-locale="en-US">
  <!-- Generated with https://github.com/citation-style-language/utilities/tree/master/generate_dependent_styles/data/asm -->
  <info>
    <title>Applied and Environmental Microbiology</title>
    <id>http://www.zotero.org/styles/applied-and-environmental-microbiology</id>
    <link href="http://www.zotero.org/styles/applied-and-environmental-microbiology" rel="self"/>
    <link href="http://www.zotero.org/styles/american-society-for-microbiology" rel="independent-parent"/>
    <link href="http://aem.asm.org/" rel="documentation"/>
    <category citation-format="numeric"/>
    <category field="biology"/>
    <issn>0099-2240</issn>
    <eissn>1098-5336</eissn>
    <updated>2014-04-30T03:45:36+00:00</updated>
    <rights license="http://creativecommons.org/licenses/by-sa/3.0/">This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 License</rights>
  </info>
</style>
```

### XML 基础 

**XML描述**：第一行通畅是 xml 描述，包括xml的版本和。

**要素和遗产** ： 要素是 XML 文件的基本块。每个 XML 文件都都一个根要素，对CSL 文件来说是 `<style/>`.如果

一个元素包括其他的元素，父元素就被分为一个开始的标签`<style>`和一个结束的标签 `</style>`. 上面的例子中，style 只含有一个子元素，就是 `<info/>`,这个元素含有很多其他的元素。

**属性和元素的内容**





```xml
<?xml version="1.0" encoding="utf-8"?>
<style xmlns="http://purl.org/net/xbiblio/csl" class="in-text" version="1.0">
  <info>
    <title>Example Style</title>
    <id>http://www.zotero.org/styles/example</id>
    <link href="http://www.zotero.org/styles/example" rel="self"/>
    <link href="http://www.zotero.org/styles/apa" rel="template"/>
    <link href="http://www.example.com/style-guide/" rel="documentation"/>
    <author>
      <name>John Doe</name>
      <email>JohnDoe@example.com</email>
    </author>
    <contributor>
      <name>Jane Doe</name>
    </contributor>
    <contributor>
      <name>Bill Johnson</name>
    </contributor>
    <category citation-format="author-date"/>
    <category field="science">
    <updated>2014-10-15T18:17:09+00:00</updated>
    <rights license="http://creativecommons.org/licenses/by-sa/3.0/">This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 License</rights>
  </info>
  <locale xml:lang="en">
    <terms>
      <term name="no date">without date</term>
    </terms>
  </locale>
  <macro name="author">
    <names variable="author">
      <name initialize-with="."/>
    </names>
  </macro>
  <macro name="issued-year">
    <choose>
      <if variable="issued">
        <date variable="issued">
          <date-part name="year"/>
        </date>
      </if>
      <else>
        <text term="no date"/>
      </else>
    </choose>
  </macro>
  <citation et-al-min="3" et-al-use-first="1">
    <sort>
      <key macro="author"/>
      <key macro="issued-year"/>
    </sort>
    <layout prefix="(" suffix=")" delimiter="; ">
      <group delimiter=", ">
        <text macro="author"/>
        <text macro="issued-year"/>
      </group>
    </layout>
  </citation>
  <bibliography>
    <sort>
      <key macro="author"/>
      <key macro="issued-year"/>
      <key variable="title"/>
    </sort>
    <layout suffix="." delimiter=", ">
      <group delimiter=". ">
        <text macro="author"/>
        <text macro="issued-year"/>
        <text variable="title"/>
        <text variable="container-title"/>
      </group>
      <group>
        <text variable="volume"/>
        <text variable="issue" prefix="(" suffix=")"/>
      </group>
      <text variable="page"/>
    </layout>
  </bibliography>
</style>
```





## 
