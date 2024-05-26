### Query Cmd
	- ```scheme
	  去年今日：{{query (between -1y -1y )}}
	  
	  ```
- Referal
	- https://logseq.pro/#/page/queries
- ![logseq下基于联系的笔记模式.png](../assets/logseq下基于联系的笔记模式_1712107068855_0.png)
-
- query-properties:: [:block]
  #+BEGIN_QUERY
  {:title "All page tags"
  :query [:find ?tag-name
      :where
      [?tag :block/name ?tag-name]
  ]
   :result-transform (fn [result]
                            (sort-by identity result))
  :view (fn [tags]
      [:div
       (for [tag (flatten tags)]
         [:a.tag.mr-1 {:href (str "#/page/" tag)}
          (str "#" tag)])])}
  #+END_QUERY
-
-
-