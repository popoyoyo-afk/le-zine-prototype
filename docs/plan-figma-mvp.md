# Plan d'exécution — Écrans Figma du MVP « alternatives écologiques »

Source : `PRD-app-alternatives-ecologiques.md` (17/11/2026)
Fichier Figma : `lEUjAfkg4Z4tKvHxDXLX1O` — page **MVP – Alternatives écologiques**
Exécutant : agent de code (Claude) via le MCP Figma (`use_figma`), **une tâche = un appel `use_figma` = une vérification visuelle**.

---

## Décisions de cadrage (validées le 17/11/2026)
| Sujet | Décision |
| --- | --- |
| Direction graphique | **Piste 2 — Fanzine** (mood board « App éco — 4 pistes graphiques », PDF `Piste 2 — Fanzine · mood board.pdf`). Versions précédentes archivées : « Archive – v1 (Inter) », « Archive – v2 (Herbier) » |
| Exemple de produit | **Vêtement** : t-shirt basique, 100 % coton conventionnel, fabriqué au Bangladesh, 12,99 €. Le scan montre l'impact par **matière**, **lieu de fabrication** et **transport** |
| Ton | **Tutoiement** |
| Navigation | Ce n° · Archives · [Scan] · Impact · Moi (entrées de la piste Fanzine + bouton scan rond au centre, ajouté car absent du mood board) |
| Fidélité | **Haute fidélité** (tokens, styles et composants Fanzine, vrais textes) |
| Noms | **Génériques** : « Nom de l'app », « Enseigne pilote – Lyon 3 » |
| Périmètre passe 1 | **Parcours critique seul** — voir liste ci-dessous ; le reste passe en *Passe 2* |

### Passe 1 — parcours critique (à exécuter maintenant, dans cet ordre)
1. T02 Styles de texte
2. T03 Sections — **seulement** `1 · Onboarding`, `2 · Scan & arbitrage`, `3 · Impact évité`
3. T04 Composants — **sous-ensemble** : TopBar, VerdictBadge, OptionCard, ProgressDots, SourceRow, EquivalenceTile, ChallengeCard, HistoryRow, Banner (Info), SheetHandle
4. T05 Charte de ton
5. T10 → T14 Onboarding (5 écrans)
6. T20 Scanner · T21 Analyse · T22 Résultat · T23 Choix confirmé · T24 Tiroir « Comment on calcule » (5 écrans)
7. T30 Impact — état rempli (1 écran)
8. T70 Prototype — chaîne T10 → T30 + overlay T22 → T24 uniquement
9. T71 / T72 / T73 Audits sur les 11 écrans

→ **11 écrans**, ~20 appels `use_figma`.

**✅ Passe 1 exécutée le 17/11/2026** : 9 styles de texte, 3 sections, 10 composants complémentaires, charte de ton, 11 écrans, 18 liens de prototype (flow « Parcours critique – scan » au départ de T10).
Résultats des audits : ton 0 terme banni · textes < 11 px : 0 · écrans avec chiffre CO₂ sans source : 0 · contraste : `verdict/good` passé de #2E8B57 à #1F7346 (4,25:1 → 5,8:1) · cible « Comment on calcule ? » passée de 42 à 44 px.
Écarts vs plan : sections placées à y = 0 / 1100 / 2200 ; T23 n'a pas d'onglet TabBar (écran modal) ; T24 est un clone de T22 avec voile + tiroir.

**🔁 Passe 1 refaite en Herbier le 17/11/2026** (la version ci-dessus est archivée) :
- Variables `Herbier` : 11 couleurs en 2 modes **Jour / Nuit**, 8 espacements `pas-*`, 3 angles, 2 filets. 13 styles `Herbier/*` (Young Serif, Literata, Courier Prime).
- 15 composants : 10 icônes au trait 1,5 · 5 silhouettes (paquet, bocal, gourde, brique, bidon) · StatusBar · Bouton (Principal / Secondaire / Lien / Lien voile) · Étiquette spécimen · Catégorie · Difficulté · Annotation · Planche (Entête / Vignette) · Navigation · TopBar · Choix · AlternativeLigne · LigneFiche · LigneHerbier.
- 11 écrans, 22 liens de prototype (flow « Parcours critique – Herbier »). T30 devient « Herbier – impact évité » avec relevé hebdomadaire en barres au trait.
- Audits : 0 terme banni, 0 vouvoiement · contraste ≥ 4,5:1 en Jour **et** en Nuit · toutes les cibles cliquables ≥ 48 px (zone « Passer », entrées de navigation, carré scan corrigés) · chaque chiffre CO₂ a sa source.
- Adaptations au DS : plus de verdict « À améliorer » sur le produit scanné (Herbier interdit le verdict négatif) ; le défi de la semaine sort de T30 et ira sur l'onglet Planche (passe 2) ; « goutte » et « feuille » retirées de l'iconographie.
- **Impact sur la passe 2** : toutes les tâches restantes utilisent Herbier, le tutoiement et la nouvelle navigation ; ajouter l'écran **Planche (accueil + défi)** et **Catalogue** au périmètre, et le composant `Defi` / `ChampRecherche` du DS.

**🔁 Passe 1 refaite en Fanzine (piste 2) avec un vêtement, le 17/11/2026** — la version Herbier est archivée sur « Archive – v2 (Herbier) » :
- Variables `Fanzine` (11 couleurs : papier, papier-carte, encre, encre-profonde, rose, rose-texte, bleu, surimpression, jaune, agrafe, filet-doux ; espacements, pilule, contour 2 px) et 13 styles `Fanzine/*` (Bowlby One + Atkinson Hyperlegible).
- Composants : icônes trait 2, visuels t-shirt / jean / sweat, trame de points, StatusBar, Bouton (pilule rose / pointillé / lien), Kicker, **Titre double** (défaut de calage rose + bleu en produit), Vignette riso, Choix, AlternativeLigne, **BarreImpact**, Tuile, Navigation, TopBar, LigneImpact.
- Données d'exemple (fictives, cohérentes) : t-shirt scanné ≈ 5,2 kg CO₂e = matière 2,4 + fabrication Bangladesh 2,2 + transport et vente 0,6. Alternatives du même rayon : coton recyclé Turquie (même prix, −1,9 kg), coton bio Portugal (+3,00 €, −2,0 kg), seconde main (−7,00 €, −4,8 kg). Impact du mois : 18,4 kg (jean seconde main 13,4 · sweat bio 3,1 · t-shirt recyclé 1,9). Sources : Ecobalyse, Base Empreinte® ADEME, étiquette produit.
- 11 écrans, 22 liens (flow « Parcours critique – Fanzine (t-shirt) »). Audits : 0 terme banni, contraste ≥ 4,5:1 (3:1 pour les titres ≥ 24 px), cibles ≥ 48 px, source sur chaque chiffre.
- Ajustements accessibilité vs mood board : texte sur rose en `encre-profonde` (5,4:1 au lieu de 4,1:1), texte sur bleu en `papier-carte` (4,6:1 au lieu de 4,2:1), bleu jamais utilisé comme petit texte.
- Point d'attention PRD : afficher l'impact du produit scanné (matière / fabrication / transport) est une demande explicite ; il reste présenté de façon neutre et toujours suivi des alternatives, sans empreinte totale de l'utilisateur.

**✅ Passe 2 exécutée en Fanzine le 17/11/2026** (15 écrans de plus, 26 au total) :
| Section | Écrans ajoutés |
| --- | --- |
| 2 · Scan & arbitrage | T25 Tiroir label GOTS (garantit / ne garantit pas) · T26 Saisie manuelle |
| 3 · Impact | T31 Premier passage (pas de zéro, premier défi) · T32 Tiroir « 92 km en voiture ? » |
| 4 · Ce n° & défi | T40 Ce n° (défi « laver à 30 °C », suivi des 7 jours) · T41 Autre défi · T42 Défi relevé · T43 Relance douce (notification) · T45 Archives |
| 5 · Cas limites | T50 Vêtement inconnu · T51 Signalement (photo de l'étiquette) · T52 Pas d'alternative ici (pull mérinos) · T53 Hors connexion |
| 6 · Moi | T60 Moi (réponses, notifications, séries privées désactivées, compte facultatif) · T61 Création de compte facultative |
- Nouveaux composants : Toggle, ChampRecherche, Bandeau (Info / Succès / Hors ligne). Couverture `📒 Couverture` avec sommaire.
- Prototype : 84 liens au total, 5 flows (Parcours critique, Défi de la semaine, Vêtement inconnu, Pas d'alternative, Moi et compte facultatif). La navigation basse est reliée sur tous les onglets.
- Audits sur les 26 écrans : 0 terme banni ni vouvoiement, contraste conforme, cibles ≥ 44 px, chaque chiffre CO₂ avec sa source (sources ajoutées sur T40, T41, T42, T53 après audit).
- Reste hors périmètre (P1/P2 du PRD) : carte locale vérifiée, liste de courses partagée, écran dédié aux séries, communauté, mode nomade, défis famille, module numérique.

### Passe 2 — après validation de la passe 1
T25, T26, T31, T32, T40–T43, T50–T53, T60–T61, compléments T03/T04 (sections et composants restants), T74.

---

## 0. Conventions communes (à respecter par TOUTES les tâches)

### 0.1 Format et grille du canevas
| Élément | Valeur |
| --- | --- |
| Format d'écran | Frame 390 × 844 (iPhone 14/15), `clipsContent = true`, fond `bg/canvas` |
| Zone sûre | StatusBar en haut (0–47), TabBar en bas (761–844) quand l'écran est un onglet principal |
| Marges | 24 px latérales, espacement vertical 16 / 24 px |
| Nommage des frames | `<ID tâche> · <Nom écran>` ex. `T22 · Résultat – vue rapide` |
| Placement | Une **Section** Figma par parcours, écrans alignés en ligne, pas horizontal = 390 + 100 px |

| Section | y | Contient |
| --- | --- | --- |
| `1 · Onboarding` | 0 | T10 → T14 |
| `2 · Scan & arbitrage` | 1100 | T20 → T26 |
| `3 · Impact évité` | 2200 | T30 → T32 |
| `4 · Défi hebdo` | 3300 | T40 → T43 |
| `5 · Cas limites` | 4400 | T50 → T53 |
| `6 · Profil & compte` | 5500 | T60 → T61 |
| `🧩 Composants` | -900 | bibliothèque (déjà créée) |

### 0.2 Tokens (variables `Eco – Couleurs`, déjà créées)
`brand/primary` #1F6B4A · `brand/primary-strong` · `brand/primary-soft` · `accent/sun` · `accent/sun-soft` · `bg/canvas` · `bg/surface` · `border/default` · `text/primary` · `text/secondary` · `text/on-brand` · `verdict/good` · `verdict/mid` · `verdict/low` · `info/blue` · `info/blue-soft` · `overlay/scrim`.
**Règle :** aucune couleur codée en dur — toujours `setBoundVariableForPaint`.

### 0.3 Composants disponibles (déjà créés)
`Icon/*` (25 icônes), `StatusBar`, `Button` (Type = Primary / Secondary / Ghost, prop. texte `Label`), `Chip` (Tone = Brand / Sun / Info / Neutral, prop. `Label`), `TabBar` (Active = Scanner / Impact / Défi / Profil), `AlternativeCard` (props `Nom`, `Détail`, `Impact`, `Prix`).
**Règle :** tout élément répété ≥ 2 fois devient un composant (voir T04).

### 0.4 Garde-fous du PRD à vérifier sur CHAQUE écran (Definition of Done)
1. **Impact évité uniquement** — aucun chiffre d'empreinte totale, aucune comparaison à un objectif national.
2. **Ton de coach** — aucun terme de la liste bannie (T05) ; pas d'injonction (« vous devez »).
3. **≤ 30 s / une main** — action principale dans le tiers inférieur de l'écran.
4. **Preuve à 1 tap** — tout chiffre d'impact porte une source + date ou un accès au tiroir « Comment on calcule ».
5. **Accessibilité RGAA** — cibles tactiles ≥ 44 px, contraste texte ≥ 4,5:1, taille de texte ≥ 11 px.
6. **Pas d'écran vide** — tout état vide/erreur propose une action.

### 0.5 Procédure type d'une tâche
1. Relire les conventions 0.1–0.4.
2. Un appel `use_figma` : retrouver les composants par nom (`findAllWithCriteria({types:['COMPONENT','COMPONENT_SET']})`) et les variables par nom, construire la frame en auto-layout dans la bonne Section.
3. Retourner les IDs créés.
4. Une capture d'écran (`get_screenshot`) → corriger texte tronqué / chevauchement si besoin (1 correctif max puis re-capture).
5. Cocher la case de la tâche ci-dessous.

### 0.6 Données fictives de référence (cohérence entre écrans)
- Ville pilote : **Lyon** · Enseigne : **« Enseigne pilote – Lyon 3 »** (nom générique, à remplacer)
- Produit scanné : **Pâtes blanches 500 g – marque A, 1,29 €**, verdict « À améliorer »
- Alternatives : Pâtes complètes bio MDD (même prix, −0,6 kg CO₂e) · Pâtes françaises blé local (+0,20 €, −0,4 kg) · Pâtes en vrac (−0,15 €, −0,3 kg)
- Cumul impact : **18,4 kg CO₂e évités** ≈ 92 km en voiture ≈ 37 douches
- Source : *Base Empreinte® ADEME, mise à jour oct. 2026* · incertitude ± 20 %
- Défi : « Remplacer 1 boisson en bouteille par l'eau du robinet cette semaine » — impact ≈ 1,2 kg, effort 2 min

---

## Phase A — Fondations

- [x] **T00 · Variables couleur** — collection `Eco – Couleurs`, 17 variables. *Fait.*
- [x] **T01 · Composants de base** — icônes, StatusBar, Button, Chip, TabBar, AlternativeCard. *Fait et vérifié visuellement.*

- [x] **T02 · Styles de texte**
  - Créer 7 styles Inter : `Display` 34 Bold · `Title` 24 Semi Bold · `Headline` 18 Semi Bold · `Body` 16 Regular · `Body strong` 16 Semi Bold · `Caption` 13 Regular · `Micro` 11 Medium.
  - Appliquer les styles aux textes des composants T01.
  - *Done* : 7 styles locaux, 0 texte de composant sans style.

- [x] **T03 · Sections du canevas**
  - Créer les 6 Sections de 0.1 avec leur titre ; vides.
  - *Done* : 6 sections aux bons y, aucune superposition avec `🧩 Composants`.

- [x] **T04 · Composants complémentaires** (dans `🧩 Composants`)
  | Composant | Variantes / props | Usage |
  | --- | --- | --- |
  | `TopBar` | Type = Back / Close / Title-only ; prop `Titre` | en-têtes |
  | `VerdictBadge` | Tone = Bon / Correct / À améliorer ; prop `Label` | résultat scan (pas de rouge, pas de note punitive) |
  | `OptionCard` | Selected = true / false ; props `Titre`, `Sous-titre`, icône | onboarding, changement de défi |
  | `ProgressDots` | Step = 1 / 2 / 3 | onboarding |
  | `SourceRow` | props `Source`, `Date` + icône external | tiroir méthode |
  | `EquivalenceTile` | props `Valeur`, `Unité`, icône | tableau de bord |
  | `ChallengeCard` | State = Actif / Réalisé ; props `Titre`, `Impact`, `Effort` | tableau de bord, défi |
  | `HistoryRow` | props `Produit`, `Date`, `Impact` | historique, hors ligne |
  | `Banner` | Tone = Info / Hors ligne / Succès ; prop `Message` | bandeaux |
  | `SheetHandle` | — | haut des bottom sheets |
  | `Toggle` | On = true / false | profil |
  - *Done* : 11 composants, chaque cible interactive ≥ 44 px, capture de la bibliothèque sans texte tronqué.

- [x] **T05 · Charte de ton (frame de référence)**
  - Frame `Garde-fous – Ton` à côté de la bibliothèque : liste provisoire de termes bannis (échec, raté, mauvais, nul, honte, culpabilité, pollueur, catastrophe, « vous devez », « il faut », « trop tard ») + 5 formulations recommandées (« Bien joué », « Pas cette semaine ? Pas de souci », « Bon à savoir »…).
  - *Done* : frame visible, marquée « provisoire – à valider UX writing » (question ouverte du PRD).

---

## Phase B — Onboarding sans compte (P0.5, user story 5)

- [x] **T10 · Bienvenue**
  - StatusBar · illustration (forme organique `brand/primary-soft` + icône leaf) · `Display` « Des alternatives réalistes, en 30 secondes » · `Body` « Même magasin, même budget. On compte ce que vous évitez, pas ce que vous émettez. » · Chips « Sans compte » « Sources ADEME » · Button Primary « Commencer » · Button Ghost « J'ai déjà un compte ».
  - *Critères* : promesse anti-culpabilisation visible, aucun formulaire, CTA en bas.

- [x] **T11 · Question 1/3 — Temps**
  - TopBar Back + lien « Passer » à droite · ProgressDots Step 1 · `Title` « Combien de temps pour vos courses ? » · 3 OptionCard : « Moins de 15 min », « 15 à 30 min », « J'ai le temps » (2e sélectionnée) · Button Primary « Suivant ».
  - *Critères* : question passable (P0.5), cibles ≥ 44 px.

- [x] **T12 · Question 2/3 — Budget** (même gabarit que T11)
  - « Votre budget courses ? » : « Serré, chaque euro compte » / « Équilibré » / « Souple ».

- [x] **T13 · Question 3/3 — Mobilité** (même gabarit)
  - « Comment vous déplacez-vous ? » : « À pied ou à vélo » (bike) / « Transports en commun » / « En voiture » (car). CTA « C'est parti ».

- [x] **T14 · Pré-autorisation caméra**
  - Icône scan grand format · « Scannez un code-barres » · texte d'explication (usage local, rien n'est enregistré sans compte) · Button Primary « Autoriser la caméra » · Ghost « Plus tard ».
  - *Critères* : total onboarding T10→T14 = 5 écrans, ≤ 4 taps minimum → < 60 s.

---

## Phase C — Scan & arbitrage express (P0.1, P0.2 — stories 1, 4, 6)

- [x] **T20 · Scanner (onglet principal)**
  - Fond `overlay/scrim` plein écran (simule la caméra) · cadre de visée 280 × 180 coins arrondis blanc · texte « Placez le code-barres dans le cadre » · boutons ronds 56 px : flash (zap), saisie manuelle (search) · lien « Derniers scans » (history) · Chip Neutral « Enseigne pilote – Lyon 3 » (magasin détecté, modifiable) · TabBar Active = Scanner.
  - *Critères* : utilisable à une main, rien d'autre à saisir.

- [x] **T21 · Analyse en cours**
  - Variante de T22 en squelettes (rectangles `border/default`) + texte « On cherche dans votre magasin… ».
  - *Critères* : indique visuellement la cible < 3 s (pas de spinner bloquant plein écran).

- [x] **T22 · Résultat — vue rapide** ⭐ écran clé
  - TopBar Close · bloc produit scanné (vignette, nom, « 1,29 € ») + VerdictBadge « À améliorer » · `Headline` « 3 alternatives dans ce magasin » · 3 AlternativeCard (données 0.6, écart de prix en € : « même prix », « +0,20 € », « −0,15 € ») · ligne `Caption` « Source : Base Empreinte ADEME · oct. 2026 » + lien « Comment on calcule ? » (info) · Button Primary sticky « Je prends l'alternative 1 » · Banner Info « Bon à savoir : le label AB… » cliquable.
  - *Critères* : verdict + ≥ 1 alternative au-dessus de la ligne de flottaison ; prix en euros ; source en 1 tap ; aucune empreinte totale.

- [x] **T23 · Choix confirmé (« small win »)**
  - Grande icône check sur cercle `brand/primary-soft` · `Display` « −0,6 kg CO₂e évités » · `Body` « ≈ 3 km en voiture. Bien joué ! » · EquivalenceTile · Button Primary « Scanner un autre produit » · Ghost « Voir mon impact ».
  - *Critères* : objectif « première action dès la session 1 » ; ton encourageant ; chiffre sourcé (lien info).

- [x] **T24 · Tiroir « Comment on calcule »** (bottom sheet sur T22)
  - Copie de T22 en fond + scrim 50 % · sheet 640 px, coins 24 px, SheetHandle · onglets « Méthode » (actif) / « Label » · blocs : *Ce qu'on compare* · *Le calcul* (formule lisible) · *Incertitude* « ± 20 % » · 2 SourceRow (Base Empreinte ADEME oct. 2026 ; Open Food Facts, mis à jour il y a 3 j) · Button Ghost « Signaler une erreur » (flag).
  - *Critères* : chaque chiffre = source + date ; fermeture visible ; ne masque pas totalement la vue rapide.

- [ ] **T25 · Tiroir — onglet « Label »** (story 6)
  - Même sheet, onglet « Label » actif · label « AB – Agriculture biologique » · « Ce qu'il garantit » (3 puces check) · « Ce qu'il ne garantit pas » (2 puces info, ton neutre) · SourceRow.
  - *Critères* : décryptage ≤ 80 mots, lisible en < 30 s.

- [ ] **T26 · Saisie manuelle / recherche**
  - TopBar Back « Rechercher un produit » · champ de recherche (search) avec clavier simulé (rectangle gris 290 px) · 3 résultats HistoryRow.
  - *Critères* : solution de repli si le code-barres ne passe pas.

---

## Phase D — Tableau de bord « impact évité » (P0.3, story 3)

- [x] **T30 · Impact — état rempli**
  - StatusBar · `Title` « Votre impact évité » · carte héro `brand/primary` : `Display` blanc « 18,4 kg CO₂e » + « évités depuis le 2 nov. » + lien info · grille 2 EquivalenceTile (car « 92 km en voiture », droplet « 37 douches ») · ChallengeCard Actif · section « Vos derniers choix » 3 HistoryRow · TabBar Active = Impact.
  - *Critères* : aucune empreinte totale ni objectif national ; progression privée (pas de classement) ; source accessible.

- [ ] **T31 · Impact — état vide**
  - Même structure, carte héro remplacée par message d'accueil « Votre premier geste compte déjà » + illustration ; ChallengeCard « Premier défi » ; Button Primary « Scanner mon premier produit ». **Aucun « 0 kg »** affiché.
  - *Critères* : P0.3 « état vide : message d'accueil + premier défi, pas un zéro ».

- [ ] **T32 · Détail d'une équivalence** (bottom sheet sur T30)
  - « Comment on passe de kg CO₂e à km en voiture ? » · facteur utilisé · SourceRow ADEME · incertitude.

---

## Phase E — Défi hebdomadaire (P0.4, story 2)

- [ ] **T40 · Défi de la semaine**
  - TopBar Title « Défi de la semaine » · Chip Sun « Semaine du 16 nov. » · carte défi grande (icône droplet, titre du défi 0.6) · 2 Chips : « ≈ 1,2 kg évités » / « 2 min d'effort » · `Caption` « Choisi selon vos réponses : budget serré, à pied » · Button Primary « C'est fait ! » · Button Secondary « Changer de défi » · TabBar Active = Défi.
  - *Critères* : 1 seul défi actif ; changement sans pénalité (aucune mention de perte).

- [ ] **T41 · Changer de défi**
  - TopBar Back · « Choisissez un autre défi » · 3 OptionCard (titre + impact + effort), triées par ratio impact/effort · `Caption` « Aucun impact sur votre progression ».

- [ ] **T42 · Défi réalisé**
  - Célébration sobre (sparkles, pas de confettis criards) · « Défi relevé ! » · « +1,2 kg CO₂e ajoutés à votre impact » · Button Primary « Voir mon impact ».

- [ ] **T43 · Relance encourageante**
  - Deux éléments sur un même artboard : (a) notification iOS simulée sur écran verrouillé « Encore 2 jours pour votre défi, ou on en choisit un plus simple ? » ; (b) écran T40 avec Banner Info « Pas cette semaine ? Pas de souci, on vous en propose un plus simple. »
  - *Critères* : jamais de message d'échec ; notifications ≤ 2/semaine (noter en annotation).

---

## Phase F — Cas limites (stories 7, 8, 9)

- [ ] **T50 · Produit inconnu**
  - Icône search sur cercle · `Title` « On ne connaît pas encore ce produit » · `Body` « Aidez-nous à l'ajouter, ça prend 20 secondes. » · Button Primary « Signaler ce produit » (flag) · Secondary « Rechercher manuellement » · Ghost « Scanner autre chose ».
  - *Critères* : message clair + bouton signaler, jamais d'écran vide.

- [ ] **T51 · Signalement (sheet + confirmation)**
  - Artboard 1 : sheet avec code-barres pré-rempli, champ « Nom du produit (facultatif) », bouton « Prendre une photo », Button Primary « Envoyer ». Artboard 2 : Banner Succès « Merci ! On vous prévient dès qu'il est ajouté. »

- [ ] **T52 · Aucune alternative dans l'enseigne**
  - Bloc produit scanné + VerdictBadge · `Headline` « Pas d'alternative dans ce magasin pour l'instant » · `Body` honnête « On préfère vous le dire plutôt que de vous envoyer loin. » · Banner Info « Bon à savoir » (astuce d'usage, ex. format familial) · Button Primary « Scanner un autre produit ».
  - *Critères* : **aucune** suggestion de magasin à plus de 10 min.

- [ ] **T53 · Hors ligne en magasin** *(P1 dans les exigences, story 9)*
  - Banner Hors ligne (wifi-off) « Hors connexion : vos derniers scans restent disponibles » · liste 4 HistoryRow avec alternative retenue · ChallengeCard en cache · TabBar Active = Scanner.

---

## Phase G — Profil & compte facultatif (P0.5)

- [ ] **T60 · Profil (sans compte)**
  - `Title` « Profil » · carte « Vos préférences » (temps / budget / mobilité, chacune modifiable) · réglages : Notifications (Toggle On, `Caption` « 2 par semaine maximum ») · Séries personnelles (Toggle Off, « privées, désactivées par défaut ») · carte incitative non bloquante « Sauvegarder votre historique » + Button Secondary « Créer un compte » · liens « Méthodologie & sources », « Confidentialité » · TabBar Active = Profil.

- [ ] **T61 · Création de compte facultative** (bottom sheet)
  - « Gardez votre historique sur tous vos appareils » · 3 boutons (Apple, Google, e-mail) — pictos génériques · Ghost « Plus tard » · `Caption` RGPD (lien « Ce que nous stockons »).
  - *Critères* : jamais imposé, sortie évidente.

---

## Phase H — Prototype & contrôles qualité

- [x] **T70 · Prototype du parcours critique**
  - Liens `ON_CLICK → NAVIGATE` : T10 → T11 → T12 → T13 → T14 → T20 → T21 → T22 → T23 → T30 ; T22 → T24 (overlay) ; T20 → T50 ; T20 → T52.
  - *Done* : point de départ du flow « Parcours scan » défini ; nombre de taps T20 → T23 ≤ 3.

- [x] **T71 · Audit ton** — script de lecture : tous les nœuds TEXT de la page comparés à la liste T05 → retourner les occurrences, puis corriger.
- [x] **T72 · Audit accessibilité** — script : cibles interactives < 44 px, textes < 11 px, contraste des paires texte/fond → corriger.
- [x] **T73 · Audit « preuve »** — chaque écran contenant « kg CO₂e » contient une source ou un lien info → liste des écarts.
- [ ] **T74 · Page de couverture / index** — frame d'en-tête : nom de l'app, statut « Brouillon », légende des sections, carte du parcours (flèches entre miniatures).

---

## Hors périmètre de ce plan (P1 / P2 du PRD — tâches à créer plus tard)
Carte locale vérifiée · Liste de courses partagée · Séries privées (écran dédié) · Mode hors ligne complet · Communauté & mentorat · Mode nomade · Défis famille · Module numérique responsable.

## Ordre d'exécution et dépendances
```
T02 → T03 → T04 → T05
            └→ B (T10–T14) ─┐
            └→ C (T20–T26) ─┼→ T70 → T71 → T72 → T73 → T74
            └→ D (T30–T32) ─┤
            └→ E (T40–T43) ─┤
            └→ F (T50–T53) ─┤
            └→ G (T60–T61) ─┘
```
Les phases B à G sont indépendantes une fois T04 terminé (elles écrivent dans des Sections différentes). Au sein d'une phase, suivre l'ordre (les écrans réutilisent le gabarit du précédent).

**Volume estimé :** 36 tâches · 33 écrans/artboards · ~45 appels `use_figma`.
