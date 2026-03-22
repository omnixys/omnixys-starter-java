# Omnixys Starter

One dependency to enable the full Omnixys platform stack.

## Usage

### 1. Import BOM

```xml
<dependencyManagement>
  <dependencies>
    <dependency>
      <groupId>com.omnixys</groupId>
      <artifactId>omnixys-bom</artifactId>
      <version>0.1.0</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
  </dependencies>
</dependencyManagement>
````

### 2. Add Starter

```xml
<dependency>
  <groupId>com.omnixys</groupId>
  <artifactId>omnixys-starter</artifactId>
</dependency>
```

---

## Example application.yaml

```yaml
omnixys:
  observability:
    service-name: address

  kafka:
    enabled: true
    bootstrap-servers: localhost:9092
    group-id: address-group

  logger:
    kafka:
      topic: address.logstream
```

---

## Example Usage

```java
private final OmnixysLogger logger;

public void createUser(String userId) {
    logger.info("Creating user {}", userId);
}
```
