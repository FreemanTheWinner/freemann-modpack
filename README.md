# Freemann Modpack

Fichiers téléchargés par le launcher Freemann.

- `pack.mrpack` : le modpack (format Modrinth). Les mods présents sur Modrinth y sont des liens, les autres sont inclus.
- `core_data.bin` : mods du serveur, chiffrés.

## Mettre à jour

Depuis le dossier du launcher :

- Mods (après les avoir changés dans l'instance CurseForge) :
  `node tools/build-pack.js "C:\Users\Justin\curseforge\minecraft\Instances\Serv dih"`
- Mods secrets :
  `node tools/encrypt-secret.js "<mod1.jar>" "<mod2.jar>"` puis copier `secret\core_data.bin` ici.

Ensuite commit + push de ce dépôt. Les launchers récupèrent la nouvelle version au lancement suivant
(quelques minutes de délai possibles, le temps que GitHub rafraîchisse son cache).

## Nouveautés (`news.json`)

Affichées à droite de l'accueil du launcher, la plus récente en premier :

```json
[
  { "tag": "maj", "label": "Mise à jour", "date": "8 nov.", "title": "Nouveaux mods", "body": "Le launcher s'occupe de tout." },
  { "tag": "event", "label": "Event", "date": "15 nov.", "title": "Chasse au trésor", "body": "Samedi 21h au spawn." }
]
```

`tag` : `maj` (vert), `event` (orange) ou `fix` (gris). `label` est le texte de l'étiquette.
Les launchers lisent ce fichier à chaque ouverture. `[]` = pas de nouveautés.

Ne jamais mettre ici un mod secret en `.jar` : seulement le fichier chiffré.
