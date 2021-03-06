# EarthsJ

É uma [biblioteca Java] (https://github.com/earthspay/EarthsJ) para interagir com o blockchain do Earths.

Suporta interação com o nó, assinatura de transação offline, ordens de correspondência e criação de endereços e chaves.

## Usando EarthsJ em seu projeto

Use os códigos abaixo para adicionar o EarthsJ como uma dependência para o seu projeto.

##### Maven:

```js
<dependency>
    <groupId>com.earthspay</groupId>
    <artifactId>earthsj</artifactId>
    <version>0.8</version>
</dependency>
```

##### Gradle:

```
compile group: 'com.earthspay', name: 'earthsj', version: '0.2'
```

##### SBT:

```
libraryDependencies += "com.earthspay" % "earthsj" % "0.2"
```

[A página desta biblioteca na Central do Maven](https://mvnrepository.com/artifact/com.earthspay/earthsj)

## Uso Básico

Crie uma conta de uma chave privada \('T' para testnet \):

```java
String seed = "health lazy lens fix dwarf salad breeze myself silly december endless rent faculty report beyond";
PrivateKeyAccount account = PrivateKeyAccount.fromSeed(seed, 0, Account.TESTNET);
byte[] publicKey = account.getPublicKey();
String address = account.getAddress();
```

Crie um nó e aprenda algumas coisas sobre o blockchain:

```java
Node node = new Node("https://my.earths.node/");
System.out.println("Current height is " + node.getHeight());
System.out.println("My balance is " + node.getBalance(address));
System.out.println("With 100 confirmations: " + node.getBalance(address, 100));
```

Envie algum dinheiro para um amigo:

```java
String buddy = "3N9gDFq8tKFhBDBTQxR3zqvtpXjw5wW3syA";
String txId = node.transfer(account, buddy, 1_00000000, 100_000, "Here's for you");
```

Assine uma transação offline:

```java
Transaction tx = Transaction.makeTransferTx(account, buddy, 1_00000000, Asset.EARTHS, 100_000, Asset.EARTHS, "");
System.out.println("JSON encoded data: " + tx.getJson());
System.out.println("Server endpoint to send this JSON to: " + tx.getEndpoint());
```

Agora envie-o de uma máquina on-line:

```java
node.send(tx);
```

Crie uma ordem DEX:

```java
Node matcher = new Node("https://testnode2.earthsnodes.earths.ga");
String matcherKey = matcher.getMatcherKey();
String wbtcId = "Fmg13HEHJHuZYbtJq8Da8wifJENq8uBxDuWoP9pVe2Qe";
Order order = matcher.createOrder(alice, matcherKey,
                new AssetPair(Asset.EARTHS, wbtcId),
                // buy 10 EARTHS at 0.00090000 WBTC each
                Order.Type.BUY, 90_000, 10 * Asset.TOKEN,
                // make order valid for 1 hour
                System.currentTimeMillis() + 3_600_000, MATCHER_FEE);
System.out.printf("Filed order " + order.id);
```

Existem alguns exemplos em `src/examples/java`.

## Construindo a biblioteca

Para construir do zero, execute

```bash
mvn clean package
```

As saídas são colocadas sob o diretório "target".

