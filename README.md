# Magazine Index Files

## Introduction

This repository contains a set of files in `.yaml` format detailing the
contents of several magazines. The long term plan is to use those files to
build a fully searchable website with the contents of some of my magazines.


So, please consider everything at very early stages of development but feel
free to reuse any file or, even better, make suggestions or contributions in the
form of more magazine `.yaml` files.


## Magazine `.yaml` format

The smallest magazine `.yaml` file you can create must consist on:

	title: Euro Modelismo      # Title of the magazine in its original language
	issue: 150                 # Issue number 
	country: es                # Two letter ISO code of the country of production
	tags: common / scale_kits  # Tags used to describe magazine items
	price: 10 euros            # Price and currency of the issue
	date: 2005-01              # Release date of the issue in YYYY-MM-DD format
	language: es-es            # Main language of the issue
	items:
	
Below you can see more details about each of the fields:

  * `title:` Title or name of the magazine.
  * `issue:` Issue number of the magazine. This is a text field so you could add
     extra information like `100 - 20th annyversary special`.
  * `country:` Two letter ISO code of the country where the magazine is produced
     or edited.
  * `tags:` Set of tags used in the description of the magazine items. More about
     this later.
  * `price:` Price and currency of the magazine issue.
  * `date:` Release date of the issue in YYYY-MM-DD format. You can ommit any
    value from right to left. e.g. `2005-07` would be valid and `2005` too.
  * `language:` Main language of the issue in XX format.
  * `items:` A list of items (articles, news, advertisements included in the issue,
    more about this later).

    
## Magazine items in the `.yaml`

As we saw before, the magazine `.yaml` file has a `items:` field under which will
put all the different items (articles, news, ads...) contained in it. The minimum
description of an item is:

    - title: Portada
      page: -1
 
   * `title:` Title and/or description of the item.
   * `page:` Page(s) where the item can be found. The format of the field must be
     either `page` (e.g. 23) or `start_page-end_page` (e.g. 16-19). It's important to
     highlight the page numbers are based on the internal numbering of the pages
     within the magazine (typically that number appears in one of the corners of
     each page). This numbering scheme typicall leads to the cover of the magazine
     having a negative page number; **this is perfectly valid and expected**.
     
Those two fields are clearly not enough to properly index and classify the contents
of a magazine. For that reason, a "dynamic" tagging system has been created. At
the top of the magazine `.yaml` file we will indicate as many tag definition files as
desired. For example, in the example minimum magazine `.yaml` file shown at
the top, we put:

    tags: common / scale_kits
 
Which means we can use the tags defined in `common(.yaml)` and
`scale_kits(.yaml)` files. We will see them in more detail below, but by now keep
in mind that **a)** multiple tags can be assigned to magazine items, **b)** they
accept multiple values, and **c)** some of them are open (you can use any value you
want) and others only allow certain list of valid values. Below you can see the
description of some items in our sample magazine `.yaml` file.

	...
	items:
	  - title: Portada
	    page: -1
	    type: cov

	  - title: Publicidad - Chaves
	    page: 0
	    type: adv

	  - title: Índice
	    page: 1
	    type: ind

	  - title: Ha llegado Santa Claus - Las Ardenas, 17 de diciembre de 1944
	    page: 2-28
	    author: Marijn Van Gils
	    type: how_bld / how_pnt
	    genre: arm / dio / fig
	    scale: 1/35
	    brand: Tamiya / Dragon / Hornet / Royal Model / Pegaso

	  - title: Publicidad - Soldat, Academy
	    page: 29
	    type: adv

	  - title: F-15 Strike Eagle - Irak 2003
	    page: 30-44
	    author: Francisco J. López de Anca García
	    type: how_bld / how_pnt
	    brand: Revell / Aires / Verlinden Productions
	    scale: 1/48


## Tag definiton files

**WIP**


