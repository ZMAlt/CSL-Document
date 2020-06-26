[TOC]



# CSL 1.0.1 Specification

## 介绍

CSL 是一种基于 XML 的格式，用来描述引用的格式，注释和参考文献，提供了

- 一种开放的(开源的)格式

- 紧凑并且稳定的格式

- 对格式要求的外部支持

- 格式的发布和更新的基本支持

- 数千种免费提供 的样式

  

有关的其他文档，CSL 介绍，样式和 locale 详见 [CSL 项目主页](https://citationstyles.org/)

### 术语

关键字 `MUST,MUST NOT,REQUIRED,SHALL,SHALL NOT,SHOULD,SHOULD NOT,RECOMMENDED,MAY 和 OPTIONAL` 将按[IETF RFC 2119](http://tools.ietf.org/html/rfc2119)中的描述解释。

## 命名习惯

在引用 CSL 元素时，将在前面使用`cs:`。

## 文件类型

这里有3种CSL文件类型：从属样式和独立样式 (都使用`.csl`作为扩展名)，以及 locale files (名字为`"locales-xx-XX.xml"`，其中 `"xx-XX"`表示语言以及其方言，e.g. `"en-US"` 表示美式英语)。

### 独立格式

独立格式包含引文，笔记以及参考文献的格式指示。虽然它们大多数自包含的，但是依赖于 locale files。

### 从属格式

从属样式是独立样式的别名，其内容仅包含样式元数据，不包括任何格式说明。通过将具有相同引用风格的期刊（e.g., “Nature Biotechnology”, “Nature Nanotechnology”）的从属样式链接到独立样式（e.g., “Nature Journals”），从属样式就不再需要重复的格式说明。

### Locale Files

每个 Locale file 包含一系列对某种语言/方言的本地化数据（词语翻译，本地化日期格式以及语法选项）

## XML 声明

每个样式或者 locale 应该以 XML 声明开头，给出具体的 XML 版本以及字符编码。大多数情况下，XML 声明是：

```xml
<?xml version="1.0" encoding="UTF-8"?>
```

## 引用格式结构(Styles)

### 根元素 `cs:style`

样式的根元素是`cs:style`。在独立格式种，根元素携带以下几种属性：

`class`

​	决定样式的引文类型是 in-text (值是 `"in-text"`) 或者 note (值是`"note"`) 。

`default-locale` (可选的)

​	为本地化设值默认的 locale。值必须是 [locale code](http://books.xmlschemata.org/relaxng/ch19-77191.html)。

`version`

​	样式的 CSL 版本。对于 CSL 1.0 兼容样式，必须是 `"1.0"`。

此外，`cs:style`可能携带任意的 [全局选项](https://docs.citationstyles.org/en/stable/specification.html#global-options) 和 [可继承名称选项](https://docs.citationstyles.org/en/stable/specification.html#inheritable-name-options)。

在这些属性种，在从属格式中，只有`version`是必须的，默认的 locale 属性可以设置为代替的 locale。其他的属性是可以忽略的。

下面是一个独立样式的 `cs:style`示例，前面是 XML 声明：

```xml
<?xml version="1.0" encoding="UTF-8"?>
<style xmlns="http://purl.org/net/xbiblio/csl" version="1.0" class="in-text" default-locale="fr-FR"/>
```

### ` cs:style`的子元素

在独立格式中，`cs:style`有以下子元素：

`cs:info`

​	`info`元素必须是`cs:style`的第一个子元素。其中包括了用来描述样式的元数据 (style name, ID, authors, etc.).

`cs:citation`

​	必要元素，用来描述 in-text 引文或者 notes 的格式。

`cs:bibliography` (可选)

​	可能会出现一次。描述参考文献的格式。

`cs:macro` (可选)

​	可能多次出现。宏通过格式化指示来重复使用，可以使样式更加的紧凑和易维护。

`cs:locale` (可选)

​	可能多次出现。用于指定或者覆盖本地化数据。



在从属格式中，`cs:style`只有一个子元素，`cs:info`。

#### Info

#### Citation

#### Biography

#### Macro

#### Locale

## Locale Files

## 渲染元素

## 样式行为

## 附录I 分类

## 附录II 术语

## 附录III 类型

## 附录IV 变量

## 附录V 页码范围格式



