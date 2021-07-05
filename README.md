```shell
(base) Maheshs-MacBook-Pro:app1 mahesh$ opa version
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

```shell

(base) Maheshs-MacBook-Pro:opa mahesh$ opa run data.json example.rego
OPA 0.30.1 (commit , built at )

Run 'help' to see a list of commands and check for updates.

> data.servers[_].id
+--------------------+
| data.servers[_].id |
+--------------------+
| "s1"               |
| "s2"               |
| "s3"               |
| "s4"               |
+--------------------+
> data.opa.example.public_servers[x]
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|                                       x                                       |                      data.opa.example.public_servers[x]                       |
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
| {"id":"s1","name":"app","ports":["p1","p2","p3"],"protocols":["https","ssh"]} | {"id":"s1","name":"app","ports":["p1","p2","p3"],"protocols":["https","ssh"]} |
| {"id":"s4","name":"dev","ports":["p1","p2"],"protocols":["http"]}             | {"id":"s4","name":"dev","ports":["p1","p2"],"protocols":["http"]}             |
+-------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
> 
```
