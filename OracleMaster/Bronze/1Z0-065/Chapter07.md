# 第七章 ユーザーおよびセキュリティの管理

## 7.1 ユーザーの管理とセキュリティの管理

**ユーザーアカウントの作成　★★★★**

- ```ユーザー属性```情報はSYSTEM表領域の**データディクショナリ**に格納されます。

|ユーザー属性 |説明 |
|---- |---- |
|名前 |ユーザーアカウントを識別する名前。**ユーザー名**という。 |
|データベース認証パスワード |ユーザー名対する**パスワード**。<br>パスワードはデータディクショナリに暗号化されて格納される。<br>Oracle Database 12cでは、大文字・小文字が区別される。 |
|デフォルト表領域 |ユーザーがオブジェクトを作成する際に、そのオブジェクトの格納先を指定しなかった場合に使用される表領域。<br>デフォルト表領域を指定しない場合は、**デフォルトの永続表領域**が暗黙的に設定される。 |
|一時表領域 |ユーザーが「**一時セグメントの作成を必要とするSQL文**」を実行した際に使用される表領域。<br>一時表領域を指定しない場合はデフォルトの一時表領域が暗黙的に指定される。 |
|表領域の割当て制限 |ユーザーに対して、使用を許可する**表領域の容量**。<br>ユーザーが使用可能な表領域ごとに設定する。<br>一時表領域やUNDO表領域は割当て制限の設定がなくても使用できる。 |
|アカウントステータス<br>(ロックまたはロック解除) |ログインできる状態(**ロック解除**)、またはログイン禁止の状態(ロック)を指定する。<br>ロックされている場合は、データベース管理者がロックを解除する必要がある。 |
|パスワードステータス<br>(有効または無効) |パスワードを無効(**期限切れ**)にするか、有効にするかを指定する。<br>無効になった場合、次回のログイン時にパスワードを変更する必要がある。 |

- データベース管理者は、ユーザーアカウントをあらかじめデータベースに作成しておく。

- ユーザーがデータベースにアクセスするには、接続時に有効なユーザー名、パスワードを入力し、データベースで認証を受ける必要がある。

- ユーザーアカウントを作成する際に、ユーザー属性をしているす。

- 新しく作成したユーザーアカウントを使用してデータベースに接続するには、**CREATE SESSIONシステム権限**が付与されているひつようがある。