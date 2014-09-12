vagrant + ansible + packer + docker

### 使い方

```sh
https://github.com/matsu-chara/an-docker
cd an-docker
vagrant up
vagrant ssh
packer-packer build /vagrant/template.json
```

### 設定

* vagrantで立てるVM(centos)のプロビジョニングはinit.ymlで設定
* VMの中のdockerのプロビジョニングはansible/site.ymlで設定

### TODO的な

* webサーバーとかを実際に動かしてみる(portとかその辺がよくわかってない)
* virtualbox, amiもビルド？(どっちもvagrant経由でプロビジョニングできるし、どっちもイメージ化は難しくないからやらないかも)

### 妄想

1. dockerイメージビルド用サーバーでイメージをビルド(Packer)
    1. app, dbくらいの粒度( http://techracho.bpsinc.jp/hachi8833/2014_06_16/17982 )
    1. 今ansibleディレクトリになっているところをdbディレクトリとかにしてdb_template.jsonを指定してビルドみたいな感じが良さそう
    1. ビルドスクリプトを作っておいていつでも好きなイメージをビルドできるように
1. 各イメージビルド後、docker pushでイメージをどこかのregistry(docker hubとか)にプッシュ
1. 他のサーバーでansibleのdockerモジュールでimage,registry,(expose,env...)を指定してコンテナを立てる
1. 完成？
