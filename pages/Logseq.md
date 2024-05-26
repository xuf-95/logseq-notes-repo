### Query Cmd
	- ```scheme
	  去年今日：{{query (between -1y -1y )}}
	  
	  ```
- Referal
	- https://logseq.pro/#/page/queries
- ![logseq下基于联系的笔记模式.png](../assets/logseq下基于联系的笔记模式_1712107068855_0.png)
-
- Query all [[tag]]
  id:: 6652dc76-3a01-4a7d-9ba6-2a46f1387ed6
  query-properties:: [:block]
	- ```apl
	  ```
- 查询所有包含 `logseq` 的页面和标签
	- #+BEGIN_QUERY
	  {:title "All page tags match regex"
	   :query [:find ?tag-name
	  	   :in $ ?match
	         :where
	         [?tag :block/name ?tag-name]
	         [(re-pattern ?match) ?regex]
	         [(re-matches ?regex ?tag-name)]
	  ]
	  :result-transform (fn [result]
	                              (sort-by identity result))
	  :view (fn [tags]
	      [:div
	       (for [tag (flatten tags)]
	         [:a.tag.mr-1 {:href (str "#/page/" tag)}
	          (str "#" tag)])])
	  :inputs [ ".*logseq.*" ]
	  }
	  #+END_QUERY
-
-
-
-
-
-
-