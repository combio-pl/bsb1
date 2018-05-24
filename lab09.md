## Wprowadzenie do Galaxy

1. Otwórz stronę publicznego serwera [Galaxy](https://usegalaxy.org).

2. Wykorzystując narzędzie z sekcji `Get Data` -> `UCSC Main` pobierz na serwer Galaxy dane z UCSC Genome Browser dotyczące pozycji wszystkich egzonów znajdujących się na chromosomie 22 człowieka. Ustaw następujące parametry:

* clade: mammal
* genome: human
* assembly: Dec. 2013 (GRCh38/hg38)
* group: Genes and Gene Predictions
* track: GENCODE v24
* region position: chr22
* output format: BED - browser extensible data
* send output to: Galaxy
* create one BED record per: coding exons

3. Pobierz na serwer Galaxy dane z UCSC Genome Browser dotyczące pozycji wszystkich SNP znajdujących się na chromosomie 22 człowieka. Ustaw następujące parametry:

* clade: mammal
* genome: human
* assembly: Dec. 2013 (GRCh38/hg38)
* group: variation 
* track: common SNPs(147)
* region position: chr22:1-50818468
* output format: BED - browser extensible data
* send output to: Galaxy
* create one BED record per: whole gene

4. Zmień nazwy plików znajdujących się w historii na *Exons* oraz *SNP*. 

> Wskazówka: wybierz symbol ołówka, zmiany zatwierdź przyciskiem save.

5. Przygotuj tabelę zawierającą informacje o SNP występujących w poszczególnych egzonach wykorzystując narzędzie `Join` z sekcji `Operate on genomic intervals`, które łączy dane na podstawie ich lokalizacji genomowej.

* Jako pierwszy zestaw danych (Dataset 1) wybierz *Exons*, natomiast drugi (Dataset 2) *SNP*. 
* Pozostałe ustawienia pozostaw domyślne. By zatwierdzić kliknij `Execute`. 

Otwórz podgląd uzyskanego wyniku. Jaka zmienność sekwencji znajduje się w egzonie `uc062bej.1_cds_9_0_chr22_15710868_f`?

6. Policz ile SNP zawiera się w poszczególnych egzonach. 

Wybierz sekcję `Join, Subtract and Group` i narzędzie `Group`. Ustaw następujące parametry: 

* select data: 3: Join on data 2 and data 1
* group by column: column 4
* operation -> insert operation type: count, on column: column 4, round results to nearest integer: yes

Otwórz podgląd uzyskanego wyniku. Ile SNP zawiera egzon o ID `uc002z1w.4_cds_2_0_chr22_16964766_r`?

7. Znajdź egzon z największą liczbą SNP. 

Posortuj malejąco plik wynikowy z pkt 6 wykorzystując narzędzie `Sort` z sekcji `Filter and Sort`. Ustaw następujące parametry:
 
* dataset: 4: group on data 3
* column: 2
* descending order

Podaj ID egzonu z największą liczbą SNP? Ile SNP zidentyfikowano w tym egzonie?

8. Wybierz 5 egzonów z największą liczbą SNP, wykorzystując narzędzie `Select First` z sekcji `Text Manipulation`. Zamieść tabelę w protokole. 

> Wskazówka: Wybierz zestaw danych z pkt 7

9. Dodaj do tabeli z pkt 8 informację o lokalizacji genomowej wybranych egzonów - wykorzystaj narzędzie `Join` z sekcji `Join, Subtract and Group`, które łączy wiersze z dwóch zbiorów danych na podstawie wspólnych pól. Ustaw następujące parametry:

* join: 1:Exons
* using column: 4
* with 6:Select first on data 5
* and column:1

Podaj pozycje startu i końca egzonu zawierającego 29 SNP.

10.  Zapisz wyniki analizy w formacie BED. 

Rozwiń sekcję `Text Manipulation` i wybierz narzędzie `Cut (columns from a table)`. Ustaw następujące parametry:

* cut columns: c1, c2, c3, c4, c8, c6 
* delimited by: Tab
* From: 7: join two datasets 

Zamieść tabelę w protokole.

Zmień typ danych na format BED.

> Wskazówka: wybierz symbol ołówka -> zakładka Datatype -> new type: bed -> save

11. Wyświetl wyniki w przeglądarce genomowej UCSC. Ustaw widok okna obejmujący cały chromosom 22. Znajdź egzon o największej liczbie SNP. Jakiego genu jest to egzon?

> Wskazówka: Rozwiń szczegółowy opis pliku i wybierz link `display at UCSC`

> Wskazówka: Ustaw filtr na widoku ścieżki `User Track` (`show only items with score at or above:` 40)

12. W bazie Gene NCBI znajdź rekord dotyczący genu z pkt 11. Podaj GeneID oraz pełną nazwę genu.


## RNA-Seq z *Drosophila melanogaster*

1. Pobierz plik z adnotacją genów *Drosophila melanogaster* (dm3) z UCSC. Ustaw następujące parametry:

* clade: insect
* genome: drosophila melanogaster
* assembly: Apr. 2006 (BDGP R5/dm3)
* group: Genes and Gene Predictions
* track: FlyBase Genes
* region: genome
* output format: GTF
* send output to: Galaxy

2. Pobierz pliki [fastq z eksperymentu](https://usegalaxy.org/library/list#folders/Ff4ce53393dae30ee). 

> Wskazówka: zaznacz wszystkie pliki (kolumna *name*) -> to history -> as datasets

3. Uporządkuj pobrane pliki w kolekcje `c1` oraz `c2`. 

* W panelu `History` wyszukaj wszystkie pliki oznaczone jako c1.
* Rozwiń opcję `Operations on multiple datasets` i wybierz `All`.
* Rozwiń listę `For all selected..` i wybierz `Built list of dataset pairs`. 
* W sekcji `unpaired forward` wpisz -f- , natomiast `unpaired reverse` -r-
* Wybierz `Auto-pair`
* Nadaj nazwę kolekcji w polu` Name:` c1 i kliknij `Create list`

Powtórz procedurę dla plików oznaczonych jako c2, nadając nazwę kolekcji w polu `Name:` c2.

### Mapowanie odczytów 

4. Wybierz narzędzie `TopHat` z sekcji `NGS:RNA Analysis`. Ustaw następujące parametry:

* is this single end or paired-end data?: paired-end (as collection)
* RNA-Seq FASTQ paired ends: c1
* mean inner distance between mate pairs: 28
* report discordant pair alignments: no
* use a built-in genome
* select a reference genome: fruit fly (Drosophila melanogaster): dm3
* TopHat settings to use: full parameter list
* library type: FR First Strand

Powtórz procedurę dla kolekcji c2 (zmiana pola RNA-Seq FASTQ paired ends na c2).

### Analiza różnicowa ekspresji

5. Odfiltruj z pliku GTF wiersze, w których nić oznaczona jest jako “.” czyli unknown. Wybierz narzędzie `Filter` z sekcji `Filter and Sort` i ustaw następujące parametry:

* Filter: UCSC Main on D. melanogaster (...)
* Following conditions: c7 != “.”
* Number of header lines to skip: 0

6. Policz liczbę odczytów na gen wykorzystując narzędzie `HTseq-count` (sekcja `NGS: RNA Analysis`) wg następujących parametrów:

* Aligned SAM/BAM File: Dataset collection, TopHat on collection 13: accepted_hits
* GFF File: Filter on data (patrz pkt wyżej)
* mode: union
* stranded: yes

Powtórz procedurę dla kolekcji c2. 

7. Różnicowa analiza ekspresji. Wybierz narzędzie `DESeq2` (sekcja `NGS: RNA Analysis`). Wybierz następujące parametry:

* Factor name: conditions
* Factor level 1: condition 1
* Counts file: Dataset collection; ht-seq-count on collection 1
* Factor level 2: condition 2
* Counts file: Dataset collection; ht-seq-count on collection 2
* Visualizing the analysis results: yes

Podaj identyfikator genu z istotną statystycznie zmianą ekspresji pomiędzy analizowanymi warunkami (c1 vs c2). 

