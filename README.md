
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
scan all
```sh
$ semgrep --config=http://localhost:8080/p/all
```
scan java
```sh
$ semgrep --config=http://localhost:8080/p/java
```

scan go
```sh
$ semgrep --config=http://localhost:8080/p/go
```

scan php
```sh
$ semgrep --config=http://localhost:8080/p/php
```

scan nodejs/javascript/deno/ts
```sh
$ semgrep --config=http://localhost:8080/p/js
```

To serve and run an individual rule:
```sh
$ semgrep --config=http://localhost:8080/r/database-sqli
```

scan solidity
```sh
$ semgrep --config=http://localhost:8080/p/solidity
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
    - arbitrary-low-level-call
    - basic-arithmetic-underflow
    - basic-oracle-manipulation
    - basic-reentrancy
    - compound-borrowfresh-reentrancy
    - compound-sweeptoken-not-restricted
    - erc20-public-burn
    - erc20-public-transfer
    - erc677-reentrancy
    - erc721-arbitrary-transferfrom
    - erc721-reentrancy
    - erc777-reentrancy
    - gearbox-tokens-path-confusion
    - keeper-network-oracle-manipulation
    - oracle-price-update-not-restricted
    - proxy-storage-collision
    - redacted-cartel-custom-approval-bug
    - rigoblock-missing-access-control
    - rikkei-setoracledata-not-restricted
    - sense-missing-oracle-access-control
    - superfluid-ctx-injection
    - tecra-coin-burnfrom-bug
    - treasuredao-input-validation-vuln 