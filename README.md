## 環境要件
a
* Mac OS
* Virtual Box
    * https://www.oracle.com/technetwork/jp/server-storage/virtualbox/overview/index.html
* Vagrant
    * https://www.vagrantup.com/
* Vagrant-Plugin
    ```
    vagrant plugin install vagrant-disksize vagrant-hostsupdater
    ```
* mutagen
    * https://mutagen.io/documentation/introduction/installation
    
## 環境の起動

### 1. 環境起動

```bash
vagrant up
```

初回だけ実施
```bash
vagrant ssh-config --host ${任意のホスト名} >> ~/.ssh/config
```
ここで設定した任意のホスト名はmutagen.ymlをbetaに設定する

### 2. docker起動

```bash
vagrant ssh
```

ssh接続したVirtualBoxの仮想マシン上で実行
```bash
cd ap
docker-compose run app composer install
docker-compose up -d

```

### 3. mutagen 起動

```
mutagen project start
mutagen syn list
```

## 環境の停止

```bash
# mutagenを停止
mutagen project terminate
# vagrantを停止
vagrant halt
```

## 補足

### vagrant up でpermissionエラーが出る場合


