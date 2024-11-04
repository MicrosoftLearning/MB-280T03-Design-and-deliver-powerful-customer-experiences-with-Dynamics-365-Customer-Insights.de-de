---
lab:
  title: 'Lab 2.2: Erstellen eines einheitlichen Kundenprofils'
---

# Lab 2.2: Erstellen eines einheitlichen Kundenprofils

## Lernpfad 2: Arbeiten mit einheitlichen Kundenprofilen in Dynamics 365 Customer Insights - Data

Nachdem Sie die Rohdaten aus Ihren Datenquellen in Entitäten eingegeben haben, beginnen Sie nun mit dem Prozess „Zuordnen, Abgleichen, Zusammenführen“, um ein einziges einheitliches Kundenprofil zu erstellen, indem Sie die Daten aus jeder Quelle für Kundenprofile zusammenführen. Dazu ordnen Sie zunächst Ihre aufgenommenen Entitäten einem Standardmodell zu und wählen den Primärschlüssel für jede Ihrer profilierten Entitäten aus. Nach Abschluss dieses Vorgangs erstellen Sie dann Ihre Vergleichsregel, die zum Abgleichen von Kontakten von allen Kundenentitäten verwendet wird. Schließlich wird durch Ausführen des Zusammenführungsprozesses ein einziger Satz eindeutiger Kundinnen und Kunden mit übereinstimmenden Profilen aus allen Kundeneinheiten unter Verwendung Ihrer Übereinstimmungsregeln erstellt. Ihr Ziel ist es, herauszufinden, wie viele eindeutige Profile von Kundinnen und Kunden Contoso Retail in verschiedenen Datenquellen hat.

## Übung 1: Vereinheitlichen der Daten

### Aufgabe 1: Zuordnen von Kontakten zu allgemeinen Datentypen
1. Melden Sie sich bei Customer Insights - Data unter https://home.ci.ai.dynamics.com an.
2. Erweitern Sie im linken Navigationsmenü **Daten** und wählen Sie **Vereinheitlichen**.
3. Wählen Sie im Abschnitt „Kundendaten“ die Option **Loslegen**.
4. Wählen Sie auf dem Bildschirm **Beschreiben der zu vereinheitlichenden Kundendaten** die Option **+ Loslegen** aus.
5. Wählen Sie die Tabellen aus, die das Kundenprofil darstellen. Es handelt sich um folgende Tabellen:
   - Contacts (eCommerce)
   - Customers (Loyalty)
6. Wählen Sie **Übernehmen**.
7. Ihnen werden nun die Zuordnungen Ihrer Quelltabelle zu den Standardmodelltypen angezeigt. Sehen Sie sich die Typen in der Tabelle an.
8. Sie müssen für jede aufgenommene Entität einen „Primärschlüssel“ auswählen. Der Primärschlüssel muss eine eindeutige Referenz sein. Wählen Sie für eCommerce-Kontakte **ContactId** als Primärschlüssel aus.
9. Die eCommerce-Kontaktdaten enthalten eine Spalte mit dem Namen **E-Mail-Abonnent**, die aufgrund des Namens dem falschen Typ „Identity.Service.Email“ zugeordnet wird. Öffnen Sie die Dropdownliste für diese Spalte, und wählen Sie die leere Option („nichts/leer“) aus. Wenn wir dies nicht tun, wird dieses Feld standardmäßig mit dem E-Mail-Feld zusammengeführt, was wir nicht möchten.
10. Wählen Sie unter „Tabellen“ die Option **Loyalty Customers** aus und legen Sie **LoyaltyId** als Primärschlüssel fest.
11. Wählen Sie oben links **Quellspalten speichern** aus.
12. Wählen Sie die Schaltfläche **Weiter** und dann erneut **Weiter**, um die doppelte Überprüfung zu überspringen und mit dem Schritt „Übereinstimmungsregeln“ fortzufahren.

### Aufgabe 2: Angeben der Übereinstimmungsreihenfolge
Für den nächsten Schritt müssen wir die Reihenfolge festlegen, in der die Profile zusammengeführt werden sollen. Sie können Attribute zusammenführen, um sicherzustellen, dass die vereinheitlichten Profile vollständig sind, und festlegen, welche Quellen für diese Attribute vorrangig verwendet werden sollen.
1. Sie sollten die vollständigste oder genaueste Profilquelle als primäre (erste) Quelle auswählen. Überprüfen Sie, ob **Contacts: eCommerce** die primäre (erste) Quelle ist (oder verschieben Sie sie, falls dies noch nicht geschehen ist).
2. Wählen Sie das Häkchen aus, um **alle Datensätze einzuschließen.**
3. Überprüfen Sie, ob **Customers: Loyalty** die zweite Quelle in der Liste ist. Wählen Sie **Alle Datensätze einbeziehen**.

### Aufgabe 3: Erstellen einer Vergleichsregel 
In dieser Aufgabe werden Sie eine einfache Regel erstellen, mit der Sie Datensätze miteinander abgleichen können. Regeln können aus einzelnen (z.B. basierend auf der ID) oder mehreren Bedingungen (z.B. vollständiger Name, Postleitzahl, Geburtsdatum) bestehen. Ausführliche Informationen zu Vergleichsregeln finden Sie in der Dokumentation zu Customer Insights.
1. Es gibt einen Warnindikator für die Zeile **Customers: Loyalty**. Wählen Sie **+ Regel hinzufügen** oder wählen Sie das Symbol **+** auf der rechten Seite.
2. Fügen Sie die erste Bedingung mit FullName hinzu:
   - Wählen Sie in der Tabelle „Contacts: eCommerce“ das Feld **FullName**.
   - Wählen Sie in der Tabelle „Customers: Loyalty“ das Feld **FullName**.
   - Lassen Sie das Dropdown-Menü „Normalisieren“ leer.
   - Stellen Sie die Präzisionsstufe mithilfe des Dropdown-Felds auf **Basic** ein.
   - Stellen Sie den Präzisionswert mit dem Schieberegler auf **Hoch** ein.
3. Geben Sie für den Namen **FullName, E-Mail** ein.
4. Fügen Sie eine zweite Bedingung für die E-Mail-Adresse hinzu, indem Sie **+ Hinzufügen** und dann **Bedingung hinzufügen** wählen.
   - Wählen Sie in der Tabelle Contacts: eCommerce das Feld **E-Mail**.
   - In der Tabelle Kunden: Loyalität wählen Sie das Feld **E-Mail**.
   - Lassen Sie das Dropdown-Menü „Normalisieren“ leer.
   - Setzen Sie die Präzisionsstufe auf **Basic.**
   - Setzen Sie den Präzisionswert auf **Hoch.**
5. Wählen Sie **Fertig** aus.
6. Wählen Sie **Weiter**, wählen Sie **Weiter** und wählen Sie **Kundenprofile erstellen.**

Customer Insights gleicht jetzt Kundendaten aus all Ihren Kundeninformationsquellen ab, um zu ermitteln, wie viele eindeutige Kundenprofile Sie auf der Grundlage Ihrer Regeln haben würden. Besprechen Sie dies mit der Klasse: Wie viele einzigartige Kunden haben Sie, wenn Sie Ihre Datensätze kombinieren?

### Vorgang 4 – Genauigkeit
In Aufgabe 3 haben wir bei der Abgleichsregel gegen Full Name eine hohe Präzision verwendet. Bei dieser Aufgabe passen Sie die Genauigkeit an, um eine höhere Anzahl von Übereinstimmungen zu erzielen, indem Sie Übereinstimmungen mit einer geringeren Konfidenz einbeziehen (was zu einer geringeren Anzahl eindeutiger Profile führt).

**Hinweise zur Genauigkeit:**
- Exakt auf der rechten Seite der Skala findet Datensätze, bei denen Ihre Bedingung eine exakte Übereinstimmung aufweist. Wählen Sie eine der anderen Ebenen, um Datensätze abzugleichen, die nicht 100 % identisch sind.
- Hohe Passgenauigkeit in Fällen, in denen Präzision wichtiger ist als Reichweite, wie z. B. bei einer Finanzdienstleistung für einen bestimmten Kunden.
- Niedrig passt zu Fällen, in denen das Gegenteil der Fall ist, wie zum Beispiel bei einer Marketingkampagne.
- Die Stufe Mittel dient als mittlere Option.

1. Erweitern Sie in Customer Insights **Daten** im linken Navigationsmenü. Wählen Sie **Vereinigen.**
2. Wählen Sie unter Übereinstimmungsregeln **Bearbeiten.**
3. Erweitern Sie die Regel **Kunden: Loyalität** und klicken Sie auf die Schaltfläche **Bearbeiten**, um den Bereich **Vollständiger Name, E-Mail** zu öffnen.
4. Wählen Sie unter Bedingung 1 **Vorschau** und notieren Sie die Werte. Bewegen Sie den Schieberegler Präzision für Bedingung 1 von **Hoch** auf **Niedrig**. Wählen Sie **Fertig** aus.
5. Wählen Sie **Weiter**, wählen Sie **Weiter** und wählen Sie **Kundenprofile erstellen.**
6. Warten Sie, bis der Abgleichvorgang abgeschlossen ist.
7. Sobald der Abgleichvorgang abgeschlossen ist, klicken Sie auf **Bearbeiten** bei den Abgleichsregeln. Wählen Sie das Menü der **vertikalen Punkte** neben der Regel **Voller Name, E-Mail** aus und wählen Sie **Vorschau** aus, um die Spielergebnisse und den Punktestand zu sehen. Dies zeigt, wie Customer Insights die Datentabellen auf der Grundlage der von Ihnen definierten Regeln abgeglichen hat. Einige Profile wurden mit einer geringeren Trefferwahrscheinlichkeit erstellt.
8. Schließen Sie die Vorschau und wählen Sie „Bearbeiten“. Wählen Sie die Schaltfläche „Vorschau“ unter Bedingung 1. Hier können Sie eine Vorschau der Anzahl der nicht übereinstimmenden und übereinstimmenden Datensätze für die Bedingung Vollname anzeigen.
9. Wählen Sie **Datenvorschau** unter „Nicht übereinstimmend“ oder „Übereinstimmend“, um eine Vorschau der Übereinstimmungen anzuzeigen. Beachten Sie, dass die hohen Punktzahlen eine exakte Schreibweise haben, aber auch dann übereinstimmen können, wenn das Namensformat (Vorname, Nachname / Nachname, Vorname) unterschiedlich ist. Beachten Sie bei den niedrigen Punktzahlen, dass selbst bei nicht identisch geschriebenen Namen Übereinstimmungen gefunden werden.
10. Schließen Sie den Kriterien-Vorschaubereich und wählen Sie **Abbrechen** aus.

Besprechen Sie sich mit der Klasse: Wie viele Unique Customer Profiles haben Sie jetzt?

### Aufgabe 5 – Vereinheitlichung der Kundenfelder
Dies ist die letzte Phase im Prozess der Datenvereinheitlichung. Der Zweck besteht darin, widersprüchliche Daten abzugleichen und die Attribute zu definieren, die im einheitlichen Kundenprofil verwendet werden sollen. Ein zusammengeführtes Attribut ist ein Attribut, das in mehreren Datenquellen vorhanden ist und dasselbe Datenelement darstellt. Zum Beispiel können wir „E-Mail-Adresse“ sowohl in den Datenquellen für eCommerce-Kunden als auch für Treuekunden haben. Customer Insights wird versuchen, die Attribute zu identifizieren, die mit den Standarddatentypen zusammengeführt werden sollen, die wir im Schritt „Quellfelder“ definiert haben.

1. Erweitern Sie in Customer Insights **Daten** im linken Navigationsmenü. Wählen Sie **Vereinigen.**
2. Wählen Sie unter Vereinheitlichte Datenansicht **Bearbeiten.**
3. Beachten Sie in den Spalten „Customer“, wie Attribute aus verschiedenen Datenquellen, die vom gleichen Typ sind (z. B. Vorname), zusammengeführt wurden.
4. Erweitern Sie das zusammengeführte Attribut **FirstName**. Sie sollten sehen, dass das Attribut „FirstName“ in „eCommerce: Contacts“ auf Platz 1 steht. Dies bedeutet, dass bei einem übereinstimmenden Kundenprofil in LoyaltyScheme und eCommerce der Vorname aus eCommerce: Contacts als primärer Vorname verwendet wird.
9. Wählen Sie **Weiter** und wählen Sie **Kundenprofile erstellen**.
10. Warten Sie, bis der Vorgang abgeschlossen ist.

Herzlichen Glückwunsch! Sie haben erfolgreich Daten aus verschiedenen Quellen in Customer Insights aufgenommen, zugeordnet, abgeglichen und vereinheitlicht, um ein einheitliches Kundenprofil zu erstellen, mit dem Sie Einblicke in Ihren gesamten Kundenstamm gewinnen können.

## Übung 2: Kundensuche
In dieser Übung richten wir Such- und Filterkriterien ein, damit Customer Insights-Benutzende nach einheitlichen Kundenprofilen suchen können, damit Sie schnell Informationen zu einem bestimmten Kunden bzw. einer bestimmten Kundin oder einer bestimmten Kundengruppe abrufen können.

### Aufgabe 1: Konfigurieren der Suchspalten und des Filterindexes
1. In Customer Insights wählen Sie **Kunden** aus dem linken Navigationsmenü.
2. Wählen Sie **Such- und Filterindex** aus.
3. Einige für die Kundensuche spezifische Felder sind bereits standardmäßig hinzugefügt und Sie können weitere hinzufügen, indem Sie **+ Hinzufügen** in der Symbolleiste wählen.
4. Stellen Sie sicher, dass **CustomerId, FirstName, LastName, FullName, DateOfBirth, EMail, PostCode, Headshot, ContactId (eCommerce_Contacts),** und **LoyaltyId** ausgewählt sind. Deaktivieren Sie alle anderen aktivierten Felder. Wählen Sie **Übernehmen**.
5. Wählen Sie **Speichern**.

### Aufgabe 2: Suchen nach einem Kundendatensatz
1. In Customer Insights wählen Sie **Kunden** aus dem linken Navigationsmenü. Sie sollten einen Satz von Kundenkarten angezeigt bekommen, die die einheitlichen Profile darstellen. Sie können Karten erweitern, um mehr über die Kundschaft zu erfahren oder die Karten nach verschiedenen Feldern zu sortieren. Versuchen Sie dies, indem Sie **Karten erweitern** und **Sortieren nach** in der Symbolleiste wählen.
2. Sie können „Kunden suchen“ verwenden, um nach Textattributen zu einheitlichen Kundenprofilen zu suchen. (Beispiele: Die Suche nach „24502“ wird in allen Textattributen durchgeführt und gibt Übereinstimmungen und Teilübereinstimmungen zurück.)

Verwenden Sie die Suchleiste, um die folgenden Fragen zu beantworten:
- Wie lautet Brian Gobbles Geburtsdatum? (Suche nach Brian Gobble)
- Welcher Kunde bzw. welche Kundin hat die Treuekarte „ID LOYID_5707“? (Suche nach LOYID_5707)
- Welcher Kunde bzw. welche Kundin hat die Postleitzahl 24502? (Suche nach 24502)
