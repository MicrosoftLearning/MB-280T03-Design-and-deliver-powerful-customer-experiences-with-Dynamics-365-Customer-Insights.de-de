---
lab:
  title: 'Lab 4.1: Erstellen eines Trigger-basierten Kontaktverlaufs'
---

# Lernpfad 4: Erstellen von Journeys

## Übungs-Lab 4.1: Erstellen einer triggerbasierten Journey 

### Lab-Überblick

#### Szenario
Nachdem wir nun unsere 3 E-Mails erstellt haben, ist es an der Zeit, eine Journey zu erstellen, um die E-Mails an unsere Kundschaft zu senden. Wir senden unserer Kundschaft unsere erste E-Mail, um sie über die bevorstehende Airpot Smart Machine Coffee Maker zu informieren.

Kundinnen und Kunden, die auf diese E-Mail antworten, werden dann in zwei Gruppen aufgeteilt: Kundinnen und Kunden, die bereits ein altes Airport-Modell besitzen, und Kundinnen und Kunden, die noch kein Modell besitzen. Unsere bestehenden Airpot-Besitzenden werden wir per E-Mail zu einem Upgrade ermutigen. Wenn sie auf einen Link in dieser E-Mail klicken, wird sich ein Vertriebsmitarbeiter bzw. eine Vertriebsmitarbeiterin direkt mit ihnen in Verbindung setzen.

Vorhandene Besitzende, die nicht auf einen Link geklickt haben, erhalten eine weitere E-Mail-Werbung für das Produkt. Diese E-Mail wird auch an Nicht-Airpot-Besitzende gesendet.


### Voraussetzungen:
- Ein Computer mit einer Dynamics 365 Customer Insights - Journeys-Umgebung

## Übung 1: Erstellen einer Echtzeitjourney

### Aufgabe 1: Erstellen einer Journey
1.  Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an.
2.  Navigieren Sie zum Arbeitsbereich **Echtzeitjourneys**.
3.  Wählen Sie unter **Engagement** die Option **Journeys.**.
4.  Klicken Sie auf **+ Neue Journey** in der Befehlsleiste. Wenn Sie aufgefordert werden, Copilot zu verwenden, um Ihre Journey zu erstellen, wählen Sie **Überspringen und Ohne Vorlage erstellen**.
5.  In **Journey benennen** geben Sie *Airpot Smart Machine Launch Campaign* ein.
6.  Wählen Sie unter **Journeytyp auswählen** die Option **Trigger-basiert**.
7.  Suchen Sie unter **Trigger auswählen** nach **E-Mail-Link geklickt** und wählen Sie diese Option aus.
8.  Unter **E-Mail auswählen**, suchen Sie nach Ihrer **Smart Machine Kampagnen-E-Mail** und wählen Sie sie aus.
9.  Klicken Sie auf **Erstellen**.

### Aufgabe 2: Konfigurieren des Journeyeintrags
1. Navigieren Sie zum Abschnitt **Journeyeinstellungen**, der auf der rechten Seite des Bildschirms erweitert wird. Der Abschnitt **Eintrag** sollte geöffnet sein.
2. Lassen Sie **Nach Segmenten ausschließen** leer.
3. Wählen Sie im Abschnitt **Wiederholen** die Option „Sofort“.
4. Im Abschnitt **Zeitzone** wählen Sie Ihre Zeitzone.
5. Wählen Sie unter **Start** den heutigen Tag aus. Stellen Sie die Zeit auf 15 Minuten ab jetzt ein. (Sie können direkt in dieses Feld tippen.)
6. Unter **Ende,** wählen Sie „morgen“ aus.

### Aufgabe 3: Konfigurieren des Journeyziels
1.  Navigieren Sie auf der rechten Seite zu den Journeyeinstellungen, die wie eine Liste von Symbolen aussehen. Fahren Sie mit der Maus über die einzelnen Symbole, um die Namen der Registerkarten zu sehen. Wählen Sie den Abschnitt **Ziel** aus.
2.  In *Das Ziel dieser Journey ist*, wählen Sie **Eine allgemeine Benachrichtigung zu senden**.
3.  In *Das Ziel ist erreicht, wenn* **Mindestens eine Person auf einen Link geklickt hat**.
4.  In *Die Anzahl der benötigten Personen,* geben Sie *50* ein. Lassen Sie die Prozentzahl ausgewählt.

### Aufgabe 4: Hinzufügen einer Attributverzweigung
1. Klicken Sie im Journey-Designer auf das **Plus-Symbol (+)** unter der Kachel **E-Mail-Link geklickt**.
2. Wählen Sie **Attributsverzweigung** aus dem Abschnitt *Bedingungen* aus.
3. Unter **Name anzeigen** auf der rechten Seite, geben Sie *Besitzt bereits einen Airpot* ein.
4. Wählen Sie **Verzweigung 1** aus. Unter Anzeigename geben Sie *Besitzt Airpot* ein.
5. Wählen Sie **Bedingungen hinzufügen**.
6. Suchen Sie unter **Attribut auswählen** unter „Kontakt“ nach **Beschreibung (Beschreibung)**.
7. Ändern Sie den Wert von „Ist gleich“ in „Enthält“.
8. Unter **Wert**, geben Sie *Airpot* ein.
9. Kehren Sie zum Journey-Designer zurück. Klicken Sie auf das **Plus-Symbol (+)** unter „Verzweigung 1“.
  - Wählen Sie **E-Mail** aus.
  - Unter **E-Mail auswählen,** wählen Sie **Airpot-E-Mail aktualisieren**.
10.  Klicken Sie auf das **Plus-Symbol (+)** unter der Kachel „E-Mail senden“.
  - Wählen Sie **Auf Trigger warten**.
  - Wählen Sie unter **Verzweigungsbedingungstyp auswählen** die Option **Die vorherige Nachricht erhält eine Interaktion** aus.
  - Wählen Sie unter **Interaktion auswählen** die Option **E-Mail-Link angeklickt**.
  - Geben Sie bei **Was ist das Zeitlimit?**, „10 Minuten“ ein.
11. Klicken Sie im Pfad **Ja** auf das **Plus Symbol (+)**.
  - Wählen Sie **Aufgabe** im Bereich „Aktivitäten“.
  - Wählen Sie unter „Vorlage wählen“ die Option **Weiterverfolgen mit Kundschaft** aus.
  - Betreff und Zuweisen werden automatisch ausgefüllt.
  - Ändern Sie **Fällig nach** in *2 Wochen*.
12. Klicken Sie im entsprechenden Pfad **Nein** (unter der Verzweigung „E-Mail-Link angeklickt, wenn/dann“) auf das **Plus-Symbol (+)**.
  - Wählen Sie **E-Mail senden** aus.
  - Unter **E-Mail auswählen** wählen Sie **Smart Machine Campaign Reminder**.
13. Kehren Sie zum Journey-Designer zurück. Suchen Sie die Kachel **Attribut**. Jetzt werden wir die Verzweigung **Nein** konfigurieren. Für Kundinnen und Kunden, die noch keinen Airpot besitzen, senden wir die dritte E-Mail.
  - Wählen Sie das Zeichen **+** unter **Sonstiges** aus.
  - Wählen Sie **E-Mail** aus.
  - Wählen Sie unter E-Mail auswählen **Smart Machine Campaign Reminder**.
14. **Speichern** Sie die Journey.
15. Überprüfen Sie die Journey. Nehmen Sie ggf. letzte Änderungen vor.
16. Klicken Sie auf **Veröffentlichen**. Warten Sie, bis die Journey veröffentlicht wurde.
