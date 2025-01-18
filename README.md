#MTA GRADER: A New Step in Exam Automation

---

### Cuprins 📑
- [Structura Folderelor](#structura-folderelor)
  - [Singleton](#singleton)
  - [Utilizatori](#utilizatori)
  - [Evaluare](#evaluare)
  - [Fisiere ATM](#fisiere-atm)
- [Utilizare](#utilizare)
- [Concepte Insușite](#concepte-insusite)

---

## Structura Folderelor 🗂️

În fereastra **Solution Explorer**, folderele sunt organizate după cum urmează:

### **Singleton 🧑‍💻**:
- **CFileManager** se ocupă cu gestionarea (citirea/scrierea sau codificarea/decodificarea) tuturor fișierelor text ce vor fi utilizate în cadrul programului.
- **MTAGrader** gestionează instanțele de grupe, studenți și profesori și este responsabilă pentru inițializarea și legătura dintre acestea.

### **Utilizatori 👤**:
- **AUtilizator** este o clasă abstractă din care derivă utilizatorii acestei aplicații (concept folosit: moștenire):
  - **CAdministrator** reprezintă un administrator care are rolul principal de a gestiona datele (profesori/studenți/grupe).
  - **CStudent** reprezintă un student care este asignat unei grupe de studii.
  - **CProfesor** reprezintă un profesor care este asignat unei/unor grupe de studii și poate preda una/mai multe materii.
- **CGrupa** este o clasă concretă care are în compunere o listă de studenți și profesori cu acces permis celor două tipuri de utilizatori la diverse modalități de evaluare alese de profesor.

### **Evaluare 📚**:
- **IEvaluare** este o clasă de tip interfață cu metode pure virtuale din care derivă examenele aplicației.
  - **AEvaluare** este o clasă abstractă derivată din interfață care conține membrii comuni celor 3 clase derivate din ea.
    - **CTema** reprezintă tema pe care un student o poate încărca prin intermediul unor fișiere text.
    - **CTestGrila** reprezintă un examen de tip grilă care poate fi corectat instant după încheierea examenului.
    - **CInterviu** reprezintă un examen sub forma unui dialog între profesor și student prin intermediul unor întrebări oferite secvențial.

### **Fisiere ATM 📂**:
- **GrupeATM.txt** fișier text cu lista numelor grupelor din universitate.
- **ProfesoriATM.txt** fișier text cu lista numelor profesorilor, parolele și materiile predate / grupa la care predau acea materie.
- **StudentiATM.txt** fișier text cu lista numelor de studenți din universitate, parolele și grupa din care fac parte.
- **ExameneSustinuteATM.txt** fișier text de tipul:
    ```
    Nume Student, Grupa Student, Disciplina Evaluată, Nume Profesor, Tip Examen + Nume Fisier Examen
    ```
    În care se salvează, printr-un proces tip backup, informațiile pentru fiecare utilizator ce examene au fost susținute.
- **RezultateATM.txt** fișier text de tipul:
    ```
    Nume Student, Grupa Student, ID Examen, Nota, Comentariu
    ```
    În care se salvează, printr-un proces tip backup, informațiile pentru fiecare utilizator ce notă și comentariu a primit fiecare.

---

## Utilizare 💻

Pentru utilizare:
1. Administratorul creează conturile pentru student și profesor.
2. Se asignează fiecare utilizator la grupa de studii aferentă.
3. Se adaugă din fișierul de backup examenele deja adăugate de utilizatori (profesori) — vezi: **ExameneATM.txt**.
4. Se adaugă din fișierul de backup examenele deja lucrate de câte fiecare student în clasa sa pentru a ști ce examene au rămas de dat — vezi: **ExameneSustinuteATM.txt**.
5. Se adaugă din fișierul de backup rezultatele pentru fiecare examen susținut de către studenți — vezi: **RezultateATM.txt**.
6. Partea de logare și cea mai importantă implică pentru profesor posibilitatea de a adăuga un examen nou sau de a corecta unul deja existent. 
   - Pentru a adăuga un examen, se cere un fișier cu datele cerinței etc.
   - Pentru corectare, se cere ID-ul examenului (îl puteți lua din **ExameneATM.txt**, asta dacă nu ați creat unul nou).

Pentru student:
- Poate vedea ce examene disponibile are.
- Poate vedea ce examene a susținut deja.
- Poate susține un examen (la susținerea unui examen temă, țineți cont că dacă sunt mai multe fișiere vor fi numite "nrfisiere+1" adică fișierul cu toate temele scrise pe o linie și câte un fișier pentru fiecare — vezi: **eticaTemaStefanAndreea.txt**).
- Își poate verifica notele pe baza ID-ului de examen.

---

## Concepte Insușite 💡

Concepte învățate în cadrul acestei teme:
- **Incapsulare**
- **Moștenire**
- **Polimorfism**

---

I hope I did it good! :)
