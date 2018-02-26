## NCBI

### Zadanie 1
W przeglądarce internetowej otwórz stronę serwisu [NCBI] (https://www.ncbi.nlm.nih.gov). Z rozwijanej listy dostępnych baz danych `All databases` wybierz bazę nukleotydową `Nucleotide`. W polu wyszukiwania wyszukaj rekord o numerze dostępu `NM_001042492`.

1. Podaj typ cząsteczki rekordu (DNA / mRNA / białko / sekwencja genomowa).
2. Jak nazywa się białko kodowane przez ten gen?
3. Z jakiego organizmu pochodzi ten gen?

Wykorzystując panel `Related Information` znajdujący się po prawej stronie przejdź do sekwencji genomowej tego genu `Gene`.

4. Na którym chromosomie znajduje się ten gen?
5. Co przedstawia graficzna mapa znajdująca się w panelu `Genomic regions`, `transcripts`, and `products`?

Wykorzystując panel `Related Information` przejdź do bazy `OMIM`.

6. Wymień trzy jednostki chorobowe powiązane z tym genem.

### Zadanie 2
W bazie `Nucleotide` NCBI wyszukaj sekwencję kontaktyny (ang. *contactin*). Następnie przy pomocy filtrów znajdujących się po lewej stronie, ogranicz wyniki wyszukiwania do cząsteczek mRNA, z bazy danych `RefSeq`, o długości między 4000 a 5000 par zasad, pochodzących od komara (ang. *mosquito*).

1. Ile sekwencji zostało znalezionych?
2. Podaj numery dostępu `Accession number` wszystkich znalezionych rekordów.
3. Z jakiego gatunku komara pochodzą sekwencje?

### Zadanie 3
**Proste wyszukiwanie**
Znajdź sekwencję genu BRCA2 wpisując w polu wyszukiwania bazy `Nucleotide` NCBI frazę **Homo sapiens BRCA2**.

1. Ile rekordów sekwencji znaleziono?

Przejdź do rekordu: `Mus musculus BRCA2 (Brca2) mRNA, complete cds` o numerze dostępu `U65594.1`.

2. Z jakiego organizmu pochodzi ten rekord?
3. Dlaczego rekord znalazł się w wyszukiwaniu?

Wróć do strony z wyszukiwaniem. Aby dowiedzieć się jak Twoje zapytanie zostało zinterpretowane spójrz na pole `Search Details`.

**Zaawansowane wyszukiwanie**
Skorzystaj z zaawansowanego wyszukiwania `Advanced` i skonstruuj tak zapytanie aby znaleźć wszystkie rekordy dotyczące genu BRCA2, pochodzące z człowieka (*Homo sapiens*). 

4. Jak brzmiało Twoje zapytanie (`Search details`)?
5. Ile sekwencji zostało znalezionych?
6. Ile rekordów pochodzi z bazy `GenBank`, a ile z bazy `RefSeq`?
7. Czym różnią się te dwie bazy danych?

### Zadanie 4
Korzystając z zaawansowanego wyszukiwania znajdź w bazie `Gene` wszystkie geny pochodzące od modliszki (ang. *mantis*). Następnie przy pomocy filtrów ogranicz wyniki wyszukiwania do genów kodujących białka (*protein-coding*). 

1. Ile genów zostało znalezionych?
2. Przejdź do rekordu dotyczącego cytochromu b. 
3. Podaj identyfikator tego genu (`Gene ID`).
4. Podaj lokalizację genu (chromosom, pozycja początku i końca)?
5. Jakie geny znajdują się w sądziedztwie (*upstream*, *downstream*)?


## EMBL/EBI - ENA

### Zadanie 5
W bazie [ENA] (https://www.ebi.ac.uk/ena) wyszukaj rekord sekwencji o numerze dostępu `U43746.1`. Podaj nazwę rekordu i typ cząsteczki.

### Zadanie 6
Korzystając z zaawansowanego wyszukiwania znajdź w bazie ENA wszystkie sekwencje mRNA (`Molecule type`), nie dłuższe niż 600 pz (`Base count`), pochodzące od wampira zwyczajnego (`Taxon name` = vampire bat).

1. Ile sekwencji znaleziono?
2. Wybierz rekord dotyczący interferonu alfa 1 (IFNa1).
3. Podaj nazwę naukową organizmu.
4. Podaj długość tej sekwencji.


## UniProt

### Zadanie 7
W serwisie [UniProt] (http://www.uniprot.org) użyj zaawansowanego wyszukiwania i znajdź białka pochodzące z dinozaura *Tyrannosaurus rex*. 

1. Ile rekordów znaleziono?
2. Jakiego białka dotyczą te rekordy?
3. Czy istnienie tych białek zostało potwierdzone doświadczalnie? Uzasadnij swoją odpowiedź.
4. Sekwencje tych białek składają się prawie całkowicie z aminokwasu X. Jak nazywa się ten aminokwas?

### Zadanie 8
Czy w bazie UniProt znajdują się inne rekordy białek należących do dinozaurów?

> Wskazówka: Użyj zaawansowanego wyszukiwania i przeszukaj pole Taxonomy frazą *Dinosauria*.

Jak nazywa się dinozaur, który kryje się pod łacińską nazwą *Gallus gallus*?

### Zadanie 9
Białko rycyna (ang. *ricin*) pochodzące z rącznika pospolitego (*Ricinus communis*) posiada silne właściwości toksyczne, dlatego niejednokrotnie wykorzystywane było jako broń biologiczna. Odszukaj rekord tego białka w bazie UniProt i odpowiedz na pytania.

1. Jaki jest numer dostępu tego białka?
2. W jakich procesach biologicznych bierze udział to białko?
3. Jaka cząsteczka RNA zostaje przerwana przez działanie rycyny?
4. Jaka jest komórkowa lokalizacja tego białka (np. jądro, cytoplazma, mitochondrium)?
5. Podaj numer dostępu tego rekordu w bazie `RefSeq`.
6. *Jaka mutacja w sekwencji aminokwasowej niweluje toksyczne działanie rycyny?

### Zadanie 10
Ile rekordów białek znajduje się w bazie UniProt, które związane są z wirusem grypy *H5N1*, ale nie zawierają słowa ptasia (ang. *avian*)? Ile z tych rekordów zostało poddanych dokładnej weryfikacji przez personel UniProt (tj. należy do bazy UniProt/SwissProt), a ile podlega komputerowym przewidywaniom (tj. należy do bazy UniProt/trEMBL)?


## BioMart

### Zadanie 11
W serwisie YouTube obejrzyj wprowadzenie do aplikacji BioMart (<a target="_blank" href="https://youtu.be/QvGT2G0-hYA">https://youtu.be/QvGT2G0-hYA</a>). Następnie, korzystając z aplikacji BioMart bazy Ensembl podaj liczbę sekwencji kodujących (CDS) wszystkich genów znajdujących się na chromosomie 22 człowieka. 

> Wskazówka: 
>1. Wejdź na stronę [Ensembl] (https://www.ensembl.org/index.html) i z menu wybierz BioMart.
>2. Użyj następujących opcji: `Database` Ensembl Genes, `DataSet` Human genes, `Filters` Region: chromosome 22
>3. Attributes: `Data type` Sequences, `Sequences` Coding sequences, `Header` Gene stable ID, Gene name, Transcript stable ID.   
>4. Przycisk `Results`

