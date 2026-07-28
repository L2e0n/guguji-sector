# 板块流向 · 咕咕鸡

A 股行业 / 概念 / 地区板块实时资金流向。

## 线上地址

- 正式域名（需 Cloudflare DNS）：https://gu.guguji.icu
- 临时入口（已可用）：https://ocr.guguji.icu/gu/
- API：`https://ocr.guguji.icu/api/sector/*`

## Cloudflare DNS（上线 gu.guguji.icu 唯一剩余步骤）

在 Cloudflare → `guguji.icu` → DNS 添加（与 `qdii` 相同写法）：

| 类型 | 名称 | 目标 | 代理 |
|------|------|------|------|
| CNAME | `gu` | `l2e0n.github.io` | 已代理 |

保存后等 1–2 分钟，打开 https://gu.guguji.icu 即可。

> 备选（走阿里云 Tunnel）：CNAME `gu` → `72037266-7d33-4cef-94c5-ea1066f69ffd.cfargotunnel.com`（已代理）。服务器侧 Nginx `:8089` 与 cloudflared ingress 已就绪。

## 本地预览

1. 启动后端：

```bash
cd C:\Users\Leos\guguji\ocr-server
python app.py
```

2. 静态页：

```bash
cd C:\Users\Leos\guguji-sector
python -m http.server 8088
```

访问 `http://127.0.0.1:8088`。

## API

- `GET /api/sector/health`
- `GET /api/sector/flow?type=industry|concept|region&period=1|5|10&sort=in|out|change&limit=50`
- `GET /api/sector/dual?type=industry&period=1&top=20`
- `GET /api/sector/<BK代码>/members?limit=30&sort=in`

数据来源：东方财富板块资金流。
