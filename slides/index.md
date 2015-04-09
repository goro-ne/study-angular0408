


<STYLE type="text/css">
div .title {
    font-size: 1.143em;
    font-weight: bold;
    margin: 0 0 1.5em;
    border-bottom: 2px solid #B92A2C;
    box-shadow: 0 1px 0 #aaaaaa;
    -webkit-box-shadow: 0 1px 0 #aaaaaa;
    -moz-box-shadow: 0 1px 0 #aaaaaa;
    text-shadow: #999999 0px 1px 1px;
}
.frame .left {
  text-align:left;
  width:60%;
}
.frame .right {
  float:right;
  text-align:left;
  width:40%;
}
.frame .right .shadow {
  -webkit-box-shadow: 1px 1px 4px rgba(0,0,0,.5);
  -moz-box-shadow: 1px 2px 4px rgba(0,0,0,.5);
  box-shadow: 4px 4px 8px rgba(0,0,0,.5);
  margin: 10px;
}
.frame .right .shadow img {
  	display: block;
  	margin: 0 auto;
  	padding: 10px;
  	background: #fff;
  	border: 1px solid #f0f0f0;
}
</STYLE>



![](http://www.designil.com/wp-content/uploads/2015/01/angularjs-video-free.png)

---

#### LAMPに代わる次世代アーキテクチャ
## MEANスタックに触れてみよう #2


---

<div class="title">前回のプロジェクトをアップデート</div>

```
$ mkdir -p ~/repos/mean-sample && cd $_

$ git pull

$ yo angular-fullstack sample

既存ソースが存在する場合は Y でスキップする
以下、すべてのコンフリクトについて、既存ファイルを上書きしない
```

![](images/yo-command.png)

---

<div class="title">MEANアプリケーション起動</div>

#### MongoDBサーバ起動

```
$ mongod --bind_ip 127.0.0.1 --logappend --dbpath ./data/db > /dev/null &

$ ps aux | grep mongo
g-hayakawa      18247   0.1  0.6  2717460  51524   ??  S     5:16PM   0:04.48 /usr/local/opt/mongodb/bin/mongod --config /usr/local/etc/mongod.conf
g-hayakawa      21252   0.0  0.0  2432772    640 s000  S+    5:48PM   0:00.00 grep mongo


```

#### Expressサーバ起動

```
$ grunt serve
```

```
--> デフォルトブラウザで自動的に起動します
```



---

<div class="title">MEANのページのファイル構成、作成方法</div>

- コントローラ  
- CSS  
- テンプレート  
- 起動スクリプト  

```
$ tar --version
bsdtar 2.8.3 - libarchive 2.8.3
```

```
$ tar zxvf page.tgz

x client/app/page/
x client/app/page/page.controller.js
x client/app/page/page.css
x client/app/page/page.html
x client/app/page/page.js
```

---

<div class="title">navigationにPageリンクを追加</div>

client/components/navbar/navbar.controller.js
```
'use strict';

angular.module('sampleApp')
  .controller('NavbarCtrl', function ($scope, $location) {
    $scope.menu = [
      {
        'title': 'Home',
        'link': '/'
      },

      // Pageのリンク
      {
        'title': 'Page',
        'link': '/page/'
      }

    ];
    $scope.isCollapsed = true;

    $scope.isActive = function(route) {
      return route === $location.path();
    };
  });
```



---

<div class="title">Pageができました</div>

![](images/page.png)


---

それでは前回の続きをやってみましょう！

https://angularjs.org/

![](images/angularjs-movie.png)


Note:
動画再生
<iframe width="1120" height="630" src="https://www.youtube.com/embed/gnuEmSz_CHI?rel=0&hd=1&showinfo=0&theme=light&autohide=1" frameborder="0" allowfullscreen></iframe>
