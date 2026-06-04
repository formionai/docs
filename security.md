# 🔐 Security

Trading means connecting real money, so security is foundational to how Formion is built.

## Your funds never leave your exchange

Formion is **non-custodial**. It connects to your exchange through **API keys** and only ever places trades on your behalf — it **cannot withdraw**. Your funds stay on your own exchange or in your own wallet at all times.

* Use **trade-only** API keys (enable trading; leave withdrawals **disabled**).
* When connecting, add the Formion **IP whitelist** to your key — see **[How to Start — API Connection](how-to-start-api-connection.md)**.

## Encryption

* All API keys, secrets and sensitive credentials are **AES-256-GCM encrypted at rest**.
* Traffic is encrypted in transit (TLS).
* Wallet keys (if you choose full mode) are encrypted; you can also link wallets **read-only**.

## Account protection

* **Two-factor authentication (2FA)** — enable it in your profile; mandatory for Institutional team accounts.
* **Session management** — review and revoke active sessions any time.
* **Recovery email** and login activity log.

## Bring Your Own Key (BYOK)

When you connect your own AI provider keys, they're stored with the same AES-256-GCM encryption and used only for your requests.

## Good practices

* Keep API-key **withdrawal permission OFF**.
* Use a **sub-account** per bot where your exchange supports it.
* Enable 2FA and a strong, unique password.
* Pause or revoke a key any time from your exchange — bots stop immediately.

{% hint style="info" %}
Found a security issue? Email **support@formion.ai**.
{% endhint %}
