---
theme: seriph
class: "text-center"
highlighter: shiki
lineNumbers: false
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# Reguliariosios išraiškos

<br>

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-info" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Sąvoka

<br>

Reguliariosios išraiškos – tai taisyklių rinkiniai, aprašantys tekstinį šabloną, pagal kurį randamas reikalingas tekstas ar fragmentas. Papraščiausios reguliariosios išraiškos – tai literalų eilutės. Sudėtingesnėse reguliariose išraiškose naudojami metasimboliai, kurie apibrėžia galimus ieškomo teksto ar fragmento variantus.

---

# Reguliariosios išraiškos metodai Javascript kalboje

<br>

- **test()** - gražina true arba false
- **exec()** - gražina masyvą su paieškos informaciją arba null
- **match()** - gražina masyvą kuriame yra visi atitikmenys, įskaitant užfiksuotas grupes, arba null, jei atitikmenų nerasta..
- matchAll() - grąžina masyvą, kuriame yra visi atitikmenys, įskaitant užfiksuotas grupes, arba null, jei atitikmenų nerasta.
- search() - tikrina, ar eilutėje yra atitikmuo. Grąžinamas atitikmens indeksas arba -1, jei paieška nepavyksta.
- **replace()** - ieško atitikimo eilutėje ir pakeičia atitikusią eilutę pakaitine eilute.
- replaceAll() - ieško atitikimų visose eilutėse ir pakeičia atitikusią eilutę pakaitine eilute.
- split() - naudoja reguliariąją išraišką arba fiksuotą eilutę, kad suskaidytų eilutę į pogrupių masyvą.

---

# Pirma užduotis

Naudodami pateiktą masyvą, sukurkite antrąjį masyvą, į kurį įtraukite tik numerius su vietovės kodu 801 (pirmi 3 skaičiai)

```js
const phoneNums = [
  "801-766-9754",
  "801-545-5454",
  "435-666-1212",
  "801-796-8010",
  "435-555-9801",
  "801-009-0909",
  "435-222-8013",
  "801-777-6655",
];
```

Atsakymas: ["801-766-9754", "801-545-5454", "801-796-8010", "801-009-0909", "801-777-6655"];

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/1uzduotis.js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Šablonai (Patterns)

<br>

```js
//Long syntax
regex = new RegExp("pattern", "flags");

//Short
regexp = /pattern/; // be rakto
regexp = /pattern/gim; // su raktu
```

---

# Raktai (Flags)

Raktai g i m o s x modifikuoja paieškos operacijas. Žemiau pateiktas jų aprašymas.

|              |                                                                                                                                                              |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <kbd>g</kbd> | Globali paieška t.y. bus rasti visi teksto fragmentai eilutėje, atitinkantys paieškos šabloną. Pagal nutylėjimą paieška baigiama suradus pirmąjį atitikmenį. |
| <kbd>i</kbd> | Paieška ignoruojant didžiasias ir mažasias raides                                                                                                            |
| <kbd>m</kbd> | Eilutė traktuojama kaip multi-eilutė, kurią sudaro keletas eilučių atskirtų naujos eilutės simboliu                                                          |
| <kbd>o</kbd> | Kintamieji, esantys šablone, naudojami tik vieną kartą.                                                                                                      |
| <kbd>s</kbd> | Eilutė traktuojama kaip viena eilutė. Metasimbolis “.” reiškia bet kokį simbolį, tame tarpe ir naujos eilutės simbolį                                        |
| <kbd>x</kbd> | Leidžiama šablonuose naudoti komentarus ir tarpo simbolius.                                                                                                  |

---

# Simboliai

|                |                                                                                                                 |
| -------------- | --------------------------------------------------------------------------------------------------------------- |
| <kbd>\\d</kbd> | Visi skaičiai, nuo žodžio “decimal” [0-9] [Pvz.](https://www.regexpal.com/?fam=126423)                          |
| <kbd>\\D</kbd> | Visi ne skaičiai, nuo žodžio “decimal” [^0-9] [Pvz.](https://www.regexpal.com/?fam=126424)                      |
| <kbd>\\w</kbd> | Visos raidės,skaičiai ir \_ ženklas, nuo žodžio “word” [a-zA-Z0-0_] [Pvz](https://www.regexpal.com/?fam=126422) |
| <kbd>\\W</kbd> | Viskas kas įeina į \\w neturi būti čia [^a-za-z0-9_] [Pvz](https://www.regexpal.com/?fam=126425)                |
| <kbd>\\s</kbd> | Visi tarpai, tabai ir naujos eilutės [Pvz](https://www.regexpal.com/?fam=126426)                                |
| <kbd>\\S</kbd> | Viskas iššskyrus \\s [Pvz](https://www.regexpal.com/?fam=126427)                                                |
| <kbd>\.</kbd>  | Visi simboliai [Pvz](https://www.regexpal.com/?fam=126428)                                                      |

---

# Specialus simboliai

<br>

### Išėjimo (Escaping)

<kbd>\\</kbd> - tai “isejimo” simbolis, reikalinas norint naudoti specialius simbolius. [Pvz](https://www.regexpal.com/?fam=126429)

<br>
<br>
<br>

### Antra užduotis

Parašykite el.pašto regex'ą.

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/2uzduotis(email).js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Specialus simboliai

<br>

### Quantifiers Kvantifikatoriai)

[\*](https://www.regexpal.com/?fam=126435), +, [?](https://www.regexpal.com/?fam=126436), [x{n}](https://www.regexpal.com/?fam=126440), x{n,}, x{n,m}

<br>
<br>
<br>

### Trečia užduotis

Parašykite slaptažodžio regex'ą (min 8 simboliai, 1 didžioji, 1 spec. simbolis, 1 skaičius)

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/3uzduotis(password).js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Specialus simboliai

<br>

### Teiginiai (Assertation)

[^](https://www.regexpal.com/?fam=126431), [$](https://www.regexpal.com/?fam=126432), [x(?=y)](https://www.regexpal.com/?fam=126433), [x(?!y)](https://www.regexpal.com/?fam=126434), [\b,\B](https://www.regexpal.com/?fam=126437)

<br>

### Groups and backreferences (Grupės ir atgalinės nuorodos)

[(x)](https://www.regexpal.com/?fam=126439), (?:x), [x|y](https://www.regexpal.com/?fam=126438), [xyz], [^xyz], \\Number

---

# Ketvirta užduotis

Su reguliariosios išraiškos pagalba įrašykite vardus į naują masyvą, bet pakeiskite vardų eiliškumą taip, kad pirmasis vardas būtų įrašytas pirmas, o pavardė - paskutinė. Pvz.: Jonas Jonaitis

```js
const names = ["Jonaitis, Jonas", "Petraitis, Petras", "Antanaitis, Antanas"];
```

Atsakymas: ['Jonas Jonaitis', 'Petras Petraitis', Antantas Antanaitis]

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/4uzduotis(replace).js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Penkta užduotis

Parašykite reguliariąją išraišką, kuri atitiktų bet kurią savaitės dieną ir tada pakeistų tą savaitės dieną eilutėje į pirmadienį. Rezultatus parodykite konsolėje

```js
const text =
  "Each and every Tuesday, at the beginning of the day, we hold a staff meeting. At the Tuesday staff meeting, you will need to make a report on the past weeks progress, and you will receive assignments for the following Tuesday. Just be aware that somedays this Tuesday meeting might not occur. When that happens, we will make an announcement.";
```

Atsakymas:
"Each and every Monday, at the beginning of the day, we hold a staff meeting. At the Monday staff meeting, you will need to make a report on the past weeks progress, and you will receive assignments for the following Monday. Just be aware that somedays this Monday meeting might not occur. When that happens, we will make an announcement.";

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/5uzduotis.js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Šešta užduotis

Parašykite regex datai patikrinti pvz: 24/12/1991

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/6uzduotis.js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

---

# Septinta užduotis

Parašykite regex IP patikrinti pvz: 255.255.255.1

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/artik777/regex-uzdaviniai/blob/main/7uzduotis.js" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>
