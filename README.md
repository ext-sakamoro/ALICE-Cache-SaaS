# ALICE-Cache SaaS

Predictive distributed caching API with Markov Oracle

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum, ALICE-Cache |

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST /api/v1/put` | キャッシュ書き込み |
| `GET  /api/v1/get/{key}` | キャッシュ読み取り |
| `GET  /api/v1/stats` | キャッシュ統計（ヒット率、予測精度） |
| `GET`  | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
