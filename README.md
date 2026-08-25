# 演習課題(共有リポジトリモデル)
## 概要
演習課題の手順に沿ってリポジトリの作成を行った。

kadai1のリポジトリでは、共有リポジトリでのモデルを使用し、役割分担を行った。

### 役割分担
🔴A: リード役 (檀上 蒼也)

🔵B: 開発者 (石井 陸登)

## 手順
### 1. AがGitHub上にリモートリポジトリを用意し、index.html（"Hello"と記述）をmainブランチにPushする

- AがGitHub上にリモートリポジトリを作成

```bash
$ mkdir kadai1
$ cd kadai1
$ git init
$ echo "# kadai1" >> README.md
$ git add .
$ git commit -m "Create kadai1"
$ gh repo create kadai1 --public --source=. --remote=origin --push
```

<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 140111" src="https://github.com/user-attachments/assets/f50b3436-3fca-421d-a67a-c58e883c9a36" />

- Aがindex.html（"Hello"と記述）をmainブランチにPush

```bash
$ echo "Hello" >> index.html
$ git add .
$ git commit -m "Create index.html"
$ git push origin main
```

<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 140225" src="https://github.com/user-attachments/assets/506f5bd4-ed2f-48c1-b1c4-c57e62b21171" />

### AのリポジトリのCollaboratorにBを追加

- AがAdd people からBを追加
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 140343" src="https://github.com/user-attachments/assets/0ee23105-c06c-4a7b-91dc-5e166e5e7f91" />

- Bが許可をする
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 140455" src="https://github.com/user-attachments/assets/0613fc45-953b-4f19-9775-f6126b036ddd" />

### 2. Bがリポジトリをcloneし、作業ブランチを作成。index.htmlを編集してPushし、Aへプルリクエストを出す

- Bがリポジトリをclone -> 作業ブランチを作成 -> index.htmlを編集 -> Push
```bash
$ git clone https://github.com/Aのユーザー名/kadai1.git
$ cd kadai1
$ git switch -c tejun2
$ vi index.html

$ git add .
$ git commit -m "Add index.html"
$ git push origin tejun2
```

- BがCompare & pull request で変更を確認
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 141656" src="https://github.com/user-attachments/assets/c6aa421c-dd55-480c-a1b5-68073d80f869" />

- BがCreate pull request でプルリクエストを作成
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 141712" src="https://github.com/user-attachments/assets/ecf7f63c-1534-4e42-bd40-c69066ddfa8c" />

### 3. AがBのプルリクエストをレビューし、mainブランチにマージする

- AがBのプルリクエストをレビュー
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 141745" src="https://github.com/user-attachments/assets/3eb515f3-7f6c-4f85-9517-63092c4a877d" />

- AがBのプルリクエストをmainブランチにマージ
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 141815" src="https://github.com/user-attachments/assets/b4f82fd6-edf8-4470-bcf3-3e79c624bb34" />

### 4. Aがローカルのmainブランチを最新化（pull）し、作業ブランチを作成。index.htmlを編集してPRを作成・マージする

- Aがローカルのmainブランチを最新化（pull） -> 作業ブランチを作成 -> index.htmlを編集 -> Push

```bash
$ git pull origin main
$ git switch -c tejun4
$ vi index.html

$ git add .
$ git commit -m "Add index.html"
$ git push origin tejun4
```

- AがCompare & pull request で変更を確認
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 142622" src="https://github.com/user-attachments/assets/70f1570a-1b6c-4ecf-aa5f-bb2a7e23ffe7" />

- AがCreate pull request でプルリクエストを作成
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 142635" src="https://github.com/user-attachments/assets/9dcc7cf2-555e-4d18-b7f3-f09793bb89e2" />

- Aがプルリクエストをmainブランチにマージ
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 142648" src="https://github.com/user-attachments/assets/49fab07c-6fcb-44d7-8ca1-3d46ea733b6e" />

### 5. Bがローカルのmainブランチを最新化（pull）し、作業ブランチを作成。stylesheet.cssを追加してAへプルリクエストを出す。

- Bがローカルのmainブランチを最新化（pull） -> 作業ブランチを作成 -> stylesheet.cssを作成 -> Push

```bash
$ git pull origin main
$ git switch -c tejun5
$ echo "new stylesheet.css" >> stylesheet.css
$ git add .
$ git commit -m "new stylesheet.css"
$ git push origin tejun5
```

- BがCompare & pull request で変更を確認
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 143036" src="https://github.com/user-attachments/assets/533f383d-51c2-44da-a7dc-abb1f630e99e" />

- BがCreate pull request でプルリクエストを作成
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 143045" src="https://github.com/user-attachments/assets/c4138e5f-b183-4d78-bdfd-5f7978a0e9fb" />

### 6. AがBのプルリクエストをレビューし、mainブランチにマージする。

- Aがレビューするプルリクエストを選択
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 143115" src="https://github.com/user-attachments/assets/25b7fdad-db19-4b06-8dd8-d4bbc539b7d8" />

- AがBのプルリクエストをmainブランチにマージ
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 143142" src="https://github.com/user-attachments/assets/9ef98126-5eb4-4843-8b9a-75ec863227e1" />
<img width="1920" height="1032" alt="スクリーンショット 2026-08-24 143158" src="https://github.com/user-attachments/assets/207df30a-86d3-4b35-92ce-764477a21f81" />
