# dotfiles

個人の開発環境設定ファイルを管理するリポジトリです。

## 新しい Mac への移管手順

### 前提条件

新しい Mac に以下をインストールしておく。

1. **Homebrew**

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

### 手順

1. このリポジトリをクローンする

   ```bash
   git clone https://github.com/irom999/dotfiles.git ~/repos/dotfiles
   ```

2. `.Brewfile` をホームディレクトリに作成し、cloneした内容をコピーする

   ```bash
   touch ~/.Brewfile
   ```

3. `brew bundle` で一括インストールする

   ```bash
   brew bundle --global
   ```

これで `.Brewfile` に記載されたすべてのパッケージがインストールされる。

## .Brewfile の更新方法

手元の Mac で `brew install` や `brew install --cask` で新しいソフトをインストールした際は、以下のコマンドで `.Brewfile` を更新する。

```bash
brew bundle dump --global --force
```

`--force` を付けることで、既存の `~/.Brewfile` を上書きして最新の状態に更新できる。更新後はこのリポジトリにコミット・プッシュしておく。

## 参考

- [brew bundle を使って Mac を移行する - Zenn](https://zenn.dev/usagiga/articles/migrate-using-brew-bundle)
