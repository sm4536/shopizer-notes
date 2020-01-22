# Shopizer

These are some brief instructions on how to get Shopizer running on your system. If you prefer a video format, also check [this](https://www.youtube.com/watch?v=SCiRreBUFNA) out. Keep in mind the video differs a little from this document.

## Dependencies

You will need these on your system before running Shopizer.

### Java 8

Ensure you have Java 8 installed and not a later version. Your `%JAVA_HOME%` and `%PATH%` environment variables should also be properly set.

### Elasticsearch

Elasticsearch is a flexible search engine used by Shopizer for search and caching. Install Elasticsearch with all default options by following these [instructions](https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html). If you are on Windows, follow the `.zip` instructions not the `.msi` instructions.

## Build

1. Clone the repository

```
git clone https://github.com/shopizer-ecommerce/shopizer
git checkout origin/2.9.0
```

2. Build using Maven (this may take some time.)

```
cd <shopizer root>
mvnw clean install
```

On macOs or Linux, use `./mvnw` instead of just `mvnw`.

## Run

1. Ensure Elasticsearch is running.

```
cd <elasticsearch root>/bin
elasticsearch.bat
```

On macOs or Linux, use `./elasticsearch` instead of the `.bat` file.

2. Start Shopizer

```
cd <shopizer root>/sm-shop
mvnw spring-boot:run
```

Once Shopizer is running, you can visit `localhost:8080` to view the storefront. You can also visit `localhost:8080/admin` with username `admin@shopizer.com` and password `password` to view the admin panel.

## Debug

To understand the internals of Shopizer, it may be helpful to step through the code using an IDE.

### InteliJ

*TODO*

### Eclipse

*TODO*

## Other

 - You may notice an interesting exception during the startup of Shopizer. To fix this, search for instances of "DETETE" in the source code (there should be three) and change them all to "DELETE".

 - If you ever need to clear all persisted data, delete all `.db` files from inside `sm-shop`, and delete the `data` directory from inside your Elasticsearch install.