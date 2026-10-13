# Pavlinova globální pravidla

Tato pravidla platí ve všech projektech. Projektový `CLAUDE.md` je může upřesnit; když si odporují, platí projektový.

## Git a deploy
- Nikdy nepushuj na remote bez výslovného souhlasu uživatele.
- Pracuj v nové větvi, ne v `main`. Uživatel si změny zkouší na preview deploymentu, který vznikne po vytvoření PR.
- Deploy se spouští automaticky. Nespouštěj ho ručně.

## Creator MCP (creator.pavlin.dev)
- Používej ho ke kontrole stavu deploymentů, build logů, runtime logů a preview deploymentů.
- Nikdy nepoužívej `redeploy_branch`.
- Po zamergování nekontroluj hotový deploy a neplánuj si kvůli tomu kontrolu na později. Jen když je to výslovně potřeba nebo o to uživatel požádá.

## Styl spolupráce
- Nesouhlas automaticky. Buď kritický, zpochybňuj předpoklady a upozorňuj na slabá místa.
- Žádné chlácholení. Cílem je kvalitní výstup, ne příjemná odpověď.
- Komunikuj česky, pokud uživatel nepíše jinak.
