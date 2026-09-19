<div align="center" dir="rtl">

<img src="./media/radpanel-light.png" alt="RadPanel" width="320">

### رادپنل (RadPanel)

**پنل کنترل وب مدرن و سبک برای Xray-core — با یک دستور نصب کن، از هر دستگاهی مدیریت کن.**

[![Release](https://img.shields.io/github/v/release/radinmovafaghh-coder/radpanel?style=flat-square&color=7c3aed)](https://github.com/radinmovafaghh-coder/radpanel/releases)
[![Build](https://img.shields.io/github/actions/workflow/status/radinmovafaghh-coder/radpanel/release.yml?style=flat-square&label=build)](https://github.com/radinmovafaghh-coder/radpanel/actions)
[![License](https://img.shields.io/badge/license-GPL--3.0-7c3aed?style=flat-square)](https://www.gnu.org/licenses/gpl-3.0.en.html)
[![Downloads](https://img.shields.io/github/downloads/radinmovafaghh-coder/radpanel/total?style=flat-square&color=7c3aed)](https://github.com/radinmovafaghh-coder/radpanel/releases)

</div>

---

## رادپنل چیست؟

رادپنل یک پنل خودمیزبان برای [Xray-core](https://github.com/XTLS/Xray-core) است. با یک رابط وب تمیز
می‌توانی اینباند بسازی، به کلاینت‌ها کانفیگ بدهی، ترافیک را ببینی و چند سرور را از یک داشبورد مدیریت کنی —
بدون دست‌کاری دستی فایل JSON.

رادپنل یک **فورک GPL-3.0 از پروژه‌ی [3x-ui](https://github.com/MHSanaei/3x-ui)** نوشته‌ی MHSanaei است.
مجوز و کپی‌رایت اصلی حفظ شده (به فایل [NOTICE](NOTICE) نگاه کن)؛ چیزی که تغییر کرده برند، تم و مقصد نصب است.

> [!IMPORTANT]
> فقط برای استفاده‌ی شخصی. لطفاً از آن برای اهداف غیرقانونی یا در محیط تولید استفاده نکنید.

## چرا رادپنل؟

- **نصب با یک دستور.** `bash <(curl -Ls .../install.sh)` و تمام.
- **سبک و تمیز.** رابطی متمرکز که سر راهت نمی‌ماند.
- **همه‌جا کار می‌کند.** لینوکس (amd64، arm64، armv7، armv6، armv5، 386، s390x) و ویندوز.
- **۱۳ زبان**، تم روشن / تیره / فوق‌تیره.
- **به‌صورت پیش‌فرض SQLite**، و PostgreSQL در صورت نیاز.
- **کاملاً باز.** GPL-3.0، سورس همراه، بدون هیچ تلمتری.

## ویژگی‌ها

- **اینباندهای چندپروتکلی** — VLESS، VMess، Trojan، Shadowsocks، WireGuard، AmneziaWG، TUIC v5، Hysteria2، MTProto، HTTP، SOCKS (Mixed)، Dokodemo-door / Tunnel و TUN.
- **ترنسپورت‌ها و امنیت مدرن** — TCP (Raw)، mKCP، WebSocket، gRPC، HTTPUpgrade و XHTTP، ایمن‌شده با TLS، XTLS و REALITY.
- **‏AmneziaWG داخلی** — نسخه‌ی مقاوم در برابر DPI از WireGuard مستقیماً درون پنل و روی یک پشته‌ی شبکه‌ی فضای کاربر اجرا می‌شود؛ بدون ماژول کرنل، DKMS یا بسته‌های اضافی.
- **‏TUIC v5 داخلی** — پراکسی با کارایی بالا مبتنی بر QUIC با اندازه‌گیری بومی ترافیک رله UDP، دست‌دادن‌های 0-RTT و کنترل ازدحام BBR.
- **پراکسی‌های MTProto** — سکرت‌های FakeTLS، ad-tag و سهمیه‌ها به‌ازای هر کلاینت، که به‌صورت زنده و بدون قطع اتصال‌های موجود اعمال می‌شوند.
- **فال‌بک (Fallback)** — ارائه‌ی چند پروتکل روی یک پورت واحد (مثلاً VLESS و Trojan روی پورت 443) با استفاده از قابلیت fallback در Xray.
- **مدیریت به‌ازای هر کلاینت** — سهمیه‌ی ترافیک، تاریخ انقضا، محدودیت IP با امکان استثنا کردن آدرس‌های مورد اعتماد، محدودیت دستگاه (HWID)، چرخه‌های تمدید زمان‌بندی‌شده، وضعیت آنلاینِ زنده و لینک‌های اشتراک‌گذاری، کدهای QR و سابسکریپشن‌ها با یک کلیک.
- **آمار ترافیک** — به‌ازای هر اینباند، هر کلاینت و هر اوتباند، همراه با کنترل بازنشانی (reset).
- **پشتیبانی از چند نود** — مدیریت و مقیاس‌دهی روی چندین سرور از یک پنل واحد، از جمله کلون‌کردن اینباندها روی نودهای دیگر.
- **اوتباند و مسیریابی** — WARP، NordVPN، PIA، قوانین مسیریابی سفارشی، متعادل‌کننده‌های بار (load balancer) با فال‌بک بین متعادل‌کننده‌ها و زنجیره‌کردن پراکسی اوتباند. دسته‌بندی‌های geosite و geoip همراه‌شده مستقیماً از ویرایشگر قوانین قابل مرور هستند.
- **سرور سابسکریپشن داخلی** — خروجی raw، JSON و Clash که بر پایه‌ی User-Agent کلاینت به‌صورت خودکار انتخاب می‌شود، به‌همراه [قالب‌های صفحه‌ی سفارشی](docs/custom-subscription-templates.md).
- **ربات‌های تلگرام و دیسکورد** برای نظارت و مدیریت از راه دور.
- **‏RESTful API** با توکن‌های محدودشده (scoped) و دارای انقضای اختیاری، به‌همراه مرجع API درون‌پنل.
- **پنل قابل نصب (PWA)** — RadPanel را به دسکتاپ یا صفحه‌ی اصلی گوشی خود سنجاق کنید.
- **ذخیره‌سازی منعطف** — SQLite (پیش‌فرض) یا PostgreSQL.
- **‏۱۳ زبان رابط کاربری** با تم‌های تیره و روشن.
- **یکپارچگی با Fail2ban** برای اعمال محدودیت IP به‌ازای هر کلاینت.

## اسکرین‌شات‌ها

<details>
<summary>برای باز شدن کلیک کنید</summary>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/01-overview-dark.png">
  <img alt="Overview" src="./media/01-overview-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/02-add-inbound-dark.png">
  <img alt="Inbounds" src="./media/02-add-inbound-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/03-add-client-dark.png">
  <img alt="Add client" src="./media/03-add-client-light.png">
</picture>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./media/05-add-nodes-dark.png">
  <img alt="Configs" src="./media/05-add-nodes-light.png">
</picture>

</details>

## شروع سریع

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh)
```

برای نصب یک نسخه‌ی مشخص، تگ آن را در انتها اضافه کنید (مثلاً `v3.7.0`):

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh) v3.7.0
```

برای نصب نسخه‌ی غلتانِ **dev** (آخرین پیش‌انتشار به‌ازای هر کامیت از شاخه‌ی `main`، نه یک انتشار پایدار)، مقدار `dev-latest` را پاس دهید:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/radinmovafaghh-coder/radpanel/master/install.sh) dev-latest
```

در حین نصب، یک نام کاربری، رمز عبور و مسیر دسترسی تصادفی تولید می‌شود. پس از نصب، دستور `radpanel` را اجرا کنید تا منوی مدیریت باز شود؛ در آنجا می‌توانید سرویس را شروع/متوقف کنید، اطلاعات ورود خود را ببینید یا بازنشانی کنید، گواهی‌های SSL را مدیریت کنید و کارهای دیگری انجام دهید.

هر فایل انتشار به‌همراه یک جمع کنترلی `.sha256` در کنارش منتشر می‌شود. هم `install.sh` و هم به‌روزرسان، آرشیو را در برابر آن جمع کنترلی بررسی می‌کنند و در صورت عدم تطابق متوقف می‌شوند.

مستندات پنل در پوشه‌ی [docs/](docs/) همین مخزن قرار دارد. مستندات پروژه‌ی اصلی در docs.sanaei.dev هم عمدتاً کاربرد دارند، چون هسته‌ی رادپنل با آن مشترک است.

### نصب بدون نظارت

نصب‌کننده به‌صورت **غیرتعاملی** نیز برای cloud-init اجرا می‌شود.
‏`XUI_NONINTERACTIVE=1` را تنظیم کنید (یا بدون TTY از طریق pipe اجرا کنید) تا نصب به‌صورت سرتاسری و بدون
هیچ پرسشی انجام شود، اطلاعات ورود تصادفی تولید کرده و آن‌ها را در
`/etc/radpanel/install-result.env` می‌نویسد. برای موارد زیر به [`deploy/`](deploy/) مراجعه کنید:

- [user-data مربوط به Cloud-init](deploy/cloud-init/) — نصب بدون نظارت روی هر ابری (Hetzner/AWS/DO/Vultr/GCP/Azure/Oracle)
- [یادداشت‌های Hetzner Cloud](deploy/marketplace/hetzner/) — استقرار مبتنی بر cloud-init روی Hetzner

## پلتفرم‌های پشتیبانی‌شده

**سیستم‌عامل‌ها:** Ubuntu، Debian، Armbian، Fedora، CentOS، RHEL، AlmaLinux، Rocky Linux، Oracle Linux، Amazon Linux، Virtuozzo، Arch، Manjaro، Parch، openSUSE (Tumbleweed / Leap)، Alpine و Windows.

**معماری‌ها:** `amd64` · `386` · `arm64` (aarch64) · `armv7` · `armv6` · `armv5` · `s390x`.

## گزینه‌های پایگاه‌داده

‏RadPanel از دو بک‌اند پشتیبانی می‌کند که در حین نصب انتخاب می‌شوند:

- **SQLite** (پیش‌فرض) — یک فایل واحد در مسیر `/etc/radpanel/radpanel.db`. بدون نیاز به تنظیمات، ایده‌آل برای استقرارهای کوچک و متوسط.
- **PostgreSQL** — برای تعداد کلاینت بالا یا راه‌اندازی‌های چندنودی توصیه می‌شود. نصب‌کننده می‌تواند PostgreSQL را به‌صورت محلی برایتان نصب کند، یا یک DSN به یک سرور موجود را بپذیرد.

در زمان اجرا، بک‌اند از طریق متغیرهای محیطی انتخاب می‌شود (نصب‌کننده این موارد را برای شما در `/etc/default/radpanel` می‌نویسد):

```
XUI_DB_TYPE=postgres
XUI_DB_DSN=postgres://xui:password@127.0.0.1:5432/xui?sslmode=disable
```

### انتقال یک نصب موجود SQLite به PostgreSQL

```bash
radpanel migrate-db --dsn "postgres://xui:password@127.0.0.1:5432/xui?sslmode=disable"
# سپس XUI_DB_TYPE و XUI_DB_DSN را در /etc/default/radpanel تنظیم کرده و ری‌استارت کنید:
systemctl restart radpanel
```

فایل اصلی SQLite دست‌نخورده باقی می‌ماند؛ پس از اطمینان از صحت بک‌اند جدید، آن را به‌صورت دستی حذف کنید.

### Docker

دستور پیش‌فرض `docker compose up -d` همچنان از SQLite استفاده می‌کند. برای اجرا با سرویس PostgreSQL همراه، دو خط متغیر محیطی `XUI_DB_*` را در `docker-compose.yml` از حالت کامنت خارج کنید و با پروفایل زیر اجرا کنید:

```bash
docker compose --profile postgres up -d
```

این ایمیج، Fail2ban را (که به‌صورت پیش‌فرض فعال است) برای اعمال **محدودیت‌های IP** به‌ازای هر کلاینت همراه دارد. ‏Fail2ban متخلفان را با `iptables` مسدود می‌کند که به مجوز `NET_ADMIN` نیاز دارد. فایل `docker-compose.yml` این مجوز را از قبل از طریق `cap_add` می‌دهد؛ اگر به‌جای آن کانتینر را با `docker run` اجرا می‌کنید، خودتان مجوزها را اضافه کنید، در غیر این صورت مسدودسازی‌ها فقط ثبت می‌شوند اما هرگز اعمال نمی‌شوند:

```bash
docker run -d --cap-add=NET_ADMIN --cap-add=NET_RAW ... ghcr.io/radinmovafaghh-coder/radpanel
```

## متغیرهای محیطی

| متغیر | توضیحات | پیش‌فرض |
| --- | --- | --- |
| `XUI_DB_TYPE` | بک‌اند پایگاه‌داده: `sqlite` یا `postgres` | `sqlite` |
| `XUI_DB_DSN` | رشته‌ی اتصال PostgreSQL (وقتی `XUI_DB_TYPE=postgres`) | — |
| `RADPANEL_DB_FOLDER` | پوشه‌ی فایل پایگاه‌داده‌ی SQLite | `/etc/radpanel` |
| `XUI_DB_MAX_OPEN_CONNS` | حداکثر اتصالات باز (استخر PostgreSQL) | — |
| `XUI_DB_MAX_IDLE_CONNS` | حداکثر اتصالات بی‌کار (استخر PostgreSQL) | — |
| `XUI_INIT_WEB_BASE_PATH` | مسیر URI اولیه برای پنل وب | `/` |
| `XUI_ENABLE_FAIL2BAN` | فعال‌سازی اعمال محدودیت IP مبتنی بر Fail2ban | `true` |
| `XUI_LOG_LEVEL` | سطح گزارش‌گیری (`debug`، `info`، `warning`، `error`) | `info` |
| `XUI_DEBUG` | فعال‌سازی حالت دیباگ | `false` |
| `XUI_TUNNEL_HEALTH_MONITOR` | فعال‌سازی پایشگر سلامت تونل (یک URL را پروب می‌کند و پس از خطاهای مکرر، xray را ری‌استارت می‌کند؛ یک ری‌استارت همه‌ی کلاینت‌ها را قطع می‌کند) | `false` |
| `XUI_TUNNEL_HEALTH_PROXY` | پراکسی‌ای که پروب از طریق آن ارسال می‌شود؛ آن را به یک اینباند محلی xray اشاره دهید تا پروب خودِ تونل را آزمایش کند (مثلاً `socks5://127.0.0.1:1080`). خالی بودن یعنی پروب فقط اتصال به هاست را بررسی می‌کند | — |
| `XUI_TUNNEL_HEALTH_URL` | URL ای که برای سلامت تونل پروب می‌شود | `https://www.cloudflare.com/cdn-cgi/trace` |
| `XUI_TUNNEL_HEALTH_INTERVAL` | فاصله‌ی زمانی بین پروب‌ها | `30s` |
| `XUI_TUNNEL_HEALTH_TIMEOUT` | مهلت زمانی هر پروب | `10s` |
| `XUI_TUNNEL_HEALTH_FAILURES` | تعداد خطاهای متوالی پیش از آن‌که یک ری‌استارت فعال شود | `3` |
| `XUI_TUNNEL_HEALTH_COOLDOWN` | حداقل تأخیر بین ری‌استارت‌های متوالی | `5m` |
| `NODE_TOKEN_ENCRYPTION` | رمزگذاری توکن‌های API نود در حالت سکون: `off`، `migration` یا `required` (بدون پیشوند `XUI_`) | `off` |
| `XUI_NODE_TOKEN_KEY_FILE` | حلقه‌کلید JSON (با دسترسی `0600`) شامل شناسه‌ی کلید فعال و کلیدهای ۳۲ بایتی base64 | `/etc/radpanel/node_token_key.json` |
| `XUI_NODE_TOKEN_KEY` | یک کلید ۳۲ بایتی base64 که تنها در صورت بارگذاری‌نشدن فایل کلید استفاده می‌شود | — |

فهرست کامل در فایل [.env.example](.env.example) موجود است.

## زبان‌های پشتیبانی‌شده

رابط کاربری پنل به ۱۳ زبان در دسترس است:

English · فارسی · العربية · 中文（简体） · 中文（繁體） · Español · Русский · Українська · Türkçe · Tiếng Việt · 日本語 · Bahasa Indonesia · Português (Brasil)

## مشارکت

از مشارکت‌ها استقبال می‌شود. لطفاً پیش از باز کردن issue یا pull request، [راهنمای مشارکت](/CONTRIBUTING.md) را مطالعه کنید.

## تشکر ویژه از (پروژه‌ی اصلی)

- [alireza0](https://github.com/alireza0/)

## قدردانی

- [Iran v2ray rules](https://github.com/chocolate4u/Iran-v2ray-rules) (مجوز: **GPL-3.0**): _قوانین مسیریابی بهبود یافته v2ray/xray و v2ray/xray-clients با دامنه‌های ایرانی داخلی و تمرکز بر امنیت و مسدود کردن تبلیغات._
- [Russia v2ray rules](https://github.com/runetfreedom/russia-v2ray-rules-dat) (مجوز: **GPL-3.0**): _این مخزن شامل قوانین مسیریابی V2Ray به‌روزرسانی شده خودکار بر اساس داده‌های دامنه‌ها و آدرس‌های مسدود شده در روسیه است._

## ابزارهای جامعه

ابزارها و یکپارچه‌سازی‌هایی که توسط جامعه پیرامون radpanel ساخته شده‌اند.

- [terraform-provider-radpanel](https://github.com/batonogov/terraform-provider-threexui) (مجوز: **MIT**): _مدیریت اینباندها، کلاینت‌ها، تنظیمات پنل و پیکربندی Xray به‌صورت کد با Terraform / OpenTofu._
- [RadPanel Manager](https://github.com/yukh975/RadPanel-Manager) (مجوز: **MIT**): _کلاینت بومی اندروید برای radpanel — داشبورد، اینباندها، کلاینت‌ها با اشتراک‌گذاری QR، نودها و مدیریت چند پنل. در F-Droid در دسترس است._

## اعتبار

رادپنل فورکی از [3x-ui](https://github.com/MHSanaei/3x-ui) است و بدون آن وجود نداشت.
تمام اعتبار پنل اصلی از آن **MHSanaei** و مشارکت‌کنندگان 3x-ui است.
اگر می‌خواهی از پروژه‌ی اصلی حمایت کنی، به آن ستاره بده و از کانال‌های خودش استفاده کن.

## حمایت از این فورک

سؤال، باگ یا ایده درباره‌ی خود رادپنل: یک [ایشو](https://github.com/radinmovafaghh-coder/radpanel/issues) باز کن.

## تاریخچه ستاره‌ها

<a href="https://www.star-history.com/?repos=mhsanaei%2Fradpanel&type=date&legend=top-left">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&theme=dark&legend=top-left" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&legend=top-left" />
   <img alt="Star History Chart" src="https://api.star-history.com/chart?repos=radinmovafaghh-coder/radpanel&type=date&legend=top-left" />
 </picture>
</a>

<p align="center">
 <a href="https://www.star-history.com/radinmovafaghh-coder/radpanel">
  <picture><source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank&theme=dark" /><source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank" /><img alt="Star History Rank" src="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=rank" /></picture> <picture><source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending&theme=dark" /><source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending" /><img alt="GitHub Trending Repository of the Day" src="https://api.star-history.com/badge?repo=radinmovafaghh-coder/radpanel&type=trending" /></picture>
 </a>
</p>
