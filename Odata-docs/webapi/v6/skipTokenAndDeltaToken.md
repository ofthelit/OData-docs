---
title: "$skiptoken & $deltatoken"
description: ""

author: madansr7
ms.author: madansr7
ms.date: 02/19/2019
ms.topic: article
ms.service: multiple
---
# Skiptoken and Deltatoken
**Applies To**: [!INCLUDE[appliesto-webapi](../includes/appliesto-webapi-v6.md)]

In ODataLib 6.12.0, we introduced support to parse $skiptoken & $deltatoken in query options.

## $skiptoken

Let's have an example:

``` csharp
~/Customers?$skiptoken=abc
```

We can do as follows to parse:

``` csharp
var uriParser = new ODataUriParser(...);
string token = parser.ParseSkipToken();
Assert.Equal("abc", token);
```

## $deltatoken

Let's have an example:

``` csharp
~/Customers?$deltaToken=def
```

We can do as follows to parse:

``` csharp
var uriParser = new ODataUriParser(...);
string token = parser.ParseDeltaToken();
Assert.Equal("def", token);
```