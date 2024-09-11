---
title: Query Preparation
tags: [delphi]
keywords: search
summary: "Query preparation in Delphi"
sidebar: mydoc_sidebar
permalink: mydoc_query_preparation.html
folder: mydoc
---

# Query Preparation

Query preparation is an optional step that precedes query execution. Query preparation sends the `Customer Query` operator and its parameters, if any, to the BDE (Borland Database Engine) for parsing, resource allocation, and optimization.

The BDE notifies the database server about the query preparation. The server can also allocate resources for the query.

These operations improve the query performance, making your app faster.

The program can prepare a query by calling the `Prepare` method.

Even if Delphi prepares the query for you, it's better to prepare it explicitly. In this case, your intentions are clear.

For example:

```delphi
CustomerQuery.Close;
if not (CustomerQuery.Prepared) then CustomerQuery.Prepare;
CustomerQuery.Open;
```

`Prepared` is a boolean value that's `true` if the query is already prepared. If the query isn't prepared, the example calls the `Prepare` method before calling `Open`.
