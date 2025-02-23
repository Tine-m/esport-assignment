# **Obligatorisk afleveringsopgave: E-sports turneringsplatform (Assignment 1 - 20 study points)**

## **🎯 Opgavens Formål**
I denne opgave skal du **designe og implementere en database** til en **E-sports Turneringsplatform** ved hjælp af **MySQL** (eller anden selvvalgt relationel database). Du skal:
- **Definere en relationel database ud fra en given datamodel.**
- **Udarbejde SQL-scripts til at oprette tabeller, indsætte data og forespørgsler på databasen.**
- **Implementere stored Procedures, functions og triggers.**
- **Bruge databasen fra en applikation via JDBC/ORM (JPA).**
---

## **1️⃣ Databasedesign og oprettelse af databasen**
### **Baggrund**
E-sports turneringsplatformen giver brugere mulighed for at **deltage i turneringer**, **oprette hold**, og **se resultater**.

### **Datamodel**
E-sports turneringsplatformen skal have følgende tabeller:
- **`Players`**: Indeholder oplysninger om spillere (player_id, username, email, ranking, created_at).
- **`Tournaments`**: Indeholder oplysninger om turneringer (tournament_id, name, game, max_players, start_date, created_at).
- **`Tournament_Registrations`**: Registrerer hvilke spillere, der deltager i hvilke turneringer (registration_id, tournament_id, player_id, registered_at).
- **`Matches`**: Registrerer kampe i turneringerne (match_id, tournament_id, player1_id, player2_id, winner_id, match_date).

📌 **Din opgave:**
1. **Bestem datatyper og constraints** (PK, FK, NOT NULL osv.).
2. **Udarbejd et SQL-script** til at oprette databasen og indsæt testdata i tabellerne.

---

## **2️⃣ SQL-Forespørgsler**
Udarbejd SQL-forespørgsler til følgende:
1. Hent alle turneringer, der starter inden for de næste 30 dage.
2. Find det antal turneringer, en spiller har deltaget i.
3. Vis en liste over spillere registreret i en bestemt turnering.
4. Find spillere med flest sejre i en bestemt turnering.
5. Hent alle kampe, hvor en bestemt spiller har deltaget.
6. Hent en spillers tilmeldte turneringer.
7. Find de 5 bedst rangerede spillere.
8. Beregn gennemsnitlig ranking for alle spillere.
9. Vis turneringer med mindst 5 deltagere.
10. Find det samlede antal spillere i systemet.
11. Find alle kampe, der mangler en vinder.
12. Vis de mest populære spil baseret på turneringsantal.
13. Find de 5 nyeste oprettede turneringer.
14. Find spillere, der har registreret sig i flere end 3 turneringer.
15. Hent alle kampe i en turnering sorteret efter dato.

📌 **Din opgave:**
- Skriv de nødvendige **SQL-forespørgsler**.
- Test forespørgslerne i MySQL - husk at dokumenterere resultatet.

---

## **3️⃣ Stored procedures, functions og triggers**
For at automatisere platformens funktioner skal du implementere:

### **Stored Procedures:**
1. **`registerPlayer`** – Registrer en ny spiller.
2. **`joinTournament`** – En spiller tilmelder sig en turnering.
3. **`submitMatchResult`** – Registrer en kamps resultat.

### **Functions:**
1. **`getTotalWins(player_id)`** – Returnerer antal sejre for en spiller.
2. **`getTournamentStatus(tournament_id)`** – Returnerer turneringens status (upcoming, ongoing, completed), 

### **Triggers:**
1. **`beforeInsertRegistration`** – Sikrer, at en turnering ikke overskrider max antal spillere.
2. **`afterInsertMatch`** – Opdaterer rang for spillere efter en kamp.

📌 **Din opgave:**
- Implementer disse Stored Procedures, functions og triggers.
- Test dem med forskellige scenarier. Husk at dokumentere resultatet.

---

## **4️⃣ Brug af Databasen fra en Applikation (JDBC/ORM)**
Du skal udvikle en simpel **applikation**, der interagerer med databasen via en applikation. Hvis du bruger Java kan det være **JDBC eller JPA**.

📌 **Din opgave:**
1. **Implementér en JDBC-baseret løsning**:
   - Opret forbindelse til MySQL.
   - Kald stored procedures (`JoinTournament`, `SubmitMatchResult`).
   - Udfør SQL-forespørgsler via `PreparedStatement`.

2. **Implementér en ORM-baseret løsning (JPA/Hibernate)**:
   - Definer `Entity`-klasser for `Players`, `Tournaments`, `Matches`.
   - Brug `EntityManager` til CRUD-operationer.
   - Kald stored procedures via JPA (`@NamedStoredProcedureQuery`).

---

## **📌 5️⃣ Aflevering**
### **📁 Du skal aflevere:**
1. **SQL-scriptet** med databaseoprettelse.
2. **15 SQL-forespørgsler**.
3. **Stored Procedures, Functions og Triggers**.
4. **Java-applikationen (JDBC + JPA)**.
5. **Kort dokumentation** om hvordan løsningen fungerer.

---

## **📌 Vurderingskriterier**
| **Kriterie** | **Vurdering** |
|-------------|--------------|
| Databaseoprettelse | Rigtigt design, brug af constraints |
| SQL-forespørgsler | Effektivitet, korrekt resultat |
| Stored Procedures, Functions, Triggers | Funktionalitet og anvendelighed |
| Applikation | Funktionalitet, korrekt brug af JDBC/JPA |
| Dokumentation | Klarhed, beskrivelse af implementering |

---

🎯 **God fornøjelse med opgaven!** 🚀

