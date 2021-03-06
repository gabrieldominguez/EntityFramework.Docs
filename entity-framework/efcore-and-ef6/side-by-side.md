---
title: EF6 and EF Core - Using them in the Same Application 
author: rowanmiller
ms.author: divega
ms.date: 10/27/2016

ms.assetid: a06e3c35-110c-4294-a1e2-32d2c31c90a7
uid: efcore-and-ef6/side-by-side
---
# Using EF Core and EF6 in the Same Application

It is possible to use EF Core and EF6 in the same .NET Framework application or library by installing both NuGet packages. 

Some types have the same names in EF Core and EF6 and differ only by namespace, which may complicate using both EF Core and EF6 in the same code file. The ambiguity can be easily removed using namespace alias directives, e.g.:

``` csharp
using Microsoft.EntityFrameworkCore;
using EF6 = System.Data.Entity; // e.g. EF6.DbContext
```

If you are porting an existing application that has multiple EF models, you can choose to selectively port some of them to EF Core, and continue using EF6 for the others.
