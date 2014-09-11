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
