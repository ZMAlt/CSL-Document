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

`author-date`引用格式会显示作者的名字和发表的日期，比如：`(Van der Klei et al. 1991; Zwart et al. 1983)`。`author`只显示做作者名字，例如：`Gidijala et al.)`。参考文献条目一般使用字母表顺序对作者进行排序。

应该注意的是，许多引用格式使用了令人疑惑的`Harvard`术语来指代`author-date`格式，但是大多数这些格式与哈佛大学并没有关系。而且页并不存在一个官方的`Harvard`格式。

**参考文献条目实例**

> Gidijala L, Bovenberg RA, Klaassen P, van der Klei IJ, Veenhuis M, et al. (2008) Production of functionally active *Penicillium chrysogenum* isopenicillin N synthase in the yeast *Hansenula polymorpha*. BMC Biotechnol 8: 29.
>
> van der Klei IJ, Harder W, Veenhuis M (1991) Methanol metabolism in a peroxisome-deficient mutant of *Hansenula polymorpha*: a physiological study. Arch Microbiol 156: 15-23.
>
> Zwart KB, Veenhuis M, Harder W (1983) Significance of yeast peroxisomes in the metabolism of choline and ethanolamine. Antonie van Leeuwenhoek 49: 369-385.

#### “numeric”格式

`numeric`格式由数字组成，比如`[1,2]和[3]`。参考文献条目一般使用作者首字母排序或者使用第一次在正文中的引用顺序排序。国标就是一种典型的`numeric`格式。

**参考文献条目实例**

>1. Gidijala L, Bovenberg RA, Klaassen P, van der Klei IJ, Veenhuis M, et al. (2008) Production of functionally active *Penicillium chrysogenum* isopenicillin N synthase in the yeast *Hansenula polymorpha*. BMC Biotechnol 8: 29.
>2. Zwart KB, Veenhuis M, Harder W (1983) Significance of yeast peroxisomes in the metabolism of choline and ethanolamine. Antonie van Leeuwenhoek 49: 369-385.
>3. van der Klei IJ, Harder W, Veenhuis M (1991) Methanol metabolism in a peroxisome-deficient mutant of *Hansenula polymorpha*: a physiological study. Arch Microbiol 156: 15-23.

#### "numeric" 复合格式

复合格式是`numeric`格式的变体。这种风格在化学领域很流行。`CSL`中暂时不支持这种格式，这里也不多作介绍。

**参考文献条目实例**

>1. Gidijala L, et al. (2008) BMC Biotechnol 8: 29.
>2. a) Zwart KB, et al. (1983) Antonie van Leeuwenhoek 49: 369-385, b) van der Klei IJ, et al. (1991) Arch Microbiol 156: 15-23.

#### 标签格式

这种引用格式由`keys`构成，例`GBKv2008]和[ZwVH1983; vaHV1991]`。`CSL`对这种格式支持有限，这里也不多作介绍。

**参考文献条目实例**

> [GBKv2008] Gidijala L, Bovenberg RA, Klaassen P, van der Klei IJ, Veenhuis M, et al. (2008) Production of functionally active *Penicillium chrysogenum* isopenicillin N synthase in the yeast *Hansenula polymorpha*. BMC Biotechnol 8: 29.
>
> [vaHV1991] van der Klei IJ, Harder W, Veenhuis M (1991) Methanol metabolism in a peroxisome-deficient mutant of *Hansenula polymorpha*: a physiological study. Arch Microbiol 156: 15-23.
>
> [ZwVH1983] Zwart KB, Veenhuis M, Harder W (1983) Significance of yeast peroxisomes in the metabolism of choline and ethanolamine. Antonie van Leeuwenhoek 49: 369-385.

### Note Styles

引用格式的第二类为`Note`格式。引用中的`marker`可以是数字或者符号，例如`[*]或者[†]`。每个`marker`指向脚注或者尾注。`CSL`不能设置使用哪些数字或者符号用于`marker`，这些应该用字处理软件(比如 `word`)设置。与上面的`in-text`格式不同，尾注或者脚注通常显示的信息更多。

**参考文献条目实例**

> [*]  Voyage to St. Kilda’ (3rd edit. 1753), p. 37.
>
> [†]  Sir J. E. Tennent, ‘Ceylon,’ vol. ii. 1859, p. 107.

## CSL 生态

要明白`CSL`是怎么运作的，首先要了解`CSL`的生态。

![](<https://docs.citationstyles.org/en/stable/_images/csl-infrastructure.png>)

### 独立格式和从属格式

`CSL`的一切都是围绕`style`的，但是并不是所有的`style`都是相似的。主要包括两种格式：独立格式`(independent styles)`和从属格式`(dependent styles)`。

独立格式有2种功能，首先，需要先定义一种引用格式。具体格式是什么样的，是 `author-date`格式还是`note`格？ 引用的顺序是按字母排序还是按日期排序？参考文献条目种是不是包含`DOI`？使用什么标点符号以及使用大写还是小写？文献发表年限在文献题目前还是后？等等，这些都是引用格式定义的。第二个功能是：`CSL`必须是能自我解释的，可以称之为格式的**元数据**。元数据种可以包括该`CSL`对应的期刊标题，以及该期刊的联接，该`CSL`的创建者等。

从属格式则仅包括格式的元数据，没有对引用格式的定义。从属格式必须指定它的参考格式(父格式)，从属格式的引用将使用它的父格式的引用格式。

当多个格式使用相同的引用格式时，从属格式非常有用。以一个出版社旗下的不同期刊为例，如果每个期刊都使用独立格式，则每个`CSL`都要完整的对引用格式的描述，即使他们的引用格式都是相同的。这样就导致`CSL`太庞大，冗余太多。这种情况下，从属格式就比较适合。例如，"Nature"，"Nature Biotechnology"和"Nature Chemistry"都使用同样的引用格式。因此，只需要创建一个"Nature" 的独立格式，将"Nature Biotechnology"和"Nature Chemistry"格式都定义为"Nature"格式的从属格式。这样，如果"Nature"的出版社想改变引用格式，只需要改变"Nature"期刊格式的`CSL`就可以，不需要改变它的从属格式对应的`CSL`。

### Locale 文件

### Item Metadata

### 引用细节

### CSL 生成器



## 理解 CSL 格式

到现在为止，我们已经知道什么是`CSL`、怎么使用它、以及它怎么运作的。接下来我们将深入到`CSL`文件内部，分析它的`XML`代码。`XML基础.md` 文件中简单介绍了`XML`，看完后可以读懂并编辑简单的`XML`文件。如果想更多的了解`XML`，可以在网上查找`XML`教程。

### 从属格式解析

下面是一个`CSL`从属格式文件：

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

如`XML基础.md`文件中的描述：一行给出了`xml`的声明。根元素为`style`，其中包含了一个子元素`info`。`info`元素中又包含了很多元素，其中很多元素都有内容和属性。`xmlns、version 和defaults-locale`都是元素`style`的属性，分别指定了??、版本和使用的语言，这里为美国英语。

大多数从属格式都是电子表格自动生成的，下面的注释也给出了指向电子表格的联接。

```xml
 <!-- Generated with https://github.com/citation-style-language/utilities/tree/master/generate_dependent_styles/data/asm -->
```

元素`info`里包含了大多数`style`的元数据，比如：

`style`的题目（也是期刊的题目）：

```xml
<title>Applied and Environmental Microbiology</title>
```

样式的ID，是文献管理软件用来区分不同`style`的标志：

```xml
<id>http://www.zotero.org/styles/applied-and-environmental-microbiology</id>
```

`style`自己的链接。该链接指向了网上的副本。

```xml
<link href="http://www.zotero.org/styles/applied-and-environmental-microbiology" rel="self"/>
```

从属格式需要指定它的父格式，父格式为独立格式。这里的父格式为 `American Society for Microbiology`

```xml
<link href="http://www.zotero.org/styles/american-society-for-microbiology" rel="independent-parent"/>
```

为了更好的维护格式，因此需要指定格式的文档链接。这里文档的链接转到了期刊的主页。

```xml
<link href="http://aem.asm.org/" rel="documentation"/>
```

为了便于分类，还可以在`category`元素中设置它的属性。这里分别设置了引用格式为`numeric`，领域为`biology`。

```xml
<category citation-format="numeric"/>
<category field="biology"/>
```

当期刊创建格式的时候，可以在`issn`元素和`eissn`元素中保存其打印标准国际连续出版物号`(ISSN)`和其电子版本`(ESSIN)`。

```xml
<issn>0099-2240</issn>
<eissn>1098-5336</eissn>
```

`updated`元素保存了最后一次更新的时间戳：

```xml
<updated>2014-04-30T03:45:36+00:00</updated>
```

`rights`元素中保存了该CSL格式的证书：

```xml
<rights license="http://creativecommons.org/licenses/by-sa/3.0/">This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 License</rights>
```

### 独立格式解析

下面是一个独立格式的实例，实例中定义了引用格式，所以要比从属格式要大一些。这里的示例只是一个简化的例子，实际的格式比这个还要大很多。但这个简化的例子仍然是完整有效的。

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

#### 结构

#### 根元素/style元素

#### info元素

#### citation元素和macro元素

#### bibliography元素

#### locale 元素

## 更进一步

这里只给出了一个基本的介绍。



## 
