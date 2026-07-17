# LEGAL-TODO — Le 100 P' (SARL CABLE 44), bar à bières

> **Ne pas mettre en ligne avant d'avoir traité la section 1.**
> État au 17 juillet 2026. Aucune donnée n'a été inventée : tout ce qui n'a pas pu être
> vérifié à une source est marqué `[à fournir]` et apparaît **en surbrillance rose sur le
> site lui-même**, exprès — pour qu'un trou se voie au lieu de se combler avec une
> supposition.

---

## 1. Bloquant avant la mise en ligne

### 1.1 Identité de l'éditeur (`mentions-legales.html`)

| Donnée | État |
|---|---|
| Capital social | **manquant** — obligatoire pour une SARL, ne figure dans aucun registre public |
| RCS | **à confirmer** — « RCS Nantes 888 913 753 » est la forme attendue (greffe probable : Nantes), non vérifiée à une source |
| Directeur de la publication | **manquant** — la société a **deux gérants** (Sylvain Averty, Guy Rapaille) : lequel des deux assume la fonction ? |
| E-mail de contact | **à confirmer** — voir § 1.2 |
| Licence de débit de boissons | **manquante** — type (licence III / IV) et numéro, section « Vente d'alcool » |
| Crédit photo | **manquant** — voir § 1.5 |

Le téléphone (**09 82 20 44 87**) est repris du site actuel : il est déjà renseigné partout.

### 1.2 L'e-mail `100pnantes@gmail.com`

Cette adresse **est déjà exposée publiquement** dans `index.html` : en clair dans la section
Infos pratiques, dans le `mailto:` du bouton « privatisation », dans l'action du formulaire
newsletter et dans le JSON-LD. Elle a donc été reprise comme e-mail de contact dans les deux
pages légales — ce n'est pas une invention, c'est une reprise.

**À confirmer malgré tout** : est-ce bien l'adresse que la maison veut voir figurer dans ses
mentions légales, ou existe-t-il une adresse dédiée ? Une boîte Gmail est acceptable
légalement, mais elle implique que la correspondance est stockée chez Google — c'est écrit
noir sur blanc dans `confidentialite.html`, section « Si vous nous écrivez ».

### 1.3 Hébergeur (article 6 III-1 LCEN — obligatoire)

Nom, adresse, téléphone et site de l'hébergeur. **Les quatre champs sont vides** dans
`mentions-legales.html`, et la durée de conservation des journaux est vide dans
`confidentialite.html`.

> **Ce qui a été retiré exprès.** L'ancien gabarit annonçait « Vercel Inc., 440 N Barranca
> Ave #4133, Covina, CA 91723, USA » comme hébergeur. **Cette information n'a été vérifiée
> nulle part** : c'était un exemple laissé dans un modèle, pas un fait. Elle a été remplacée
> par `[à fournir]`. Publier une fausse identité d'hébergeur est précisément ce que
> l'article 6 LCEN interdit.

Une fois l'hébergeur retenu, vérifier s'il implique un **transfert hors UE** (section
correspondante de `confidentialite.html`).

### 1.4 Vérifier avant publication

```bash
grep -rn "à fournir\|à confirmer" *.html    # ne doit plus rien renvoyer
```

### 1.5 Photographies

**Aucun crédit photo ne figure nulle part sur le site** — ni en pied de page, ni dans le
gabarit légal, qui se contentait d'un `[à préciser]`. L'auteur des images n'a pas pu être
établi, donc `[à fournir]` dans `mentions-legales.html`.

À documenter : auteur, étendue des droits cédés (support, durée, territoire), et
autorisation au titre du droit à l'image pour les personnes reconnaissables (clients,
équipe, brasseurs).

> Le dossier `assets/images/maq/` (« maquette ») contient l'essentiel des visuels utilisés.
> À confirmer que ce sont bien les photos définitives de l'établissement et non des images
> de calage.

---

## 2. Ce qui a été vérifié (et n'est donc pas à redemander)

Relevé le **17 juillet 2026** au registre national des entreprises via l'API publique
`recherche-entreprises.api.gouv.fr` :

- Dénomination sociale : **CABLE 44** — l'enseigne **Le 100 P'** n'est pas la raison sociale
- Forme : **SARL** (code INSEE 5499 — société à responsabilité limitée)
- Siège : **3 rue de l'Échelle, 44000 Nantes** — **identique à l'adresse du bar**, donc pas
  de distinction siège / établissement à faire
- SIREN : **888 913 753** · SIRET siège : **888 913 753 00024**
- TVA : **FR05888913753**
- APE : **56.30Z — Débits de boissons** (cohérent avec l'activité affichée)
- Immatriculation : **4 septembre 2020**
- Gérants : **Sylvain Averty**, **Guy Rapaille**
- État administratif : **actif**

> **Les gérants devinés par l'ancien gabarit sont les bons.** Le modèle proposait
> « [Nom du gérant — ex. Sylvain Averty / Guy Rapaille] » : le registre **confirme** ces deux
> noms. Ils sont donc désormais affirmés comme gérants. En revanche, savoir **lequel des deux**
> est directeur de la publication ne se déduit d'aucun registre — ce champ reste ouvert.

---

## 3. Pages légales : ce qui a été créé, et ce qui ne l'a pas été

### Créées / refaites

| Page | Pourquoi |
|---|---|
| `mentions-legales.html` | **Refaite intégralement.** Existait, mais c'était un gabarit à trous entre crochets (`[raison sociale exacte]`, `[montant] €`, `[n° SIRET]`…), dans une DA étrangère au site — voir § 5. |
| `confidentialite.html` | **Créée.** N'existait pas : le pied de page pointait « Politique de confidentialité » vers `mentions-legales.html`. Contient la section cookies (ancre `#cookies`). |

### Volontairement non créées

| Page | Pourquoi pas |
|---|---|
| **CGV** | Ce site ne vend rien, n'encaisse rien, ne réserve rien. Aucun contrat n'est conclu par son intermédiaire : une CGV serait un document sans objet. |
| **CGU** | Aucun compte, aucun contenu déposé par l'utilisateur, aucun service interactif. Sans objet. |
| **Droit de rétractation** | Pas de vente à distance depuis ce site. |
| **Bannière de consentement cookies** | Voir § 4. |

---

## 4. Cookies, traceurs, données — le constat réel

### Ce que le site fait, vérifié le 17 juillet 2026 dans le code source

| | |
|---|---|
| Cookies déposés | **aucun** — aucune occurrence de `cookie` dans le HTML ou le JS |
| Stockage local | **aucun** — ni `localStorage`, ni `sessionStorage` |
| Mesure d'audience | **aucune** — ni `gtag`, ni `analytics`, ni `fbq` |
| Iframes | **aucune** |
| Requêtes vers des tiers | **aucune** depuis la reprise des polices — voir ci-dessous |
| Comptes utilisateurs | **aucun** |
| Paiement | **aucun** |
| Formulaires | **un seul**, celui de la newsletter — voir § 4.1 |

### 4.1 Le formulaire newsletter — décrit honnêtement

`index.html` contient :

```html
<form class="nl-form" action="mailto:100pnantes@gmail.com" method="get">
  <input type="email" placeholder="Votre email" aria-label="Votre email" required>
  <button type="submit">S'inscrire</button>
</form>
```

Ce **n'est pas** une collecte côté serveur : il n'y a ni base, ni service d'e-mailing, ni
sous-traitant. Le bouton ouvre le client mail du visiteur sur un message adressé à la
maison. Ce n'est pas non plus « aucun formulaire » : il y en a bien un, et
`confidentialite.html` lui consacre une section entière qui dit ce qu'il fait vraiment.

> **⚠︎ Défaut fonctionnel à signaler au client — ce champ ne marche pas.**
> L'`<input>` **n'a pas d'attribut `name`**, et aucun JavaScript ne gère la soumission
> (vérifié : aucun `addEventListener('submit')` dans `index.html`). Or un champ sans `name`
> n'est **pas** inclus dans les données envoyées par un formulaire. Résultat : cliquer
> « S'inscrire » ouvre un message **vide** vers `100pnantes@gmail.com`, et **l'adresse tapée
> par le visiteur est purement et simplement perdue**.
>
> Ce n'est pas un problème juridique — rien n'est collecté, donc rien à déclarer — mais
> **c'est un bug produit** : quelqu'un qui croit s'inscrire ne s'inscrit pas. Trois options :
> 1. retirer le champ tant qu'il n'y a pas de vraie newsletter (le plus honnête) ;
> 2. le remplacer par un simple lien « Écrivez-nous » ;
> 3. mettre en place un vrai outil d'envoi — auquel cas `confidentialite.html` **doit** être
>    mise à jour (base légale du consentement, sous-traitant, durée de conservation, lien de
>    désinscription). La section correspondante le dit déjà.

### 4.2 L'e-mail est exposé en clair dans le HTML

`100pnantes@gmail.com` apparaît quatre fois en clair dans `index.html` (infos pratiques,
bouton privatisation, action du formulaire, JSON-LD). **C'est un choix assumé, pas une
fuite** — une adresse de contact professionnelle a vocation à être joignable — mais elle
sera moissonnée par les robots à spam. Si le volume de courrier indésirable devient un
problème, la parade est un filtre côté boîte, pas un masquage côté site.

### Pourquoi il n'y a pas de bannière

L'article 82 de la loi Informatique et Libertés impose le consentement **avant tout dépôt de
cookie non strictement nécessaire**. Aucun cookie n'étant déposé, il n'y a rien à consentir.
Une bannière serait une gêne sans objet. C'est un choix argumenté, pas un oubli.

**Ce qui déclencherait l'obligation d'en poser une :**

- ajouter Google Analytics, Matomo (en mode non exempté), un pixel Meta ou tout traceur ;
- **intégrer une carte Google Maps en `<iframe>`** (aujourd'hui c'est une image locale
  doublée d'un lien sortant, exprès) ;
- intégrer une vidéo, un widget Instagram ou Facebook, un module de réservation ;
- **recharger les polices depuis Google Fonts** — voir ci-dessous.

### 4.3 Correction d'une affirmation fausse de l'ancien gabarit

L'ancienne page annonçait :

> « La carte Google Maps intégrée sur la page contact est susceptible de déposer des cookies
> tiers émis par Google lors de son chargement. »

**C'est faux, deux fois.** Il n'y a **aucune** iframe Google Maps sur ce site (vérifié :
zéro occurrence de `<iframe>`), et il n'y a **pas de page contact** — le site est une page
unique. Le plan du quartier est une image locale (`assets/images/maq/map-nantes.jpg`)
enveloppée dans un lien sortant vers Google Maps : rien n'est chargé depuis Google tant que
le visiteur ne clique pas. La nouvelle page dit le vrai.

### Polices — ce qui a changé le 17 juillet 2026

Le site chargeait **Oswald, Playfair Display, Caveat et Barlow depuis `fonts.googleapis.com`
et `fonts.gstatic.com`**. Chaque visite transmettait donc l'adresse IP du visiteur à Google,
sans consentement — le point précis sur lequel la CNIL et plusieurs autorités européennes
ont sanctionné des éditeurs.

Les quatre familles sont désormais **auto-hébergées** dans `assets/fonts/` (licence SIL OFL
1.1, sous-ensembles latin + latin-ext, **392 Ko**, 18 fichiers `.woff2`). Oswald, Playfair
Display et Caveat sont des **polices variables** ; Barlow est **statique** (une graisse par
fichier, 5 graisses). Les `<link>` vers Google ont été retirés des trois pages, les
`@font-face` regroupés dans `fonts.css` à la racine, et deux `<link rel="preload">` ajoutés.

**Test de non-régression :** ouvrir l'onglet Réseau, filtrer sur « third-party ». Le compte
doit rester à zéro.

> `assets/fonts/Shrimp.ttf` était déjà présent dans le dépôt, avec sa licence
> (« free for commercial use », Anton Darri). **Cette police n'est utilisée nulle part** :
> aucune règle `@font-face` ne la déclare, aucune règle CSS ne l'appelle. Elle n'est donc
> pas citée dans les mentions légales. Soit c'est un reliquat à supprimer, soit un choix
> typographique abandonné — à trancher.

---

## 5. Anomalies relevées sur l'existant

- **L'ancien `mentions-legales.html` n'était pas dans la DA du site.** Il utilisait sa propre
  palette (`--noir:#16150F`, `--craie:#F2EDE1`, `--ambre:#C4863A`) et les polices **Fraunces
  et Archivo**, que l'accueil n'utilise pas — l'accueil est en Oswald / Playfair Display /
  Caveat / Barlow sur fond `#0e0b08` et or `#c9963f`. La page refaite reprend la DA réelle
  du site.
- **`robots.txt` se contredisait avec `sitemap.xml`** : le premier faisait
  `Disallow: /mentions-legales.html`, le second déclarait cette même URL aux moteurs. La page
  était en outre en `noindex`. Les mentions légales ont vocation à être trouvables : le
  `Disallow` a été retiré, les deux pages légales sont en `index, follow` et présentes au
  sitemap.
- **Le pied de page mentait sur sa destination** : le lien « Politique de confidentialité »
  pointait vers `mentions-legales.html`. Il pointe désormais vers la vraie page.
- **Dossier en double — à trancher.** `/Users/louisonbobin/le-100p-site` pointe vers **le
  même dépôt GitHub** (`louisonb4-arch/100P.git`) que `/Users/louisonbobin/100p-site` et
  contient lui aussi un `mentions-legales.html` (le même gabarit). **Seul `100p-site` a été
  modifié.** Le doublon contient en plus un dossier `.vercel`. Deux copies de travail sur un
  même dépôt finiront par diverger : en supprimer une.
- **Horaires non confirmés** : `index.html` affiche lui-même un badge « Horaires à
  confirmer » (`.hours-warn`) à côté du tableau des horaires, lesquels sont par ailleurs
  repris dans le JSON-LD comme s'ils étaient fermes. À valider ou à retirer.
- **Note d'avis Google dans le JSON-LD** : `aggregateRating` annonce `4.8` sur `286` avis.
  Une note structurée doit correspondre à des avis réellement recueillis et affichés ; si ce
  chiffre est repris de la fiche Google Business, il doit être tenu à jour, sinon il devient
  une allégation trompeuse.

---

## 6. À vérifier après la mise en ligne

- [ ] `grep -rn "à fournir\|à confirmer" *.html` ne renvoie plus rien
- [ ] `robots.txt` et `sitemap.xml` pointent le vrai domaine (`le100p-nantes.fr` est celui
      déjà présent dans les `canonical` — à confirmer qu'il est bien déposé)
- [ ] Le site est déclaré dans Google Search Console
- [ ] La fiche Google Business est cohérente avec les horaires du site
- [ ] Aucune requête tierce dans l'onglet Réseau
- [ ] `document.cookie` est vide
- [ ] Le champ newsletter a été traité (§ 4.1) — retiré, remplacé ou branché
