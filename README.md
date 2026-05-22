Zadania proste
1. ✏ Zadanie 1 – Usuwanie zadań (Raw SQL)
Dodaj do aplikacji app_raw_sql.py opcję menu "Usuń zadanie". Zaimplementuj funkcję
usun_zadanie(id_zadania) w database_raw.py, która użyje zapytania DELETE FROM
zadania WHERE id = ?.
(proste)
2. ✏ Zadanie 2 – Usuwanie zadań (SQLAlchemy)
Zrób to samo dla aplikacji app_orm.py. Funkcja w warstwie danych powinna znaleźć obiekt
zadania, a następnie użyć db.delete(obiekt_zadania) i db.commit().
(proste)
3. ✏ Zadanie 3 – Wyświetlanie ID
Zmodyfikuj funkcję pokaz_zadania w obu aplikacjach tak, aby oprócz opisu i statusu,
wyświetlała również ID każdego zadania. (W wersji ORM już to zrobiliśmy, upewnij się, że
wiesz dlaczego to działa).
(proste)
4. ✏ Zadanie 4 – Dodanie priorytetu (Raw SQL)
Ręcznie zmodyfikuj tabelę zadania w database_raw.py (w funkcji init_db), dodając kolumnę
priorytet INTEGER DEFAULT 1. Następnie zaktualizuj funkcję dodaj_zadanie, aby
przyjmowała nowy argument i zapisywała go w bazie.
(proste)
5. ✏ Zadanie 5 – Dodanie daty utworzenia (SQLAlchemy)
W pliku sqlalchemy_app/models.py, do klasy Zadanie dodaj nową kolumnę:
data_utworzenia = Column(DateTime, default=datetime.datetime.utcnow). Nie zapomnij o
imporcie from sqlalchemy import DateTime i import datetime. Następnie wygeneruj i
zastosuj nową migrację Alembic.
6. 🧠 Zadanie 6 – Wyszukiwanie po opisie (Raw SQL)
Dodaj do aplikacji app_raw_sql.py funkcję wyszukiwania zadań. Użytkownik podaje frazę, a
program wyświetla wszystkie zadania, których opis zawiera tę frazę. Użyj operatora LIKE i
wzorca %fraza% w zapytaniu SELECT.
(challenge)
7. 🧠 Zadanie 7 – Wyszukiwanie po opisie (SQLAlchemy)
Zaimplementuj tę samą funkcjonalność w aplikacji ORM. Użyj metody .filter() oraz metody
.contains() na kolumnie, np. db.query(Zadanie).filter(Zadanie.opis.contains(fraza)).all().
(challenge)
8. 🧠 Zadanie 8 – Refaktoryzacja do klas (Raw SQL)
Przepisz aplikację app_raw_sql.py i database_raw.py używając klas. Stwórz klasę
TaskManagerRaw, która w konstruktorze inicjalizuje bazę, a jej metody (dodaj, pobierz itd.)
wykonują operacje na bazie.
(challenge)
9. 🧠 Zadanie 9 – Dodanie tagów do zadań (SQLAlchemy)
Rozbuduj aplikację ORM o system tagów. Będziesz potrzebować:
a. Nowego modelu Tag (id, nazwa).
b. Tabeli pośredniej do obsługi relacji wiele-do-wielu między zadaniami a tagami.
c. Zdefiniowania relacji relationship w modelach Zadanie i Tag.
d. Wygenerowania i zastosowania migracji.
e. Zmodyfikowania logiki aplikacji, aby można było dodać taga do zadania.
(challenge)
10. 🧠 Zadanie 10 – Interaktywna edycja (dowolna aplikacja)
W wybranej przez siebie aplikacji (Raw SQL lub ORM) dodaj funkcję "Edytuj zadanie". Po
jej wybraniu, użytkownik powinien podać ID zadania, a następnie wpisać nowy opis.
Zaktualizuj odpowiedni wpis w bazie danych.
