---
lab:
  title: 'Übung 3.2: Erstellen einer E-Mail'
---

# Lernpfad 3: Verwalten von Kundschaft und Ressourcen in Dynamics 365 Customer Insights - Journeys

## Übungs-Lab 3.2: Erstellen einer E-Mail

### Lab-Überblick

#### Szenario
Für diese Kampagne plant das Marketingteam eine groß angelegte Werbekampagne für seine neueste intelligente Kaffeemaschine. Sie planen, eine Serie von drei E-Mails zu versenden. In der ersten E-Mail wird die intelligente Kaffeemaschine von Contoso beworben. Die zweite E-Mail soll die Besitzenden des regulären Airports dazu ermutigen, auf die neue intelligente Maschine umzusteigen. Die dritte E-Mail ist eine Erinnerung an den neuen Produktstart. 

### Lab-Überblick
Dieses Lab umfasst drei Übungen:
1. In dieser Übung erstellen Sie eine E-Mail mithilfe einer E-Mail-Vorlage.
2. In dieser Übung erstellen Sie eine E-Mail, indem Sie eine andere E-Mail kopieren.
3. In dieser Übung erstellen Sie eine E-Mail, indem Sie eine andere E-Mail kopieren.

### Voraussetzungen:
- Ein Computer mit einer Dynamics 365 Customer Insights - Journeys-Umgebung

## Übung 1: Erstellen einer Marketing-E-Mail
### Aufgabe 1: Erstellen einer E-Mail aus einer Vorlage
1. Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an. Vergewissern Sie sich, dass Sie sich im Bereich **Echtzeitjourneys** befinden.
2. Navigieren Sie zu **E-Mails** unter der Gruppe „Kanäle“.
3. Klicken Sie auf **+ Neu**, um eine neue E-Mail zu erstellen.
4. Scrollen Sie in der Vorlagengalerie nach unten zum Abschnitt **Layouts**. Wählen Sie **1-2 Spalte** und **Auswählen**.
5. Ändern Sie in der oberen linken Ecke den Namen der E-Mail von *E-Mail 1* in *Smart Machine Campaign Email*. (Wenn Sie den Mauszeiger über **E-Mail 1** in der oberen linken Ecke bewegen, sollten Sie in dieses Textfeld tippen können).
6. Wählen Sie das Feld **Absender/Betreff** im Designer aus, um die Details der E-Mail-Überschrift anzuzeigen.
   - Geben Sie im Betreff Folgendes ein: „Endlich eine Kaffeemaschine, die mich versteht.“
   - Wählen Sie **Contoso Coffee** als den Absender aus (falls nicht bereits geschehen). Der Absendername und die Absender-E-Mail sollten ausgefüllt werden und schreibgeschützt sein.
7. Suchen Sie das Menü **Toolbox** ganz rechts, das als eine Reihe von Symbolen angezeigt wird. Wenn Sie mit dem Mauszeiger über die Symbole fahren, sehen Sie den Namen der einzelnen Registerkarten. Wählen Sie die Registerkarte **Design** aus, die wie ein Pinsel aussieht.
   - **Hinweis:** Die Details in diesem Abschnitt wirken sich auf die gesamte E-Mail aus. Wenn Sie der E-Mail neue Textelemente hinzufügen, werden standardmäßig die hier aufgeführten Schriftart, -größe und -farbe verwendet. Sie können diese Elemente dann nach Bedarf anpassen.
   - Ändern Sie die **Schriftfamilie** in: Segoe UI.
   - Ändern Sie die **Farbe des Textkörpers** in: #404040.
   - Ändern Sie den **E-Mail-Hintergrund** in: #CCCCCC.
8. Suchen Sie in der E-Mail selbst den ersten Abschnitt und wählen Sie ihn aus. Es erscheint eine Registerkarte „Layout bearbeiten“. Ändern Sie die Hintergrundfarbe des Abschnitts in einen Grauton.

## Aufgabe 2: Aktualisieren von Bildern
In dieser Aufgabe aktualisieren wir das Logo.

1. Wählen Sie das Bild im ersten Abschnitt des Designers aus.
2. Klicken Sie auf der rechten Seite auf das Platzhalterbild. Wählen Sie **Bild ersetzen** und dann **Bibliothek durchsuchen.**.
3. Wählen Sie das **Contoso-Logo** aus, und klicken Sie dann auf **Auswählen**.
4. Ersetzen Sie den Alternativtext durch das *Contoso-Logo*.
5. Wählen Sie das Dropdown-Menü **Verknüpfen mit** und dann **URL**. Geben Sie *www.contoso.com* ein.
6. Wenn im Abschnitt „Größe und Ausrichtung“ die Option „Automatische Breite“ aktiviert ist, deaktivieren Sie sie mit dem Schalter. Geben Sie *150px* als Breite ein. Die andere Dimension wird automatisch aktualisiert.
7. Als Nächstes aktualisieren wir das zweite Bild in der E-Mail. Wählen Sie das Bild im Abschnitt unterhalb des Logos aus.
8. Wählen Sie **Bild ersetzen** und **Bibliothek durchsuchen**.
9. Wählen Sie das Bild **hero-page.jpg** aus. Klicken Sie auf **Auswählen**.

## Aufgabe 3: Aktualisieren einer Überschrift mithilfe der Personalisierung
In dieser Aufgabe aktualisieren wir eine Überschrift, um den Vornamen des Empfängerkontakts widerzuspiegeln.
1. Navigieren Sie zum Textabschnitt unter dem Logo und wählen Sie ihn aus.
2. Setzen Sie den Cursor an den Anfang des Headertextes und klicken Sie auf **Personalisierung** in der Symbolleiste oben in der E-Mail. Wählen Sie **Vorname** aus der Dropdown-Liste. Stellen Sie sicher, dass **Kontakt** ausgewählt ist und wählen Sie **Auswählen**.
3. Fügen Sie ein Komma und ein Leerzeichen hinter {{Firstname}} hinzu.
4. Ändern Sie den Platzhaltertext in: „Wir kümmern uns um Ihre Kaffeepausen.“
5. Markieren Sie den Text, machen Sie ihn fett und ändern Sie die Schriftgröße auf *26*.
6. Ändern Sie „Passen Sie Ihre E-Mail an ...“ in „Die neue intelligente Kaffeemaschine Airpot XL ist wie Ihr eigener persönlicher Barista.“
7. Markieren Sie den Text und ändern Sie die Schriftgröße auf *18*.

## Aufgabe 4: Entwerfen der restlichen E-Mail
1. Markieren Sie den zweispaltigen Abschnitt unterhalb des Texts. Ändern Sie die Hintergrundfarbe des Abschnitts in eine Blauschattierung.
2. Wählen Sie in der linken Spalte den Platzhalter „Bild“ aus und klicken Sie auf **Bild ersetzen**. Wählen Sie **Bibliothek durchsuchen** und wählen Sie **coffee-machine.jpg.** Klicken Sie auf **Auswählen**.
3. Ersetzen Sie den Alternativtext durch „Kaffeemaschine“. (Wenn sich das Fenster zum Bearbeiten des Bildes nicht sofort öffnet, finden Sie die Bildeigenschaften als unterstes Symbol im Menü **Toolbox**).
4. Wählen Sie im Feld **Verknüpfen mit** **URL** aus. Geben Sie [https://dynamics.microsoft.com/] ein.
5. Schalten Sie im Abschnitt „Größe und Ausrichtung“ die automatische Breite **aus**. Ändern Sie die Breite auf *150px* und lassen Sie die andere Abmessung automatisch einstellen.
6. Wählen Sie in der rechten Spalte unter der Unterüberschrift den Platzhalter „Bild“ aus und klicken Sie auf **Bild ersetzen**. Wählen Sie **Bibliothek durchsuchen** und wählen Sie **barista.jpg**. Klicken Sie auf **Auswählen**.
7. Ersetzen Sie den Alternativtext durch *Barista*.
8. Wählen Sie im Feld „Verknüpfen mit“ die Option „URL“ aus. Geben Sie [https://dynamics.microsoft.com/] ein.
9.  Wählen Sie den Bereich mit den sozialen Symbolen aus. Ändern Sie die Hintergrundfarbe des Abschnitts in einen Grauton.
10. Wählen Sie den Abschnitt mit den Copyrightinformationen aus. Aktualisieren Sie das Urheberrecht von *2022 Company Inc.* auf *2024 Contoso Coffee.*
11. Nehmen Sie ggf. weitere Änderungen vor. Seien Sie ruhig kreativ und nutzen Sie Ihre gesamte Designerfahrung. Was finden Sie auffällig, wenn Sie eine Marketing-E-Mail erhalten?

## Aufgabe 5: Speichern und Testen der E-Mail
16. Klicken Sie in der Symbolleiste auf **Speichern**.
17. Wählen Sie **Vorschau und Test**.
18. Klicken Sie auf **Beispieldaten bearbeiten**. Geben Sie im Bereich „Vorschau-Personalisierung“ den Vornamen eines von Ihnen erstellten Kontakts ein. Wählen Sie den Kontakt aus, um die Änderung der Personalisierung zu beobachten.
19. Kehren Sie zum Bildschirm **Vorschau und Test** zurück. Zeigen Sie eine Vorschau der E-Mail auf allen Bildschirmgrößen an.
20. Klicken Sie auf den **Pfeil** neben „Inhalt prüfen“. Führen Sie die **Barrierefreiheitsprüfung** durch, um zu sehen, ob es in der E-Mail noch andere Probleme gibt. Beheben Sie andere Probleme nach eigenem Ermessen.
21. Klicken Sie in der Symbolleiste auf **Bereit zum Senden**.

### Übung 2: Erstellen einer E-Mail durch Kopieren einer E-Mail

## Aufgabe 1: Erstellen einer E-Mail an bestehende Kundschaft
1. Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an. Stellen Sie sicher, dass Sie sich im Echtzeitmarketingbereich befinden.
2. Navigieren Sie zu **E-Mails** unter der Gruppe „Kanäle“.
3. Öffnen Sie die E-Mail, die Sie in Aufgabe 1 erstellt haben.
4. Klicken Sie in der Befehlsleiste auf den **Dropdown-Pfeil** neben „Speichern“. Wählen Sie **Speichern unter**.
5. Benennen Sie im Schnellerfassung-Menü auf der rechten Seite die E-Mail *Airpot E-Mail aktualisieren*.
6. Geben Sie im Feld „Betreff“ ein: „Ist es Zeit für ein Upgrade?“
7. Klicken Sie auf **Speichern und schließen**. Es erscheint ein Pop-up-Fenster mit der Meldung: *Ihre Änderungen wurden gespeichert*. Klicken Sie auf **Datensatz anzeigen**, um die neue E-Mail zu öffnen. (Sie können auch zu **E-Mails** zurückkehren und **Airpot-E-Mail aktualisieren** öffnen.)
8. Ändern Sie den Text in der Kopfzeile des Designers in: „{{Firstname}}, Kaffee ganz nach Ihrem Geschmack, immer griffbereit.“
9. Ändern Sie den Text unter der Überschrift in: „Ihre Kaffeebestellung ist so einzigartig wie Sie selbst. Zeit, unsere neue Airpot Smart Coffee Machine auszuprobieren.“
10. Wählen Sie den nächsten zweispaltigen Abschnitt aus. Ändern Sie das Layout von 2 auf 1:2.
    - Nehmen Sie in der linken Spalte die folgenden Aktualisierungen vor:
      - Entfernen Sie den Text.
      - Entfernen Sie die Schaltfläche.
    - Nehmen Sie in der rechten Spalte die folgenden Aktualisierungen vor:
      - Entfernen Sie das Bild.
      - Ändern Sie den Text in: „Halb entkoffeinierter Americano oder doppelter Latte Macchiato? Wie auch immer Sie sich für Ihren Tag stärken möchten, Contoso Coffee hat alles, was Sie brauchen.“ ‎
      - Ändern Sie den Schriftgrad in 16 und kursiv.
11. Aktualisieren Sie die Schaltfläche.
    - Wählen Sie die Schaltfläche  aus.
    - Ändern Sie den Link zu URL.
    - Geben Sie https://dynamics.microsoft.com/ ein.
    - Ändern Sie den Text der Schaltfläche in *ENTDECKEN SIE DIE NEUE INTELLIGENTE MASCHINE*.
    - Erweitern Sie **Größe und Ausrichtung.** Ändern Sie „Textanpassung“ auf **Aus**. Ändern Sie die Breite auf *200px*.
12. Klicken Sie in der Symbolleiste auf **Speichern**.
13. Vorschau der E-Mail.
14. Klicken Sie auf **Inhalt prüfen**. Korrigieren Sie eventuelle Fehler.
15. Klicken Sie in der Symbolleiste auf **Bereit zum Senden**.

### Aufgabe 2: Erstellen einer Nachverfolgungs-E-Mail-Kampagne
1. Melden Sie sich bei Dynamics 365 Customer Insights - Journeys an. Stellen Sie sicher, dass Sie sich im Echtzeitmarketingbereich befinden.
2. Navigieren Sie zu **E-Mails** unter der Gruppe „Kanäle“.
3. Öffnen Sie die E-Mail, die Sie in Aufgabe 2 erstellt haben.
4. Klicken Sie in der Befehlsleiste auf den Dropdown-Pfeil neben **Speichern**. Wählen Sie **Speichern unter**.
5. Nennen Sie die E-Mail im Schnellerfassung-Menü auf der rechten Seite *Smart Machine Campaign Reminder*.
6. Geben Sie in das Feld Betreff „Haben Sie die Neuigkeiten gesehen?“ ein.
7. Klicken Sie auf **Speichern und schließen**. Oben rechts erscheint ein Pop-up-Fenster mit der Meldung „Ihre Änderungen wurden gespeichert“. Klicken Sie auf **Datensatz anzeigen**, um die neue E-Mail zu öffnen. (Sie können auch zur E-Mail-Liste navigieren und **Smart Machine Campaign Reminder** öffnen.)
8. Ändern Sie den Überschriftstext in: „Die neue Airpot Smart Machine: ab Herbst erhältlich!“
9. Ändern Sie den Text unter der Überschrift in: „Unsere neue Airpot Smart Machine ist eine neue Art, Kaffee zuzubereiten.“ Erfahren Sie noch heute mehr über die erste Kaffeemaschine ihrer Art.“
10. Entfernen Sie den zweispaltigen Abschnitt.
11. Klicken Sie in der Symbolleiste auf **Speichern**.
12. Vorschau der E-Mail.
13. Klicken Sie auf **Inhalt prüfen**. Korrigieren Sie eventuelle Fehler.
14. Klicken Sie in der Symbolleiste auf **Bereit zum Senden**.

