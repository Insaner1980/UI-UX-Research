# UI/UX-suunnittelu mallikuvien avulla Claude Codessa

Claude Code tukee multimodaalista AI:ta, mikä tarkoittaa että voin analysoida kuvia (PNG, JPG, SVG jne.) ja käyttää niitä suunnittelun pohjana. Tässä on kattava selvitys mahdollisuuksista ja rajoituksista:

## 🎯 Mitä voin tulkita mallikuvista

### **Vahvuudet:**
- **Visuaalinen rakenne**: Layout-asettelut, spacing, hierarkia
- **Komponenttien tunnistus**: Napit, input-kentät, kortit, navigaatio
- **Värianalyysi**: Väripalettit, kontrastit, yhtenäisyys
- **Typografia**: Fonttikoot, painotukset, hierarkia (ei tarkkoja fontteja)
- **Kuviot ja kuvakkeet**: Muodot, tyylit, sijoittelu
- **Responsiivisuus**: Eri näkymäkoot, breakpointit
- **Vuorovaikutustilat**: Hover, active, disabled -tilat (jos näkyvissä)

### **Rajoitukset:**
- ❌ **Tarkat värikoodit**: Voin arvioida värejä, mutta ne eivät ole pikselintarkkoja
- ❌ **Tarkat mittasuhteet**: Pikselikokojen täytyy olla arvioita
- ❌ **Fonttien tunnistus**: En voi tunnistaa tarkkoja fonttinimiä (Arial vs Helvetica)
- ❌ **Animaatiot**: Staattiset kuvat eivät näytä liikkeitä tai siirtymiä
- ❌ **Interaktiivisuus**: En näe klikkauksia, scrollausta tai dynaamisia toimintoja
- ❌ **Monimutkaiset gradientit**: Tarkkojen gradienttien parametrit ovat vaikeita

---

## 📋 Käyttötapaukset yksityiskohtaisesti

### **1. Layoutin suunnittelu**

**Mitä voin tehdä:**
```
- Tunnistan grid-järjestelmät (12-column, flexbox, grid)
- Analysoin spacing-järjestelmät (8px, 16px jne.)
- Tunnistan container-leveydet ja max-widthit
- Määrittelen responsiiviset breakpointit
```

**Hyvä promptti:**
```
"Tässä on desktop-layout kuva [kuva.png]. Analysoi:
1. Grid-järjestelmä (kolumnit, gutterit)
2. Spacing-arvot (padding, margin)
3. Elementtien leveydet ja korkeudet
4. Luo CSS/Tailwind-toteutus tälle layoutille"
```

**Vältä:**
- ❌ "Tee täsmälleen samanlainen" (ilman kontekstia)
- ❌ Epäselviä, sumennettuja kuvia

---

### **2. Navigaation rakentaminen**

**Mitä voin tehdä:**
```
- Tunnistan navigaatiotyypit (top nav, sidebar, hamburger)
- Analysoin dropdown-menut ja alavalikot
- Määrittelen mobile vs desktop -navigaation
- Tunnistan breadcrumbs, tabs, pagination
```

**Hyvä promptti:**
```
"Tässä on navigaation mockup [nav.png].
- Rakenna React-komponentti tälle navigaatiolle
- Tee responsive: hamburger-menu mobiilissa
- Käytä Tailwind CSS:ää tyylittelyyn
- Lisää active-state nykyiselle sivulle"
```

**Toteutusesimerkki:**
Voin generoida:
- `<Navbar>` komponentin
- Mobile hamburger-menu logiikan
- Dropdown-toiminnallisuuden
- Accessibility-ominaisuudet (ARIA)

---

### **3. Komponenttien määrittely**

**Mitä voin tehdä:**
```
- Tunnistan UI-komponentit (Button, Card, Modal, Input)
- Analysoin komponenttien variantit (primary, secondary, outline)
- Määrittelen state-variaatiot (default, hover, disabled)
- Luo component library -rakenteen
```

**Hyvä promptti:**
```
"Tässä on button-komponenttien design system [buttons.png].
Luo:
1. React-komponentti kaikille varianteille
2. TypeScript-propsit (size, variant, disabled)
3. Tailwind-tyylit jokaiselle tilalle
4. Storybook-dokumentaatio"
```

**Vältä:**
- ❌ Liian monta komponenttia yhdessä kuvassa ilman selitystä
- ❌ Pyytämättä "luo kaikki komponentit kerralla"

---

### **4. Värimaailman analyysi**

**Mitä voin tehdä:**
```
- Tunnistan päävärit ja aksenttivärit
- Analysoin väripalettien hierarkian
- Ehdotan värimuuttujia (CSS variables, Tailwind config)
- Arvioin kontrastit saavutettavuuden kannalta
```

**Hyvä promptti:**
```
"Analysoi tämän designin väripaletti [design.png]:
1. Listaa kaikki värit (primary, secondary, grays)
2. Luo Tailwind-color-config
3. Tarkista WCAG-kontrastit tekstille
4. Ehdota dark mode -värejä"
```

**Tuloksena saan luotua:**
```javascript
// tailwind.config.js
colors: {
  primary: {
    50: '#e6f2ff',
    500: '#0066cc',
    900: '#003366',
  },
  // ... jne
}
```

**Huom:** Värikoodit ovat arvioita - tarkista lopputulos!

---

### **5. Ikonien ja elementtien tunnistaminen**

**Mitä voin tehdä:**
```
- Tunnistan ikoni-tyylit (line, filled, duotone)
- Ehdotan icon library -vaihtoehtoja (Heroicons, Lucide)
- Analysoin ikonien koot ja yhtenäisyys
- Määrittelen custom SVG-ikonit
```

**Hyvä promptti:**
```
"Tässä mockupissa on useita ikoneita [mockup.png].
1. Tunnista mitä ikoneita käytetään
2. Ehdota sopiva icon library (esim. Heroicons)
3. Jos custom-ikoneita, luo SVG-toteutukset
4. Määrittele icon-sizing system (16px, 24px, 32px)"
```

---

### **6. Wireframejen ja mockupien tulkinta**

**Mitä voin tehdä:**
```
- Tulkitsen low-fidelity wireframet
- Käännän high-fidelity mockupit koodiksi
- Ymmärrän placeholder-sisällön
- Tunnistan interaktiiviset elementit
```

**Wireframe-promptti:**
```
"Tässä on wireframe uudelle sivulle [wireframe.png].
1. Tulkitse rakenne ja toiminnallisuus
2. Ehdota tekninen toteutus (komponentit)
3. Luo HTML/React-runko
4. Lisää placeholder-sisältö"
```

**Mockup-promptti:**
```
"Tässä on valmis mockup [mockup.png].
1. Luo pixel-perfect toteutus
2. Käytä Tailwind CSS:ää
3. Varmista responsiivisuus
4. Optimoi kuvat ja assettit"
```

---

### **7. Käyttöpolkujen suunnittelu**

**Mitä voin tehdä:**
```
- Analysoin user flow -kaavioita
- Tunnistan sivujen väliset navigaatiot
- Määrittelen state management -tarpeet
- Suunnittelen routing-rakenteen
```

**Hyvä promptti:**
```
"Tässä on user flow checkout-prosessille [flow.png].
1. Analysoi kaikki vaiheet ja päätöksentekopisteet
2. Luo React Router -rakenne
3. Määrittele tarvittavat state-muuttujat
4. Tee komponenttihierarkia
5. Lisää error handling ja validointi"
```

**Vältä:**
- ❌ Epäselvät flow-kaaviot ilman selityksiä
- ❌ Liian monimutkaiset prosessit yhdessä kuvassa

---

### **8. Kehityssuunnitelmien tekeminen**

**Mitä voin tehdä:**
```
- Luon task breakdown -listat
- Priorisoin ominaisuudet
- Arvioin teknologiavalinnat
- Ehdotan toteutusjärjestyksen
```

**Hyvä promptti:**
```
"Tässä on koko sovelluksen design [full-design.png].
1. Luo kattava kehityssuunnitelma
2. Jaa komponentteihin ja moduuleihin
3. Ehdota teknologiastack
4. Määrittele toteutusjärjestys (MVP → full)
5. Arvioi aikataulu ja monimutkaisuus"
```

---

## 💎 Parhaat prompttimallit

### **Template 1: Komponenttitoteutus**
```
"Analysoi tämä [komponentti-tyyppi] kuvasta [kuva.png]:

Konteksti:
- Projekti: [React/Vue/vanilla]
- Styling: [Tailwind/CSS/styled-components]
- Erityisvaatimukset: [responsiivisuus/a11y/jne]

Toimenpiteet:
1. Analysoi visuaalinen rakenne
2. Tunnista kaikki interaktiiviset elementit
3. Luo toimiva komponentti
4. Lisää propsit ja variantit
5. Testaa eri tiloissa (hover, disabled jne)

Haluan:
- [Tarkat tiedostopolut]
- [Dokumentaatio]
- [Käyttöesimerkit]"
```

### **Template 2: Kokonainen sivu**
```
"Toteuta tämä sivunäkymä [sivu.png]:

Tekniset vaatimukset:
- Framework: [Next.js/React/jne]
- Styling: [määrittele]
- State management: [jos tarvitaan]
- API-integraatiot: [jos tarvitaan]

Vaiheet:
1. Analysoi layout ja rakenne
2. Jaa komponentteihin
3. Toteuta top-down (layout → komponentit)
4. Lisää data fetching
5. Tee responsive (mobile-first)

Huomioi:
- [SEO/a11y/performance]
- [Error states]
- [Loading states]"
```

### **Template 3: Design system**
```
"Luo design system tämän UI:n pohjalta [ui-examples.png]:

Analyysi:
1. Väripaletti (primary, secondary, neutrals)
2. Typography scale (headings, body, captions)
3. Spacing system (4px, 8px, 16px jne)
4. Komponenttikirjasto (listaa kaikki)
5. Ikonit ja grafiikat

Toteutus:
- Tailwind config / CSS variables
- React component library
- Storybook dokumentaatio
- Usage guidelines

Deliverables:
- tailwind.config.js
- components/ui/ -kansio
- README.md ohjeilla"
```

---

## ⚠️ Mitä kannattaa VÄLTTÄÄ

### **1. Huonot kuvat**
```
❌ Sumeita screenshot-kuvia
❌ Liian pieniä kuvia (alle 500px)
❌ Useita eri designeja yhdessä kuvassa ilman merkintöjä
❌ Kuvia joissa teksti on lukukelvotonta
✅ Selkeät, korkearesoluutioiset kuvat
✅ Yksi konsepti per kuva TAI selkeästi merkityt alueet
```

### **2. Epäselvät pyynnöt**
```
❌ "Tee tämä" (ilman kontekstia)
❌ "Kopioi tämä design" (ilman teknisiä vaatimuksia)
❌ "Tee samanlainen" (ei määrittelyä mitä osia)
✅ "Analysoi tämän header-komponentin rakenne ja luo React-versio Tailwindilla"
✅ "Ota väripaletti tästä kuvasta ja luo Tailwind-config"
```

### **3. Liialliset odotukset**
```
❌ Olettaa että värikoodit ovat pikselintarkkoja
❌ Olettaa että fonttinimet tunnistetaan automaattisesti
❌ Pyytää animaatioita staatisesta kuvasta (ilman määrittelyä)
❌ Olettaa että kaikki edge caset huomioidaan ilman mainintaa
✅ Pyytää arviota väreistä + antaa lopullisen värimallin
✅ Määrittää fontit erikseen tai kysyy ehdotuksia
✅ Kuvaa animaatiot sanallisesti kuvan lisäksi
```

### **4. Kontekstin puute**
```
❌ Pelkkä kuva ilman selitystä
❌ Ei mainintaa teknologiasta (React? Vue? vanilla?)
❌ Ei mainintaa projektin rakenteesta
✅ "Tässä on checkout-sivu Next.js-projektille, käytämme Tailwindiä"
✅ "Olemassa oleva projekti käyttää styled-components + TypeScript"
```

---

## 🚀 Käytännön workflow-esimerkki

### **Vaihe 1: Lataa kuva**
```bash
# Jos kuva on lokaalisti
"Analysoi kuva /home/user/designs/homepage.png"

# Tai lähetä kuva suoraan keskusteluun
[Liitä kuva]
```

### **Vaihe 2: Anna konteksti**
```
"Tämä on meidän uuden landing pagen design.
- Projekti: Next.js 14 + TypeScript
- Styling: Tailwind CSS
- Komponentit: shadcn/ui
- Tarvitsemme: hero, features, CTA sections"
```

### **Vaihe 3: Pyydä analyysi**
```
"Analysoi:
1. Layout-rakenne (grid, spacing)
2. Väripaletti
3. Tarvittavat komponentit
4. Responsiivisuuden breakpointit"
```

### **Vaihe 4: Pyydä toteutus**
```
"Luo:
1. app/page.tsx - pääsivu
2. components/ - kaikki komponentit
3. Tailwind-konfiguraatio väreille
4. README toteutuksesta"
```

---

## 📊 Yhteenveto: Mihin kuvat soveltuvat parhaiten

| Käyttötapaus | Soveltuvuus | Tarkkuus | Huomiot |
|--------------|-------------|----------|---------|
| Layout-analyysi | ⭐⭐⭐⭐⭐ | Korkea | Erinomaiset tulokset |
| Värimaailma | ⭐⭐⭐⭐ | Keskitaso | Tarkista värikoodit |
| Komponentit | ⭐⭐⭐⭐⭐ | Korkea | Toimii loistavasti |
| Typografia | ⭐⭐⭐ | Matala | Fonttinimet arvioita |
| Ikonit | ⭐⭐⭐⭐ | Korkea | Tunnistaa hyvin |
| Animaatiot | ⭐⭐ | - | Vaatii sanallisen kuvauksen |
| Mittasuhteet | ⭐⭐⭐ | Keskitaso | Suhteelliset arvot toimii |
| User flows | ⭐⭐⭐⭐⭐ | Korkea | Erinomaiset tulokset |

---

## 🎓 Lopuksi: Pro tips

1. **Yhdistä kuva + teksti**: Kuva näyttää MITÄ, teksti kertoo MIKSI ja MITEN
2. **Iteroi**: Aloita analyysillä, sitten toteutus, sitten hienosäätö
3. **Käytä useita kuvia**: Desktop + mobile + komponentit erikseen
4. **Dokumentoi**: Pyydä README:ta ja kommentteja koodiin
5. **Testaa**: Pyydä myös testejä ja eri state-vaihtoehtoja

**Valmis aloittamaan?** Lähetä mallikuva ja kerro mitä haluat toteuttaa, niin lähdetään liikkeelle! 🚀
