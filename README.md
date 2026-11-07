# HOMY online store (2014–2016)

Source code of the HOMY online store (homy.su) for Domashniy, a home appliance and electronics shop in Kursk, Russia. I built it alone in about four months and then ran it until 2019.

This is archived code, kept as a portfolio sample. It targets PHP 5 (it uses the removed `mysql_*` functions), so it will not run on a modern PHP version without changes.

Case study: https://tarasov.ca/en/portfolio/homy-online-store

## What it does

- Catalog with nested categories, a brand filter, grid and list views, and sorting by price or rating.
- Product pages with photos, customer reviews and ratings, and similar products.
- Search with suggestions as you type.
- One-page cart and checkout with delivery time slots and a payment choice; one-click buying.
- Customer accounts: registration with email confirmation, login, password recovery, order history.
- Social login with VK, Facebook, Yandex, Twitter, and Google.
- Admin panel: dashboard, orders with statuses and a timeline, product photo upload, price list upload.
- Stock and prices imported from a 1C CSV export, with live progress.
- SMS alerts for new orders (SMS.ru).
- Telegram bot that links a customer's Telegram account to their store account with a PIN sent by SMS.
- SEO: readable URLs, Open Graph tags, a sitemap generator, robots rules, and a Yandex.Market product feed.

## Structure

- `index.php` – entry point; `class/core` – autoloader, router, and config.
- `*.php` in the root – page modules (`category`, `product`, `cart`, `checkout`, `my`, `cc` for the admin panel, `bot` for Telegram).
- `class/` – application classes (database, auth, orders, SMS, mail, Telegram, AJAX handlers).
- `templates/` – templates for the custom `{placeholder}` template engine.
- `api/` – sitemap generator and the Yandex.Market feed.

## Configuration

All keys and passwords were removed. Database settings live in `class/core/config/cfg.class.php`; the other settings (API keys, SMS, social login, Telegram) were loaded from a `config` table in the database, which is not included.
