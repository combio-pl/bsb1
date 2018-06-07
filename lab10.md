## Analiza strukturalna RNA

### Zadanie 1
Zidentyfikuj poniższą sekwencję wykorzystując *Sequence search* w bazie [Rfam](http://rfam.xfam.org/).

```
>UTR
UGAUCUCUGUAUUUGUUUCUAUUUUGAACAUUUGCCUGCUACCUUGGCAUAACAUCAAUAAGGUACAAA
CAUCGCAAAAAGUCAUCAUAAGGUGGGUUUUAGUACGUAGGCGCUGUAGAACUUAAUUGUUCUGAUAGA
GCAGCGAGUCGUGCAUGCUAGUCUAGCAUUUCUUGCUACCUAGUAUCUUUAGAAGAUUUCCCUCCCUUA
GCGGUCAAA
```

1. Podaj *Accession number* rekordu.
2. Jaki to RNA?  
3. W ilu organizmach zidentyfikowano ten element? 

### Zadanie 2
Za pomocą programu [RNAstructure](https://rna.urmc.rochester.edu/RNAstructureWeb/) wykonaj przewidywanie struktury drugorzędowej RNA z zadania 1.

1. Jakie elementy struktury drugorzędowej RNA zostały przewidziane?
2. Ile wynosi minimalna swobodna energia dla tej struktury?
3. Jak oznaczone są zasady, których prawdopodobieństwo sparowania/niesparowania wynosi min. 99%?
4. Zapisz strukturę (plik PNG) i załącz do protokołu. 

### Zadanie 3
Za pomocą programu [mfold](http://unafold.rna.albany.edu/?q=mfold/RNA-Folding-Form) wykonaj przewidywanie struktury drugorzędowej RNA z zadania 1.

1. Czy struktura jest zgodna z przewidywaniami programu RNAstructure?
2. Ile wynosi minimalna swobodna energia dla tej struktury?
3. Zapisz strukturę (plik PNG) i załącz do protokołu. 

### Zadanie 4
Za pomocą programu [RNAfold](http://rna.tbi.univie.ac.at//cgi-bin/RNAWebSuite/RNAfold.cgi) wykonaj przewidywanie struktury drugorzędowej RNA z zadania 1.

1. Czy struktura jest zgodna z przewidywaniami programu RNAstructure oraz mfold?
2. Ile wynosi minimalna swobodna energia dla tej struktury?
3. Zapisz strukturę w formacie dot bracket.
4. Zapisz strukturę (plik PDF) i załącz do protokołu. 

### Zadanie 5
Za pomocą programu [RNAbows](http://rna.williams.edu/rnabows/) (*AllPairs*) wykonaj przewidywanie struktury drugorzędowej RNA z zadania 1. 

1. Ile wynosi minimalna swobodna energia dla tej struktury?
2. Co odzwierciedla grubość linii łuków?
3. Zapisz dowolny element struktury w formacie dot bracket. 
4. Zapisz strukturę (plik PDF) i załącz do protokołu.

### Zadanie 6
Zapisz przykładową sekwencję RNA, którą opisuje poniższa struktura drugorzędowa w formacie dot bracket:

```
((((.(((......)))...(((((...)))))..((((....))))))))
```

Za pomocą programu [RNAfold](http://rna.tbi.univie.ac.at//cgi-bin/RNAWebSuite/RNAfold.cgi) wykonaj przewidywanie jej struktury drugorzędowej. 

1. Ile wynosi minimalna swobodna energia dla tej struktury?
2. Czy przewidziana struktura jest zgodna ze strukturą zapisaną w formacie dot bracket?
3. Zapisz strukturę (plik PDF) i załącz do protokołu. 

Za pomocą programu [RNAinverse](http://rna.tbi.univie.ac.at/cgi-bin/RNAWebSuite/RNAinverse.cgi) wyszukaj inną sekwencję, która może przyjąć strukturę drugorzędową zapisaną w formacie dot bracket. 

>Wskazówka: W sekcji `Fold algorithms and basic options` zaznacz opcję `minimum free energy (MFE) only`

4. Zapisz uzyskaną sekwencję.
5. Ile wynosi minimalna swobodna energia dla tej struktury?

>Wskazówka: `Submit this sequence to our RNAfold Webserver (...)`

### Zadanie 7
Poniżej znajdują się 2 sekwencje RNA. 

```
>trna
AGUGGUUCACAGGUAGCUCAGAUGGUUAGAGCAAAGGACUGUAAAUCCUUGUGUUAGUGGUUCGAUUCCACAACCACU
>tls
GGGCAUUUGGUCUAGUGGUAUGAUUCUCGCUUAGGGUGCGAGAGGUCCCGAGUUCAAUUCUCGGAAUGCCCC
```

Za pomocą programu [RNAfold](http://rna.tbi.univie.ac.at//cgi-bin/RNAWebSuite/RNAfold.cgi) wykonaj przewidywanie struktury drugorzędowej obu sekwencji. 

Zwizualizuj obie struktury wykorzystując program [forna](http://rna.tbi.univie.ac.at/forna/).

>Wskazówka: `Add Molecule` -> `Add Sequence and Secondary Structure` -> wklej obie sekwencje wg wzoru -> `Submit`
 
1. Czy struktury mają wspólne elementy?
2. Zapisz struktury (plik PNG) i załącz do protokołu. 

### Zadanie 8
W pliku [trna_szczur.fasta](./trna_szczur.fasta) znajdują się sekwencje tRNA szczura. Wykonaj przyrównanie tych sekwencji. 

1. Jakiego programu użyłaś/eś? 
2. Ile zasad nie jest zachowanych we wszystkich sekwencjach?

Wykorzystując program [RNAalifold](http://rna.tbi.univie.ac.at//cgi-bin/RNAWebSuite/RNAalifold.cgi) wykonaj przewidywanie struktury drugorzędowej.

3. Ile regionów sparowanych (*stem*) zostało przewidzianych?
4. Ile wynosi minimalna swobodna energia dla struktury?
5. Czy wyniki są zgodne z wynikami przyrównania?
6. Zapisz strukturę w formacie dot bracket i załącz do protokołu. 

### Zadanie 9
Poniżej znajduje się fragment sekwencji DNA. 

```
>DNA_9
acccgcgcacgcacacatgctgataacagccccgacccccggcgggagccaca
```

1. Z jakiego organizmu pochodzi ta sekwencja? 
2. Jakiego genu jest to fragment? Podaj pozycję startu i końca fragmentu w tym genie.
3. Zapisz w formacie FASTA sekwencję białka, kodowanego przez ten gen, zamieszczając w nagłówku *Accession number* rekordu białkowego.
4. Wykorzystując dowolny program (`RNAfold`, `mfold`, `RNAstructure`) wykonaj przewidywanie struktury drugorzędowej RNA. 
5. Ile wynosi minimalna swobodna energia dla przewidzianej struktury? 

### Zadanie 10
W pliku [trna_scan.fasta](./trna_scan.fasta) znajduje się fragment sekwencji genomowej. Za pomocą programu [tRNAscan-SE](http://lowelab.ucsc.edu/tRNAscan-SE/index.html) sprawdź czy zawiera on sekwencje tRNA. 

1. Ile tRNA zostało przewidzianych?
2. Jakie tRNA zostały przewidziane?

Przejdź do listy podobnych treoninowych tRNA w bazie GtRNAdb (`Similar tRNAs in GtRNAdb`).

3. Zapisz sekwencję tRNA w formacie FASTA.
4. Jaką długość ma tRNA człowieka uwzględniony w wyszukiwaniu?

Wyświetl tRNA z pkt. 4 w przeglądarce genomowej UCSC. 

5. Podaj lokalizację tRNA na chromosomie. 

Zmodyfikuj ścieżkę `Conservation` tak, aby zawierała informację dotyczące tRNA u następujących organizmów: szympans, mysz, świnia, słoń, pancernik, kurczak, jaszczurka, danio pręgowany.

6. W których organizmach występuje tRNA podobny do analizowanego?




