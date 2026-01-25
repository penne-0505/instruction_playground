以下の `docker run` コマンドを、同等の機能を持つ `docker-compose.yml` ファイルに変換してください。
ボリュームのマウントや再起動ポリシーも正確に反映させてください。

```bash
docker run -d --name my-database \
  -p 3306:3306 \
  -e MYSQL_ROOT_PASSWORD=secret \
  -e MYSQL_DATABASE=app_db \
  -v mysql_data:/var/lib/mysql \
  --restart always \
  --network app-network \
  mysql:8.0

```

---

Excelで以下のような複雑なネストになった関数を使っています。
これをPythonのPandasを使って、DataFrameの新しい列 `Status` として追加するコードに書き換えてください。

**Excel数式**:
`=IF(AND(A2>=80, B2="Member"), "VIP", IF(OR(A2>=50, B2="Member"), "Regular", "Guest"))`
※ A列は「購入額」、B列は「会員ランク」と仮定します。

---

以下のJavaコード（冗長なGetter/Setterを持つクラス）を、PyhonicなPythonコードに書き換えてください。

```java
public class User {
    private String name;
    private int age;

    public User(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }
    // ...ageのGetter/Setterは省略
}

```

---

"料理のおいしさ"について、わかりやすく圏論で表してみてください。