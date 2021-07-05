```(base) Maheshs-MacBook-Pro:app1 mahesh$ opa version
Version: 0.30.1
Build Commit: 
Build Timestamp: 
Build Hostname: 
Go Version: go1.16.5
WebAssembly: unavailable
(base) Maheshs-MacBook-Pro:app1 mahesh$ opa run
OPA 0.30.1 (commit , built at )

Run 'help' to see a list of commands and check for updates.

> true
true
> ["hello","world"]
[
  "hello",
  "world"
]
> true == false
false
> items := ["pizza", "apples", "bread", "coffee"]
Rule 'items' defined in package repl. Type 'show' to see rules.
> users := {"bob": {"likes": [0, 2]}, "alice": {"likes": [1, 2, 3]}}
Rule 'users' defined in package repl. Type 'show' to see rules.
> likes[[name, item]] { index := users[name].likes[_]; item := items[index] }
Rule 'likes' defined in package repl. Type 'show' to see rules.
> likes[["alice", item]]
+----------+------------------------+
|   item   | likes[["alice", item]] |
+----------+------------------------+
| "apples" | ["alice","apples"]     |
| "bread"  | ["alice","bread"]      |
| "coffee" | ["alice","coffee"]     |
+----------+------------------------+
> 
```
