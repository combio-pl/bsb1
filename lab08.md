## Analizy genomowe

## Przeglądarki genomowe - UCSC, Ensembl
### Zad. 1 
#### SNP w mysim genie BRCA1 (UCSC)
Sprawdź jaki wpływ na sekwencję białka mają SNP w mysim genie BRCA1 (*breast cancer type 1 susceptibility protein*).
 
Otwórz stronę serwisu [UCSC Genome Browser](https://www.genome.ucsc.edu/). 

Przywróć ustawienia domyślne (`Genome Browser` -> `Reset all users settings`). 

W zakładce `Genome` wybierz genom myszy (`mouse GRCm38/mm10`). 

Wyszukaj gen BRCA1.

> Wskazówka: Użyj podpowiedzi wyświetlanych podczas wspisywania.

1. Podaj lokalizację genomową tego genu (chromosom, pozycja startu i końca).
2. Z ilu egzonów składa się ten gen?
3. Na której nici występuje ten gen (+ czy -)?

 Zwróć uwagę na ścieżkę `SNPs (142)`. Rozwiń dostępne opcje formatowania tej ścieżki. Zmień następujące opcje: 
	
* Tryb wyświetlania (`display mode`) -> `pack`
* `Coloring options` -> `SNP Feature for Color Specification` -> `Function`
* `Coding-NonSynonymous` -> blue, pozostałe typy -> czarny

4. Co oznacza `Coding-NonSynonymous substitution`? 

Wybierz SNP rs28273098. 

5. Co to jest SNP?
6. Podaj pozycję tego SNP w sekwencji genomowej.

Przejdź do bazy danych `dbSNP`. 

7. Jaka zmiana aminokwasu jest powiązana z tym SNP?

### Zad. 2
#### SNP w mysim genie BRCA1 (Ensembl)
Otwórz stronę serwisu [Ensembl](https://www.ensembl.org) i wybierz genom myszy. 

Wyszukaj gen BRCA1 (*breast cancer type 1 susceptibility protein*). 

Z karty genu przejdź do jego lokalizacji (`Location`). 

Włącz wyświetlanie ścieżki `Sequence variants`.

> Wskazówka: Z menu po lewej wybierz `Configure this page`, następnie wybierz grupę `Variation`. Zaznacz ścieżkę `Sequence variants (dbSNP and all other sources)`, wyświetloną w stylu `expanded with names`.

Znajdź ten sam SNP co w zadaniu 1 (SNP rs28273098). 

>Wskazówka: Nazwy SNP wyświetlane będą jeżeli okno widoku obejmować będzie mniej niż 10 kb sekwencji. 

Jaka jest konsekwencja biologiczna występowania tego wariantu?

### Zad. 3
#### Miejsca wiązania czynnika transkrypcyjnego (UCSC)

W przeglądarce UCSC znajdź w genomie człowieka (`GRCh37/hg19`) gen NRAS (*neuroblastoma RAS viral (v-ras) oncogene homolog*).

Zwiększ wyświetlany obszar o 1000 par zasad z obu stron genu.
 
Znajdź ścieżkę `TFBS Conserved` (grupa `Regulation`) i zmien opcję jej wyświetlania na `full`. 

Wyświetl szczegółowe informacje dotyczące czynnika transkrypcyjnego `V$CDC5_01`. 

Na podstawie bazy UniProt krótko opisz jakie pełni funkcje. 


## Sekwencje powtarzalne
### Zad. 4
#### Identyfikacja elementów powtarzalnych (RepeatMasker)

Otwórz stronę programu [RepeatMasker](http://www.repeatmasker.org) i wybierz serwis `RepeatMasking`. 

Umieść sekwencję genomową z pliku [genomic.fasta](./genomic.fasta) w polu `Sequence`. 

W polu `DNA source` wybierz genom człowieka. 

W zaawansowanych ustawieniach (`Advanced Options`) wybierz `Masking options` > `Repetitive sequences in lower case`. 

Naciśnij przycisk `Submit sequence`.

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


## Przewidywanie genów *ab initio*
### Zad. 5
#### FGENESH

Otwórz program [FGENESH](http://www.softberry.com). 

Wybierz `Run Programs Online` > `Gene Finding in Eukaryota` > `FGENESH`. 

Wklej sekwencję `genomic_masked.fasta` i wybierz odpowiedni organizm. 

Naciśnij `search`.

1. Ile potencjalnych genów zostało zidentyfikowanych w tej sekwencji?
2. Co to jest TSS i PolyA?
3. Z ilu egzonów składa się przewidziany gen?
4. Czy gen został zidentyfikowany na nici + czy -?
5. Zapisz wszystkie zidentyfikowane elementy genu wraz z ich lokalizacją w sekwencji DNA.
6. Ile wynosi długość białka kodowanego przez przewidziany gen?
7. Zapisz sekwencję białka w formacie FASTA do pliku `fgenesh.fasta` i załącz do protokołu.

#### GENSCAN

Otwórz program [GENSCAN](http://genes.mit.edu/GENSCAN.html). 

W polu sekwencji wklej tylko sekwencję (bez nagłówka) z pliku `genomic_masked.fasta`. 

Wybierz odpowiedni organizm i naciśnij `Run GENSCAN`.

8. Czym różnią się uzyskane wyniki przewidywań od wyników FGENESH?
9. Podaj nazwy i lokalizacje wszystkich zidentyfikowanych elementów struktury genów.

#### Augustus

Otwórz program [Augustus](http://bioinf.uni-greifswald.de/augustus/submission.php). 

W polu sekwencji wklej sekwencję FASTA z pliku `genomic_masked.fasta`. 

Wybierz odpowiedni organizm i naciśnij `Run AUGUSTUS`.

10. Czym różnią się uzyskane predykcje od wyników GENSCAN, FGENESH?
11. Podaj nazwy i lokalizacje wszystkich zidentyfikowanych elementów struktury genów.
12. Podaj elementy struktury genów przewidziane przez wszystkie programy (FGENESH, GENSCAN, Augustus)?


## Analiza sekwencji EST
### Zad. 6
#### Wyszukiwanie sekwencji EST

Korzystając z programu NCBI BLAST przeszukaj bazę `Expressed sequence tags (est)` u człowieka, wykorzystując sekwencję z pliku `genomic_masked.fasta` jako zapytanie.

1. O czym świadczy istnienie sekwencji EST dla tej sekwencji genomowej?

Zaznacz najbardziej podobne sekwencje EST (`E-value` ~ 0.0). 

2. Ile takich sekwencji zostało znalezionych?

Zapisz zaznaczone sekwencje (`Download` -> `Fasta (complete sequences)`) i nazwij plik `est.fasta`.

#### Składanie sekwencji EST

W celu złożenia krótkich nakładających się sekwencji EST w dłuższe sekwencje (*contigi*) użyj programu [CAP3](http://doua.prabi.fr/software/cap3). W polu sekwencji umieść pobrane sekwencje EST i naciśnij przycisk `Submit`. Otwórz wyniki `Contigs`. 

3. Ile złożonych sekwencji uzyskano? Zapisz każdą z nich w osobnym pliku.

Otwórz szczegóły złożenia (`Assembly details`). 

4. Który contig składa się z większej liczby sekwencji EST?

Otwórz wyniki `Single sequences`.

5. Czy jakieś sekwencje nie zostały uwzględnione w złożeniu?

#### Mapowanie sekwencji contigów do genomu

W celu zmapowania sekwencji contigów do sekwencji genomowej `genomic_masked.fasta` użyj programu [Splign](http://www.ncbi.nlm.nih.gov/sutils/splign/splign.cgi?textpage=online&level=form). Wykonaj przyrównanie osobno dla każdego contigu i zapisz ich lokalizację w sekwencji.

6. Czy lokalizacje contigów pokrywają się z predykcjami sekwencji kodujących (CDS) programów przewidywania *ab initio*?
7. O czym świadczy istnienie więcej niż jednego contigu?


## Wyszukiwanie sekwencji homologicznych 
### Zad. 7

Korzystając z programu NCBI BLAST dla sekwencji białkowych sprawdź czy w bazie RefSeq znajdują się sekwencje człowieka podobne do białka przewidzianego przez program FGENESH (`fgenesh.fasta`).

1. Jak nazywa się gen, który przewidziałaś/eś?
2. W oparciu o wyniki BLAST sprawdź czy przewidziana sekwencja białkowa została poprawnie wyznaczona.


### Zad. 8

Korzystając z programu NCBI BLAST przeszukaj sekwencje kręgowców w bazie RefSeq stosując jako zapytanie sekwencję białkową uzyskaną w programie FGENESH (`fgenesh.fasta`). Zapisz do pliku `zad8.fasta` po jednej, najwyżej punktowanej sekwencji z następujących organizmów:
   * człowieka (*Homo sapiens*), 
   * szympansa (*Pan troglodytes*),
   * makaka (*Macaca mulatta*),
   * szczura (*Rattus norvegicus*), 
   * myszy (*Mus musculus*), 
   * orki oceanicznej (*Orcinus orca*),
   * rudawki żałobnej (*Pteropus alecto*).

Wykonaj dopasowanie zapisanych sekwencji. Jaki motyw jest najlepiej zachowany?

## Domeny białkowe (Pfam)
### Zad. 9

Zidentyfikuj domeny białkowe wystepujące w sekwencji białkowej przewidzianej przez program FGENESH (`fgenesh.fasta`). Użyj narzędzia [Pfam](http://pfam.xfam.org) -> `Search` -> `Sequence`. 

1. Jaka domena (rodzina) została zidentyfikowana w tym białku?

Przejdź do rekordu. 

2. Ile sekwencji zidentyfikowanych w bazie Pfam posiada tę domenę?
3. W ilu organizmach ją zidentyfikowano?
4. Czy domena występuje w sekwencjach organizmów innych niż kręgowce?

Przejdź do zakładki `HMM logo`.

5. Jaka jest długość sekwencji domeny?
6. Jaki aminokwas i na jakich pozycjach jest najbardziej zachowany?
7. Czy zachowawczość tego aminokwasu jest zbieżna z wynikami, które otrzymaliśmy w zadaniu 8?

### Zadanie dodatkowe*
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
 
Otwórz stronę publicznego serwera [Galaxy](http://usegalaxy.org). 
Zapoznaj się z [wprowadzeniem](https://galaxyproject.org/tutorials/g101/).

* W panelu, z sekcji `Get Data` wybierz odpowiednie narzędzie i prześlij na serwer wcześniej pobranej pliki.
* Posortuj pliki BED (`BEDTools` -> `SortBED`). Uruchom narzędzie dwukrotnie z domyślnymi opcjami wybierając każdy z załadowanych plików.
* Wyszukaj geny najbliższe miejscom wiązania czynników transkrypcyjnych (`BEDTools -> ClosestBed`). Jako pierwszy plik wybierz plik z posortowanymi pozycjami czynnika transkrypcyjnego SMARCB1, natomiast w drugim oknie wybierz plik z posortowanymi pozycjami genów. Opcje pozostaw domyślne z wyjątkiem `Ignore Features in B that overlap A`, którą należy ustawić na `Yes`.
* Wytnij z powstałej tabeli kolumnę zawierającą identyfikatory genów - kolumna 9 (`c9`). Wybierz odowiednie narzędzie z sekcji `Text Manipulation`).
* Otwórz podgląd uzyskanego wyniku i skopiuj listę genów do schowka. Zamieść listę genów w protokole.
* Przejdź do strony serwisu [GProfiler](http://biit.cs.ut.ee/gprofiler/index.cgi) i wklej zachowaną listę genów, wybierając odpowiedni organizm. Przeanalizuj uzyskane wyniki pod kątem związku genów z listy z fenotypem.


