# HANDOFF COMPLETO — Copia identica del sito delfinitx su un altro account Hostinger AI Builder

> Istruzioni da incollare nell'AI Builder del nuovo account Hostinger.
> Il sito originale è https://delfinitx.com — la copia deve essere identica in pagine, design, testi (tedesco/inglese) e funzioni.
> IMPORTANTE: il saldo della Wallet deve essere letto IN TEMPO REALE dalla blockchain (indirizzi pubblici, nessuna chiave privata). Nessun saldo finto/simulato.

---

## 1. PROMPT DA INCOLLARE NEL NUOVO AI BUILDER (inizio conversazione)

Crea un sito web per una piattaforma di trading/wallet criptovalute chiamata **delfinitx**, in **React + Tailwind + shadcn/ui**, con **PocketBase** per autenticazione e dati. Lingua predefinita: **tedesco**, con switch **DE/EN** in header (persistito in localStorage, aggiorna `document.documentElement.lang`). Design scuro/professionale stile Kraken/Crypto.com. Il sito deve avere: home page, guide/FAQ, chi siamo, contatti, privacy policy, registrazione/login con verifica email e approvazione admin, wallet personale multi-valuta con saldi letti dalla blockchain, dashboard admin. Metadati `noindex, nofollow`.

---

## 2. BRAND & DESIGN (da replicare esattamente)

- **Nome:** delfinitx (logo: icona Bitcoin in un quadrato arrotondato `bg-primary/10`, testo "delfinitx")
- **Font:** DM Sans (Google Fonts), `font-variant-numeric: tabular-nums` per i prezzi
- **Radius:** 0.75rem; card `rounded-2xl`; pulsanti `rounded-xl`/`rounded-lg`
- **Dark mode:** classe `.dark` su `<html>`, toggle nella Wallet
- **Footer:** © 2026 delfinitx · "Echtzeitdaten unterstützt / Powered by real-time data" · Lizenz Nr. VL/23/07/003 · "SOC2 Type II und ISO27001 geprüft und zertifiziert — der Goldstandard für Sicherheitscompliance." · Gesellschaftskapital: US$54M · badge certificazioni SOC2/ISO27001 · link: Datenschutzrichtlinie, Nutzungsbedingungen, Startseite, Leitfäden, Über uns, Kontakt · support@delfinitx.com
- **SEO:** ogni pagina ha `<Helmet>` con title e meta description propri; `noindex, nofollow` globale

### Variabili CSS (incollare in `src/index.css` — valori esatti)

```css
@import url('https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap');

:root {
  --background: 240 20% 98%;
  --foreground: 240 6% 10%;
  --card: 0 0% 100%;
  --card-foreground: 240 6% 10%;
  --primary: 259 90% 58%;        /* viola #6D28D9 circa */
  --primary-foreground: 0 0% 100%;
  --secondary: 152 60% 42%;      /* verde */
  --secondary-foreground: 0 0% 100%;
  --muted: 240 20% 96%;
  --muted-foreground: 240 4% 46%;
  --accent: 259 90% 96%;
  --accent-foreground: 259 60% 30%;
  --destructive: 0 84% 60%;
  --border: 240 15% 90%;
  --input: 240 15% 90%;
  --ring: 259 90% 58%;
  --radius: 0.75rem;
  --eco-green: 152 60% 42%;
  --crypto-blue: 259 90% 58%;
  --eco-orange:  25 95% 53%;
}
.dark {
  --background: 250 20% 6%;
  --foreground: 0 0% 98%;
  --card: 250 18% 10%;
  --primary: 259 90% 62%;
  --secondary: 152 60% 45%;
  --muted: 250 15% 14%;
  --muted-foreground: 0 0% 63%;
  --border: 250 15% 18%;
}
```

Body: `font-family: "DM Sans", sans-serif; background: hsl(var(--background)); color: hsl(var(--foreground)); overflow-x: clip;` — headings `font-weight:700; text-wrap: balance;` — `html { scroll-behavior: smooth; }` — scrollbar custom sottile.

---

## 3. PAGINE & ROUTE (tutte bilingue DE/EN, tedesco predefinito)

| Route | Pagina | Contenuto |
|---|---|---|
| `/` | HomePage | Hero con sfondo crypto + overlay `bg-background/90`, badge "Live-Daten, detailliert und fortschritten", H1 "Professioneller Krypto-Handel angetrieben durch Echtzeitdaten", CTA "Leitfäden entdecken" / "Mehr erfahren". TickerBar prezzi live. Sezione download app. "Unsere Leistungen" (4 card: Zahlungen, Handel, Wallets, Stablecoins). Sezione trust. Sezione tools con immagine. TrendingAssets. Widget TradingView. Sezioni staking (4 sezioni animate). "Warum delfinitx wählen" (4 feature: Echtzeit-WebSocket-Daten, Sicherheit auf Unternehmensebene, Fortschrittliche Marktwerkzeuge, Blitzschnelle Aktualisierungen). "Empfohlene Leitfäden" (3 guide). WhyChooseEcoCrypto. Footer. |
| `/guides` | GuidesPage | Hero + FAQ in accordion, 3 categorie: "Registrierung & E-Mail-Verifizierung" (6 domande), "KYC & Identitätsverifizierung" (6), "Sicherheit & Zertifizierungen" (6). Box finale "Ihre Antwort nicht gefunden?" → support@delfinitx.com |
| `/guides/crypto-staking` | Guida | "Was ist Crypto Staking?" — categoria Anfänger, Einfach, 8 min, 15. April 2026, hero immagine monete viola, sezioni: cosa è, come funziona (4 step), vantaggi, rischi, sicurezza, staking su delfinitx + CTA |
| `/guides/proof-of-stake` | Guida | "Proof of Stake erklärt" — Blockchain, Mittel, 12 min, 12. April 2026, sezioni: cosa è, PoS vs PoW, selezione validatori, sicurezza, efficienza, sostenibilità + CTA |
| `/guides/carbon-neutral-blockchains` | Guida | "Kohlenstoffneutrale Blockchains" — Nachhaltigkeit, Einfach, 10 min, 10. April 2026, sezioni: questione ambientale, riduzione footprint (3 strategie), CO₂-Zertifikate, PoS, investitori, impegno delfinitx + CTA |
| `/about` | AboutPage | Visione "Cryptocurrency in Every Wallet", missione "Den Übergang der Welt zu Kryptowährung beschleunigen", partner, team (150M+ utenti, 90+ paesi), valori (6 card numerate), sicurezza |
| `/contact` | ContactPage | Email support@delfinitx.com, live chat (Mon–Fri 9–17 EST), FAQ, tempi di risposta (30–45 Min), orari supporto, canali, priority support |
| `/privacy-policy` | PrivacyPolicyPage | 14 sezioni complete (raccolta dati, uso, GDPR, diritti, sicurezza SOC2/ISO27001, condivisione, retention, cookie, bambini, trasferimenti, modifiche, contatto) — "Zuletzt aktualisiert: 18. Juli 2026" |
| `/signup` `/login` `/auth` | Auth | Card centrata con icona Bitcoin, tab Anmelden/Registrieren; dopo signup: "E-Mail prüfen" (verifica email → poi approvazione delfinitx). Login: "Passwort vergessen?" → `/forgot-password` |
| `/forgot-password` `/reset-password/:token` | Reset | Richiesta link via PocketBase `requestPasswordReset` / `confirmPasswordReset` |
| `/auth/confirm-verification/:token` | VerifyEmail | Stati: verifying / success ("E-Mail verifiziert! Warten Sie nun auf die Freigabe durch delfinitx…") / error |
| `/wallet` | WalletPage | **Protetta** — vedi sezione 6 (la più importante) |
| `/admin` | AdminPage | **Protetta, solo role=admin** — vedi sezione 7 |

Header (sticky, `bg-background/95 backdrop-blur`): Logo | nav (Startseite, Leitfäden, [Wallet se loggato], [delfinitx se admin], Über uns, Kontakt) | toggle DE/EN | Anmelden/Registrieren oppure Abmelden. Menu mobile in Sheet.

---

## 4. POCKETBASE — SCHEMA (migrazioni esatte)

### Collection `users` (auth, già esiste — estendere con findCollectionByNameOrId)

Campi aggiuntivi: `name` (text max 255), `avatar` (file), `role` (select: `client`, `admin`), `status` (select: `pending`, `approved`, `rejected`, `disabled`), `approvedAt` (date).

Regole (attenzione al campo privilegiato `role`/`status`):
```js
listRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || id = @request.auth.id)",
viewRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || id = @request.auth.id)",
createRule: "",   // signup pubblico; hook server-side forza role=client, status=pending
updateRule: "@request.auth.id != '' && (@request.auth.role = 'admin' || id = @request.auth.id)",
deleteRule: "@request.auth.role = 'admin'",
```
Verifica email attiva; durata token verifica: 604800s (7 giorni); `emailVisibility = true` per default.

### Collection `client_wallets` (base) — assegnazione wallet personali per cliente

Campi: `email` (email, required, unique), `client_name` (text 200), `btc_address`, `eth_address`, `usdt_address`, `sol_address` (text 200), `btc_zpub` (text 500), created/updated autodate.

```js
listRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.email = email)",
viewRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.email = email)",
createRule: "@request.auth.role = 'admin'",
updateRule: "@request.auth.role = 'admin'",
deleteRule: "@request.auth.role = 'admin'",
```
Indice: `CREATE UNIQUE INDEX idx_client_wallets_email ON client_wallets (email)`.

### Collection `transactions` (base)

Campi: `email` (text 255), `amount` (number), `recipient` (text 255), `usd` (number), `status` (text 50), `owner` (relation → users, maxSelect 1), `created` autodate.

```js
listRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.id = owner)",
viewRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.id = owner)",
createRule: "@request.auth.id != ''",
updateRule: "@request.auth.role = 'admin'",
deleteRule: "@request.auth.role = 'admin'",
```

### Collection `kyc_documents` (base)

Campi: `email` (text 255), `documents` (file, maxSelect 5, 10MB, mime jpeg/png/webp/gif/pdf, required), `docType` (select: `id_card`, `drivers_license`, `passport`), `status` (select: `pending`, `approved`, `rejected`), `reviewedAt` (date), `owner` (relation → users, required), created/updated.

```js
listRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.id = owner)",
viewRule:   "@request.auth.id != '' && (@request.auth.role = 'admin' || @request.auth.id = owner)",
createRule: "@request.auth.id != '' && @request.auth.id = owner",
updateRule: "@request.auth.role = 'admin'",
deleteRule: "@request.auth.role = 'admin'",
```
Indici su `owner` e `status`.

### Collection `password_resets` (base)

Campi: `token` (text 100, required, unique), `user` (relation → users, required), `expiresAt` (date, required), `used` (bool), `created` autodate. Tutte le regole `null` (solo server-side).

### Seed (in migrazione, NON da dashboard)

- **Admin:** `support@delfinitx.com` / password forte (es. `Milano123@`), `name: "delfinitx Team"`, `role: "admin"`, `status: "approved"`, `emailVisibility: true`.
- **Cliente demo:** `info@tamp-vino.store` (tamp), `role: "client"`, `status: "approved"`.
- **client_wallets tamp:** BTC `bc1qqm7hmkwt89ktxp609yrlvkjfs5jedecw37fuy9`, zpub `zpub6rjfNemXaKR6FvSFpT9xwP6xYHJoAkujS776N1o9NMiPUHGPGt4HXEmZosqgLY5XizB6MbNhvkzWLTSZT7g4bW1dwYZUtB8FZavtUjvt1Ay`.
- **NON creare** account/dati di test Bruno Marra o Sandra Marra (rimossi definitivamente dal sito originale).

---

## 5. POCKETBASE — HOOKS (`pb_hooks/*.pb.js`)

1. **`user-signup-defaults.pb.js`** — su creazione record `users`: forza `role = "client"`, `status = "pending"`, `emailVisibility = true`; blocca modifiche a `role`/`status` da parte di non-admin (protezione privilege escalation).
2. **`branded-verification-email.pb.js`** — `onMailerRecordVerificationSend`: email di verifica brandizzata delfinitx (design scuro crypto, pulsante "Verify", messaggio "in attesa di approvazione"), link `{appURL}/auth/confirm-verification/{token}`, sender con nome "delfinitx".
3. **`approval-notification.pb.js`** — `onRecordUpdate` users quando cambia `status`: email brandizzata di approvazione/rifiuto al cliente con link login `{domain}/login` + notifica separata a support@delfinitx.com.
4. **`forgot-password.pb.js`** — `onMailerRecordPasswordResetSend`: email brandizzata reset con link `{domain}/reset-password/{token}`; protezione enumerazione email.
5. **`admin-delete-user.pb.js`** — route server-side `/api/admin-delete-user` (POST, solo admin/superuser): cancellazione definitiva utente + transazioni collegate, libera l'email per nuove registrazioni.
6. **`builder-mailer.pb.js`** — helper `brandedFrom()` = `{name: "delfinitx", address: senderAddress di sistema}` per sender coerente.

---

## 6. WALLET (`/wallet`) — LA FUNZIONE PRINCIPALE

Accesso: solo utenti autenticati **e** approvati (`status = "approved"` o admin). Se in attesa → schermata "Warten auf delfinitx-Freigabe" con pulsante "Status prüfen". Se non loggato → redirect `/login`.

Flusso: Splash 2s ("delfinitx Wallet", barra di caricamento, "Sitzung wird gesichert …") → **PIN lock** (creazione/verifica PIN a 4 cifre, salvato in localStorage, tastierino numerico, reset PIN con conferma) → **auto-lock dopo 2 minuti di inattività**.

### Monete supportate (selettore a 4 pulsanti)

```js
const COINS = [
  { id:'bitcoin',  symbol:'BTC',  name:'Bitcoin',  glyph:'₿', decimals:8,
    address:'bc1qqm7hmkwt89ktxp609yrlvkjfs5jedecw37fuy9',
    zpub:'zpub6rjfNemXaKR6FvSFpT9xwP6xYHJoAkujS776N1o9NMiPUHGPGt4HXEmZosqgLY5XizB6MbNhvkzWLTSZT7g4bW1dwYZUtB8FZavtUjvt1Ay',
    binancePair:'BTCUSDT', tvSymbol:'BINANCE:BTCUSDT' },
  { id:'ethereum', symbol:'ETH',  name:'Ethereum', glyph:'Ξ', decimals:6,
    address:'0xf1E69059bACa32d3D07C75d20453E24130443484',
    binancePair:'ETHUSDT', tvSymbol:'BINANCE:ETHUSDT' },
  { id:'solana',   symbol:'SOL',  name:'Solana',   glyph:'◎', decimals:4,
    address:'AyBQdPREuvh1vW9yDdehUrTFKFFQ8d68scPHWmFbuKH5',
    binancePair:'SOLUSDT', tvSymbol:'BINANCE:SOLUSDT' },
  { id:'tether',   symbol:'USDT', name:'USDT',     glyph:'₮', decimals:2,
    address:'0xf1E69059bACa32d3D07C75d20453E24130443484',
    tvSymbol:'KRAKEN:USDTUSD' },
];
```
Se esiste un record `client_wallets` con la email dell'utente, gli indirizzi personali sostituiscono i default (solo le monete con indirizzo assegnato; BTC usa anche `btc_zpub` per il modal zpub).

### SALDO DALLA BLOCKCHAIN (requisito chiave per la NUOVA copia — nessun saldo hardcoded)

> **NOTA DI TRASPARENZA:** nel sito attuale il saldo mostrato in "Gesamtguthaben" e "Portfolio" è un **importo fisso di visualizzazione** (attualmente 0,23366158 BTC / $19.572,08), **non** un saldo on-chain verificato. Questa sezione descrive il comportamento **richiesto per la nuova copia**: il saldo deve diventare reale e verificabile on-chain. Non copiare l'importo fisso come saldo reale e non dichiarare mai "attivo" un saldo on-chain senza verifica pubblica dell'indirizzo.

Il saldo deve essere **il vero saldo on-chain dell'indirizzo**, letto da API pubbliche con catena di fallback, refresh ogni 20 secondi, con guardia anti-stale quando si cambia moneta:

```js
// BTC — catena di fallback in ordine:
// 1) https://blockchain.info/q/addressbalance/{addr}?cors=true   → satoshi / 1e8
// 2) https://api.blockcypher.com/v1/btc/main/addrs/{addr}/balance → data.balance / 1e8
// 3) https://mempool.space/api/address/{addr} → (chain_stats.funded_txo_sum - chain_stats.spent_txo_sum) / 1e8

// ETH — fallback:
// 1) https://api.blockcypher.com/v1/eth/main/addrs/{addr}/balance → / 1e18
// 2) POST https://eth-mainnet.g.alchemy.com/v2/demo {method:"eth_getBalance",params:[addr,"latest"]} → parseInt(hex,16)/1e18

// SOL — RPC JSON {method:"getBalance",params:[addr]} verso in ordine:
// https://solana-rpc.publicnode.com · https://api.mainnet-beta.solana.com ·
// https://solana.public-rpc.com · https://rpc.ankr.com/solana ·
// https://solana-mainnet.g.alchemy.com/v2/demo → result.value / 1e9

// USDT (ERC-20, contract 0xdAC17F958D2ee523a2206206994597C13D831ec) — fallback:
// 1) https://api.ethplorer.io/getAddressInfo/{addr}?apiKey=freekey → token USDT balance / 10^decimals
// 2) eth_call balanceOf via Alchemy demo → parseInt(hex,16)/1e6
```
Il valore USD = saldo on-chain × prezzo live. **"Gesamtguthaben" e "Portfolio" mostrano il saldo reale della moneta selezionata** (nessun importo fisso, nessun aumento automatico).

### Prezzo live (fallback, refresh 30s)

1. Binance `https://api.binance.com/api/v3/ticker/24hr?symbol={pair}` (lastPrice + priceChangePercent)
2. CoinGecko `simple/price?ids={id}&vs_currencies=usd&include_24hr_change=true`
3. CoinCap `https://api.coincap.io/v2/assets/{id}`
USDT: fallback finale `{price:1, change:0}`.

### Altri blocchi della Wallet

- **Grafico prezzo** (Chart.js line con gradiente, verde se 24h ≥0 altrimenti rosso): timeframe 1H/1D/7D/30D/1Y; fonti in fallback: CoinGecko market_chart → Binance klines → CryptoCompare histo → CoinCap history; USDT flat-line fallback.
- **Fear & Greed Index**: `https://api.alternative.me/fng/?limit=1`, gauge SVG circolare colorato.
- **Convertitore** valuta ↔ USD a due input sincronizzati.
- **EMPFANGEN**: modal con QR code (qrcode.react) dell'indirizzo + copia negli appunti.
- **SENDEN**: form indirizzo/amount/email ricevuta → review → conferma. La transazione viene **registrata in PocketBase** (`transactions`: email, amount, recipient, usd, status "Confirmed", owner) e mostrata nella cronologia — non è un broadcast on-chain.
- **Verlauf**: cronologia transazioni (localStorage + PocketBase) con dettaglio.
- **zpub**: modal con QR dell'extended public key (solo lettura, avviso "niemals private Keys teilen").
- **Preisalarm**: prezzo target → notifica browser + email quando raggiunto.
- **News Bitcoin**: lista statica di 4 notizie (ETF inflows, Lightning capacity, long-term holders, mining difficulty).
- **Widget TradingView** symbol-info della moneta selezionata.
- **Guida Kraken** (modal step-by-step, 9 step con illustrazioni phone-frame animate): scarica app Kraken → registra conto → KYC → compra Bitcoin → copia indirizzo delfinitx → withdrawal → incolla indirizzo/verifica rete → conferma → verifica transfer. Link: app `https://app.kraken.com/JDNW`, signup `https://www.kraken.com/sign-up`, buy `https://www.kraken.com/buy`. Note di sicurezza (mai condividere password/OTP/seed). **SENZA pulsante download PDF** (rimosso).
- Pulsanti: "Anleitung: Bitcoin kaufen" (apre guida) + "Bitcoin kaufen" (link Kraken).
- Notifiche email (EmailJS, vedi sezione 8) su accesso wallet/PIN e transazioni.

### 6.1 CHECKLIST DETTAGLIATA DELLE FUNZIONI WALLET (molto importante)

Legenda:
- ✅ **[CONFERMATO nel sito attuale]** — funzione esistente e verificata sul sito originale: riprodurla uguale nella copia.
- 🔗 **[RICHIESTO per la nuova copia]** — funzionalità on-chain richiesta per la copia: **NON esiste nel sito attuale**, va implementata nel nuovo build e verificata on-chain prima di dichiararla attiva. Nessun saldo o transazione on-chain va presentato come già funzionante senza verifica pubblica.

#### A. Accesso e sicurezza
- ✅ Pagina protetta: solo utenti autenticati con `status = "approved"` (o admin); se in attesa → schermata "Warten auf delfinitx-Freigabe" con pulsante "Status prüfen"; non loggato → redirect `/login`.
- ✅ Splash screen 2s ("delfinitx Wallet", barra di caricamento, "Sitzung wird gesichert …").
- ✅ PIN lock a 4 cifre: creazione + conferma + verifica, tastierino numerico, PIN salvato in localStorage, reset PIN con dialog di conferma.
- ✅ Auto-lock dopo 2 minuti di inattività (reset su mousemove/keydown/click/scroll/touchstart).
- ✅ Toggle dark/light dentro la Wallet (classe `.dark` su `<html>`, preferenza persistita in localStorage).
- ✅ Nessuna chiave privata / seed phrase mai richiesta, salvata o mostrata — solo indirizzi pubblici e zpub read-only.

#### B. Asset e reti supportate
- ✅ 4 monete con selettore a pulsanti: Bitcoin (BTC, mainnet, 8 decimali), Ethereum (ETH, mainnet, 6), Solana (SOL, mainnet, 4), Tether (USDT, token ERC-20 su Ethereum, 2).
- ✅ Indirizzi default per moneta + override personale dal record `client_wallets` (match sulla email utente); solo le monete con indirizzo assegnato; BTC mostra anche il modal zpub se `btc_zpub` presente.
- ✅ Widget TradingView symbol-info per la moneta selezionata (BINANCE:BTCUSDT, BINANCE:ETHUSDT, BINANCE:SOLUSDT, KRAKEN:USDTUSD).

#### C. Saldo (Gesamtguthaben + Portfolio)
- ✅ **[CONFERMATO — ma è un importo fisso di visualizzazione]** Nel sito attuale "Gesamtguthaben" e "Portfolio" mostrano un valore fisso (0,23366158 BTC / $19.572,08), senza aumenti automatici. **Non è un saldo on-chain verificato e non va riprodotto come saldo reale nella copia.**
- 🔗 **[RICHIESTO per la nuova copia]** Leggere il vero saldo on-chain dell'indirizzo pubblico con catena di fallback (vedi "SALDO DALLA BLOCKCHAIN" sopra), refresh ogni 20s, guardia anti-stale al cambio moneta. Valore USD = saldo on-chain × prezzo live. Se nessuna API risponde → mostrare "—"/stato di caricamento, **mai un importo inventato**; ogni saldo mostrato deve essere verificabile pubblicamente sull'indirizzo.

#### D. Ricevere (EMPFANGEN)
- ✅ Modal con QR code dell'indirizzo della moneta selezionata (qrcode.react) + copia negli appunti con feedback "Adresse kopiert".
- ✅ (solo BTC con zpub assegnato) Modal zpub: QR + testo dell'extended public key, avviso read-only "Schreibgeschützter öffentlicher Schlüssel. Teilen Sie niemals Ihre privaten Schlüssel."

#### E. Inviare (SENDEN) — stato e commissioni
- ✅ Form: indirizzo destinatario, importo (con controvalore ≈ USD live), email opzionale per ricevuta → schermata di review → conferma.
- ✅ **[CONFERMATO — solo registrazione interna]** La transazione viene registrata **solo in PocketBase** (collection `transactions`: email, amount, recipient, usd, status, owner) + cronologia locale (localStorage). **NON è un broadcast on-chain: nessuna crypto viene realmente trasferita nel sito attuale.**
- ✅ Stato transazione: sempre "Confirmed" al momento della registrazione (nessun ciclo pending→confirmed, nessun hash on-chain, nessun tracking).
- ✅ **Commissioni di rete: nessun calcolo fee** nel sito attuale (né stima né detrazione dall'importo).
- 🔗 **[RICHIESTO per la nuova copia, solo se si vuole invio reale]** Broadcast on-chain con commissioni di rete stimate/reali, stato verificabile e hash transazione — da implementare ex novo nel nuovo account; **non esiste nel sito attuale** e non va descritto come già attivo.

#### F. Cronologia transazioni (Verlauf)
- ✅ Lista transazioni (localStorage + PocketBase) con dettaglio (tipo "Gesendet", status, importo, valore USD, data, destinatario); stato vuoto "Noch keine Transaktionen.".

#### G. Prezzi, grafico e mercato
- ✅ Prezzo live + variazione 24h con catena di fallback (Binance → CoinGecko → CoinCap; USDT fallback finale 1 USD), refresh 30s, indicatore "ping" verde.
- ✅ Grafico prezzo Chart.js (linea con gradiente, verde se 24h ≥ 0 altrimenti rosso), timeframe 1H/1D/7D/30D/1Y, fallback fonti (CoinGecko → Binance klines → CryptoCompare → CoinCap; USDT flat-line), retry breve su errore transient.
- ✅ Fear & Greed Index (api.alternative.me) con gauge SVG circolare colorato.
- ✅ Convertitore valuta ↔ USD a due input sincronizzati (aggiorna al cambio prezzo/moneta).
- ✅ Preisalarm: prezzo target → notifica browser + email quando raggiunto (cooldown 60s).
- ✅ News Bitcoin: lista statica di 4 notizie (ETF inflows, Lightning capacity, long-term holders, mining difficulty).
- ✅ Guida Kraken (modal 9 step con illustrazioni animate, **senza download PDF**) + pulsanti "Anleitung: Bitcoin kaufen" / "Bitcoin kaufen" (link a Kraken).

#### H. Visibilità admin
- ✅ Le transazioni registrate compaiono nella tab "Transaktionen" del dashboard admin (email cliente, importo, destinatario, data, status) con aggiornamento realtime + polling.
- ✅ Le assegnazioni wallet (`client_wallets`: email, nome, indirizzi BTC/ETH/SOL/USDT, zpub) sono gestite dall'admin nella tab "Wallets" (CRUD via modal).

#### I. UI bilingue DE/EN
- ✅ Tutti i testi della Wallet (titoli, pulsanti, modali, errori, stati vuoti, placeholder) in tedesco/inglese via `t(de, en)` — tedesco predefinito, switch DE/EN nell'header persistito in localStorage.

---

## 7. ADMIN (`/admin`) — solo `role = "admin"`

Header con icona ShieldCheck, "delfinitx Dashboard", email admin, pulsante test EmailJS + refresh. Tab:

1. **Ausstehend** (pending): tabella Email/Name/Registriert/Verifiziert/Aktionen → Genehmigen (status approved + approvedAt + email al cliente), Ablehnen, **Löschen** (cancellazione definitiva via hook server-side, conferma, libera email).
2. **Genehmigt**: Details, Deaktivieren (status disabled), Löschen.
3. **Transaktionen**: lista da collection `transactions`.
4. **Dokumente**: review KYC (approva/rifiuta, link ai file caricati).
5. **Wallets**: CRUD assegnazioni `client_wallets` (email, nome, indirizzi BTC/ETH/SOL/USDT, zpub) via modal.
6. **Statistik**: card Registered/Approved/Pending/Transactions.

Aggiornamento realtime (subscribe PocketBase) + polling 3s + refresh on focus. Toast sonner per ogni azione.

---

## 8. EMAILJS (notifiche dal browser)

- Service ID: `service_gs2854d` · Template ID: `template_zg0xugk` · Public Key: `PVZsj-PMME9U0FbEn`
- Destinatario notifiche: `support@delfinitx.com`
- Eventi: nuovo cliente registrato, accesso wallet/PIN, transazione inviata, prezzo raggiunto, test dal pannello admin.
- Libreria EmailJS caricata dinamicamente lato client; errori solo in console, mai bloccanti.

---

## 9. ALTRE FUNZIONALITÀ

- **TickerBar** home: prezzi crypto scorrevoli (animazione marquee CSS).
- **TrendingAssets**, **TradingViewWidget**, **AppDownloadSection**, **StakingSection1-4** (animate, monete 3D flottanti), **WhyChooseEcoCrypto**, **CertificationBadges** (SOC2/ISO27001).
- **InstallPrompt / install-app** (PWA-lite, pagina nascosta).
- **MaintenancePage** con flag `maintenanceMode` (attualmente disattivato).
- **i18n**: `LanguageContext` con `t(de, en)` — tedesco sempre primo argomento; persist in localStorage `delfinitx_lang`; default `de`.

---

## 10. ESCLUSIONI OBBLIGATORIE (non riprodurre)

- ❌ Nessun pulsante/funzione "Anleitung herunterladen" (download PDF guida) — rimosso.
- ❌ Nessun servizio "Deblock".
- ❌ Nessun account o dato di test per Bruno Marra / Sandra Marra.
- ❌ Nessun saldo fisso/simulato nella Wallet: **solo saldi reali on-chain**.
- ❌ `noindex, nofollow` su tutto il sito (mantenere).
- ❌ Nessuna richiesta o esposizione di chiavi private / seed phrase (solo indirizzi pubblici e zpub read-only).

---

## 11. CHECKLIST FINALE PER IL NUOVO BUILDER

- [ ] React + Vite + Tailwind + shadcn/ui, PocketBase abilitato, Express API abilitato
- [ ] Migrazioni: users estesa, client_wallets, transactions, kyc_documents, password_resets + seed admin e cliente tamp
- [ ] Hooks: signup-defaults, verification email brandizzata, approval notification, forgot-password, admin-delete-user
- [ ] Tutte le pagine/route della tabella al punto 3, bilingue DE/EN
- [ ] Wallet completa secondo la **checklist 6.1**: PIN, auto-lock, prezzi live, grafico, QR, send→PocketBase, storia, alarm, F&G, TradingView, guida Kraken (senza PDF)
- [ ] Saldo **on-chain** (catene di fallback del punto 6) — funzionalità 🔗 RICHIESTA per la copia: verificare pubblicamente il saldo sull'indirizzo prima di dichiararlo attivo; mai importi fissi/inventati
- [ ] Inviare: nel sito attuale è solo registrazione PocketBase (status fisso "Confirmed", nessuna fee, nessun broadcast on-chain); l'invio reale on-chain è 🔗 RICHIESTO e va implementato e verificato ex novo
- [ ] Admin dashboard con 6 tab e cancellazione definitiva
- [ ] EmailJS configurato con le chiavi sopra
- [ ] Footer con licenza/capitale/badge, `noindex, nofollow`
