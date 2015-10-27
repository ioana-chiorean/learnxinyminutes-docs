---
name: perl
category: language
language: perl
contributors:
    - ["Korjavin Ivan", "http://github.com/korjavin"]
translators:
    - ["Ștefania Ioana Chiorean", "https://github.com/ioana-chiorean"]
lang: ro-ro
filename: learnperl-ro.pl
---

Perl 5 este un limbaj de programare foarte capabil, bogat in caracteristicii cu mai bine de 25 de ani de dezvoltare în spate. 

Perl 5 rulează pe peste 100 de platforme pornind de la sisteme portabile până la mainframe-uri și este adecvat atât pentru a crea prototipuri rapide cât și pentru proiecte de dezvoltare la o scară mai mare. 



```perl
# Comentariile de o singură linie încep cu semnul diez.


#### Tipuri de variable în Perl 

#  Variabilele încep cu un semn, care este reprezintă tipul. 
#  Numele unei variabile valide începe cu o literă sau linie joasă
#  urmată de orice număr de litere, numere sau linii joase. 

### Perl are trei mari tipuri de variabile: $scalar (mărime scalară), @array (șir) și %hash (valoare de dispersie).

## Mărimiile scalare
#  O mărime scalară reprezintă o singură valoare:
my $animal = "cămilă"; 
my $answer = 42;

# Valorile de mărimi scalare pot fi șiruri, numere întregu sau umerele cu virgulă mobilă și
# Perl le va converti automat între ele după cum este necesar.

## Șiruri
#  Un șir reprezintă o listă de valori. 
my @animals = ("cămilă", "lama", "bufniță");
my @numbers = (23, 42, 69);
my @mixed   = ("cămilă", 42, 1.23);



## Valoarile de dispersie
#  O valoare de dispersie reprezintă un set de cheie/perechi devalori:

my %fruit_color = ("măr", "roșu", "banană", "galben");

#  Poți folosi spațiu și operatorul "=>" pentru a le așeza mai frumos:

my %fruit_color = (
  măr  => "roșu",
  banană => "galben",
);
# Mărimile scalare, șirurile și valorile de dispersie sunt descrise mai în detaliu în perldata.
# (perldoc perldata).

# Tipuri de date mai compleze pot fi construite folosind referințe, care îți permit 
# să construiești liste și valori de dispersie în liste și valori de dispersie

#### Constructori condiționali și repetitivi

# Perl are majoritatea constructori condiționali și repetitivi.

if ($var) {
  ...
} elsif ($var eq 'bar') {
  ...
} else {
  ...
}

unless (condition) {
  ...
}
# Aceasta este o versiune ai ușor de urmărit pentru conditionalul "If (!condition)" /("Dacă (!condiție)")

# versiunea Perl pentru a avea condiția la sfârșit
print "Yow!" if $zippy;
print "Nu avem banane" unless $bananas;

# când
while (condition) {
  ...
}


# pentru cicluri și iterații 
for (my $i = 0; $i < $max; $i++) {
  print "Indexul este $i";
}

for (my $i = 0; $i < @elements; $i++) {
  print "Elementul curent este " . $elements[$i];
}

for my $element (@elements) {
  print $element;
}

# În mod implicit

for (@elements) {
  print;
}

# versiunea Perl pentru a avea condiția la sfârșit
print for @elements;

#### Expresii obișnuite

# Suportul pentru expresiile obișnuite este larg și intră în multe detalii și este subiectul
# lungiilor documentații în perlrequick, perlretut și în alte locuri.
# Totuși, pe scurt:

# Potrivire simplă
if (/foo/)       { ... }  # adevarată dacă $_ conține "foo"
if ($a =~ /foo/) { ... }  # adevarată dacă $a conține "foo"

# Substitușie simplă

$a =~ s/foo/bar/;         # înlocuiește foo cu bar în $a
$a =~ s/foo/bar/g;        # înlocuie TOATE INSTANȚELE foo cu bar în $a


#### Fișiere și comenzi de intrare/ieșire 

# Poți deschide un fișier pentru scriere sau citire folosind funcția "open()".

open(my $in,  "<",  "input.txt")  or die "Nu pot deschide input.txt: $!";
open(my $out, ">",  "output.txt") or die "Nu pot deschide output.txt: $!";
open(my $log, ">>", "my.log")     or die "Nu pot deschide my.log: $!";

# Poți citi dintrun fișier deschis folosind operatorul "<>". În contextul mărimilor scalare
# citește o singură linie din fișier și în contextul șirurilor
# citește tot fișierul asignând fiecărei linie un element din listă:

my $line  = <$in>;
my @lines = <$in>;

#### Scrierea subprogramelor / subrutinelor
# Scrierea subprogramelor / subrutinelor este ușoară:

sub logger {
  my $logmessage = shift;

  open my $logfile, ">>", "my.log" or die "Nu pot deschide my.log: $!";

  print $logfile $logmessage;
}

# Acum poți folosi subrutina asemeni oricărei alte funcții integrate:

logger("Avem o subbrutină de înregistrare!");
```

#### Folosirea modulelor Perl

Modulele Perl oferă un categorie mare de caracteristici ca să te ajute să eviți reinventarea roții și pot fi descărcate din CPAN (http://www.cpan.org/). Un număr de module pupulare sunt incluse în distribuția Perl.

perlfaq conține întrebări și răspunsuri legate de multe activități obișnuite și deseori oferă sugestii pentru module CPAN bune de utilizat.

#### Mai multe detalii

 - [perl-tutorial](http://perl-tutorial.org/)
 - [Learn at www.perl.com](http://www.perl.org/learn.html)
 - [perldoc](http://perldoc.perl.org/)
 - and perl built-in : `perldoc perlintro`
