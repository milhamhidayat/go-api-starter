# internal/app

Private application and library code. Consist of:

### delivery

Any protocol interface used in the app (ex: grpc, graphql, http). If service and repository have different interface method, put service interface in this layer.

```
- delivery
    - http
        - user
            - user.go
            - user_test.go
        - article
            - article.go
            - article_test.go
    - grpc
    - graphql
```

### service

Service used in the app. Service is a layer handle business logic. If service and repository interface is same, then just put interface in the service. Otherwise, put repository interface in this layer. For example, the structure is:

```
- service
    - user
        - user.go
        - user_test.go
    - article
        - article.go
        - article_test.go
```

### service_mock

Contain mocks of service. Can be generated automatically using tool, or build manually.

### repository

Repository used in the app. Repository is a layer to organize data in db. For example, the structure is:

```
- repository
    - user
        - user.go
        - user_test.go
    - article
        - article.go
        - article_test.go
```

### repository_mock

Contain mocks of repository. Can be generated automatically using tool, or build manually.
