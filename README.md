# larabean-cli

# Larabean — Controls & Rules

_Controls with rule titles only — for planning/backlog seed._


## LAR-C01 · Environment & Baseline Integrity

- LAR-R001 — APP_ENV is production
- LAR-R002 — APP_DEBUG is false
- LAR-R003 — APP_KEY present with strong entropy
- LAR-R004 — APP_URL uses HTTPS and correct host
- LAR-R005 — Routes and config are cached in production
- LAR-R006 — Optimize/autoload dumped for production
- LAR-R007 — Storage and bootstrap/cache permissions are safe
- LAR-R008 — Timezone and locale configured explicitly
- LAR-R009 — Trusted proxies configured for reverse proxies
- LAR-R010 — Debug handlers/Whoops disabled in production

## LAR-C02 · Secrets & .env Hygiene

- LAR-R011 — .env not committed to VCS
- LAR-R012 — Secrets sourced from env/vault (not hard‑coded)
- LAR-R013 — Secret rotation policy documented
- LAR-R014 — .env.example is safe (no real values)
- LAR-R015 — No secrets in logs or exception messages
- LAR-R016 — APP_KEY rotation procedure present
- LAR-R017 — No .env exposure via web server

## LAR-C03 · Authentication & Session Security

- LAR-R018 — Password hashing uses argon2id/bcrypt with cost policy
- LAR-R019 — Rehash on login when parameters change
- LAR-R020 — 2FA available/enforced for privileged users
- LAR-R021 — Account lockout/decay after failed attempts
- LAR-R022 — Session driver suitable for production (redis/database)
- LAR-R023 — Session cookies have Secure, HttpOnly, SameSite flags
- LAR-R024 — Session invalidated on password change/logout
- LAR-R025 — Remember‑me TTL within policy limits
- LAR-R026 — Concurrent session policy defined
- LAR-R027 — Email verification enforced where applicable
- LAR-R028 — Password reset token TTL and throttle configured
- LAR-R029 — Sensitive routes require recent authentication

## LAR-C04 · Authorization & Policy Coverage

- LAR-R030 — Policies cover all sensitive models
- LAR-R031 — Controllers avoid authorization bypasses
- LAR-R032 — Deny‑by‑default strategy for gates/policies
- LAR-R033 — Ability naming is consistent and scoped
- LAR-R034 — Route middleware enforces auth scopes
- LAR-R035 — Admin actions are audited
- LAR-R036 — Fallback policy prevents implicit allows

## LAR-C05 · CSRF & Request Integrity

- LAR-R037 — CSRF middleware enabled for web routes
- LAR-R038 — CSRF exceptions are narrowly scoped
- LAR-R039 — CSRF token present on unsafe methods
- LAR-R040 — SameSite strategy aligns with CSRF design
- LAR-R041 — Origin/Referer checks for cross‑site POSTs (where applicable)
- LAR-R042 — Method spoofing guarded and validated

## LAR-C06 · CORS & API Surface

- LAR-R043 — No wildcard origins when using credentials
- LAR-R044 — Allowed methods/headers are explicit and minimal
- LAR-R045 — Preflight cache (max_age) tuned securely
- LAR-R046 — Credentials disabled unless strictly needed
- LAR-R047 — Vary headers set correctly for CORS responses

## LAR-C07 · Rate Limiting & Abuse Control

- LAR-R048 — Login endpoint has per‑IP and per‑account throttling
- LAR-R049 — OTP/2FA verification has throttling
- LAR-R050 — Password reset/email verification throttled
- LAR-R051 — API keys/IPs have separate rate limits
- LAR-R052 — Exponential backoff for repeated abuse
- LAR-R053 — Global fallback limiter present

## LAR-C08 · Outbound HTTP & SSRF Mitigation

- LAR-R054 — HTTP client sets request timeout
- LAR-R055 — HTTP client sets connect timeout
- LAR-R056 — TLS verification enabled (no verify=false)
- LAR-R057 — Domain allowlist enforced for egress
- LAR-R058 — Retries limited with backoff and cap
- LAR-R059 — Proxy usage controlled and restricted
- LAR-R060 — Raw URL/file_get_contents for remote calls avoided
- LAR-R061 — URL validation/sanitization before outbound call
- LAR-R062 — cURL calls include TIMEOUT/CONNECTTIMEOUT
- LAR-R063 — Circuit breaker or failure budget policy documented
- LAR-R064 — DNS rebinding protections considered (no internal targets)
- LAR-R065 — Sensitive metadata endpoints blocked (IMDS/169.254.*)

## LAR-C09 · Storage, Upload & File System

- LAR-R066 — Upload MIME and extension whitelist enforced
- LAR-R067 — Upload max size and image dimensions limited
- LAR-R068 — User‑controlled filenames sanitized
- LAR-R069 — Path traversal prevented on filesystem ops
- LAR-R070 — S3/Cloud storage ACL is private by default
- LAR-R071 — Signed URL TTLs are reasonable and scoped
- LAR-R072 — Public vs private disk usage reviewed
- LAR-R073 — Symbolic links validated and secure
- LAR-R074 — Temporary files cleaned up securely

## LAR-C10 · View & Blade Rendering Safety

- LAR-R075 — Output escaped by default (`{{ }}` not `{!! !!}`)
- LAR-R076 — Blade components/slots escape user data
- LAR-R077 — Raw HTML rendering whitelisted and reviewed
- LAR-R078 — Template includes avoid untrusted paths
- LAR-R079 — Auto‑escape rules documented for team

## LAR-C11 · Queue, Jobs & Scheduler Reliability

- LAR-R080 — Queue driver is not `sync` in production
- LAR-R081 — Job timeout/backoff/retry configured
- LAR-R082 — Horizon dashboard gated with auth/gates
- LAR-R083 — Scheduled tasks use withoutOverlapping/locks
- LAR-R084 — One‑server scheduling on multi‑node setups
- LAR-R085 — Failed job handling and alerts configured

## LAR-C12 · Database, Eloquent & Data Handling

- LAR-R086 — Strict mode enabled for SQL
- LAR-R087 — Transactional migrations where applicable
- LAR-R088 — utf8mb4 key length and collation set correctly
- LAR-R089 — Models use $fillable/$guarded safely
- LAR-R090 — Avoid passing $request->all() into mass assignment
- LAR-R091 — Pagination required for large listings
- LAR-R092 — Basic N+1 detection heuristics in reviews/tests
- LAR-R093 — Casting/serialization avoids unsafe unserialize
- LAR-R094 — Soft deletes and privacy rules respected for PII

## LAR-C13 · Logging, Monitoring & Telemetry

- LAR-R095 — Sensitive data redacted in logs
- LAR-R096 — Production log level and channels reviewed
- LAR-R097 — Log rotation/retention configured
- LAR-R098 — External logging endpoints use TLS/keys
- LAR-R099 — PII access audited where feasible
- LAR-R100 — Unhandled exceptions reported/alerted
- LAR-R101 — Health/readiness probes instrumented

## LAR-C14 · Dependency & Package Security

- LAR-R102 — composer.lock present and locked
- LAR-R103 — Dev dependencies excluded from production
- LAR-R104 — composer audit executed in CI
- LAR-R105 — Abandoned packages detected
- LAR-R106 — Yanked versions detected
- LAR-R107 — Vendor advisories integrated (e.g., Magebean feed)
- LAR-R108 — platform.php constrains runtime versions
- LAR-R109 — Pinned versions for critical deps
- LAR-R110 — Repository trust policy reviewed
- LAR-R111 — Post‑install scripts reviewed and safe
- LAR-R112 — License compliance reviewed for deps

## LAR-C15 · Deployment & Runtime Surface

- LAR-R113 — PHP expose_php disabled
- LAR-R114 — OPcache enabled with sane settings
- LAR-R115 — upload_max_filesize/post_max_size aligned with policy
- LAR-R116 — Memory/time limits set for prod stability
- LAR-R117 — Real IP/forwarded headers configured at proxy
- LAR-R118 — Web server security headers baseline applied
- LAR-R119 — Production error pages (no stack traces)
- LAR-R120 — Containers run as non‑root where applicable
- LAR-R121 — Read‑only filesystem or restricted write paths
- LAR-R122 — CI/CD secrets injected securely (no echo in logs)
