# InHive — Windows

[![Latest release](https://img.shields.io/github/v/release/TwilgateLabs/inhive-windows?sort=semver&label=latest)](https://github.com/TwilgateLabs/inhive-windows/releases/latest)
[![Windows](https://img.shields.io/badge/Windows-10%20(1809%2B)%20%2F%2011-blue)](#)
[![Arch](https://img.shields.io/badge/arch-x86__64-orange)](#)

InHive — кроссплатформенный VPN-клиент. Этот репозиторий — публичная точка для **Windows-сборок** (portable ZIP + опционально installer).

## 📥 Скачать

→ [**Latest release**](https://github.com/TwilgateLabs/inhive-windows/releases/latest) — `inhive-windows-x.y.z-x64.zip` (portable) + опциональный `.exe` installer (если приложен в релизе). SHA-256 для каждого артефакта в release notes.

## 🚀 Установка (portable ZIP)

1. Скачай `inhive-windows-x.y.z-x64.zip` со страницы релиза.
2. Распакуй архив в любую папку (например `C:\Apps\InHive\`).
3. Запусти `inhive.exe`.
4. При первом старте Windows покажет UAC-prompt для установки TUN-драйвера — нажми **Yes**.

**SmartScreen warning** на первом запуске — это нормально для подписанных EXE без массового install base. Нажми **More info → Run anyway**. После накопления репутации с тем же signing cert SmartScreen перестанет ругаться.

## 📋 Требования

- Windows 10 (build 1809) или новее, либо Windows 11.
- Архитектура **x86_64** (Intel/AMD). ARM64 пока не сборка.
- Свободно ~150 МБ диска.

## 🔐 Безопасность

Каждый релиз подписан Authenticode-сертификатом организации `twilgate`. Проверь подпись:

```powershell
Get-AuthenticodeSignature inhive.exe
```

Status должен быть `Valid`. SHA-256 каждого артефакта публикуется рядом с бинарём в release notes:

```powershell
Get-FileHash inhive-windows-x.y.z-x64.zip -Algorithm SHA256
```

Нашёл security issue? **Не открывай публичный issue.** Пиши в [@InHive_support_bot](https://t.me/InHive_support_bot) с темой `SECURITY` — coordinated disclosure, 90-дневный embargo.

## 🔗 Связанные репозитории

- [twilgate/inhive-app](https://github.com/twilgate/inhive-app) — Flutter-приложение (private; Windows-код в `windows/`)
- [TwilgateLabs/inhive-core](https://github.com/TwilgateLabs/inhive-core) — Go-ядро (sing-box 1.13 fork; сборка `inhive-core.dll` через `go build`)
- [twilgate/inhive-web](https://github.com/twilgate/inhive-web) — Web (private; `inhive.ru`)

## 📜 Лицензия

Этот mirror-repo не содержит исходного кода — только release notes и подписанные бинарные артефакты. Исходники Windows в [twilgate/inhive-app](https://github.com/twilgate/inhive-app) (private). Go-ядро — Apache 2.0 (upstream sing-box + наши патчи), см. [TwilgateLabs/inhive-core](https://github.com/TwilgateLabs/inhive-core/blob/main/LICENSE).
