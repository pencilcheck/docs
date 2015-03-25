# コントローラーのアクション

テンプレートバインディングもしくはタグがビューをレンダリングする際には、まず始めにコントローラーが読み込まれます。レンダリングに関係するコールバックは4つあります。```{action}``` はビューファイルの名前と同一です。したがって、```about.html``` がレンダリングされたときには、```about``` がアクションとなります。コントローラーに正しくメソッドを定義しておくだけで、それらは対応するタイミングで実行されます。

| アクション名           | 詳細 |
|-----------------------|-----------------------------------------------------|
| ```{action}``` | レンダリングの前に実行されます。必要なデータのセットアップに利用してください。       |
| ```{action}_ready``` | ビューがレンダリングされた後に実行されます。DOM に直接バインドする必要があればそのコードをここで実行します。例えば (bootstrap に必要な) jQuery の設定コードなどです。 |
| ```before_{action}_remove``` | ビューが削除される (レンダリングが解かれる) ときに実行されます。ここで DOM バインディングの後始末をします。|
| ```after_{action}_remove``` | ビューがDOM から削除された後に実行されます。コントローラーに後始末が必要なものがあれば、ここで後始末します。||

ほとんどの場合、これらのアクションを利用して、コントローラーやモデルなどをセットアップすることになるでしょう。
