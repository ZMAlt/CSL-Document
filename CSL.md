[TOC]

# CSL 文档

## 介绍

### 前言

CSL是一种基于`XML`的开放的语言，用来描述引用和参考文献的格式。对CSL更加技术和详细的描述见。

### CSL 是什么

### 引用格式

#### 文本中引用

##### 作者日期和作者格式

###### 例

##### 数字格式

###### 例

##### 标签格式

###### 例

#### 注释格式

### CSL 生态

#### 独立的和不独立的格式

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





# CSL 1.0.1 Specification

## 介绍

CSL 是一种基于 XML 的格式，用来描述引用的格式，注释和参考文献，提供了

* 一种开放的格式

* 紧凑并且稳定的格式

* 对格式要求的外部支持

* 格式的发布和更新的基本支持

* 数千种免费提供 的样式

  

有关的其他文档，CSL 介绍，样式和 locale 详见 [CSL 项目主页](https://citationstyles.org/)

### 术语



## 命名习惯

在引用 CSL 元素时，

## 文件类型

## XML 声明

## 引用格式结构(Styles)

## 本地文件结构(locale Files)

## 渲染元素
