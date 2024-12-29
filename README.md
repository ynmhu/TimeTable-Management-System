Frissítés a time_table.sql fájlban

A következő frissítéseket és módosításokat végeztük el az adatbázis struktúráján, hogy biztosítsuk a kompatibilitást és a hatékony működést MariaDB alatt:

Táblák átalakítása InnoDB-re: Az adatbázis motorját a MyISAM-ról InnoDB-re módosítottuk a következő táblák esetében:

[https://](https://forum.ynm.hu/t/timetable-management-system-fixed-sql/269)

admin

alloc_slots

assigned_course

lecturer

courses

rooms

slots

slot_allocs

Módosítás: Eredeti: ENGINE=MyISAM Módosított: ENGINE=InnoDB

Idegen kulcsok hozzáadása: Az adatbázis integritásának biztosítása érdekében idegen kulcsokat (foreign keys) adtunk hozzá, amelyek biztosítják az adatok közötti kapcsolatok épségét.

slot_allocs tábla esetében a következő idegen kulcsokat adtuk hozzá:

course_id hivatkozás a courses táblára

room_id hivatkozás a rooms táblára

table_name, day, slot_num hivatkozás a slots táblára

Adatbeillesztések és inicializálások: A szükséges adatokat beillesztettük az admin, alloc_slots, assigned_course, és más táblákba, hogy biztosítsuk a megfelelő működést és tesztelhetőséget.

Összegzés: A módosítások eredményeként az adatbázis mostantól hatékonyabban működik MariaDB alatt, kihasználva az InnoDB által nyújtott előnyöket, mint a tranzakciók kezelése, az adat integritás biztosítása, és a jobb egyidejű írási teljesítmény. Az idegen kulcsok hozzáadásával az adatok közötti kapcsolatok is biztosítottak, így az adatbázis könnyebben kezelhető és fenntartható.

[https://](https://forum.ynm.hu/t/timetable-management-system-fixed-sql/269)
