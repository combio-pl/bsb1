## Analiza filogenetyczna


### Zad. 1 
### Rekonstrukcja filogenetyczna genu RBP3
Gen białka wiążącego retinoid (**RBP3**) jest dobrze zachowany u kręgowców. Poniżej znajduje się sekwencja białkowa kodowana przez ten gen u człowieka.

```
>gi|4506453|ref|NP_002891.1| retinol-binding protein 3 precursor [Homo sapiens]
MMREWVLLMSVLLCGLAGPTHLFQPSLVLDMAKVLLDNYCFPENLLGMQEAIQQAIKSHEILSISDPQTL
ASVLTAGVQSSLNDPRLVISYEPSTPEPPPQVPALTSLSEEELLAWLQRGLRHEVLEGNVGYLRVDSVPG
QEVLSMMGEFLVAHVWGNLMGTSALVLDLRHCTGGQVSGIPYIISYLHPGNTILHVDTIYNRPSNTTTEI
WTLPQVLGERYGADKDVVVLTSSQTRGVAEDIAHILKQMRRAIVVGERTGGGALDLRKLRIGESDFFFTV
PVSRSLGPLGGGSQTWEGSGVLPCVGTPAEQALEKALAILTLRSALPGVVHCLQEVLKDYYTLVDRVPTL
LQHLASMDFSTVVSEEDLVTKLNAGLQAASEDPRLLVRAIGPTETPSWPAPDAAAEDSPGVAPELPEDEA
IRQALVDSVFQVSVLPGNVGYLRFDSFADASVLGVLAPYVLRQVWEPLQDTEHLIMDLRHNPGGPSSAVP
LLLSYFQGPEAGPVHLFTTYDRRTNITQEHFSHMELPGPRYSTQRGVYLLTSHRTATAAEEFAFLMQSLG
WATLVGEITAGNLLHTRTVPLLDTPEGSLALTVPVLTFIDNHGEAWLGGGVVPDAIVLAEEALDKAQEVL
EFHQSLGALVEGTGHLLEAHYARPEVVGQTSALLRAKLAQGAYRTAVDLESLASQLTADLQEVSGDHRLL
VFHSPGELVVEEAPPPPPAVPSPEELTYLIEALFKTEVLPGQLGYLRFDAMAELETVKAVGPQLVRLVWQ
QLVDTAALVIDLRYNPGSYSTAIPLLCSYFFEAEPRQHLYSVFDRATSKVTEVWTLPQVAGQRYGSHKDL
YILMSHTSGSAAEAFAHTMQDLQRATVIGEPTAGGALSVGIYQVGSSPLYASMPTQMAMSATTGKAWDLA
GVEPDITVPMSEALSIAQDIVALRAKVPTVLQTAGKLVADNYASAELGAKMATKLSGLQSRYSRVTSEVA
LAEILGADLQMLSGDPHLKAAHIPENAKDRIPGIVPMQIPSPEVFEELIKFSFHTNVLEDNIGYLRFDMF
GDGELLTQVSRLLVEHIWKKIMHTDAMIIDMRFNIGGPTSSIPILCSYFFDEGPPVLLDKIYSRPDDSVS
ELWTHAQVVGERYGSKKSMVILTSSVTAGTAEEFTYIMKRLGRALVIGEVTSGGCQPPQTYHVDDTNLYL
TIPTARSVGASDGSSWEGVGVTPHVVVPAEEALARAKEMLQHNQLRVKRSPGLQDHL
```

#### Wyszukiwanie sekwencji ortologicznych
Wyszukaj sekwencje RBP3 innych kręgowców pochodzące z bazy RefSeq. 
W opcjach algorytmu (`Algorithm parameters`) zwiększ maksymalną liczbę wynikowych sekwencji z `100` do `250`.

Do dalszej analizy wybierz po jednym - najwyżej punktowanym - białku: 
   * myszy (*Mus musculus*), 
   * szczura (*Rattus norvegicus*), 
   * makaka (*Macaca mulatta*), 
   * szympansa (*Pan paniscus*),
   * kurczaka (*Gallus gallus*),
   * krowy (*Bos taurus*),
   * żaby (*Xenopus laevis*),
   * danio pręgowatego (*Danio rerio*),
   * człowieka.
Zapisz wybrane sekwencje w formacie FASTA do pliku `vertebrates.fasta`.

#### Przygotowanie nazw sekwencji do wyświetlenia na drzewie
W edytorze tekstu zamień identyfikatory sekwencji z pliku `vertebrates.fasta` na odpowiednie nazwy gatunkowe (nie używając polskich znaków).

   Przykład:
   ```
   >NP_002891.1 retinol-binding protein 3 precursor [Homo sapiens]
   ```
   zamień na
   ```
   >czlowiek NP_002891.1 retinol-binding protein 3 precursor [Homo sapiens]
   ```

#### Dopasowanie sekwencji
Wykonaj dopasowanie sekwencji (`vertebrates.fasta`) i zapisz je do pliku `vertebrates.aln`

1. Które części dopasowania, Twoim zdaniem, nie będą pomocne w analizie filogenetycznej?

#### Budowa drzewa filogenetycznego
* Otwórz aplikację BioNJ (<a href="http://phylogeny.lirmm.fr/phylo_cgi/phylogeny.cgi">http://phylogeny.lirmm.fr/phylo_cgi/phylogeny.cgi</a>).
* Wybierz zaawansowany typ analizy (`Advanced`).
* Odznacz krok związany z dopasowaniem (`Multiple Alignment`).
* Naciśnij przycisk `Create Workflow`.
* W polu tekstowym wklej dopasowanie sekwencji.
* Naciśnij przycisk `Submit`.

### Odczytywanie relacji filogenetycznych na drzewie
2. Które pary gatunków są bliżej ze sobą spokrewnione na filogramie: 
   * człowek z szympansem
   * mysz ze szczurem
   * ryba z żabą?

Uzyskane drzewo umieść w protokole. 

Skorzystaj z opcji `reroot (outgroup)` aby ustawić takson **ryby** jako grupę zewnętrzną (`outgroup`). Uzyskane drzewo umieść w protokole. 

Użyj opcji `Swap subtrees` i dokonaj odwrócenia taksonu myszy i szczura. Uzyskane drzewo umieść w protokole.

3. Czy drzewo odpowiada aktualnie przyjętej systematyce kręgowców?

### Tekstowy format zapisu drzew filogenetycznych
Naciśnij na odsyłacz `Tree in Newick format`. 

4. Jakie informacje zawiera ten format zapisu drzewa?


## Zad. 2 
## Sprawa kryminalna
W latach 90’ u ośmiu pacjentów dentysty z Florydy chorego na AIDS zdiagnozowano wirus HIV (HIV+). Mimo, że dentysta przeprowadzał inwazyjne procedury dentystyczne (np. leczenie kanałowe, ekstrakcja zębów) śledztwo przeprowadzone przez amerykańską agencję epidemiologiczną nie wykazało istotnych uchybień w postępowaniu zapewniającym bezpieczeństwo i higienę wykonywanych zabiegów.

W celu ustalenia źródła zakażenia wirusem HIV, wyizolowałeś/aś wirusowe RNA z próbek krwi należących do: 

* dentysty, 
* żony dentysty chorej na AIDS, 
* pacjentów dentysty chorych na AIDS oraz 
* innych osób z okolicy Florydy zakażonych wirusem HIV, którzy nie mieli kontaktu z dentystą (*local group*). 

Sekwencje wirusowego białka gp120, które otrzymałeś, znajdują się w pliku [HIV_data_set.fasta](./HIV_data_set.fasta).

---

Otwórz program MEGA7 zainstalowany na komputerze.

### Dopasowanie sekwencji
Otwórz w programie sekwencje znajdujące się w pliku `HIV_data_set.fasta` (`Align` > `Edit/Build Alignment` > `Retrieve sequences from a file`). Zaznacz wszystkie sekwencje i przeprowadź ich dopasowanie (`Alignment` > `Align by ClustalW`) korzystając z domyślnych ustawień.

1. Jaka jest długość dopasowania?
2. Ile jest pozycji w dopasowaniu, w których aminokwas zachowany jest we wszystkich sekwencjach?


### Analiza filogenetyczna
W oknie dopasowania sekwencji wybierz z menu `Data` > `Phylogenetic Analysis`. W głównym oknie programu MEGA wygeneruj drzewo używając algorytmu *Neighbor-Joining (NJ)* (`Analysis` > `Phylogeny` > `Construct Neighbor-Joining tree`). W opcjach `Test of Phylogeny` ustaw `None`. Naciśnij przycisk `Compute`. Uzyskane drzewo umieść w protokole. 

3. Czy uważasz, że dentysta z Florydy mógł zakazić któregokolwiek z ośmiu pacjentów?
4. W jakim celu pobrano materiał genetyczny od osób zarażonych HIV nie mających kontaktu z dentystą (`Local Controls`)?


### Formatowanie i ukorzenianie drzewa
Wyświetl drzewo w formie kladogramu (`View` > `Topology only`). Uzyskane drzewo umieść w protokole. 

5. Jaka jest różnica pomiędzy filogramem, a kladogramem?

Zmodyfikuj tak drzewo, żeby jego korzeniem była gałąź prowadząca do białka gp120 Dentysty. Uzyskane drzewo umieść w protokole. 

Użyj funkcji `Subtree` > `Compress/Expand` i ukryj klad składający się z taksonów `local control 1-5` i `PATIENT D`. Umieść drzewo w protokole. 

### Macierz dystansów
Oblicz odległości w dopasowaniu par sekwencji analizowanych białek gp120 (główne okno programu > `Analysis` > `Distance` > `Compute Pairwise`).

6. Która para białek gp120 jest najbliżej, a która najdalej spokrewniona?


## Zadanie 3 
## Badanie początków powstania wirusa HIV
AIDS (*Acquired Immune Deficiency Syndrome*) może być wywołany dwoma różnymi wirusami: **HIV-1** (odpowiedzialny za globalną pandemię) oraz **HIV-2** (mniej wirulentny i do niedawna zakres jego występowania ograniczony był jedynie do Afryki Zachodniej). 

Do pierwszych zakażeń wirusem HIV u człowieka doszło w Afryce najprawdopodobniej między 1910 a 1930 rokiem. Wirusy spokrewnione z HIV znalezione zostały również u wielu innych gatunków naczelnych i zostały one nazwane **SIV**. 

Występujące w cząsteczce wirusa białko gp120 jest odpowiedzialne za łączenie się cząsteczek wirusa do komórek gospodarza. W pliku [gp120.fasta](./gp120.fasta) znajduje się dopasowanie sekwencji 27 białek gp120 różnych naczelnych. 

### Badanie wiarygodności rozgałęzienia drzewa - bootstrap (pseudoreplikacje)
Korzystając z programu MEGA zbuduj drzewo filogenetyczne wraz z analizą bootstrap (`Phylogeny` > `Contruct NJ tree` > `Test of Phylogeny` > `Bootstrap method; No. of bootstrap replications: 100`).

1. Jakie są relacje między wirusami HIV-1, HIV-2 oraz SIV?
2. Co oznaczają liczby znajdujące się na węzłach uzyskanego drzewa?
3. Czy podział drzewa na dwie grupy monofiletyczne jest wiarygodny?
4. Czy na drzewie znajdują się grupy sekwencji o niskim poziomie ufności?


## Zad. 4
## Drzewo gatunków: analiza mitochondrialnego DNA
Plik [mito.fasta](./mito.fasta) zawiera dopasowanie sekwencji mitochondrialnego DNA pochodzące z człowiekokształtnych i innych naczelnych. Korzystając z programu MEGA utwórz drzewa filogenetyczne opisujące relacje między tymi sekwencjami używając 4 metod filogenetycznych z analizą bootstrap (50 pseudoreplikacji):

1. Neighbor-Joining
2. Maximum Likelihood
3. Minimum Evolution
4. Maximum Parsimony

---
Umieść w protokole drzewa otrzymane wszystkimi metodami filogenetycznymi. 

1. Czy topologie drzew uzyskane powyższymi  metodami znacznie się różnią?
2. Które węzły są najbardziej wiarygodne (100% bootstrap) we wszystkich drzewach?
3. Które grupy współczesnych ludzi są ze sobą najbliżej spokrewnionie?
4. Jaki gatunek naczelnych (inny niż neandertalczyk) jest najbliżej spokrewniony z współczesnym człowiekiem?
5. Czy topologia drzewa potwierdza teorię "Wyjścia z Afryki" (*Out of Africa theory*)?

