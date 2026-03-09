# Tech Stack Research: Product Image → Lifestyle Video Tools

Research date: 2026-03-09

## Sites Analyzed

- qiantingai.com (潜艇 AI / Submarine AI)
- neobund.com (NeoBund / 牛邦科技)

Both sites returned HTTP 403 on all programmatic access attempts. Findings are based on indexed content, search snippets, and third-party sources.

---

## 潜艇 AI — qiantingai.com

### What it does
Users upload product images; the platform generates lifestyle/advertising short-form videos for ecommerce. Claims 1.2M viral videos generated, 25,000+ creators, 4.5x ad conversion lift.

### Tech Stack

| Layer | Details |
|---|---|
| Product | Upload product images → AI generates lifestyle/ad short videos |
| AI Engine | Proprietary "V02 advanced AI video generation engine" (model undisclosed) |
| Likely video model | Kling (快手可灵), Wan (通义万象/Alibaba), CogVideo, or 即梦AI (ByteDance) |
| Frontend | SPA — likely React or Vue (login-gated, unconfirmed) |
| Auth | Phone + SMS OTP (likely Alibaba Cloud SMS) |
| Infra | Likely Alibaba Cloud or Tencent Cloud |
| Billing | Credit-based ("算力" computing credits); new users get 600 credits |

### Inferred Pipeline
1. User uploads product image(s)
2. Platform calls image-to-video model API (Kling, Wan, or similar)
3. Lifestyle scene context applied (inpainting / scene generation)
4. Optional: AI-generated voiceover + ad copy
5. Output: short-form video formatted for Douyin/TikTok/Instagram

---

## NeoBund — neobund.com

### What it does
AI-driven TikTok video creation + cross-border ecommerce supply chain platform. Primary use: input a viral TikTok URL → AI deconstructs script/hooks → generates a similar video for your own product. Also supports dropshipping from China to US.

### Tech Stack

| Layer | Details |
|---|---|
| Product | TikTok video creation + cross-border dropshipping SCM |
| Video AI | Proprietary engine trained on viral TikTok video data |
| Script analysis | Multimodal LLM (likely Qwen-VL, InternVL, or GPT-4V) to deconstruct viral video structure |
| Video generation | Likely Kling or Wan 2.1 for output video |
| Text/script gen | LLM — DeepSeek, Qwen, or OpenAI-compatible API |
| Frontend | Multi-app architecture — likely React or Vue (unconfirmed) |
| Shopify integration | Yes — NeoBundSCM Shopify app (Node.js or Python backend) |
| Infra | Likely Alibaba/Tencent Cloud (China); possibly AWS for US SCM portal |
| Architecture | Microservices — multiple subdomains: scm.us., brand., mall. |
| Founded | 2021 (Hong Kong entity: NeoBund Technology Co., Limited) |

### Inferred Pipeline
1. Input: viral TikTok URL or product info/images
2. Multimodal LLM deconstructs viral video structure and hooks
3. LLM generates new script matching product
4. Video generation model (Kling/Wan) produces output video
5. Distribution to 30,000+ US TikTok KOLs or direct posting

---

## Comparison

| Dimension | 潜艇 AI (qiantingai.com) | NeoBund (neobund.com) |
|---|---|---|
| Core input | Product image | Viral video URL or product info |
| Core output | Lifestyle/ad video | UGC-style TikTok video |
| AI engine | Proprietary "V02" | Proprietary (TikTok-trained) |
| Likely video model | Kling / Wan / CogVideo | Kling / Wan 2.1 |
| LLM usage | Unknown | Yes (script deconstruction + generation) |
| Frontend | SPA (React/Vue) | Multi-app (React/Vue) |
| Shopify | No | Yes |
| Distribution | None | 30,000+ US TikTok KOLs |
| Target market | Chinese brands/creators | Cross-border sellers (China → US TikTok) |

---

## Key Limitation

Neither site exposes its tech stack publicly. Frontend framework, specific AI model integrations, CDN, and backend language/framework remain unconfirmed without browser-level inspection.
