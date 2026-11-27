# Git-logg

Klistra in utskrifter och svara på frågorna. Det här är din dokumentation av dagens arbete.

## 1. Utgångsläget

Skriv ut `git log --oneline --graph --all` direkt efter att du klonat. Klistra in här:

* 696768f Agent host session 6ae9a5b3-c0ce-4f05-a3a7-077f527eddba - turn 2
* ae00e1f Agent host session 6ae9a5b3-c0ce-4f05-a3a7-077f527eddba - turn 2 start
* c3c39df Agent host session 6ae9a5b3-c0ce-4f05-a3a7-077f527eddba - turn 1
* d004b32 Agent host session 6ae9a5b3-c0ce-4f05-a3a7-077f527eddba - turn 1 start
 \
  * 750fd80 Agent host session 6ae9a5b3-c0ce-4f05-a3a7-077f527eddba - baseline checkpoint
* 5a5841d (HEAD -> main, origin/main, origin/HEAD) Modul 5 i TypeScript med Vite
* 3804533 Add files via upload
* f7a13a4 Add files via upload
* c9a0075 Initial commit

* main
  remotes/origin/HEAD -> origin/main
  remotes/origin/main

On branch main
Your branch is up to date with 'origin/main'.

## 2. Merge utan konflikt

Klistra in `git log --oneline --graph --all` efter merge:

```text

* b42c566 (HEAD -> main) Merge branch 'meny-nyheter'
|\
| * 0d2d804 (meny-nyheter) Lägg till chokladboll på menyn
* | a29fd4e Lägg till telefonnummer
|/
* ce5f37f 9.1: Update git-logg.md example outputs
* 5a5841d (origin/main, origin/HEAD) Modul 5 i TypeScript med Vite
* 3804533 Add files via upload
* f7a13a4 Add files via upload
* c9a0075 Initial commit
```

Fråga: Vad är skillnaden mellan en *fast-forward*-merge och en merge som skapar en egen merge-commit? Svara med egna ord:
Fast forward Skapar en linjär commit-historik utan att skapa en separat merge-commit.
En merge-commit skapar en commit som förenar historiken från båda grenarna.

## 3. Konflikten

Klistra in filen med konfliktmarkörerna, precis som den såg ut innan du löste den:

```
# Öppettider

Vardagar: 07–18
<<<<<<< HEAD
Helger: 10–17
=======
Helger: 09–18
>>>>>>> oppettider-sommar
Röda dagar: stängt
```

Fråga: Vad betyder

`<<<<<<< HEAD` Här börjar innehållet från den gren du står på just nu. HEAD betyder ungefär "min aktuella position".

`=======` Separator mellan de två konkurrerande versionerna.

`>>>>>>> grennamn`? Här slutar innehållet från den andra grenen.
grennamn visar vilken gren ändringarna kommer från.

Hur löste du den, och varför blev det så?
Kompromiss - 10-18 fick det bli. Eftersom ändringen från ena branchen krockar med förändringen från den andra inkommande/existerande.
Jag valde en kompromiss: Helger: 10–18. Grenarna föreslog olika helgtider, så jag skrev en ny tid som tar hänsyn till båda förslagen.

## 4. Ångra

Vad är skillnaden mellan `git restore`, `git revert` och `git reset`? Vilken är säkrast när ändringen redan är pushad?

## 5. Pull request

Länk till din pull request (på ditt eget repo):

## 6. Reflektion

Vad är det värsta som kan hända om man kör `git push --force` på en gren som andra använder?
