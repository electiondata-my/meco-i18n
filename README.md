# meco-i18n

Translation files for [electiondata.my](https://electiondata.my), served via Cloudflare R2.

## Structure

```
{locale}/{namespace}.json
```

| Locale | Language |
|--------|----------|
| `en-GB` | English |
| `ms-MY` | Bahasa Malaysia |

| Namespace | Description |
|-----------|-------------|
| `common` | Shared UI strings |
| `home` | Homepage |
| `election` | Single election page |
| `elections` | Elections listing |
| `byelections` | By-elections |
| `candidates` | Candidates |
| `parties` | Party listing |
| `party` | Single party page |
| `seats` | Seats |
| `catalogue` | Data catalogue |
| `research` | Research section |
| `redelineation` | Redelineation |
| `console` | Admin console |
| `trivia` | Trivia |
| `error` | Error pages |

## CDN

Files are publicly accessible at:

```
https://internal.electiondata.my/i18n/{locale}/{namespace}.json
```

Example: `https://internal.electiondata.my/i18n/en-GB/common.json`

## Deployment

Pushing to `main` automatically uploads changed files to the `meco-internal` Cloudflare R2 bucket via the [upload workflow](.github/workflows/upload-to-r2.yml).

Required GitHub Actions secrets:

| Secret | Description |
|--------|-------------|
| `CF_ACCOUNT_ID` | Cloudflare account ID |
| `CF_API_TOKEN` | Cloudflare API token with R2 write access |
