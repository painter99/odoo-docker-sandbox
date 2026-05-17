# Odoo Docker Sandbox 🏭💻

Tento repozitář obsahuje mé vývojové a testovací prostředí pro učení Odoo ERP pomocí Dockeru. Slouží jako praktický "můstek" mezi mou dlouholetou praxí v průmyslové výrobě (lakovna) a světem podnikového softwaru.

## 📂 Struktura projektu
- `docker-compose.yml` – orchestrace služeb (Odoo + PostgreSQL)
- `config/odoo.conf` – hlavní konfigurační soubor Odoo
- `custom_addons/` – adresář pro vývoj mých vlastních Python modulů a instalaci třetích stran
- `.env.example` – šablona pro bezpečné nastavení proměnných prostředí (hesla, porty)
- `.gitignore` – ochrana před nechtěným nahráním databázových volumů a citlivých dat

## 🚀 Jak to spustit
1. Zkopírujte soubor s prostředím: `cp .env.example .env` (a doplňte hesla)
2. Spusťte Docker kontejnery: `docker compose up -d`
3. Otevřete v prohlížeči: `http://localhost:8069`

## 🔄 Můj denní vývojový cyklus (Odoo Best Practices)
Vývoj ERP není jen o psaní kódu, ale o bezpečné práci s daty. Proto při učení striktně dodržuji tento "bezpečný workflow":

1. **Záloha produkce (Backup):** Ranní vytvoření dumpu hlavní databáze.
2. **Klonování (Staging/Dev DB):** Vytvoření testovací kopie databáze pro vývoj (nikdy nepracuji na živých datech).
3. **Vývoj a úpravy:** Tvorba modulů v `custom_addons`, nastavování procesů a úprava UI na testovací databázi.
4. **UAT Testování:** Ověření "Happy paths" – projde zakázka od vytvoření až po fakturu bez chyby?
5. **Git Commit & Záloha:** Uložení funkčního kódu do repozitáře a případná záloha úspěšného stavu DB.
6. **Deployment:** V případě 100% úspěšnosti testů nasazení (Update) modulu na hlavní produkční databázi.

## 🎯 Cíle tohoto projektu
- **UAT & Procesy:** Pochopit a nasimulovat logiku výroby, kusovníků (BOM), správu skladů a pracovních příkazů z pohledu uživatele.
- **Backend & Architektura:** Prozkoumat databázi, ORM vrstvu a vývojářský mód (Developer Mode).
- **Python Vývoj:** Aplikovat znalosti z *Odoo 19 Development Cookbook* a napsat vlastní custom moduly pro fiktivní výrobní procesy.

## 📌 Milníky (Logbook)
- [x] Úspěšné nasazení Odoo a PostgreSQL přes Docker na Pop!_OS
- [x] Základní konfigurace `docker-compose` a vytvoření testovací DB
- [ ] Zvládnutí Database Manageru (klonování a zálohy DB)
- [ ] Instalace a UAT testování modulů Výroba a Sklady
- [ ] Vytvoření prvního vlastního modulu v `custom_addons`

> ⚠️ **Poznámka:** Toto prostředí není určeno pro produkční nasazení. Jedná se o osobní studijní laboratoř a simulátor reálných IT procesů.
