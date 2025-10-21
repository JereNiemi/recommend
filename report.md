# Reflektion och Diskussion 

## 1. Tillvägagångssätt och Metodval

Projektet implementerar ett **Hybrid Rekommendationssystem** för att uppnå hög prestanda genom att balansera **relevans** (precision) med **diversitet/serendipitet** (upptäcktsförmåga).

* **Kärnmetoder:**
    1.  **Kollaborativ Filtrering (CF) med NMF (Non-negative Matrix Factorization):** Används för djup **personalisering**. NMF upptäcker latenta faktorer i användares preferenser, vilket är avgörande för att uppnå **serendipitet**.
    2.  **Innehållsbaserad Filtrering (CBF) med Kosinuslikhet (TF-IDF):** Fungerar som en **robust reserv** och hanterar effektivt **Cold Start**-problemet genom att rekommendera objekt baserat på genrelikhet.

* **Värde:** Hybridansatsen valdes för att hantera **gleshet** i betygsmaterialet (25 miljoner betyg filtrerade till aktiva användare/populära filmer) och för att säkerställa att systemet kan ge både logiskt förväntade och oväntade, men relevanta, rekommendationer.

---

## 2. Resultat och Utvärdering

Kvalitativt sett visade utdata att CF-komponenten rekommenderade filmer baserade på en bredare, implicit smak (*Trainspotting*, *Memento*), medan CBF-komponenten fokuserade på nära genre-matchningar (*Toy Story 2*). Den slutliga hybridmodellen tenderade att **prioritera CF-resultaten**, vilket indikerar att systemet lägger störst vikt vid den personliga preferensen.

Systemets kvantitativa prestanda utvärderas baserat på följande **tre nyckelmetriker** som direkt mäter systemets balans mellan relevans och upptäcktsförmåga: Precision, Coiverage, Novelty.


Projektet strävar efter att maximera **Precision** samtidigt som en tillräcklig nivå av **Coverage** och **Novelty** bibehålls för att undvika att användaren fastnar i en smal filterbubbla.
