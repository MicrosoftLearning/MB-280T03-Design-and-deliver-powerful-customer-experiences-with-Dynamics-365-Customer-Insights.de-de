---
lab:
  title: 'Übung 3.1: Hochladen von Ressourcen'
---

# Modul 3: Verwalten von Kundschaft und Ressourcen in Dynamics 365 Customer Insights - Journeys

## Übung 3.1: Hochladen von Ressourcen

### Lab-Überblick

#### Szenario
Contoso Coffee verkauft gewerbliche und private Kaffeemaschinen an Inhaber von Kaffeegeschäften, die Contoso-Kaffeemaschinen in ihren einzelnen Geschäften verwenden, an Unternehmen, die Contoso-Kaffeemaschinen in ihren Firmenbüros haben, und an einzelne Kundinnen und Kunden, die Contoso-Kaffeemaschinen zu Hause verwenden. In diesem Jahr veröffentlicht das Unternehmen ein brandneues Produkt namens Airpot XL Smart Coffee Machine. Sie planen, dieses neue Produkt sowohl für Unternehmen als auch für Einzelpersonen zu vermarkten.

Das Marketingteam beschließt, eine Cross-Selling-Kampagne zu erstellen, um aktuelle Kundinnen und Kunden zu ermutigen, ein Upgrade auf ihre neue intelligente Kaffeemaschine in Betracht zu ziehen. Sie planen, eine Reihe von E-Mails mit einer Handlungsaufforderung an die Kundinnen und Kunden zu senden, um auf einen Link zu klicken, der einen Anruf von einer Mitarbeiterin bzw. einem Mitarbeiter des Vertriebs auslöst. Sie planen, diese Kampagne 2 Monate lang durchzuführen.


Für diese Kampagne muss das Marketingkoordinationsteam Folgendes tun:
- Hochladen von Marketing-Assets zur Verwendung in den E-Mail-Kampagnen.
- Erstellen von Marketing-E-Mails, die an Kundinnen und Kunden gesendet werden sollen.
- Erstellen einer Journey, die die Bereitstellung der Kampagneninhalte automatisiert.

Zunächst muss das Marketingkoordinationsteam die digitalen Ressourcen hochladen, die in der Kampagne verwendet werden. Sie müssen auch alle neuen Vertriebskontakte hochladen, die das Unternehmen kürzlich erworben hat, und Details zu vorhandenen Kontakten und Konten aktualisieren.

## Lab-Überblick
Dieses Lab besteht aus vier Aufgaben:
1. In der ersten Aufgabe laden Sie Bilddateien hoch, die in Marketing-E-Mails verwendet werden sollen. Diese Dateien werden in die Echtzeit-Objektbibliothek hochgeladen.
2. In der zweiten Aufgabe aktualisieren Sie Details zu vorhandenen Kontakten innerhalb Dynamics 365 Customer Insights - Journeys.
3. Im dritten Vorgang erstellen Sie eine Aufgabenvorlage, die in der Reise verwendet wird.
4. In der vierten Aufgabe konfigurieren Sie das Standard-Markenprofil, das in Ihren Marketing-Assets (z. B. E-Mails) verwendet werden soll.

### Voraussetzungen:
- Ein Computer oder eine VM mit einer Dynamics 365 Customer Insights - Journeys-Umgebung
- Die Bilddateien, die in Marketinginhalten verwendet werden sollen. Diese finden Sie in Ihrem autorisierten Lab-Host oder in der Datei **MB-280T03-Assets.zip** im Ordner „Instructions/Labs/Media“ im GitHub-Repository. Fragen Sie die Kursleitung, wenn Sie Probleme haben, sie zu finden.

### Übung 1: Vorbereiten von Marketingressourcen 
## Aufgabe 1: Hochladen von Bildern in die Objektbibliothek
1. Laden Sie die Bilddateien aus den Ressourcendokumenten herunter. Entpacken Sie die Dateien in einen Ordner auf Ihrem Desktop.
2. Melden Sie sich mit Ihren Admin-Anmeldedaten bei Dynamics 365 Customer Insights – Journeys an.
3. Standardmäßig sollten Sie sich im Echtzeitjourney-Bereich befinden. Vergewissern Sie sich, dass Sie sich im Bereich „Echtzeitjourneys“ befinden, indem Sie die Bereichsauswahl unten links auf dem Bildschirm öffnen.
4. Navigieren Sie im linken Menü zum Abschnitt „Assets“. Wählen Sie **Bibliothek** aus. Wählen Sie die Schaltfläche **+ Neu** aus, um das Fenster zum Hochladen von Dateien zu öffnen.
5. Wählen Sie **+ Dateien hinzufügen** aus, suchen Sie die Bilddateien auf Ihrem lokalen Computer und wählen Sie sie aus.
6. Fügen Sie, während das Upload-Fenster geöffnet ist, ein Logo-Tag zu contosologo.png hinzu. (Beginnen Sie mit der Eingabe von „Logo“ in das Textfeld unter dem Namen der Bilddatei. Nachdem Sie *Logo* eingegeben haben, wählen Sie das soeben eingegebene aus. Unter dem Dateinamen wird ein Tag hinzugefügt.)
7. Wählen Sie die Option **Hochladen**. Stellen Sie sicher, dass die Bilddateien hochgeladen wurden – für jede Datei wird ein grünes Häkchen mit der Aufschrift „Fertig“ angezeigt. (Es kann einige Minuten dauern, bis die Dateien hochgeladen sind.) Wählen Sie **Schließen** aus.
8. Geben Sie in das Suchfeld „Nach Stichwort filtern“ *con* ein und drücken Sie die Eingabetaste. Standardmäßig sucht dieser Filter nach dem Dateinamen. Stellen Sie sicher, dass contosologo.png in den Suchergebnissen angezeigt wird.

Diese Dateien sind jetzt für Benutzende verfügbar, die in ihre Marketingvorgänge integriert werden können.

### Aufgabe 2: Aktualisieren vorhandener Kontakte
1. Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an. Stellen Sie sicher, dass Sie sich im Echtzeitjourney-Bereich befinden.
2. Wählen Sie in der linken Navigation unter der Zielgruppe **Kontakte** aus.
3. Öffnen Sie den Kontakt **Alva Tharaldsen.**
   - Wählen Sie unter „Kontoname“ **Bellows College** aus. Anschließend navigieren Sie zum Datensatz des Bellows College-Kontos.
   - Scrollen Sie nach unten zum Untergitter **Kontakte**. Alle Kontakte, die dem Bellows College zugeordnet sind, sind hier aufgeführt. Klicken Sie auf die vertikalen Ellipsen am oberen Rand des Untergitters, klicken Sie auf **Auswählen** und verwenden Sie die Kontrollkästchen, um alle Kontakte in der Liste auf einmal auszuwählen.
   - Wählen Sie am oberen Rand des Untergitters Kontakte die **vertikalen Ellipsen.** Klicken Sie dann auf **Bearbeiten**.
   - Suchen Sie auf der Registerkarte „Details“ das Feld „Persönliche Notizen“. Geben Sie „Airpot-Besitzer“ in das Feld ein. Wählen Sie **Speichern**.
   - Wählen Sie einen anderen Kontakt als Alva aus. Navigieren Sie zur Registerkarte **Details**. Überprüfen Sie, ob im Feld „Persönliche Notizen“ der Eintrag „Airpot-Besitzer“ angezeigt wird.
4. Navigieren Sie zurück zur Entität **Kontakte** unter der Gruppe „Zielgruppe“. 
5. Festlegen eines Filters für den Firmennamen:
   - Wählen Sie den **Dropdown-Pfeil** neben Firmenname. Wählen Sie **Filtern nach**. Wählen Sie **Ist gleich** und wählen Sie dann **Lucerne Publishing, Southridge Video,** und **Wingtip Toys.** (Sie können die Konten auswählen, indem Sie entweder den Namen direkt aus der Liste auswählen oder indem Sie mit der Eingabe des Namens beginnen und den Kontonamen auswählen, sobald er angezeigt wird). Wählen Sie **Anwenden.**
   - Wählen Sie alle Kontakte für diese 3 Konten aus. (Sie können das Häkchen neben „Vollständiger Name“ in der Kopfzeile der Ansicht auswählen, um alle Kontakte auf einmal auszuwählen.)
   - Wählen Sie in der Befehlsleiste **Bearbeiten** aus. Geben Sie Folgendes ein:
     - **Adresse 1: Stadt:** Bellevue
     - **Adresse 1: Bundesland/Kanton**: Washington
     - **Details > Persönliche Notizen:** Airpot-Besitzer
     - Wählen Sie **Speichern**.
6. Ändern des Filters für den Firmennamen:
   - Wählen Sie den **Dropdown-Pfeil** neben Firmenname. Wählen Sie **Filter löschen**.
   - Wählen Sie erneut den **Dropdown-Pfeil** aus. Wählen Sie **Filter nach**. Wählen Sie **Adatum Corporation** und **Northwind Traders** aus. Wählen Sie **Übernehmen**.
   - Wählen Sie alle Kontakte für diese 2 Konten aus.
   - Wählen Sie in der Befehlsleiste **Bearbeiten** aus. Geben Sie Folgendes ein:
     - **Adresse 1: Stadt:** Redmond
     - **Adresse 1: Bundesland/Kanton**: Washington
     - **Details > Persönliche Notizen:** Airpot-Besitzer
     - Wählen Sie **Speichern**.
7. Ändern des Filters für den Firmennamen:
   - Wählen Sie den **Dropdown-Pfeil** neben Firmenname. Wählen Sie **Filter löschen**.
   - Wählen Sie erneut den Dropdown-Pfeil und wählen Sie **Filtern nach**. Wählen Sie **Trey Research**, **The Phone Company,** und **Wide World Importers.** Wählen Sie **Übernehmen**.
   - Wählen Sie alle Kontakte für diese 3 Konten aus.
   - Wählen Sie „Bearbeiten“ in der Befehlsleiste aus. Geben Sie Folgendes ein:
     - **Adresse 1: Ort:** Seattle
     - **Adresse 1: Bundesland/Kanton**: Washington
     - **Details > Persönliche Notizen:** Airpot-Besitzer
     - Wählen Sie **Speichern**.

### Aufgabe 3: Erstellen einer Aufgabenvorlage
1. Melden Sie sich mit Ihren Admin-Anmeldedaten bei Dynamics 365 Customer Insights – Journeys an.
2. Navigieren Sie unter der Gruppe **Assets** zu **Aufgabenvorlagen**.
3. Wählen Sie **+ Neu** aus.
   - Name: Nachbereitung mit der Kundschaft
   - Betreff: Upgrade von Airpot auf Airpot XL Smart Coffee Machine
   - Zeitplantyp: Verzögerung (in Tagen).
   - Startverzögerung: 0.
4. Im Abschnitt „Startzeit“ wählen Sie **01** für Stunde. Lassen Sie „Minute“ leer.
4. Wählen Sie **Speichern und schließen** aus.

### Übung 4: Konfigurieren des Standardmarkenprofils
1. Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an. Wechseln Sie zum Bereich **Einstellungen**.
2. Navigieren Sie in der **Kundenbindungsgruppe** zu **Markenprofilen**.
3. Wählen Sie das **Standardmarkenprofil aus**.
4. Navigieren Sie zur Registerkarte **Absender**. Im Unterraster sollte der Standard-Absenderdatensatz angezeigt werden. 
5. Wählen Sie die Registerkarte „Soziale Links“ aus. Füllen Sie Folgendes aus:
    - LinkedIn-URL: https://www.linkedin.com/company/contoso12345/about/
    - Twitter-URL: https://twitter.com/ContosoInc
    - Facebook-URL: https://www.facebook.com/Contoso-102137176602590/
6. Wählen Sie **Speichern und schließen** aus.

