# 12_Forecasting

毎日更新型の占い・開運・性格タイプ別アドバイス記事を置く軽量コンテンツ領域。

この領域は `10_Published` のEvidence-Based長文記事とは分けて扱う。内容はエンタメと生活提案を中心にし、医療・法律・投資・進路などの重大な判断を占いで決める表現は避ける。

## 生成対象

- `zodiac.md`: 12星座別・今日の運勢
- `blood-type.md`: 血液型別・今日の運勢
- `eto.md`: 干支別・今日の運勢
- `mbti.md`: MBTI別・今日の行動アドバイス
- `lucky-action.md`: 今日の開運アクション

## 出力先

```text
12_Forecasting/daily/YYYY/MM/YYYY-MM-DD/
```

## 更新時刻

毎日 07:00 JST。

GitHub Actions ではUTC基準のため、cronは前日 22:00 UTC に設定する。

## 生成方式

Discord bot の `/daily_forecast` コマンド、または 07:00 JST の自動スケジューラが5種類のCodex jobをキューする。

各jobは `.agents/skills/ebe-daily-forecasting/SKILL.md` に従い、ソース調査、文脈整理、画像生成、Publish Gate確認を行う。既存ファイルは上書きしない。
