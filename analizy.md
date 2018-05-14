## Analizy genomowe

## Przeglądarki genomowe - UCSC, Ensembl
### Zad. 1 
#### SNP w mysim genie BRCA1 (UCSC)
Otwórz stronę serwisu [UCSC Genome Browser](https://www.genome.ucsc.edu/) i w zakładce `Genome` wybierz genom myszy (`mouse NCBI37/mm9`). Wyszukaj gen BRCA1 (*breast cancer type 1 susceptibility protein*).

> Wskazówka: Użyj podpowiedzi wyświetlanych podczas wspisywania.


Zresetuj ustawienia (`defaut tracks` oraz `default order`). Zwróć uwagę na ścieżkę SNPs (128). Rozwiń dostępne opcje formatowania ścieżki SNPs (128). Zmień nastepujące opcje: 
	* `Color Specification: Function` - `Coding-NonSynonymous` - blue, pozostałe typy - czarny
	* Tryb wyświetlania (`display mode` - pack

Wybierz SNP rs28273098. Podaj jego pozycję genomową?
Przejdź do bazy danych `dbSNP`. Jaka zmiana aminokwasu jest powiązana z tym polimorfizmem?

### Zad. 2
#### SNP w mysim genie BRCA1 (Ensembl)
Otwórz stronę serwisu [Ensembl](https://www.ensembl.org) i wybierz genom myszy. Wyszukaj gen BRCA1 (*breast cancer type 1 susceptibility protein*). Z karty genu przejdź do jego lokalizacji (`Location`). Włącz wyświetlanie ścieżki `Sequence variants`.

> Wskazówka: Z menu po lewej wybierz `Configure this page`, następnie wybierz grupę `Variation i sequence variants`. Zaznacz ścieżkę `Sequence variants (dbSNP and all other sources)`, wyświetloną w stylu `expanded with names`.

Znajdź ten sam polimorfizm co w zadaniu 1 (SNP rs28273098). Jaka jest konsekwencja występowania tego wariantu?

>Wskazówka: Nazwy SNP wyświetlane będą jeżeli okno widoku obejmować będzie mniej niż 10 kb sekwencji. 


### Zad. 3
#### Miejsca wiązania czynnika transkrypcyjnego (UCSC)

W przeglądarce UCSC znajdź w genomie człowieka (`GRCh37/hg19`) gen NRAS (*neuroblastoma RAS viral (v-ras) oncogene homolog*). Zwiększ wyświetlany obszar o 1000 par zasad z obu stron genu. Znajdź ścieżkę `TFBS Conserved` (grupa `Regulation`) i zmien opcję jej wyśiwtlania na `full`. Wyśiwtl szczegółowe informacje dotyczące czynnika transkrypcyjnego `V$CDC5_01`, Na podstawie bazy UniProt krótko opisz jakie pełni funkcje. 


### Zad. 4
#### Wizualizacja własnych ścieżek z danymi (UCSC)

Otwórz UCSC Genome Browser i przywróć ustawienia domyślne. Wybierz genom człowieka (`GRCh37/hg19`). 

* Wybierz przycisk `add custom tracks`
* Załaduj plik z rozszerzeniem `.wig.tar.gz`
* Naciśnij przycisk `Submit`
* Kliknij nazwę ścieżki i edytuj konfigurację dodając:

```
track type=wiggle_0 name="normal_MCF" description="normal" visibility=full autoScale=on
alwaysZero=on maxHeightPixels=50:50:5 color=0,120,0`
```

* Powtórz czynność z plikiem dla linii komórkowej HCC1937 zmieniając nazwę na `tumor_HCC1937`
* Gdy pojawi się lista dodanych ścieżek, kliknij `Go to genome browser`

Wyszukaj gen AFAP-AS1 i znajdź różnice pomiędzy wprowadzonymi ścieżkami. Zinterpretuj wyniki.

> Wskazówka: Szczegółowe opcje konfiguracyjne opisane są [tutaj](http://genome.ucsc.edu/goldenPath/help/hgTracksHelp.html#CustomTracks) 

### Zad. 5
#### Identyfikacja genów regulowanych przez czynnik regulatorowy SMARCB1

W przeglądarce UCSC Genome Browser wybierz z menu `Tools -> Table Browser`. Pobierz dane dla genomu człowieka (złożenie hg19, chromosom 22) dotyczące pozycji wiązania czynnika transkrypcyjnego SMARCB1. 

W tym celu wybierz:
* `Group` Regulation
* `Track` Txn Factor ChIP
* `Table` WgEncodeRegTfbsClusteredV3
* `Region` position: chr22
* `Filter` wybierz `create`, a następnie w pozycji `name` ustaw `SMARCB1`. Wybierz `Submit`. 
* `Output format` BED
* `Output file` factors.bed.gz
* `File type returned` gzip compressed

Kliknij `Get output` i na następnej stronie potwierdź pobranie danych.

Pobierz również pozycje znanych genów wg adnotacji ENSEMBL. W tym celu wybierz:
* `Group` Gene and gene prediction tracks
* `Track` Ensembl Genes
* `Table` ensGene
* `Region` position: chr22
* `Output format` BED
* `Output file` genes.bed.gz
* `File type returned` gzip compressed

Kliknij `Get output` i na następnej stronie potwierdź pobranie danych.

Otwórz stronę publicznego serwera [Galaxy](http://usegalaxy.org). W panelu narzędzi (po prawej stronie) wybierz narzędzie `Get Data` -> `Upload File`. Prześlij na serwer wcześniej pobranej pliki.

Posortuj pliki BED (`BEDTools` -> `Sort BED Files`). Uruchom narzędzie dwukrotnie z domyślnymi opcjami wybierając każdy z załadowanych plików.

Wyszukaj geny najbliższe miejscom wiązania czynników transkrypcyjnych (`BEDTools -> ClosestBed`). Jako pierwszy plik wybierz plik z posortowanymi pozycjami czynnika transkrypcyjnego SMARCB1, natomiast w drugim oknie wybierz plik z posortowanymi pozycjami genów. Opcje pozostaw domyślne z wyjątkiem `Ignore Features in B that overlap A`, którą należy ustawić na `Yes`.

Wytnij z powstałej tabeli kolumnę zawierającą identyfikatory genów - kolumna 9 (`Text Manipulation` -> `Cut columns from a table`). Jako warunek wycinania w pozycji `Cut columns` wpisz `c9`.

Otwórz podgląd uzyskanego wyniku i skopiuj listę genów do schowka. Zamieść listę genów w protokole.

> Wskazówka: Podgląd - ikona "oczka" przy nazwie pliku w historii.

Przejdź do strony serwisu [GProfiler](http://biit.cs.ut.ee/gprofiler/index.cgi) i wklej zachowaną listę genów w odpowiednie okno, wybierając organizm *Homo sapiens*. Przeanalizuj uzyskane wyniki pod kątem udziału genów z listy w znanych sieciach regulatorowych.

## Sekwencje powtarzalne
### Zad. 6
#### Identyfikacja elementów powtarzalnych (RepeatMasker)

Otwórz stronę programu [RepeatMasker](http://www.repeatmasker.org) i wybierz serwis `RepeatMasking`. Umieść sekwencję genomową z pliku `genomic.fasta` w polu `Sequence`. W polu `DNA source` wybierz genom człowieka. W zaawansowanych ustawieniach (`Advanced Options`) wybierz `Masking options` > `Repetitive sequences in lower case`. Naciśnij przycisk `Submit sequence`.

1. Ile wynosi procentowy udział wszystkich zidentyfikowanych sekwencji powtarzalnych?
2. Wypisz nazwy elementów powtarzalnych, które zostały zidentyfikowane w sekwencji.
3. Do jakiego typu elementów powtarzalnych należą sekwencje SINE i LINE? 

Otwórz szczegółowe wyniki adnotacji (`Annotation file`).

4. Wypisz sekwencje znalezionych prostych powtórzeń (`Simple repeats`).
5. Podaj miejsce początku i końca elementu LINE w sekwencji zapytania.

Otwórz szczegóły dopasowania sekwencji zapytania ze znalezionymi sekwencjami elementów powtarzalnych (`Alignment file`).

6. Co oznaczają litery `i`, `v` w dopasowaniach? 

> Wskazówka: [pomoc RepeatMasker'a](http://www.repeatmasker.org/webrepeatmaskerhelp.html).

#### Soft-masking
Otwórz wynikową sekwencję genomową (plik `.masked`). 

7. W jaki sposób sekwencje elementów powtarzalnych zostały zamaskowane w sekwencji?

#### Hard-masking
Uruchom ponownie program RepeatMasker. Tym razem z opcji `Masking options` wybierz `Repetetive sequences replaced by string of N`.

8. Na czym polega różnica między maskowaniem sekwencji małymi literami, a ciągami `N` znaków?

#### Zapisywanie wyników
Zapisz zamaskowaną sekwencję genomową w pliku `genomic_masked.fasta` i załącz do protokołu. 


## Przewidywanie genów
### Zad. 7
#### Przewidywanie genów ab initio (FGENESH)

Otwórz program [FGENESH](http://www.softberry.com). Wybierz `Run Programs Online` > `Gene Finding in Eukaryota` > `FGENESH`. Wklej sekwencję `genomic_masked.fasta` i wybierz odpowiedni organizm. Naciśnij `search`.

1. Ile potencjalnych genów zostało zidentyfikowanych w tej sekwencji?
2. Co to jest TSS i PolyA?
3. Z ilu egzonów składa się przewidziany gen?
4. Czy gen został zidentyfikowany na nici + czy -?
5. Zapisz wszystkie zidentyfikowane elementy genu wraz z ich lokalizacją w sekwencji DNA.
6. Ile wynosi długość białka kodowanego przez przewidziany gen?
7. Zapisz sekwencję białka w formacie FASTA do pliku `fgenesh.fa` i załącz do protokołu.


### Zad. 8
#### Przewidywanie genów ab initio (GENSCAN)

Otwórz program [GENSCAN](http://genes.mit.edu/GENSCAN.html). W polu sekwencji wklej tylko sekwencję (bez nagłówka) z pliku `genomic_masked.fasta`. Wybierz odpowiedni organiz i naciśnij `search`.

1. Czym różnią się uzyskane wyniki przewidywań od wyników FGENESH (zad. 7)?
2. Podaj nazwy i lokalizacje wszystkich zidentyfikowanych elementów genów.


### Zad. 9
#### Przewidywanie genów ab initio (Augustus)

Otwórz program [Augustus](http://bioinf.uni-greifswald.de/augustus/submission.php). W polu sekwencji wklej sekwencję FASTA z pliku `genomic_masked.fasta`. Wybierz odpowiedni organizm i naciśnij `Run AUGUSTUS`.

1. Czym różnią się uzyskane predykcje od wyników GENSCAN, FGENESH?
2. Podaj nazwy i lokalizacje wszystkich zidentyfikowanych elementów genów.


## Analiza sekwencji EST
### Zad. 10
#### Wyszukiwanie sekwencji EST

Korzystając z programu NCBI BLAST przeszukaj bazę `Expressed sequence tags (est)` u człowieka, wykorzystując sekwencję z pliku `genomic_masked.fasta` jako zapytanie.

1. O czym świadczy istnienie sekwencji EST dla tej sekwencji genomowej?

Zaznacz najbardziej podobne sekwencje EST (`E-value` ~ 0.0). 

2. Ile takich sekwencji zostało znalezionych?

Zapisz zaznaczone sekwencje (`Download` -> `Fasta (complete sequences)`) i nazwij plik `est.fasta`.

####Składanie sekwencji EST

W celu złożenia krótkich nakładających się sekwencji EST w dłuższe sekwencje (*contigi*) użyj programu [CAP3](http://doua.prabi.fr/software/cap3). W polu sekwencji umieść pobrane sekwencje EST i naciśnij przycisk `Submit`. Otwórz wyniki `Contigs`. 

1. Ile złożonych sekwencji uzyskano? Zapisz każdą z nich w osobnym pliku.

Otwórz szczegóły złożenia (`Assembly details`). 

2. Który contig składa się z większej liczby sekwencji EST?

Otwórz wyniki `Single sequences`.

3. Czy jakieś sekwencje nie zostały uwzględnione w złożeniu?

####Mapowanie sekwencji contigów do genomu

W celu zmapowania sekwencji contigów do sekwencji genomowej `genomic_masked.fasta` użyj programu [Splign](http://www.ncbi.nlm.nih.gov/sutils/splign/splign.cgi?textpage=online&level=form). Wykonaj przyrównanie osobno dla każdego contigu i zapisz ich lokalizację w sekwencji.

1. Czy lokalizacje contigów pokrywają się z predykcjami sekwencji kodujących (CDS) programów przewidywania *ab initio*?
2. O czym świadczy istnienie więcej niż jednego contigu?


## Sekwencje homologiczne
### Zad. 11
#### Wyszukiwanie sekwencji homologicznych 

Korzystając z programu NCBI BLAST dla sekwencji białkowych sprawdź czy w bazie RefSeq znajdują się sekwencje człowieka podobne do białka przewidzianego przez program FGENESH.

1. Jak nazywa się gen, który przewidziałaś/eś?
2. W oparciu o wyniki BLAST sprawdź czy przewidziana sekwencja białkowa została poprawnie wyznaczona?


