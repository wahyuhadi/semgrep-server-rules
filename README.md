
This is a simple semgrep rule server for serving individual rules and packs.

To run:

```sh
$ go run main.go -listen=:8080
```

The `packs.yml` file contains rule packs.

```yaml
packs:
    expr:
        - bad-exponentiation
        - ...

```

The rule names must be the `id`s of the rules, *not* the filenames.

To serve and run a rule pack:

```sh
$ pip3 install semgrep
```

```sh
$ semgrep --config=http://localhost:8080/p/expr
```

To serve and run an individual rule:
```sh
$ semgrep --config=http://localhost:8080/r/database-sqli
```

Rules include

    - bidirectional-char
    - database-sqli
    - tainted-sql-string
    - gorm-dangerous-method
    - grpc-client-insecure-connection
    - jwt-go-none-algorithm
    - hardcoded-jwt-key
    - math-rand-used
    - missing-ssl-minversion
    - string-formatted-query
    - unescaped-data-in-js
    - gosql-sqli
    - pg-orm-sqli
    - pg-sqli
    - go-ssti
    - tainted-session-from-http-request
    - tainted-xpath-from-http-request
    - unsafe-reflection
    - unvalidated-redirect
    - weak-ssl-context
    - jdbc-sql-formatted-string
    - hibernate-sqli
    - jdbc-sqli
    - jdo-sqli
    - jpa-sqli
    - spring-sqli
    - jpa-raw-sqli
    - java-jwt-hardcoded-secret
    - dangerous-exec-command
    - detected-generic-secret
    - hardcoded-apikey