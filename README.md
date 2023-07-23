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

## 11. Proiectaţi o interogare, ce ar afişa descrierea celui mai scump produs.

SELECT descriere
FROM Produse
WHERE Pret = any( select max(Pret) from Produse)

## 12. Proiectaţi o interogare, ce ar afişa descrierea celui mai ieftin produs.

SELECT descriere
FROM Produse
WHERE Pret = any ( select min(Pret) from Produse)

## 13. Proiectaţi o interogare, ce ar afişa descrierea celui mai scump produs, ce există la depozit

SELECT descriere
FROM Produse
WHERE Pret = any (select max(Pret) from Produse) AND exist = 'Da'

## 14. Proiectaţi o interogare, ce ar afişa descrierea celui mai ieftin produs, ce exista la depozit.

SELECT descriere
FROM Produse
WHERE Pret = any (select min(Pret) from Produse) AND exist = 'Da'

## 15. Proiectaţi o interogare, ce ar afişa descrierea celui mai scump produs, ce nu există la depozit.

SELECT descriere
FROM Produse
WHERE Pret = any (select max(Pret) from Produse) AND exist = 'Nu'

## 16. Proiectaţi o interogare, ce ar afişa descrierea celui mai ieftin produs, ce nu există la depozit.


SELECT descriere
FROM Produse
WHERE Pret = any (select min(Pret) from Produse) AND exist = 'Nu'

## 17. Proiectaţi o interogare, ce ar afişa: numele, prenumele şi funcţia angajatului, căruia i s-a planificat cel mai mult.

SELECT nume, prenume, functia 
FROM Angajati
WHERE [suma planificata] = any (select max( [suma planificata]) FROM Angajati)

## 18. Proiectaţi o interogare, ce ar afişa: numele, prenumele şi funcţia angajatului, căruia i s-a planificat cel mai puţin.

SELECT nume, prenume, functia
FROM Angajati
WHERE [suma planificata] = any (select min( [suma planificata]) FROM Angajati)

## 19. Proiectaţi o interogare, ce ar afişa varsta, nume, prenume , ce sunt mai in varstă de 30 ani.

SELECT varsta , nume ,prenume
FROM Angajati
WHERE Varsta > 30
## 20. Proiectaţi o interogare, ce ar afişa varsta, nume, prenume ce sunt mai în vârstă de 30 ani sau mai tineri de 25 ani.

SELECT varsta, nume ,prenume
FROM Angajati
WHERE varsta < 25 OR varsta > 30

## 21. Proiectaţi o interogare, ce ar afişa: numele, prenumele angajaţilor şi localitatea unde activează in ordinea alfabetică după nume şi prenume.

SELECT nume, prenume, localitatea
FROM Angajati, Oficii
ORDER BY nume, prenume

## 22. Proiectaţi o interogare, ce ar afişa descrierea produselor, ce au fost vândute precum şi cantitatea lor.

SELECT descriere, cantitatea
FROM Produse, Tranzactii

## 23. Proiectaţi o interogare, ce ar afişa: numele, prenumele şi funcţia reprezentanţilor unei singuri companii, in ordinea alfabetică a companiilor.

SELECT  nume, prenume, functia, compania
FROM Angajati, Companii
ORDER BY compania

## 24. Proiectaţi o interogare, ce ar afişa: numele, prenumele, funcţia, localitatea angajatului, care a incheiat contractul de cea mai mare sumă.

SELECT nume ,prenume, functia, localitatea
FROM Angajati, Oficii
WHERE [suma planificata] = any (select min([suma planificata]) FROM Angajati)

## 25. Proiectaţi o interogare, ce ar afişa: numele, prenumele, funcţia, localitatea angajatului, care a incheiat contractul de cea mai mica sumă.

SELECT nume ,prenume, functia, localitatea
FROM Angajati, Oficii
WHERE [suma planificata] = any (select max([suma planificata]) FROM Angajati)

## 26. Proiectaţi o interogare, ce ar afişa: numele, prenumele, data angajării, funcţia şi regiunea angajatului, care a incheiat contractul de cea mai mică sumă.

SELECT nume, prenume, functia ,regiune
FROM Angajati, Oficii
WHERE [suma planificata] = any (select min([suma planificata]) FROM Angajati)

## 27. Proiectaţi o interogare, ce ar afişa: numele, prenumele, vârsta celui mai tânăr reprezentant a unei companii şi denumirea companii pe care o reprezintă.

SELECT nume, prenume, varsta,compania
FROM Angajati, Companii
WHERE varsta = any(select min(varsta) FROM Angajati)

## 28. Proiectaţi o interogare, ce ar afişa: numele, prenumele, varsta celui mai varstnic reprezentant a unei companii şi denumirea companii pe care o reprezintă.

SELECT nume,prenume,varsta,compania
FROM Angajati,Companii
WHERE varsta = any(select max(varsta) FROM Angajati)

## 29. Proiectaţi o interogare, ce ar introduce in baza de date un angajat nou cu numele Ciobanu şi prenumele Vasile.

INSERT INTO Angajati ([cod-angajat],nume,prenume,varsta,functia)
VALUES(5,'Ciobanu','Vasile',56,'macelar')

## 30. Proiectaţi o interogare, ce ar introduce in baza de date o companie nouă cu denumirea Dumbrava Nord, ce are datorii în sumă de 3 000 euro.

INSERT INTO Companii ([cod-companie],compania,[reprezentantul companiei],datoria)
VALUES(7,'Dumbrava Noua',5,3000)

## 31. Proiectaţi o interogare, ce ar introduce in baza de date un produs nou, ce există la depozit cu descrierea „telefon Nokia 32”, cu preţul de 105 euro.

INSERT INTO Produse ([cod-produs],descriere,pret,exist)
VALUES(6,'telefon NOKIA 32',105,'Da')

## 32. . Proiectaţi o interogare, ce ar mări suma acumulată a angajatului Cristescu Iulian cu 5 000 euro.

UPDATE Angajati
SET [suma planificata] = '5000'
WHERE [cod-angajat] = 1

