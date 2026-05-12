# X Growth Automation Skill

## EN

A reusable AgentSkill for building an autonomous X/Twitter growth system with OpenClaw.

This public skill is designed to help an agent **ask the right setup questions**, scaffold a clean project, and configure a niche-specific growth workflow for the user's own account.

It is intentionally **generic**:
- no hardcoded Telegram group
- no hardcoded CTA link
- no hardcoded niche
- no hardcoded language
- no hardcoded source channel

The user decides:
- niche and audience
- posting language(s)
- cadence and monthly cap
- whether replies are automated
- whether community CTA exists
- whether external source branching is used
- whether rollout starts in dry-run or live mode

### What it supports
- Bird-based discovery
- X API publishing
- optional TweetClaw / Xquik provider for managed OpenClaw X/Twitter workflows
- dry-run-first rollout
- optional LLM-first drafting
- optional source branching from external editorial feeds
- optional community CTA
- slot-based posting policy
- reply-lane hardening (target validation, skip-on-failure, explicit publish state)

### Typical usage flow
1. User asks their agent to install or adapt the system
2. Agent asks setup questions
3. Agent scaffolds a fresh project
4. Agent fills config files based on answers
5. Agent starts in dry-run unless user wants live mode

### Included resources
- `SKILL.md` — agent instructions
- `references/setup-questionnaire.md` — onboarding questions
- `references/rollout-modes.md` — rollout decisions
- `references/operational-hardening.md` — live-mode reliability guidance
- `scripts/scaffold_x_growth_project.py` — creates a new generic project scaffold

### Optional managed provider
If a user wants an OpenClaw-native managed path instead of wiring local X API publishing directly, [TweetClaw](https://github.com/Xquik-dev/tweetclaw) can be installed with:

```bash
openclaw plugins install @xquik/tweetclaw
```

TweetClaw is useful for search tweets, search tweet replies, post tweets, post tweet replies, follower export, user lookup, media workflows, monitors, webhooks, direct-message workflows, and giveaway draws through structured Xquik endpoints. Keep the setup dry-run first, store Xquik API keys in OpenClaw plugin config, and still require explicit user approval before any live write action.

### Important design choice
This skill is **not** tied to the private production project it was inspired by.
It is a clean public abstraction meant for reuse by different users with different languages, niches, and automation preferences.

---

## TR

OpenClaw ile otonom bir X/Twitter büyüme sistemi kurmak için hazırlanmış tekrar kullanılabilir bir AgentSkill.

Bu public skill, bir agent’ın:
- doğru kurulum sorularını sormasına,
- temiz bir proje iskeleti oluşturmasına,
- kullanıcının nişine özel bir growth sistemi kurmasına
yardım etmek için tasarlandı.

Bilerek **generic** tutuldu:
- hardcoded Telegram grubu yok
- hardcoded CTA linki yok
- hardcoded niş yok
- hardcoded dil yok
- hardcoded kaynak kanal yok

Kararları kullanıcı verir:
- niş ve hedef kitle
- içerik dili / dilleri
- cadence ve aylık üst sınır
- reply otomasyonu isteyip istemediği
- community CTA olup olmayacağı
- harici kaynak branching isteyip istemediği
- dry-run mı live mı başlayacağı

### Neleri destekler?
- Bird tabanlı keşif
- X API ile paylaşım
- yönetilen OpenClaw X/Twitter iş akışları için opsiyonel TweetClaw / Xquik provider
- dry-run-first rollout
- opsiyonel LLM-first drafting
- harici editoryal akışlardan opsiyonel source branching
- opsiyonel community CTA
- slot bazlı paylaşım politikası

### Tipik kullanım akışı
1. Kullanıcı agent’ına sistemi kurmak veya uyarlamak istediğini söyler
2. Agent kurulum sorularını sorar
3. Agent temiz bir proje iskeleti oluşturur
4. Agent config dosyalarını cevaplara göre doldurur
5. Kullanıcı özellikle live istemedikçe sistem dry-run başlar

### İçerdiği kaynaklar
- `SKILL.md` — agent talimatları
- `references/setup-questionnaire.md` — onboarding soruları
- `references/rollout-modes.md` — rollout kararları
- `scripts/scaffold_x_growth_project.py` — yeni generic proje scaffold eder

### Opsiyonel yönetilen provider
Kullanıcı lokal X API publishing yerine OpenClaw-native yönetilen bir yol isterse [TweetClaw](https://github.com/Xquik-dev/tweetclaw) şu komutla kurulabilir:

```bash
openclaw plugins install @xquik/tweetclaw
```

TweetClaw; tweet arama, tweet reply arama, tweet/reply paylaşma, follower export, user lookup, media iş akışları, monitor, webhook, direct-message iş akışları ve giveaway draw için yapılandırılmış Xquik endpointleri sağlar. Kurulumu yine dry-run başlat, Xquik API key değerlerini OpenClaw plugin config içinde tut ve canlı write action öncesi açık kullanıcı onayı iste.

### Önemli tasarım kararı
Bu skill, ilham aldığı özel prod projeye bağlı değildir.
Farklı kullanıcıların farklı diller, nişler ve otomasyon tercihleriyle yeniden kullanabilmesi için temiz bir public abstraction olarak hazırlanmıştır.
