# Ukázka Verzování 
Verzování pomocí nástroje Git 

---

### Co je to Git  
Git je nástroj, který zaznamenává historii vývoje projektu. Zaznamenáva změny, pamatuje si různé verze projektu.  
Umožňuje tzv. větvení, tedy práci v různých větvích stejného souboru.  
Umožňuje kdykoliv se vrátit zpět do kterékoliv dříve zaznamenané fáze projektu.  
Umožňuje spojit různé větve do jedné. 

---

## Začínáme 

### Instalace 
Stáhneme z oficiáních stránek https://git-scm.com a nainstalujeme. 

### Otevřeme Git
V průzkumníku souborů otevřeme složku projektu a klikneme v ní pravým, rozbalí se nabídka.  
Klikneme levým na _Git Bash Here_, které zde po úspěšné instalaci Gitu přibylo.  
Otevře se nám okno Git Bash. V tomto okně pracujeme s Gitem, sem zadáváme příkazy uvedené níže. 

### Nastavíme Git
Zaregistrujeme se, řeknete Gitu, kdo jste.  
Uvedeme jméno a email, kterým jsme registrovaní na github.com. 
```
git config --global user.name "MojeJmeno"
git config --global user.email "muj@email.xy“
```

---

## Pracujeme s Gitem

### Zaktivujeme projekt v Gitu
Připravíme vytvoření nového repositáře pro nový projekt.  
Můžem to provést i ve složce s už rozpracovaným projektem. 
```
git init
```

Můžeme zkontrolovat změny:
```
git status
```

### Uložíme stav
V souboru jsme provedli změnu a tuto verzi souboru chceme uchovat pro případný pozdější návrat po dalších (třeba nepovedených) změnách, je to taková "záložka stavu souboru v tomto čase, ke které bude možné se vrátit". A zárověň si k této konkrétní verzi uložíme poznámku, co a proč jsme tady změnili.
Připravíme verzi souboru k uložení: 
```
git add ZkouskaVerzovani.txt
```
Verze zatím není v Gitu uložená, ale už je připravená k uložení. Můžeme zkontrolovat stav:
```
git status
```
Do Gitu provedeme uložení připravené verze souboru a připíšeme poznámku.
```
git commit -m "Vytvořil jsem soubor ZkouskaVerzovani.txt"
```
Nyní je verze uložená v Gitu. Opět můžeme zkontrolovat stav:
```
git status
```
A takto postupujeme po každé změně nebo po každém uceleném logickém souboru změn,  
které stručně a výstižně popíšeme.  
Stále dokola:  
<sub>
git add soubor.přípona  
git commit -m "druhý komentář"  
git add soubor.přípona  
git commit -m "třetí komentář"  
. . .
</sub> 

### Zkontrolujeme stav
Stav projektu - zda se něco změnilo a není připravené k uložení,  
nebo zda se něco změnilo a je připravené k uložení,  
nebo zda se nic nezměnilo - si zkontrolujeme už známým:
```
git status
```

A na historii změn a vývoj projektu se podíváme pomocí:
```
git log
```

### Další možnosti práce s Gitem
Pokud chceme připravit k uložení změny pro všechny soubory v adresáři, přidáme místo názvu souboru za add tečku. 
```
git add .
```
Pro uložení takto připravených souborů pokračujeme už známým _git commit -m "komentář"_. 


Ke starší verzi souboru se můžeme vrátit pomocí příkazu _git checkout_ a čísla uložené verze, tzv. hash commit.  
Číslo verze najdeme ve výpisu po zadání už známého příkazu _git log_, podle komentářů se výpisu můžeme orientovat.  
```
git log
git checkout b273981
```

Zpět k poslední verzi projektu se můžeme vrátit pomocí:
```
git checkout master
```
Master je název hlavní větev projektu, kterou automaticky vytvořil Git. 

Další větve projektu (odbočky) můžeme vytvořit příkazem _git branch NazevVetve_: 
```
git branch Feature
```
a přepnout se do nové větve:
```
git checkout Feature
```
Projekt si takto můžeme rozdělit do několika paralelních větví, kde každá funguje samostatně.  
Můžeme zkoušet různé verze projektu a v případě neúspěchu se kdykoliv se vrátit a vydat se jinou cestou.  

Spojování větví zde podrobněji nerozepisuji, jen zmíním, že je to možné příkazem _git merge_.  
  
Poznámka: Některé editory kódu nebo vývojová prostředí v sobě už mají podporu Gitu nebo přímo Git vestavěný a ovládá se různými tlačítky.  
  
---

## Vzdálený server

### GitHub není Git!
Git je program, který máme nainstalovaný v počítači. Git ukládá informace o verzích projektu na disk počítače.  
GitHub je veřejný server, kam můžeme projekt nebo soubory nahrát. 

Vytvoříme si repořitář na GitHubu (Repositories >> New >> Repository name...)  
Po vytvoření repořitáře nám GitHub nabídne návod, jak spojit náš projekt s HitHubem :-)  
  
V Gitu zadáme odkaz na vzdálený server, na konkrétní repozitář a vytvoříme spojení se GitHubem: 
```
git remote add origin https://github.com/mojejmeno/mujnazevreporitare.git
```
Větev v GitHubu si přejmenujeme z _main_ na _master_, pokud chceme a  
nahrajeme soubory i s historií změn z našeho počítače na server GitHub, zadáme  
v Gitu: 
```
git push -u origin master
```
Poprvé po nás možná bude chtít přihlášení do GitHubu.  

Na projektu pracujeme v počítači a projekt i s v Gitu zaznamenanými změnami pošele na GutHub:
```
git push origin master
```







