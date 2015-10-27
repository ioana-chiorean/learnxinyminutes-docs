---
language: brainfuck
filename: learnbrainfuck-ro.bf
contributors:
    - ["Prajit Ramachandran", "http://prajitr.github.io/"]
    - ["Mathias Bynens", "http://mathiasbynens.be/"]
translators:
    - ["Ștefania Ioana Chiorean", "https://github.com/ioana-chiorean"]
lang: ro-ro
---

Brainfuck (nu se scrie cu literă mare decât la începutul unei propoziții) este un limbaj de proramare Turing-complet simplu cu doar 8 comenzi. 

Poți încerca brainfuck în navigatorul tău cu [brainfuck-visualizer](http://fatiherikli.github.io/brainfuck-visualizer/).

```
Orice caracter înafară de "><+-.,[]" (excluzând ghilimelele) este ignorat.

Brainfuck este reprezentat de un șir cu 30 000 de celule inițializate cu 0 și un pointer 
care indică celula curentă. 

Există opt comenzi:
+ : Incrementează valoarea celulei curnete cu unu.
- : Decrementează valoarea celulei curnete cu unu.
> : Mută indicatorul la următoarea celulă ( celula din dreapta).
< : Mută indicatorul la celula precedentă ( celula din stânga).
. : Afișează valoarea ASCII a celulei curente (i.e. 65 = 'A').
, : Citește un singur caracter în celula curentă.
[ : Dacă valoarea celulei curente este 0, sare la ] corespunzător.
    Dacă nu, se mută la următoarea instrucțiune.
] : Dacă valoarea celulei curente este 0, se mută la următoarea instrucțiune.
    Dacă nu, e mută înapoi în instrucțiuni la ] corespunzător.

[ și ] formează o buclă « până când » (« while loop »). Bineînteles, trebuie să fie în perechi. 

Să ne uităm peste câteva programe brainfuck simple de bază.

++++++ [ > ++++++++++ < - ] > +++++ .

Acest program afișează litera'A'. Inițial, incrementează celula #1 până la 6.
Celula #1 va fi folosita în bucla repetitivă. Apoi, intră în buclă([) și se mută la celula #2. Se incrementează celula 2 de 10 ori și se mută înapoi la celula #1 și o decrementează. Aceasta buclă se repetă de 6 ori (va face 6 decrementări în celula #1 pentru a ajunge la 0, punct în care sare la următoarea ] și continuă). 

În acest punct, ne aflăm în celula #1 care are valoarea 0, în timp ce celula #2 are valoarea 60. Ne mutăm la celula 2, o incrementăm de 5 ori, pentru a ajunge la 65 și afișăm valoarea celulei. 65 este 'A' în ASCII, deci 'A' este afișat în terminal.

, [ > + < - ] > .

Acest program citește un caracter introdus de utilizatorși îl copiază în celula #1. Apoi începe o buclă. Se mută la celula #2, imcrementează valoarei ei, se mută înapoi la celula #1 și decrementează valoarei ei. Aceasta buclă continuă până când celula #1 este 0 și celula #1 conține valoarei inițială a celulei #1. Deoarece suntem în celula #1 la sfârșitul buclei, se mută la celula #2 și afișează valoarea ASCII. 

Ține-ți minte că spațiile sunt pur și simplu pentru o lizibilitate mai bună. Programele se pot scrie de asemeni așa: 

,[>+<-]>.

Încercați șă aflați ce face acest program:

,>,< [ > [ >+ >+ << -] >> [- << + >>] <<< -] >>

Acest program citește doua numere și le înmulțește.

Inițial se citesc două valori și apoi se începe o buclă externă condiționată de celula #1. Se mută la celula #1 și începe bucla internă condiționată de celula #2, incrementând celula 3. Totuși, apare o problemă: la sfârșitul buclei interne celula #2 este 0. În acest caz, bucla internănu va mai funcționa încă o dată. Pentru a fixa această problemă incrementăm celula #4 și apoi copiem valoare in celula #2. Celula #1 va fi rezultatul final. 

```

Acesta este brainfuck. Nu e chiar așa de greu, nu e așa? 
Poți scrie programele tale în brainfuck programs sau poti dezvolta un interpret de brainfuck în alt limbaj. Acesta este destul de simplu de implementat, dar dacă ești un masochist încearcă să faci un interpret de brainfuck în .. in brainfuck.
