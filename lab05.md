## Przyrównanie wielu sekwencji (*Multiple Sequence Alignment*)

### Zadanie 1
W pliku [ube.fa](./ube.fa) znajdują się sekwencje aktywnego enzymu koniugującego ubikwitynę pochodzące z wielu organizmów. Korzystając z programu [ClustalOmega](http://www.ebi.ac.uk/Tools/msa/) wykonaj dopasowanie sekwencji z pliku.

1. Jakie aminokwasy są zachowane u wszystkich organizmów?
2. Jaka może być przyczyna zachowania tych aminokwasów we wszystkich sekwencjach?
3. W ilu procentach są identyczne sekwencja enzymu drożdżowego UBC6_YEAST (P33296) i sekwencja enzymu królika UB2R2_RABIT (Q29503)? 

>Wskazówka: `Result Summary` –> `Percent Identity Matrix`

4. Jakie sekwencje wykazują najwyższy procent identyczności? Ile wynosi?

Dwa białka pochodzące z drożdży o numerach dostępu `NP_588162` i `NP_011428` należą do tej samej rodziny białkowej, ale nie posiadają aktywności katalitycznej. W nowej karcie przeglądarki wykonaj dopasowanie sekwencji z pliku **ube.fa** dodając do nich dwie sekwencje białek drożdżowych. 

5. Jakie aminokwasy są zachowane u wszystkich organizmów?
6. Porównaj wyniki obu przyrównań i podaj aminokwas kluczowy dla aktywności enzymu. Uzasadnij swój wybór.


### Zadanie 2
W pliku [myoglobins.fa](./myoglobins.fa) znajdują się sekwencje białkowe mioglobiny z 14 gatunków kręgowców. Wykonaj dopasowanie tych sekwencji przy pomocy trzech programów: [ClustalOmega](http://www.ebi.ac.uk/Tools/msa/), [T-COFFEE](http://tcoffee.crg.cat/apps/tcoffee) i [MAFFT](http://mafft.cbrc.jp). Umieść wyniki w protokole. Podaj fragmenty sekwencji, w których programy zwracają różne dopasowania?


### Zadanie 3
W pliku [tata.fa](./tata.fa) znajdują się sekwencje fragmentów promotora, odpowiedzialnych za przyłączanie czynnika transkrypcyjnego. Wykorzystując program [Clustal Omega](http://www.ebi.ac.uk/Tools/msa/) i [T-COFFEE](http://tcoffee.crg.cat/apps/tcoffee) wykonaj przyrównanie tych sekwencji. Zwizualizuj uzyskane przyrównania za pomocą programu [WebLogo](http://weblogo.berkeley.edu/logo.cgi). Uzyskane logo umieść w protokole. 

1. Ile konserwatywnych domen można zidentyfikować na otrzymanych logotypach graficznych? 
2. Zapisz motyw bogaty w sekwencje AT.
3. Które z motywów zostały zidentyfikowane przez oba programy?


## PSI-BLAST

### Zadanie 4
Poniżej znajduje się nieznana sekwencja białkowa. 
```
>Query1
MKDTDLSTLLSIIRLTELKESKRNALLSLIFQLSVAYFIALVIVSRFVRYVNYITYNNLV
EFIIVLSLIMLIIVTDIFIKKYISKFSNILLETLNLKINSDNNFRREIINASKNHNDKNK
LYDLINKTFEKDNIEIKQLGLFIISSVINNFAYIILLSIGFILLNEVYSNLFSSRYTTIS
IFTLIVSYMLFIRNKIISSEEEEQIEYEKVATSYISSLINRILNTKFTENTTTIGQDKQL
YDSFKTPKIQYGAKVPVKLEEIKEVAKNIEHIPSKAYFVLLAESGLRPGELLNVSIENID
LKARIIWINKETQTKRAYFSFFSRKTAEFLEKVYLPAREEFIRANEKNIAKLAAANENQE
IDLEKWKAKLFPYKDDVLRRKIYEAMDRALGKRFELYALRRHFATYMQLKKVPPLAINIL
QGRVGPNEFRILKENYTVFTIEDLRKLYDEAGLVVLE
```

1. Zidentyfikuj tę sekwencję wykorzystując program BLAST. Ogranicz przeszukiwanie do bazy PDB (Protein Data Bank).
2. Ile istotnych statystycznie wyników zostało znalezionych?

Wróć do BLAST i wykonaj ponownie przeszukiwanie. Ogranicz wyszukiwanie do bazy danych `nr (non-redundant protein sequences)` oraz wybierz algorytm `PSI–BLAST (Position-Specific Iterated BLAST)`.  

3. Ile istotnych statystycznie wyników zostało znalezionych?

>Wskazówka: zaznacz wszystkie istotne statystycznie wyniki poprzez `Select: All` w sekcji `Sequences producing significant alignments with E-value BETTER than threshold)`

4. Jaki procent sekwencji znajduje się w wynikach istotnych statystycznie *Query coverage* (pomiń wynik identyczny)? 
5. Czy wśród istotnych statystycznie wyników znajduja się wyniki pochodzące z bazy PDB?

>Wskazówka: szukaj identyfikatora bazy PDB w kolumnie `Accession`. Identyfikator składa się z min. 4 znaków, w których pierwszy jest cyfrą np. "1XYZ_A"

Wykonaj drugie przeszukiwanie PSI-BLAST w celu przygotowania matrycy PSSM (*Position-Specific Scoring Matrix*). 

>Wskazówka: wybierz przycisk `Go` przy `Run PSI-Blast iteration 2`

6. Ile istotnych statystycznie wyników zostało znalezionych?
7. Jaki procent sekwencji znajduje się w 20 pierwszych istotnych statystycznie wynikach *Query coverage* (pomiń wynik identyczny)?
8. Dlaczego w wynikach drugiego przeszukiwania PSI-BLAST znajduje się więcej istotnie statystycznych wyników?

Zapisz na pulpicie matrycę PSSM stworzoną przez PSI-BLAST do pliku o nazwie *matrix_PSSM*. Wykorzystaj matrycę do przeszukania bazy PDB. Nie zamykaj karty z wynikami przeszukiwania PSI-BLAST nr 2.

>Wskazówka: przejdź do początku strony wynikowej PSI-BLAST i kliknij `Download` -> `PSSM` (sekcja PSSM to restart search) 

Otwórz stronę BLAST w nowej karcie przeglądarki. Ogranicz wyszukiwanie do bazy danych `PDB (Protein Data Bank proteins)` oraz wybierz algorytm `PSI–BLAST (Position-Specific Iterated BLAST)`. Rozwiń menu `Algorithm parameters` i wybierz zapisany wcześniej plik z matrycą PSSM w sekcji `Upload PSSM`. 

9. Ile istotnie statystycznie wyników pochodzi z bazy PDB?
10. Podaj identyfikatory PDB i wartości *E-value* dwóch najlepszych wyników przeszukiwania?
11. Podaj wartości *Query coverage*, *Identities* oraz *sequence similarity (positives)* dla najlepszego wyniku przeszukiwania.

>Wskazówka: wykorzystaj szczegółowe przyrównanie dwóch sekwencji

12. Przejdź do rekordu odpowiadającemu najlepszemu wynikowi przeszukiwania.
a) Jakie to białko? 

b) Jaka jest długość tego białka? 

c) Jaką metodą eksperymentalną została otrzymana struktura tego białka? 

d) Z jakiego organizmu pochodzi to białko? 

e) Z ilu helis składa się to białko? 

Wróć do karty z wynikami przeszukiwania PSI-BLAST nr 2 i wykonaj kolejne przeszukiwanie `Run PSI-Blast iteration 3`. Zapisz na pulpicie matrycę PSSM do pliku o nazwie *matrix2_PSSM*. 

Wykonaj nowe przeszukiwanie PSI-BLAST w bazie PDB z wykorzystaniem zapisanej matrycy PSSM (plik *matrix2_PSSM*).

13. Ile istotnie statystycznie wyników pochodzi z bazy PDB?
14. Podaj identyfikator PDB i wartość *E-value* najlepszego wyniku przeszukiwania? 
15. Podaj wartości *Query coverage*, *Identities* oraz *sequence similarity (positives)* dla najlepszego wyniku przeszukiwania.

Użyj programu [Blast2logo](http://www.cbs.dtu.dk/biotools/Blast2logo/) do identyfikacji reszt, które są zachowane w analizowanej sekwencji białkowej (`Query1`). Ogranicz przeszukiwanie do bazy `NR70`. Otrzymane logo umieść w protokole. 

>Wskazówka: [Query1](http://www.cbs.dtu.dk/biotools/Blast2logo/teaching/Query1/)

Wyświetl szczegółową wizualizację poprzez `Customize visualization using Seq2Logo`. Nie zmieniając formularza kliknij `Submit`. 

16. Jaka jest zależność pomiędzy wielkością liter a stopniem ich zakonserwowania w sekwencji?
17. Na podstawie analizy profilu wybierz z poniższego zestawu 4 najbardziej zakonserwowane reszty aminokwasowe
(a): H271

(b): R287

(c): E290

(d): Y334

(e): F371

(f): R379

(g): R400

(h): Y436

18. Jaka może być przyczyna zakonserwowania/zachowania tych reszt aminokwasowych?

