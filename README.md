# git Workshop Tag 3

[toc]

## Was ist CI/CD?

[Continuous Integration und  Continuous Developement](https://de.wikipedia.org/wiki/CI/CD)

[Video CI/CD](https://www.youtube.com/watch?v=YMJ_sdeDbFE)

**Definition:** CI/CD ist eine Methodik in  der Softwareentwicklung, die darauf abzielt, Codeänderungen häufiger und zuverlässiger in die Produktion zu überführen. CI/CD verbessert die  Effizienz und Qualität der Softwareentwicklung durch Automatisierung und häufige, zuverlässige Deployments.

**Wozu ist das gut?**

-   **Automatisierung:** Reduziert manuelle Fehler und erhöht die Effizienz.
-   **Schnelle Rückmeldung:** Fehler werden frühzeitig erkannt und behoben.
-   **Stabile Releases:** Regelmäßige und automatisierte Deployments sorgen für konsistente Qualität.

**Früher:**

-   **Manuelle Builds und Tests:** Entwickler führten Builds und Tests manuell aus, was zeitaufwendig und fehleranfällig war.
-   **Seltene Releases:** Codeänderungen wurden in großen  Mengen integriert und selten in die Produktion überführt, was oft zu  unstabilen Releases führte. vgl. [Big Ball of Mud](https://de.wikipedia.org/wiki/Big_Ball_of_Mud)

### Übliche Schritte in CI/CD

1.  Code Commit:
    -   Entwickler pushen Codeänderungen in ein Versionskontrollsystem (z.B. Git).
2.  Continuous Integration (CI):
    -   **Build:** Der Code wird automatisch gebaut.
    -   **Unittests:** Kleine Tests, die einzelne Funktionen oder Klassen testen.
    -   **Code-Analyse:** Automatische Prüfungen auf Codequalität und Sicherheitslücken.
3.  Continuous Deployment (CD):
    -   **Integrationstests:** Testen das Zusammenspiel mehrerer Komponenten oder Systeme.
    -   **Staging Deployment:** Der Code wird in eine Staging-Umgebung deployt.
    -   **Automatisierte Tests:** Weitere Tests (End-to-End, UI-Tests) werden durchgeführt.
    -   **Produktion Deployment:** Erfolgreich getesteter Code wird automatisch in die Produktionsumgebung überführt.

### Automatisierung mit Github Actions

Mit GitHub Actions kannst du deine Softwareentwicklungs-Workflows direkt in Ihrem  Repository automatisieren, anpassen und ausführen. Du kannst Actions entdecken, erstellen und weitergeben, um beliebige Aufträge (einschließlich CI/CD) auszuführen.

Github Actions werden in yaml geschrieben. YAML steht für „Yet Another Markup Language“. Es ist eine  für Menschen lesbare Auszeichnungssprache, die häufig für  Konfigurationsdateien verwendet wird, insbesondere von CI- und  [DevOps](https://de.wikipedia.org/wiki/DevOps)-fokussierten Softwaretools. YAML ist eine Erweiterung von JSON um syntaktisch  wichtige Zeilenumbrüche und Einrückungen, ähnlich wie auch in Python  geschrieben wird. ***Anders als in Python allerdings erlaubt YAML  keine Tabulator-Zeichen.***

→ [Cheat Sheet YAML](https://quickref.me/yaml.html) 

→ [Cheat Sheet Github Actions](https://resources.github.com/actions/github-actions-cheat/)

### Kleine Automatisierung selber bauen

https://dev.to/sre_panchanan/hello-world-in-github-actions-a-beginners-guide-to-your-first-workflow-1mbh

oder

https://graphite.dev/guides/github-actions-beginner-guide

Erweitert die Ausgabe: Wenn auf einen anderen Branch  gepusht wird, soll etwas anderes im Log stehen, als wenn auf Main  gepusht wird.

Wenn Ihr Zugriff auf einen Teams-Channel habt, könnt Ihr dort auch eine Nachricht hineinschreiben:

https://www.indiumsoftware.com/blog/github-event-request-notification-to-teams-channel/

Macht was zeitgesteuert: https://crontab.guru/

Findet raus, was man mit Actions noch machen kann und erzählt uns davon.

Zeigt mal die Anbindung an Discord oder eine andere Ausgabe.

### Automatisiere die Automatisierung mit Dependabot

Wenn Du [Dependabot](https://docs.github.com/de/code-security/dependabot/working-with-dependabot/keeping-your-actions-up-to-date-with-dependabot) Version Updates für GitHub Actions aktivierst, sorgt Dependabot dafür, dass die Verweise auf Aktionen in der *workflow.yml*-Datei  eines Repositorys und wiederverwendbare Workflows  auf dem neuesten Stand sind.

### Fragen

Was sind Github-Actions?

Was ist CI/CD? Wozu braucht man das?

## Exkurs Verschlüsselung (ca. 30 Minuten)

Video 13 Minuten: https://www.youtube.com/watch?v=yWrtCtQ7Wno

### Symmetrische Verschlüsselung

**Definition:** Bei der symmetrischen Verschlüsselung wird derselbe Schlüssel zum Ver- und Entschlüsseln von Daten verwendet.

**Vorteile:**

-   Schneller und weniger rechenintensiv
-   Einfach zu implementieren

**Nachteile:**

-   Schlüsselverteilung ist problematisch; beide Parteien müssen denselben Schlüssel sicher austauschen

**Algorithmen:**

-   AES (Advanced Encryption Standard)
-   DES (Data Encryption Standard)
-   3DES (Triple DES)

**Einsatzzwecke:**

-   Verschlüsselung von Daten während der Speicherung (z.B. auf Festplatten)
-   Sicherer Datentransfer über unsichere Netzwerke (wenn der Schlüssel sicher verteilt wurde)

### Asymmetrische Verschlüsselung

**Definition:** Bei der asymmetrischen Verschlüsselung werden ein öffentlicher  Schlüssel zum Verschlüsseln und ein privater Schlüssel zum Entschlüsseln verwendet.

**Vorteile:**

-   Sicherer Schlüsselaustausch; der öffentliche Schlüssel kann frei verteilt werden
-   Ermöglicht digitale Signaturen zur Authentifizierung und Integrität

**Nachteile:**

-   Langsamer und rechenintensiver im Vergleich zur symmetrischen Verschlüsselung

**Algorithmen:**

-   [RSA](https://de.wikipedia.org/wiki/RSA-Kryptosystem) (Rivest-Shamir-Adleman)
-   ECC (Elliptic Curve Cryptography)
-   DSA (Digital Signature Algorithm)

**Einsatzzwecke:**

-   Sichere Schlüsselverteilung für symmetrische Verschlüsselung
-   Digitale Signaturen und Zertifikate
-   Sichere Kommunikation (z.B. HTTPS)

### tl;dr

-   **Symmetrische Verschlüsselung**: Schnell, einfacher Schlüssel, schwierig zu verteilen. Verwendet für schnelle Datenverschlüsselung.
-   **Asymmetrische Verschlüsselung**: Sicherer Schlüssel, langsamer, einfach zu verteilen. Verwendet für sicheren Schlüsselaustausch und digitale Signaturen.

## Abschluss

### Was Ihr gelernt habt

Git, Git-Config, Github, Repo, Remote, Commits und Commit-Messages,  Markdown, Push, Merge, Pull vs. Fetch, add, status, log, Branch, Pull Requests,  Kanban-Board, Git GUI, SSH-Key, Git auf der Kommandozeile, YAML, CI/CD,  Git Actions, workflows, symmetrische, asymmetrische und hybride  Verschlüsselung. 

Ihr könnt ein Log lesen und Probleme selbständig lösen.

Ihr könnt zusammen arbeiten.

### Wie war es?

Wenn Ihr den Git-Workshop für die Azubis im nächsten Jahr geben würdet – was würdet Ihr anders machen? Reihenfolge, Inhalte, mehr oder weniger von  irgendwas?

#### Aufgabe (Git, Refactoring, Ordnung und Struktur)

Fasst die drei Repos unter https://github.com/elfengleich/ zu einem zusammen, das eine README mit allgemeineren Infos enthält und jeweils ein md-File für jeden Tag. Strukturiert dabei auch innerhalb der Tage so um, wie ihr den Workshop besser gefunden hättet. 

## Weiterführende Links

Github-Repo mit allen Inhalten für die Berufsschule als werdender FiSi https://github.com/TredexOwl/Berufsschule



Danke!
