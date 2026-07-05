# 🚀 Goida26 Clash Meta Subscription

**Автоматическая, самообновляемая подписка** для Clash Meta (mihomo) на основе **Goida 26**.  
Все серверы из исходного списка — без потерь, каждый час.

---

### 📊 Текущее состояние

<!-- PROXY_COUNT_START -->
🔄 **Сейчас в подписке:** 0 серверов  
🕒 **Последнее обновление:** никогда
<!-- PROXY_COUNT_END -->

---

## ⚡ Быстрый старт

Добавь эту ссылку в своё приложение: 


После обновления появятся три группы:

| Группа | Тип | Описание |
|--------|-----|----------|
| 🚀 **Auto-Select** | url-test | Самый быстрый сервер из всех |
| 🌍 **Global** | select | Ручной выбор любого сервера |
| 🛑 **Direct** | select | Напрямую, без прокси |

---

## 📱 Поддерживаемые приложения

Подписка работает **только** с клиентами на ядре **Clash Meta (mihomo)**.

### Android
- [**Karing**](https://play.google.com/store/apps/details?id=com.karing.android) – Google Play  
  `https://play.google.com/store/apps/details?id=com.karing.android`
- [**Clash Mi**](https://github.com/MetaCubeX/ClashMi/releases) – скачать APK с GitHub  
  `https://github.com/MetaCubeX/ClashMi/releases`

### iOS
- [**Karing**](https://apps.apple.com/app/karing/id6470924433) – App Store  
  `https://apps.apple.com/app/karing/id6470924433`
- [**Stash**](https://apps.apple.com/app/stash/id1596063349) – App Store (поддерживает Clash Meta)  
  `https://apps.apple.com/app/stash/id1596063349`
- [**Shadowrocket**](https://apps.apple.com/app/shadowrocket/id932747118) – только с поддержкой Meta‑правил (требуется версия 2.2.29+)

### Windows / macOS / Linux
- [**Clash Verge**](https://github.com/clash-verge-rev/clash-verge-rev/releases)
- [**Mihomo Party**](https://github.com/mihomo-party-org/mihomo-party/releases)

> ❗ FLClashX, старые версии Clash for Windows/Android (Premium‑ядро) **не поддерживаются** — они не умеют работать с VLESS, Reality, Hysteria.

---

## 🔄 Как работает автообновление

- **Каждый час** GitHub Actions скачивает исходную подписку, извлекает **все** серверы и сохраняет их в `proxies.yaml`.
- Конфиг (`config.yaml`) ссылается на этот файл через `proxy-provider`, поэтому клиент всегда получает актуальный список.
- Вручную можно запустить обновление: **Actions → Update proxies.yaml hourly → Run workflow**.
- Количество серверов и время последней синхронизации автоматически отображаются в этом README (секция вверху).

---

## 🛠 Если серверы не отображаются

1. Зайди в [Actions](../../actions) и убедись, что последний запуск зелёный. Если нет – запусти вручную.
2. В клиенте **полностью удали старую подписку** и добавь заново (кеш иногда мешает).
3. Проверь, что используешь приложение с ядром **Clash Meta** (Karing, Clash Mi, Stash и т.д.).

---

## 📁 Структура репозитория

- `config.yaml` – основной конфиг подписки.
- `proxies.yaml` – автоматически обновляемый список всех серверов.
- `.github/workflows/update-sub.yml` – workflow для ежечасного обновления.
- `README.md` – этот файл (с живым счётчиком серверов).

---

## 🧑‍💻 Для разработчиков

Исходная подписка задаётся через секрет `SOURCE_URL` в настройках репозитория.  
Workflow использует Python‑скрипт, который умеет парсить все современные протоколы (VLESS, VMess, Trojan, Shadowsocks, Hysteria, TUIC).  
При необходимости можно изменить расписание (`cron`) или правила маршрутизации в `config.yaml`.

---

**Автор:** [crolankawasaki](https://github.com/crolankawasaki)  
**Лицензия:** MIT
