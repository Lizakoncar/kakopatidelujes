# Kako pa ti deluješ? — spletna stran za Lizine delavnice

Enostranska statična spletna stran (`index.html` + mapa `images/`, brez gradnje), pripravljena za **GitHub Pages**.

## Objava na GitHub Pages

1. Ustvari nov repozitorij na GitHubu (npr. `kako-pa-ti-delujes`).
2. Naloži `index.html` in mapo `images/` v koren repozitorija.
3. V repozitoriju pojdi na **Settings → Pages**.
4. Pod *Build and deployment → Source* izberi **Deploy from a branch**, vejo `main` in mapo `/ (root)`. Shrani.
5. Čez nekaj minut bo stran na `https://<tvoje-ime>.github.io/<repo>/`.

> Za lastno domeno (npr. `kakopatidelujes.si`) jo dodaš v Settings → Pages → Custom domain.

## Kako zamenjati slike

V mapi `images/` so barvni placeholderji (`.svg`). Najlažje: svojo fotografijo poimenuj
**enako kot placeholder** (a s svojo končnico) in v `index.html` popravi `src`. Mesta so v kodi
označena z `<!-- TODO: zamenjaj ... -->`:

| Placeholder | Kje | Priporočeno razmerje |
|---|---|---|
| `images/hero.svg` | glavna fotografija (poster) | pokončno **3:4** |
| `images/craft-polstenje.svg` | veščina Polstenje & filcanje | **4:3** |
| `images/craft-kvackanje.svg` | veščina Kvačkanje & štrikanje | **4:3** |
| `images/craft-sivanje.svg` | veščina Šivanje | **4:3** |
| `images/craft-kamen.svg` | veščina Oblikovanje milnega kamna | **4:3** |
| `images/craft-les.svg` | veščina Oblikovanje lesa | **4:3** |
| `images/craft-nakit.svg` | veščina Izdelava nakita | **4:3** |
| `images/about-liza.svg` | portret Lize | pokončno **4:5** |

> V mapi `images/` so še stari `prog-*.svg` placeholderji, ki se ne uporabljajo več — lahko jih izbrišeš.

### Realne fotografije (že vstavljene)

Tvoje fotografije so že obrezane, pomanjšane za splet in vstavljene na ta mesta:

- **Hero (uokvirjena skupinska slika na zelenem ozadju)** → `hero.jpg`
- **Povabilo / delovni list** → `intro-worksheet.jpg` (list »Kako pa ti deluješ?«)
- **Veščina: oblikovanje milnega kamna** → `craft-kamen.jpg`
- **Veščina: izdelava nakita** → `craft-nakit.jpg`
- **O Lizi** → `about-liza.jpg`

Še **4 kartice veščin** (polstenje & filcanje, kvačkanje & štrikanje, šivanje, oblikovanje lesa)
uporabljajo barvne placeholderje (`craft-polstenje.svg`, `craft-kvackanje.svg`, `craft-sivanje.svg`,
`craft-les.svg`), ker zanje v mapi ni bilo fotografij — zamenjaj jih, ko jih boš imel.

> Galerija (»Utrinki«) je odstranjena. Datoteke `gal-1.jpg … gal-5.jpg` in `hero-group.jpg` ostajajo
> v mapi `images/`, a se ne uporabljajo več — lahko jih izbrišeš ali jih uporabiš za prazne kartice veščin.

> Opomba: 5 datotek `.heic` (IMG_…) ni bilo mogoče samodejno pretvoriti za splet. Če jih želiš
> uporabiti, jih izvozi/shrani kot `.jpg` in mi povej, kam naj jih postavim.

## Obrazec za prijave (kontakt)

GitHub Pages je statičen, zato sam ne pošilja e-pošte. Najlažja rešitev je **Formspree**:

1. Registriraj brezplačen račun na [formspree.io](https://formspree.io).
2. Ustvari nov obrazec — dobiš povezavo oblike `https://formspree.io/f/abcdwxyz`.
3. V `index.html` poišči `action="https://formspree.io/f/YOUR_FORM_ID"` in `YOUR_FORM_ID` zamenjaj s svojim.

Brez tega gumb »Pošlji sporočilo« ne deluje — lahko pa stranke pišejo na e-pošto/Instagram iz razdelka Kontakt.

## Kar je še vredno zamenjati

- E-pošta in povezave do **Instagrama/Facebooka** v razdelku Kontakt in v nogi (trenutno `info@kakopatidelujes.si` ter prazni `instagram.com` / `facebook.com`).
- Besedila programov, če želiš dodati cene ali trajanje.
- `og:image` v glavi (slika za predogled pri deljenju povezave).

## Barve in pisave

Mehka, vključujoča pastelna paleta (vse v `:root` na vrhu CSS-ja):

| Vloga | Hex | Pomen |
|---|---|---|
| Primary (anchor) | `#AB87B7` | ustvarjalnost, globina, introspekcija |
| Secondary (balance) | `#B8D9B5` | mir, rast, povezanost |
| Warm neutral (softness) | `#F1CAD5` | nežnost, toplina, podpora |
| Cool neutral (clarity) | `#CDE6FF` | jasnost, zaupanje, lahkotnost |
| Accent (energy) | `#F5C84B` | veselje, energija, optimizem |
| Dark (contrast) | `#43344A` | globina, stabilnost, kontrast |
| Podlaga (paper) | `#F7F4EF` | topla bela |

Pisave: **Fraunces** (naslovi) + **Mulish** (besedilo) + **Space Mono** (oznake, napisi pod slikami,
navigacija), naložene z Google Fonts.

Slog je **organski tok**: namesto toge mreže vsebina vijuga po strani (veščine se izmenjujejo levo/desno
kot tok), fotografije so v organskih »kamenčkastih« oblikah z mehkim barvnim blobom za sabo, v ozadju
plavajo nežni pastelni oblaki (blur), elementi se rahlo gibljejo (float). Papirnata tekstura in monospace
oznake ostajajo. Vsa gibanja upoštevajo `prefers-reduced-motion`.

Organske oblike slik so določene z `--b1 … --b5` (border-radius) v `:root` — če želiš drugačno obliko,
spremeniš te vrednosti.
