# agent-config-base

Jedno místo pro pravidla, workflow a skills, které používám ve všech projektech.

## Instalace (jednou, pro celý účet)

Přidej repo jako marketplace na claude.ai, ne přes `/plugin` v terminálu:

1. Otevři [claude.ai/customize/plugins](https://claude.ai/customize/plugins).
2. **Add > Add marketplace** a zadej `pepavlin/agent-config-base`. U privátního repa dialog vyzve k připojení GitHubu a instalaci Claude GitHub App.
3. Zapni plugin **core** a u marketplace zapni **Sync automatically**.

Plugin je pak uložený na účtu a dostane se všude, kde jsi přihlášený:

| Kde | Co se načte |
| --- | --- |
| Claude Code v terminálu a desktopové appce | Vše (hook s pravidly, skills). Stáhne se při startu session. |
| Claude Code na webu (claude.ai/code) | Vše, stejně jako terminál. |
| Cowork | Vše. |
| Chat na claude.ai | Jen skills. Hooky chat ignoruje, takže `RULES.md` se tam nenačte. Pro chat platí preference v nastavení účtu. |

Ověření: v nové session se zeptej „Which Creator MCP tool must you never use?“. Pokud odpoví `redeploy_branch`, pravidla se načetla.

Neinstaluj plugin zároveň přes `/plugin` v terminálu. Měl bys pak na jednom stroji dvě kopie a lokální by přebila tu z účtu, včetně toho, že by se neaktualizovala.

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
- Do `plugin.json` nepřidávej `version`. Bez ní se verze odvozuje z commitu a změny se šíří samy. S pevnou verzí by se nestahovaly, dokud ji ručně nezvýšíš.
- Creator MCP sem nepatří. Je v samostatném pluginu `creator` na claude.ai; druhá kopie by vytvořila duplicitní nástroje.
