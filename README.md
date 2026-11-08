# Sakuragawa Crew ホームページ

茨城県桜川市の有志チーム「Sakuragawa Crew」の紹介ページ（静的HTML 1ページ）。
団体の理念・想いを伝えるページで、イベント情報・申込み・問い合わせ・メンバー募集・クルー紹介・実績数字は載せない方針。

- リポジトリ: https://github.com/a-mi3/sakuragawa-crew （`main` が公開用）
- Instagram: https://www.instagram.com/sakuragawacrew/
- 公開先: https://sakuragawa-crew.see-en.net/ （see-en.net のサーバーへFTPでアップロード。Vercelは使わない）

## 構成
```
index.html            ページ本体（CSSは<style>内に同梱、JSなし）
images/               hero / view1-4 / logo（webp）, ogp.jpg（SNS共有用 1200x630）
favicon.ico/png, apple-touch-icon.png
robots.txt, sitemap.xml
```
ページ順: トップ → Sakuragawa Crewとは → 理念 → 地域に還元したいこと → 大切にしていること → 桜川市の風景（写真4枚）→ チーム概要 → Instagram

## 現在の状況
- [x] ページ実装（スマホ対応）、写真・ロゴは元画像から作成
- [x] Instagramリンク設定済み
- [x] OGP・ファビコン・robots.txt・sitemap.xml 追加、画像webp化
- [x] サブドメイン `sakuragawa-crew.see-en.net` を登録し、`YOUR-DOMAIN` を置換済み
- [x] FTPで `public_html/sakuragawa-crew/` にアップロードして公開済み
- [x] お問い合わせボタン（Googleフォーム https://forms.gle/QqmuJNmbf98xmZ4E9 ）を追加。回答はメール通知
- [ ] SNS共有時の見え方（OGP）とスマホ実機表示を確認

## ドメイン確定後の置換
`index.html`（canonical / og:url / og:image）、`robots.txt`、`sitemap.xml` に仮の `YOUR-DOMAIN` が入っている。
```bash
sed -i 's|YOUR-DOMAIN|ここにドメイン|g' index.html robots.txt sitemap.xml
```

## 要確認事項
- 風景写真のキャプション（「雨引観音のしだれ桜と石段」など）は元デザイン画像の文言のまま。掲載してよいか確認。
- チーム概要の表（メンバー構成・活動方針など）は、提供された文面の範囲で作成。
- 将来、個別イベントの特設ページへのリンクを追加する予定（現状は載せない）。

## 別PCで作業するとき
```bash
git clone https://github.com/a-mi3/sakuragawa-crew
cd sakuragawa-crew
# ブラウザで index.html を開いて確認 → 編集 → push（Vercel連携後は自動公開）
```
