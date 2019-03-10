# Object-Oriented Programming Homework

## Mod de implementare: 
- Pe prima pagina a aplicatiei se pot observa doua butoane: LOGIN si IESIRE. Al doilea buton pur si simplu inchide aplicatia. Primul buton, cel de login, deschide un JDialog cu doua campuri: User si Pass, pentru a ne autentifica in aplicatie. Cand se apasa butonul de logare se verifica existenta in fisierul users.txt a datelor introduse. Daca acestea au fost introduse corect va aparea pagina de start a aplicatiei pe care se pot observa 4 butoane: Gestiune, Produse, Statistici si Iesire. 
- Apasand butonul de gestiune va aparea o fereastra in care avem posibilitatea de a introduce cele 3 fisiere de test: produse.txt, taxe.txt, facturi.txt si de a crea fisierul de output out.txt. Odata creat, acesta se va deschide pe ecran pentru a verifica corectitudinea datelor si calculelor. Pentru alegerea fisierelor s-a folosit JFileChooser la care am adaugat un filtru pentru a permite doar incarcarea de fisiere cu extensia ".txt". De asemenea avem si un buton Meniu Principal care ne readuce la pagina de start.	  
- Apasand butonul produse se va deschide o fereastra in care avem posibilitatea sa incarcam fisierul de produse (produse.txt) iar acestea vor fi afisate in lista din partea stanga a ferestrei. In cazul in care fisierul de produse nu a fost introdus, butoanele celelalte vor afisa un warning corespuzator. Lista a fost implementata folosit JScrollPane si JList. Totodata, avem posibilitea de a adauga, sterge, edita si cauta un produs. Butoanele de adaugare, editare si cautare vor deschide fiecare cate un JDialog in care se introduc datele dorite. Numele si pretul se introduc in doua JTextField-uri iar pentru categorie si pentru tara de origine am folosit doua JComboBox-uri din care se pot alege datele dorite. Actualizarile se vor reflecta si in fisierul produse.txt. In cazul in care se adauga un produs pentru o anumita tara, preturile pentru celelalte tari vor fi 0. Ex: Se adauga Pateu Mancare RO 4. Linia corespunzatoare din fisierul produse va fi: Pateu Mancare 4.0 0.0 0.0 . De asemenea, avem posibilitatea de a sterge un produs in functie de selectia din lista. In cazul in care nu este selectat niciun produs, se va afisa un warning corespunzator. Iar in cazul in care lista este goala, vom primi o eroare care ne atentioneaza "Lista este goala!". Avem posibilitatea de a sorta elementele din JList dupa denumire si dupa tara de provenienta. Alegerea dintre cele doua se realizeaza folosind JRadioButton. Am creat un o clasa numita ListaProduse care extinde un AbstractListModel pentru a-mi usura sortarea acestei liste. Iar pentru sortarea in sine am folosit Collections.Sort care primeste ca parametru ArrayList-ul de produse si un comparator creat de mine numit ComparatorProduseDenumire sau ComparatorProduseTara in functie de sortarea dorita. De asemenea avem si un buton Meniu Principal care ne readuce la pagina de start. 
 - Apasand butonul Statistici putem vizualiza statisticile dorite din cerinta si anume: magazinul cu cele mai mari vanzari (total cu taxe) si a datelor acestuia, magazinul cu cele mai mari vanzari pentru fiecare tara in parte si a datelor acestuia, magazinul cu cele mai mari vanzari pentru fiecare categorie in parte si a datelor acestuia, factura cu suma totala (fara taxe) cea mai mare. Pentru a afisa a doua si a treia statistica se folosesc doua JComboBox-uri din care se alege tara, respectiv categoria pentru care se doreste afisarea datelor. Iar pentru factura se va afisa denumirea, cele doua totaluri (cu si fara taxe), si magazinul de unde provine acea factura, deoarece exista mai multe facturi cu aceeasi denumire si se puteau crea confuzii. De asemenea avem si un buton Meniu Principal care ne readuce la pagina de start.
- Toate ferestrele sunt implementate folosind JFrame. Majoritatea butoanelor sunt puse pe JPanel-uri ce folosesc ca Layout Manager -> FlowLayout.
- Pentru parsarea fisierului de input am folosit o noua clasa numita Parsare in care se creaza ArrayList-ul de produse si HashMap-ul de taxe. Pentru a citi fisierele linie cu linie s-a folosit un BufferedReader peste un FileReader. Pentru scrierea fisierului out.txt am folosit un BufferedWriter peste un OutputStreamWriter. Pentru a scrie o linie noua in fisier am folosit constructia System.getProperty( "line.separator" ), pentru a nu tine cont de sistemul de operare, in Windows fiind nevoie de "\r\n", iar in Linux doar de '\n'. Clasa gestiune a fost implementat folosit Design Pattern-ul Single Tone iar clasa MagazinFactory a fost implementata folosind Design Pattern-ul Factory. In fisierul java ce contine main-ul am folosit acel try-catch pentru a seta Look and Feel-ul pentru UIManager la Nimbus pentru a face aplicatia mai interesanta. M-am inspirat din Window Builder-ul din NetBeans pentru a face acest lucru. Iar apoi se creaza o instanta a clasei InterfataGrafica pentru a porni interfata grafica a aplicatiei.
- In concluzie, consider ca a fost o tema destul de dificila, dar din care am avut foarte multe lucruri de invatat. Am preferat sa scriu cod de la 0 pentru interfata grafica tocmai pentru a ma familiariza cu Swing si AWT si nu am ales sa folosesc un WindowBuilder. 
