---
layout: post
title:  "Mysql查询使用not in时没有数据的问题"
date:   2016-05-26 09:33:00 +0800
description: 
---

在一次查询时发现，使用in与not in的得到的数据不是全集。

{% highlight sql %}
select * from tableA where id in (select id from tableB where xx = yy);
select * from tableA where id not in (select id from tableB where xx = yy);
{% endhighlight %}

经过查询后发现是子查询的id含有NULL导致。可以在查询条件中加上NULL的过滤。

select * from tableA where id IS NULL or id in (select id from tableB where xx = yy and xx is not null);

{% highlight sql %}

select 2 in (1, 3);   //0
select 2 in (2, 1);   //1
select 2 in (null, 1);   //null
select 2 in (null, 1, 2); //1

select 1 not in (1, null);  //0
select 1 not in (2, null);  //null
select 1 not in (2);       //1

select null in (1);         //null
select null in (null, 1);   //null
select null not in (1);     //null
select null not in (null, 1);  //null

{% endhighlight %}
