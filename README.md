# 板块流向 · 咕咕鸡

A 股行业 / 概念 / 地区板块实时资金流向。

## 本地预览

1. 启动后端：

```bash
cd C:\Users\Leos\guguji\ocr-server
python app.py
```

2. 浏览器打开本目录 `index.html`，或起静态服务：

```bash
cd C:\Users\Leos\guguji-sector
python -m http.server 8088
```

访问 `http://127.0.0.1:8088`（页面会请求 `http://127.0.0.1:5000` API）。

## API（挂在 ocr.guguji.icu / 本地 app.py）

- `GET /api/sector/health`
- `GET /api/sector/flow?type=industry|concept|region&period=1|5|10&sort=in|out|change&limit=50`
- `GET /api/sector/dual?type=industry&period=1&top=20`
- `GET /api/sector/<BK代码>/members?limit=30&sort=in`

数据来源：东方财富板块资金流。
