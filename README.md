# agent-config-base

Jedno místo pro pravidla, workflow a skills, které používám ve všech projektech s Claude Code.

## Instalace (jednou na každém počítači)

V Claude Code:

```
/plugin marketplace add pepavlin/agent-config-base
/plugin install core@pavlin
```

Aktualizace se stahují automaticky při startu session. Ručně: `/plugin marketplace update pavlin`.

## Co kde je

| Soubor | K čemu |
| --- | --- |
| `plugins/core/RULES.md` | Globální pravidla. Hook je vloží do každé session. Drž pod 10 000 znaky, nad tím je Claude Code ořízne. |
| `plugins/core/skills/<nazev>/SKILL.md` | Sdílené skills. Načítají se jen když jsou potřeba, takže sem patří delší postupy. |
| `plugins/core/hooks/hooks.json` | Hook, který při startu session vypíše `RULES.md` do kontextu. |
| `.claude-plugin/marketplace.json` | Manifest, díky kterému jde repo přidat jako marketplace. |

## Pravidla pro obsah
- Do `RULES.md` jen to, co platí všude. Projektová specifika patří do `CLAUDE.md` daného projektu.
- Žádné tokeny, hesla ani klíče.
- Do `plugin.json` nepřidávej `version`. Bez ní se verze odvozuje z commitu a každá změna v `main` se projeví sama. S pevnou verzí by se změny nestahovaly, dokud ji ručně nezvýšíš.

## Omezení
Funguje jen v Claude Code. claude.ai ani Claude Desktop pluginy z Claude Code nenačítají; tam je potřeba pravidla vložit do preferencí a skills nahrát zvlášť.
