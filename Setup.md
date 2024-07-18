# 開発環境構築手順

## 開発ツール・言語

- [direnv](https://github.com/direnv/direnv)
- [Docker](https://www.docker.com/ja-jp/products/docker-desktop/)
- Java 21

## Docker

### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-docker.git
```

### コンテナの起動

```sh
$ cd schneider-docker
$ docker compose up -d
```

## Gradleプラグインのセットアップ

### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-code-generator.git
```

### Gradleプラグインのビルド

```sh
$ cd schneider-code-generator
$ ./gradlew build
```

### ローカルのMavenリポジトリへのpublish

```sh
$ ./gradlew publish
```

## DBマイグレーション

### eule-db

#### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-eule-db.git
```

#### Flywayによるマイグレーション

```sh
$ cd schneider-eule-db
$ ./gradlew flywayMigrate
```

#### Entityクラスの自動生成

```sh
$ ./gradlew generateEntity
```

#### ローカルのMavenリポジトリへのpublish

```sh
$ ./gradlew publish
```

### fasan-db

#### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-fasan-db.git
```

#### Flywayによるマイグレーション

```sh
$ cd schneider-fasan-db
$ ./gradlew flywayMigrate
```

#### Entityクラスの自動生成

```sh
$ ./gradlew generateEntity
```

#### ローカルのMavenリポジトリへのpublish

```sh
$ ./gradlew publish
```

## Enumクラスの自動生成

### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-enums.git
```

### Enumクラスの自動生成

```sh
$ cd schneider-enums
$ ./gradlew generateEuleEnum
$ ./gradlew generateFasanEnum
```

### ローカルのMavenリポジトリへのpublish

```sh
$ ./gradlew publish
```

## バックオフィス向けAPI

### リポジトリのクローン

```sh
$ git clone git@github.com:s-kugel/schneider-backoffice-api.git
```

### アプリケーションのビルド

```sh
$ cd schneider-backoffice-api
$ ./gradlew build
```

### アプリケーションの起動

```sh
$ ./gradlew run
```
