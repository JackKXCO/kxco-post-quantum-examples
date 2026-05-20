# kxco-post-quantum-examples

Drop-in webhook receiver templates verifying KXCO hybrid HMAC + ML-DSA-65 signatures across common platforms. Every example is **copy-paste runnable** with two environment variables.

| Example                       | Path                              | What it shows |
|-------------------------------|-----------------------------------|---------------|
| Express (Node.js)             | [`./express/`](./express)         | The reference Node.js receiver with raw-body capture |
| Next.js (App Router)          | [`./nextjs/`](./nextjs)           | Route handler with `Request.text()` for raw body |
| AWS Lambda (Node.js)          | [`./aws-lambda/`](./aws-lambda)   | API Gateway proxy event verifier |
| Cloudflare Workers            | [`./cloudflare-worker/`](./cloudflare-worker) | Edge worker verifier |
| Vercel Edge Function          | [`./vercel-edge/`](./vercel-edge) | Edge runtime verifier |
| GitHub Actions step           | [`./github-action/`](./github-action) | Verify webhook payloads relayed into a workflow |

## Required environment variables

Every example reads these two:

```
KXCO_PUBLIC_KID=648b1e9b142ce625
KXCO_PUBLIC_KEY_HEX=648b1e9b142ce625697fcd4d906f2ff0a7...   # 3904 hex chars
KXCO_WEBHOOK_SECRET=your-per-receiver-shared-secret         # optional, for HMAC
```

Fetch the current values once from `https://chain.kxco.ai/wallet/api/.well-known/kxco-pq-pubkey` and pin them.

## License

MIT.
