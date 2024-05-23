- {query {:[[title]] ["Tasks for next 7 days"]
   :query [:find (pull ?block [*])
       :in $ ?start ?next
       :where
          (or
            [?block :block/scheduled ?d]
            [?block :block/deadline ?d])
          [(> ?d ?start)]
          [(< ?d ?next)]
          (task ?block #[[May 23rd, 2024]])
   ]
   :inputs [:today :+7d]
   :result-transform :add-task-attrs
   :collapsed? false
  }}
-
-
-
-