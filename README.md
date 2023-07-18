# SQL

![Screenshot_9](https://github.com/RafayBeatrice/SQL/assets/137804590/d0a43e36-a3c6-45b5-afe0-e5b1f1cd4b00)

![Screenshot_10](https://github.com/RafayBeatrice/SQL/assets/137804590/2ba1a2a4-a885-40c9-aef2-82dbbbdc5fe6)

![Screenshot_11](https://github.com/RafayBeatrice/SQL/assets/137804590/cb7d83ed-f744-40b0-8a35-57a756a1a27b)

![Screenshot_12](https://github.com/RafayBeatrice/SQL/assets/137804590/cb7ccf3b-d123-478e-b615-9b52805592e3)

![Screenshot_13](https://github.com/RafayBeatrice/SQL/assets/137804590/3601bb3f-cb75-4335-9b6b-c6678346998a)

## 1. Proiectaţi o interogare, ce ar afişa denumirea tuturor companiilor.
SELECT  compania 
FROM Companii

## 2. Proiectaţi o interogare, ce ar afişa localitatea şi regiunea tuturor oficiilor.
SELECT localitatea, regiune
FROM Oficii

## 3. Proiectaţi o interogare, ce ar afişa: numele, prenumele tuturor angajaţilor.
SELECT  nume, prenume
FROM Angajati

## 4. Proiectaţi o interogare, ce ar afişa: numele, prenumele tuturor angajaţilor cu titlurile câmpurilor:„Numeangajat” pentru numele angajatului şi „Prenumeangajat” pentru prenumele angajatului.

SELECT nume AS NumeAngajat, prenume AS PrenumeAngajat
FROM Angajati

## 5. Proiectaţi o interogare, ce ar afişa denumirea companiilor ce au datorii mai mici ca 2500 euro.

SELECT compania, datoria 
FROM Companii
WHERE datoria < 2500

## 6. Proiectaţi o interogare, ce ar afişa descrierea şi preţul tuturor produselor ce există la depozit.
    
SELECT descriere, pret
FROM Produse
WHERE exist = 'Da'


## 7. Proiectaţi o interogare, ce ar afişa: numele, prenumele angajaţilor a căror nume conţine litera „o”.

SELECT nume, prenume
FROM Angajati
WHERE nume like '%o%'

## 8. Proiectaţi o interogare, ce ar afişa: numele, prenumele angajaţilor a căror nume incepe cu litera „v”.

SELECT nume, prenume
FROM Angajati
WHERE nume like 'v%'

## 9. Proiectaţi o interogare, ce ar afişa: numele, prenumele angajaţilor a căror nume se sfârşeşte cu litera „a”.

SELECT nume, prenume
FROM Angajati
WHERE nume like '%a'

## 10. Proiectaţi o interogare, ce ar afişa: numele, prenumele şi vârsta celui mai tânăr angajat, a cărui nume incepe cu litera „c”.

SELECT nume, prenume, varsta
FROM Angajati
Where varsta < 25 AND nume LIKE 'c%'
