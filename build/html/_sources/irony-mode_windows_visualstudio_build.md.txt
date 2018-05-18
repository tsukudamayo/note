# windowsにてirony-serverをVisualStudioを使ってビルドする

## 手順

### 1. LLVMをインストールする

### 2. LLVMにパスを通す

### 3. melpaからironyとcompany-ironyをインストール
```sh
M-x package install irony
M-x package install company-irony
```

### 4. インストールしたironyのパスへ移動
```sh
cd AppData\Roaming\.emacs.d\elpa\irony-20180408.429
```

### 5. buildディレクトリを作成して移動
```sh
mkdir build
cd build
```

### 6. CMakeでビルド
```sh
cmake -G "Visual Studio 15 2017 Win64" ..
```

### 7. MSBuildを使ってビルド
```sh
MSBuild IronyMode.sln /p:Configuration=Release
```

### 8. exeファイルを.emacs.d\irony\binへ移動
```sh
cd ..\..\..\
mkdir irony
mkdir irony\bin
mv elpa\irony-20180408.429\server\build\bin\Release\irony-server.exe irony\bin\
```

### 9. .emacsにパスを追加
```sh
(add-to-list 'exec-path "path-to-libclang")
```

## 参考記事

[Setting up irony mode on Windows](https://github.com/Sarcasm/irony-mode/wiki/Setting-up-irony-mode-on-Windows)

[company-ironyを使ってemacsでC/C++の補完](https://qiita.com/sune2/items/c040171a0e377e1400f6)