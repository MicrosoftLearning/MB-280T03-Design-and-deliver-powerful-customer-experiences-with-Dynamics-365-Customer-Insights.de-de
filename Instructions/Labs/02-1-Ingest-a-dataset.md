---
lab:
  title: 'Übung 2.1: Aufnehmen eines Datasets'
---

# Modul 2: Erfassen von Daten in Dynamics 365 Customer Insights - Data

## Lab-Szenario: Contoso Coffee
Contoso Coffee stellt hochwertigen Kaffee und Kaffeemaschinen her, die über verschiedene Kanäle vertrieben werden, darunter neue Contoso-Einzelhandelsgeschäfte in erstklassigen Lagen, erstklassige Lebensmittelhändler und die Contoso Coffee-Website. Contoso plant, sein Angebot mit Contoso-Cafés und einer neuen vernetzten Kaffeemaschine zu erweitern, die Nachfüllbestellungen auslösen und den Contoso-Service bei Problemen benachrichtigen kann. Dieses neue Angebot wird ihnen dabei helfen, direkte Beziehungen zu ihren Kundinnen und Kunden aufzubauen und mehr darüber zu erfahren, wie diese ihre Produkte konsumieren.

### Herausforderungen von Contoso Coffee
- **Transaktionsbeziehung:** Ihr vorhandenes Geschäftsmodell bedeutet, dass sie keine direkte Beziehung zu ihrer Kundschaft haben.
- **Datensilos:** Sie können keine personalisierten Kundenerfahrungen liefern.

### Vorhandene Datenlandschaft von Contoso
- **Lückenhaften Kundendaten:** Da Contoso mehrere Systeme verwendet, verfügt das Unternehmen über mehrere Datensätze für dieselbe Person. Dies führt zu einer unangenehmen Erfahrung für die Kundinnen und Kunden, die erwarten, unabhängig vom Kanal, über den sie ihre Transaktionen abwickeln, als eine Person behandelt zu werden.
- **Mehrere Plattformen:** Die Architektur von Contoso hat sich durch Akquisitionen und Altsysteme weiterentwickelt, sodass Daten nicht nur in verschiedenen Systemen, sondern auch auf verschiedenen Plattformen, in mehreren Clouds und vor Ort gespeichert werden können.
- **Nicht-Kundendaten:** Contoso zeichnet Korrelationen zwischen Nicht-Kundendaten und den Auswirkungen auf die Kundenerfahrung, einschließlich Daten von Dritten wie Wetterdaten.

### Customer Insights-Projekt von Contoso Coffee
Sie wurden als Projektmanager bzw. Projektmanagerin für die Implementierung von Dynamics 365 Customer Insights bei Contoso Coffee ausgewählt. Aufgrund Ihrer Erfahrung legen Sie die folgende Vorgehensweise fest:
1. Erstellen einer Customer Insights-Umgebung
2. Daten aus Datenquellen mit der höchsten Priorität aus dem Unternehmen erfassen:
   - Verkaufsstelle (POS)
   - Daten zur Kundenbindung
   - E-Commerce-Kundschaft
   - Online-Einkäufe
3. Erstellen eines einheitlichen Kundenprofils aus erfassten Daten

## Modul-Einführung

### Lab-Voraussetzungen:
Bevor Sie diese Übung starten können, müssen Sie Lab 0 abgeschlossen haben, um Ihre Umgebung einzurichten.

### Datenerfassung und Datenvereinheitlichung
Als Projektmanager bzw. Projektmanagerin für Contoso Retail erstellen Sie ein einheitliches Kundenprofil, indem Sie wichtige Quellen für Kundendaten einbeziehen und den Prozess des Zuordnens, Abgleichens und Zusammenführens befolgen. In diesem Lab werden wir Daten erfassen. Im nächsten Lab werden wir die Daten vereinheitlichen.

**Geschätzter Zeitaufwand:** 45 Minuten

### Vertrautmachen mit Customer Insights - Data
In dieser Aufgabe erkunden Sie die vorkonfigurierte Demoumgebung, um sich mit dem Navigieren in der Customer Insights - Data-Anwendung vertraut zu machen.
1. Melden Sie sich bei Customer Insights - Data unter https://home.ci.ai.dynamics.com an, falls Sie noch nicht angemeldet sind.
2. Vergewissern Sie sich, dass im Auswahlmenü „Umgebung“ oben rechts die Option **Marketing-Testversion** ausgewählt ist.
3. Erkunden Sie die Optionen für das linke Menü, um sich mit der Navigation vertraut zu machen:
   - **Home:** Startseite
   - **Kundinnen und Kunden:** Ansichtskarten für einheitliche Kundenprofile (Sie können dies noch nicht einsehen – wir müssen zuerst unsere Daten erfassen und vereinheitlichen)
   - **Daten > Datenquellen:** Erfassen von isolierten demografischen, transaktionsbezogenen oder verhaltensbezogenen Daten. Zuordnen, Abgleichen und Zusammenführen in ein einheitliches Kundenprofil. Zeigen Sie Ihre Entitäten an, und definieren Sie Aktivitätstypen und deren Beziehungen zu Ihrer Kundschaft.
   - **Daten > Anreicherung:** Gehen Sie über Ihr einheitliches Profil hinaus und bereichern Sie Kundenprofile mit proprietären Microsoft-Daten. Erhalten Sie Daten zu Affinitäten für Hunderte von Marken und Dutzende von Interessenkategorien. Diese Affinitäten werden für Profile extrahiert, die Ihrer Kundschaft ähneln könnten.
   - **Erkenntnisse > Segmente, Kennzahlen und Prognosen:** Segmente anzeigen, Kennzahlen konfigurieren und sofort einsatzbereite Prognosemodelle verwenden (oder eigene erstellen). (Diesen Abschnitt können Sie noch nicht einsehen.)
   - **Einstellungen:** Verwalten der Rollen, Berechtigungen, APIs und Exportziele für Kundensegmente.

## Übung 1: Datenerfassung
In diesem Lab werden Sie mit der Erfassung von Daten aus verschiedenen Quellen vertraut gemacht. Als Projektmanager bzw. Projektmanagerin für Contoso Retail haben Sie bereits festgestellt, dass zu den wichtigsten Datenquellen Kundinnen und Kunden des E-Commerce, Online-Käufe, Barkäufe in den Geschäften und Daten aus dem Treueprogramm für Kundenkarten von Contoso Retail gehören.

### Aufgabe 1: Datenerfassung von Kundendaten aus der eCommerce-Plattform
1. Melden Sie sich bei Customer Insights unter http://home.ci.ai.dynamics.com an und vergewissern Sie sich, dass **Marketing-Testversion** im Dropdown-Menü oben rechts ausgewählt ist.
2. Erweitern Sie in Customer Insights im linken Navigationsmenü **Daten** und wählen Sie **Datenquellen** aus.
3. Wählen Sie **+ Datenquelle hinzufügen** aus. Sehen Sie sich die verfügbaren Methoden zur Datenerfassung an. Wählen Sie für dieses Lab Microsoft Power Query, benennen Sie die Quelle *eCommerce* und wählen Sie dann **Weiter**.
4. Sie erhalten eine Übersicht über die Power Query-Datenquellen, die Customer Insights erfassen kann. Achten Sie auf die verfügbaren Konnektoren. Wählen Sie den **Text/CSV**-Konnektor aus.
5. Geben Sie https://aka.ms/CI-ILT/Contacts für Dateipfad oder URL ein und wählen Sie **Weiter**. Es kann einen Moment dauern, bis die Daten hochgeladen wurden.
6. Sie sollten nun die Daten aus der Quelle durch Tabulatorzeichen getrennt sehen. Wählen Sie **Daten transformieren**, um die Datentypen und -formate für die von Ihnen erfassten Daten zu konfigurieren.
7. Sie werden feststellen, dass die Spaltenüberschrift in der ersten Zeile der Daten angezeigt wird. Um dies zu korrigieren, wählen Sie entweder **Transformieren > Erste Zeile als Überschrift** auf der Registerkarte „Startseite“ aus oder wählen Sie die Registerkarte **Transformieren** und dann **Erste Zeile als Überschrift** aus.
8. Da wir Daten aus einer Text-/CSV-Quelle erfasst haben, sind alle Spalten standardmäßig auf den Datentyp „Text“ eingestellt. Um die Daten erfolgreich zu erfassen und zu modellieren, können wir den Datentyp für Nicht-Text-Spalten festlegen. Um den Datentyp zu ändern, wählen Sie das ABC-Symbol in der jeweiligen Spaltenüberschrift aus. Aktualisieren Sie den Datentyp für die folgenden Spalten:
   - **DateOfBirth**: Datum
   - **CreatedOn:** Datum
   - **Einkommen:** Währung
9. Überprüfen Sie, ob im Bereich „Abfrageeinstellungen“ im Feld „Name“ die Option „Kontakte“ festgelegt ist. Wählen Sie **Weiter** aus. Wählen Sie **Speichern**.
   - Herzlichen Glückwunsch. Sie haben nun erfolgreich Ihre erste Datenquelle mit einem Dataset erstellt! Wir werden den Import des nächsten Datasets in der nächsten Aufgabe fortsetzen.

## Aufgabe 2: Erfassen von Daten zu Online-Einkäufen
In dieser Aufgabe werden wir Online-Kaufdaten erfassen, die Käufe über die Contoso Coffee-Website darstellen.

1. Erweitern Sie in Customer Insights im linken Menü **Daten** und wählen Sie **Datenquellen**.
2. Wählen Sie unter *Von mir verwaltet (1)* den Datensatz **eCommerce** aus und wählen Sie **Bearbeiten**. Wählen Sie **Weiter** aus.
   - **Hinweis:** Wenn Ihre Daten noch aktualisiert werden, müssen Sie warten, bis der Vorgang abgeschlossen ist, bevor Sie sie bearbeiten können. Sie können direkt zu Aufgabe 3 springen und dann zu Aufgabe 2 zurückkehren, nachdem Sie die Aufgaben 3 bis 5 abgeschlossen haben.
3. Sie sollten die Power Query-Ansicht der E-Commerce-Kontaktdaten erhalten, die Sie in Aufgabe 1 importiert haben. Wählen Sie auf der Registerkarte **Startseite** die Option **Daten abrufen** aus.
4. Sie erhalten eine Ansicht der Connectoren der Datenquellen, die Customer Insights erfassen kann. Wählen Sie den **Text/CSV**-Konnektor aus.
5. Geben Sie https://aka.ms/CI-ILT/OnlinePurchases für Dateipfad oder URL ein und wählen Sie **Weiter**. Klicken Sie auf **Erstellen**.
6. Wie zuvor wählen Sie **Transformieren**, dann **Erste Zeile als Überschrift verwenden**.
7. Aktualisieren Sie die Datentypen für die folgenden Spalten:
   - **PurchasedOn**: Datum
   - **TotalPrice**: Währung
8. Nennen Sie diese Abfrage *Einkäufe* und wählen Sie **Speichern.**

## Aufgabe 3: Einlesen von Kundendaten aus dem Treueprogramm
1. Erweitern Sie in Customer Insights im linken Menü **Daten** und wählen Sie **Datenquellen**.
2. Wählen Sie **+ Datenquelle hinzufügen** aus und wählen Sie **Microsoft Power Query** als Importmethode aus. Nennen Sie die Quelle *Treue* und wählen Sie dann **Weiter.**.
3. Wählen Sie den **Text/CSV**-Konnektor aus.
4. Geben Sie https://aka.ms/CI-ILT/LoyaltySchemeCustomers für Dateipfad oder URL ein, wählen Sie **Weiter** und dann **Daten umwandeln**.
5. Wählen Sie wie zuvor „Transformieren“ aus, und verwenden Sie dann die erste Zeile als Überschrift.
6. Aktualisieren Sie den Datentyp für die folgenden Spalten:
   - **DateOfBirth**: Datum
   - **RewardsPoints**: Ganze Zahl
   - **CreatedOn:** Datum
7. Benennen Sie diese Abfrage im Bereich „Abfrageeinstellungen“ in *Kundschaft* um und wählen Sie **Weiter**.
8. Wählen Sie auf dem Aktualisierungsbildschirm **Speichern**.

## Aufgabe 4: Erfassen von Kundendaten aus den Point-of-Sale-Käufen
1. Erweitern Sie in Customer Insights im linken Navigationsmenü **Daten** und wählen Sie **Datenquellen** aus.
2. Wählen Sie **+ Datenquelle hinzufügen**, wählen Sie **Microsoft Power Query** und benennen Sie die Quelle *PoS*, dann wählen Sie anschließend **Weiter**.
3. Wählen Sie den **Text/CSV**-Konnektor aus.
4. Geben Sie https://aka.ms/CI-ILT/POSPurchases für Dateipfad oder URL ein. Wählen Sie **Weiter** und dann **Daten transformieren**.
5. Wie zuvor wählen Sie **Transformieren**, dann **Erste Zeile als Überschrift verwenden**.
6. Aktualisieren Sie den Datentyp für die folgenden Spalten:
   - **PurchasedOn**: Datum
   - **GesamtPreis**: Währung
   - **RewardsPointsAdded:** Ganze Zahl
7. Benennen Sie die Abfrage im Feld **Name** im Bereich „Abfrageeinstellungen“ in *Einkäufe* um. Wählen Sie **Weiter** aus.
8. Wählen Sie auf dem Bildschirm zur Datenaktualisierung **Speichern**.

## Aufgabe 5: Erfassen von Kundendaten aus Websitebewertungen
1. Erweitern Sie in Customer Insights im linken Navigationsmenü **Daten** und wählen Sie **Datenquellen** aus.
2. Wählen Sie **+ Datenquelle hinzufügen**. Wählen Sie **Microsoft Power Query** und nennen Sie die Quelle *Website*, und wählen Sie anschließend**Weiter**.
3. Wählen Sie den **Text/CSV**-Konnektor aus.
4. Geben Sie https://aka.ms/CI-ILT/WebReviews für Dateipfad oder URL ein. Wählen Sie **Weiter** und dann **Daten transformieren**.
5. Wählen Sie wie zuvor **Transformieren,** dann **Die erste Zeile als Überschrift verwenden**.
6. Aktualisieren Sie den Datentyp für die folgenden Spalten:
   - **ReviewRating**: Ganze Zahl
   - **ReviewDate**: Datum
7. Benennen Sie die Abfrage im Feld **Name** im Bereich „Abfrageeinstellungen“ in *Bewertungen* um. Wählen Sie **Weiter** aus.
8. Wählen Sie auf dem Bildschirm „Einstellungen aktualisieren“ die Option **Speichern**.
