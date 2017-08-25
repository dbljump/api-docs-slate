# <a name="search_intro"></a>Search

Resources for searching resources. Additional [URL query fields](#using-url-queries) are supported, such as `fields`, `filter`, `include`, `page[number]`, `page[size]` and `sort`.

The search string param is `q`. Here is an example query:

`/search/genres?q=action&sort=name&page[number]=1&page[size]=3&fields[genres]=name,short_name&filter[created_by_id]=1&include=games`
