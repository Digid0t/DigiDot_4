# DigiDot_4
Die Webseite ist ein "Python Module Explorer", der Entwicklern hilft,Importus: Python-Module nach Kategorien zu entdecken, zu testen und den passenden Installationscode zu generieren.


![alt text](https://via.placeholder.com/800x450.png?text=Python+Module+Explorer+Screenshot)


(Hier sollte ein Screenshot oder eine GIF-Animation der Anwendung eingefügt werden)
🚀 Live-Demo

Hier geht's zur Live-Anwendung
🌟 Über das Projekt

Der Python Module Explorer wurde entwickelt, um den Prozess der Einrichtung neuer Python-Projekte zu beschleunigen. Anstatt mühsam nach den richtigen Modulnamen und Installationsbefehlen zu suchen, bietet dieses Tool eine zentrale Anlaufstelle, um Module nach Anwendungsbereichen zu durchsuchen, eine Auswahl zu treffen und direkt den benötigten Code zu erhalten. Es dient sowohl als Lernwerkzeug für neue Python-Entwickler als auch als Produktivitäts-Tool für erfahrene Programmierer.
✨ Features

    Interaktive Modul-Entdeckung: Durchsuchen Sie über 600 Python-Module, die in mehr als 50 logische Kategorien unterteilt sind.

    Dynamische Auswahlliste: Fügen Sie Module per Klick oder durch manuelle Eingabe zu Ihrer Auswahlliste hinzu.

    Code-Generierung: Erstellen Sie automatisch Installationsbefehle (pip install ...) für Windows, macOS und Linux.

    Sicherer Import-Code: Generieren Sie Python-Code mit try-except-Blöcken, um zu überprüfen, welche Module in Ihrer Umgebung bereits vorhanden sind.

    Modul-Test-Funktion: Testen Sie direkt im Tool, welche Module importiert werden können und welche fehlen.

    Lokales Speichern: Sichern Sie Ihre Modulauswahl direkt im Browser, um später daran weiterzuarbeiten.

    Dunkelmodus: Wechseln Sie zwischen einem hellen und einem dunklen Design für eine angenehme Nutzung.

    Responsive Design: Nutzbar auf Desktops, Tablets und mobilen Geräten.

🛠️ Nutzung und Anwendung

Die Bedienung des Tools ist intuitiv und in wenige Schritte unterteilt.
1. Module entdecken und auswählen

    Per Kategorie: Klicken Sie auf eine der Modulkategorien (z.B. "Datenanalyse", "Webentwicklung", "Machine Learning").

    Modaltabelle: Es öffnet sich ein Fenster mit einer Tabelle aller Module dieser Kategorie.

    Auswählen: Setzen Sie ein Häkchen in der Spalte "Auswahl", um ein Modul zur zentralen Liste "Ausgewählte Module" hinzuzufügen.

    Manuell hinzufügen: Geben Sie im Feld "Füge fehlende Imports hier ein" kommagetrennte Modulnamen ein (z.B. numpy, pandas) und klicken Sie auf "Hinzufügen".

2. Auswahl verwalten

Im Bereich "Ausgewählte Module" sehen Sie alle hinzugefügten Module. Von hier aus können Sie:

    Liste leeren: Entfernt alle Module aus der aktuellen Auswahl.

    Auswahl speichern: Sichert die aktuelle Liste im Local Storage Ihres Browsers. Beim nächsten Besuch wird die Liste automatisch geladen.

3. Code generieren

Klicken Sie auf den Button "Installationscode generieren", um ein neues Fenster zu öffnen. Dort finden Sie drei Tabs:

    Import-Code:

        Erzeugt ein Python-Skript.

        Mit der Option "Import-Tests hinzufügen" wird für jedes Modul ein try-except-Block generiert. Führen Sie dieses Skript aus, um zu sehen, welche Module fehlen.
        .

    Installationsbefehle:

        Zeigt den vollständigen pip install-Befehl an, um alle ausgewählten Module auf einmal zu installieren.

        Es werden spezifische Befehle für Windows (CMD/PowerShell) und Linux/macOS bereitgestellt.
        .

    Einzelne Module:

        Listet jedes Modul einzeln mit seinem Installationsbefehl auf.

        Klicken Sie auf einen Befehl, um ihn in die Zwischenablage zu kopieren.

4. Module testen

Mit dem Button "Module testen" können Sie eine kommagetrennte Liste von Modulen eingeben und simulieren, ob diese importierbar sind. Fehlende Module können optional direkt zur Auswahlliste hinzugefügt werden.
Anwendungsfälle

    Schnelles Projekt-Setup: Richten Sie eine neue Projektumgebung in wenigen Minuten ein.

    Lernwerkzeug: Entdecken Sie populäre Bibliotheken für verschiedene Anwendungsbereiche (z.B. "Welche Bibliotheken gibt es für die Spieleentwicklung?").

    Anforderungsliste erstellen: Stellen Sie eine Liste von Abhängigkeiten für ein Projekt zusammen und teilen Sie den generierten pip-Befehl mit Ihrem Team.

    Umgebungs-Check: Generieren Sie den Test-Import-Code, um schnell zu überprüfen, ob alle benötigten Tools in einer bestehenden virtuellen Umgebung installiert sind.

💻 Technische Umsetzung

Der Python Module Explorer ist eine reine Frontend-Anwendung, die mit HTML, CSS und "Vanilla" JavaScript (ohne externe Frameworks) erstellt wurde.
HTML-Struktur

Die index.html-Datei ist das Grundgerüst der Anwendung und besteht aus mehreren Hauptkomponenten:

    <header>: Enthält den Titel und den Umschalter für das Farbschema.

    container: Der Hauptwrapper für alle sichtbaren Inhalte.

    module-section: Wiederverwendbare Blöcke für die verschiedenen Funktionsbereiche (manuelle Eingabe, ausgewählte Module).

    module-category-grid: Ein CSS-Grid, in das die Kategorien-Karten dynamisch geladen werden.

    Modals: Mehrere <div>-Elemente mit der Klasse .modal, die standardmäßig ausgeblendet sind. Sie dienen als Pop-up-Fenster für:

        categoryModal: Anzeige der Module einer Kategorie.

        codeModal: Anzeige des generierten Codes.

        testModuleModal: Dialog zum Testen von Modulen.

        pypiInfoModal: (Simulierte) Anzeige von PyPI-Informationen.

CSS (Styling)

Das Styling wird durch eine einzige interne <style>-Sektion realisiert und nutzt moderne CSS-Features:

    CSS-Variablen: Das Theming (Hell/Dunkel) wird effizient über CSS-Variablen (:root und .dark-theme) gesteuert. Eine Änderung der Variablen färbt die gesamte Anwendung um.
    Generated css

      
:root {
    --bg-light: #e8f5e9;
    --accent: #4caf50;
    /* ... */
}

.dark-theme {
    --bg-light: #bed3b6;
    --accent: #4caf50;
    /* ... */
}

    

IGNORE_WHEN_COPYING_START

    Use code with caution. Css
    IGNORE_WHEN_COPYING_END

    Flexbox und Grid: Für das Layout der Hauptkomponenten und der Modul-Kategorien werden display: flex und display: grid verwendet, um ein flexibles und responsives Design zu gewährleisten.

    Responsivität: @media-Queries passen das Layout für kleinere Bildschirme (Tablets und Smartphones) an, um eine gute Benutzererfahrung auf allen Geräten sicherzustellen.

JavaScript (Logik)

Die gesamte Funktionalität der Webseite wird durch ein einziges <script> am Ende der HTML-Datei gesteuert.

    Datenquelle (moduleData):

        Die Modul- und Kategoriendaten sind als großes JSON-ähnliches Objekt (const moduleData) direkt im Code festgeschrieben. Dies macht die Anwendung unabhängig von externen APIs, bedeutet aber auch, dass zur Aktualisierung der Daten der Code selbst geändert werden muss.

        Die Struktur ist einfach: Ein Array categories und ein Objekt modules, bei dem jeder Schlüssel eine Kategorie ist und der Wert ein Array von Modul-Objekten ist.

    Zustandsverwaltung (appState):

        Ein zentrales Objekt appState verwaltet den aktuellen Zustand der Anwendung.

        selectedModules: Ein Set-Objekt speichert die Namen der ausgewählten Module. Ein Set wird verwendet, um Duplikate automatisch zu verhindern.

        currentCategory: Speichert die aktuell im Modal geöffnete Kategorie.

        theme: Speichert das aktuelle Theme ('light' oder 'dark').

    Initialisierung (initApp, DOMContentLoaded):

        Der Code wird ausgeführt, sobald das DOM vollständig geladen ist (DOMContentLoaded).

        Die initApp()-Funktion ist der Einstiegspunkt. Sie ruft loadSavedState() auf, um Daten aus dem localStorage zu laden und registriert alle notwendigen Event-Listener für die Buttons und interaktiven Elemente.

    Dynamische UI-Generierung:

        initializeCategoriesGrid(): Iteriert durch moduleData.categories und erstellt dynamisch die klickbaren Kategorie-Karten.

        showCategoryModules(category): Filtert die Module aus moduleData.modules für die angeklickte Kategorie und erzeugt dynamisch die Tabellenzeilen (<tr>) im Kategoriemodal.

    Kernfunktionen:

        updateSelectedModulesDisplay(): Liest die Module aus appState.selectedModules und aktualisiert die Textanzeige im Hauptfenster.

        generateCode(): Sammelt die ausgewählten Module und ruft die Hilfsfunktionen updateImportCode(), updateInstallationCode() und updateSingleModulesTable() auf, um die Inhalte der Tabs im Code-Modal zu befüllen.

        runImportTest(): Simuliert einen Import-Test mit Math.random(), um Erfolgs- und Fehlerfälle darzustellen.

    Persistenz (localStorage):

        saveSelection(): Konvertiert das Set der ausgewählten Module in ein Array, wandelt es mit JSON.stringify() in einen String um und speichert es im localStorage.

        loadSavedState(): Überprüft beim Start, ob gespeicherte Daten (Module und Theme) im localStorage vorhanden sind und stellt den Anwendungszustand wieder her.

🚀 Zukünftige Verbesserungen

Dieses Projekt hat Potenzial für viele Erweiterungen:

    Externe Datenquelle: Die Moduldaten aus moduleData in eine externe modules.json-Datei auslagern, um die Wartung zu erleichtern.

    Echte PyPI-API-Integration: Anstelle von simulierten Daten könnten die Modul-Details (Version, Beschreibung) live von der PyPI-API abgerufen werden.

    Erweiterte Suche: Eine globale Suchfunktion, die alle Kategorien und Module durchsucht.

    Export/Import: Die Möglichkeit, eine Modulauswahl als JSON-Datei zu exportieren und zu importieren.

    Benutzer-Accounts: Speichern von verschiedenen Modul-Listen in einem Benutzerkonto.
