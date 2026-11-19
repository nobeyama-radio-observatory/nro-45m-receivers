# nro-45m-receivers

国立天文台 野辺山宇宙電波観測所の 45m 鏡の受信機の**運用リポジトリ**です。観測所でこの装置群をどう使い、どう保守しているかを集めます。文脈基盤のハブ [nro-context](https://github.com/nobeyama-radio-observatory/nro-context) から参照されます。

扱う受信機：H22、H40、Z45、FOREST（4ビーム）、HINOTORI-TZ、7BEE（7ビーム3帯域）、eQ（所外の装置、試験中）。廃止したもの：T70、S40、S100/80、BEARS

## 位置づけ

文脈基盤では、装置の情報を次の四つの層に分けて置きます（ハブの判断記録 [0006](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/decisions/0006-資産の情報を装置群ごとの運用リポジトリに置く.md)）。参照は上の層から下の層へだけ行います。

```
ハブ（nro-context）→ 運用（このリポジトリ）→ 製品 → 開発
```

- **このリポジトリが正本のもの：** 台帳（構成、依存関係、提供の状態、保守の状況、更新の見込み、担い手の数）、運用と保守の文書、聞き取りの記録。
- **製品と開発のリポジトリ：** HINOTORI-TZ の 230 GHz モードのファーストライトに使った、観測指示書の書き換えの開発の [tz230-firstlight](https://github.com/ars096/tz230-firstlight)。台帳の `repos` から参照します。

## 中身

| 場所 | 中身 |
|---|---|
| [assets.yaml](assets.yaml) | 台帳。項目の定義はハブの [assets/README.md](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/assets/README.md) |
| [interviews/](interviews/README.md) | 聞き取りの記録。公開資料にない値（保守の手間、担い手の数、更新の見込みなど）の出典 |

台帳の `depends_on` と `part_of` にある id の置き場所は、ハブの[資産の索引](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/assets/README.md)で引けます。`nro45m`（アンテナ）は [nro-45m-antenna](https://github.com/nobeyama-radio-observatory/nro-45m-antenna) にあります。`if-system`（IF 系）は [nro-45m-if](https://github.com/nobeyama-radio-observatory/nro-45m-if) にあります。

## 進め方

進め方の決まりの正本は、ハブの [CONTRIBUTING.md](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/CONTRIBUTING.md) です。とくに次を守ってください。

- 機微情報を入れない。制御の手順、接続先、ネットワーク構成は、既存の非公開の場所に置いたままにする。
- 主ブランチに直接書き込まず、プルリクエストを出す。AI が作ったものにはラベル `AI作成` を付ける。
- 事実には出典を添える。出典を示せない事実は仮説として扱う（ハブの判断記録 [0004](https://github.com/nobeyama-radio-observatory/nro-context/blob/main/decisions/0004-事実の根拠は出典で示す.md)）。

担当：装置システムグループの受信機チーム（[聞き取り 2026-11-18（2）](interviews/2026-11-18-2.md) 問1）

## 利用許諾

- コード：BSD 3-Clause License（[LICENSE](LICENSE)）
- 文書：クリエイティブ・コモンズ 表示 4.0 国際（CC BY 4.0、[LICENSE-docs](LICENSE-docs)）
