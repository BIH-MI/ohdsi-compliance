# Betriebskonzept: OHDSI-Forschungsdatenbank

- **Verantwortlicher:** [Name]
- **Autor:** [Name]
- **Datum:** [TT.MM.YYYY]
- **Version:** [1.0]

## Inhalt

1. Überblick
2. Betriebsprozesse
   * 2.1 Installation
   * 2.2 Updates
   * 2.3 Releasewechsel
   * 2.4 Starten und Stoppen der Komponenten
   * 2.5 Nutzer- und Berechtigungsverwaltung
   * 2.6 Backup
   * 2.7 Wiederanlaufplan
   * 2.8 Verfügbarkeit
3. Kontinuierliche Verbesserung
4. Referenzen

## 1 Überblick

Das vorliegende Dokument beschreibt alle Maßnahmen zum sicheren Betrieb der OHDSI-Forschungsdatenbank. Diese besteht aus verschiedenen technischen Komponenten und Anwendungssoftware, die in der Verfahrensbeschreibung [1] detailliert beschrieben sind. Rechte und Rollen sind im Berechtigungskonzept [2] beschrieben. Das vorliegende Dokument umfasst Angaben zur Installationsumgebung, zum Betrieb, zu Updateprozessen und zur Weiterentwicklung.

## 2 Betriebsprozesse

### 2.1. Installation

Die Installation findet in Form des Broadsea-Paketierung [3] mittels *Docker Compose* statt. Der genutzte Server erfüllt die in [3] beschriebenen Systemvoraussetzungen:

- **Spezifikation des Servers und Betriebssystems, z.B. Ubuntu 22.04.3 LTS**
- **Spezifikation der CPU, z.B. 8 Kerne**
- **Spezifikation weiterer Eigenschaften, z.B. 16 GB RAM**

[_Hinweis: Anpassen._]

Es wurden entsprechende Zertifikate erstellt und konfiguriert, um verschlüsselte Verbindungen zu unterstützen. Ports, die unverschlüsselte Kommunikation ermöglichen (z.B. HTTP) wurden deaktiviert.

[_Hinweis: Der vorliegende Text beschreibt eine Installation mittels der OHDSI Broadsea-Paketierung auf Basis von Docker. Wird eine native Installation vorgenommen, muss der Text entsprechend angepasst werden._]

### 2.2 Updates

Das Betriebssystem ist so konfiguriert, dass alle 24 Stunden eine Prüfung auf und ggf. ein einspielen von Security Patches stattfindet. Drüber hinaus finden Software Updates nach Bedarf manuell statt. Der Softwarestand des Servers wird einmal im Quartal manuell durch die technischen Administrierenden geprüft.

[_Hinweis: Bei Abweichungen anpassen._]

### 2.3 Releasewechsel

Ein Releasewechsel der OHDSI-Komponenten und der Datenbank ist nur bei Auslaufen der Wartung geplant. Selbiges gilt für das Betriebssystem. Falls ein Releasewechsel notwendig wird, wird das entsprechende Update manuell eingespielt.

[_Hinweis: Bei Abweichungen anpassen._]

### 2.4 Starten und Stoppen der Komponenten

Für ein Starten und Stoppen der Komponenten muss Docker Compose mittels „docker compose up“ bzw. „docker compose down“ ausgeführt werden. Im Anschluss kann beispielsweise das Betriebssystem neu gestartet werden.

[_Hinweis: Bei Abweichungen anpassen._]

### 2.5 Nutzer- und Berechtigungsverwaltung

Die Prozesse zur Nutzer- und Berechtigungsverwaltung sind im Berechtigungskonzept [2] beschrieben.

### 2.6 Backup

Alle 24 Stunden findet ein automatisches Backup des Servers durch die zentrale Infrastruktur statt. Die erstellten Backups werden 30 Tage vorgehalten. Für die medizinischen Daten sind die Quellsysteme führend. Diese werden dort gesichert. Deshalb ist eine Sicherung im Rahmen der Forschungsdatenbank nicht notwendig. Die Forschungsdatenbank ist lediglich für die Nutzerverwaltung und Konfiguration führend. Hier ist ein Backup von 30 Tagen ausreichend, so dass kein weiteres Backup notwendig ist. Eine Archivierung der für Forschungszwecke genutzten Daten erfolgt separat durch die Forschenden unter Nutzung anderer Angebote der Organisation.

[_Hinweis: An lokale Gegebenheiten anpassen._]

### 2.7 Wiederanlaufplan

Im Falle eines unerwarteten Systemausfalls müssen die Komponenten zunächst mit „docker compose up“ gestartet werden. Der Startprozess sollte überwacht und Logging-Dateien kontrolliert werden. Sollte es zu Fehlern kommen kann (1) eine Wiedereinspielen des Backups in Betracht gezogen werden oder (2) ein neu starten des ETL-Prozesses. Ersteres wäre beispielsweise der Fall, wenn die Fehler sich auf fehlerhafte Nutzerdaten beziehen, letzteres wenn die Fehler sich auf die medizinischen Daten beziehen.

[_Hinweis: An lokale Gegebenheiten anpassen._]

### 2.8 Verfügbarkeit

Es wird angestrebt, dass ein Zugriff auf die Forschungsdatenbank für Nutzung und Administration mindestens von Montag bis Freitag von 08:00 - 20:00 Uhr möglich ist. Geplante Abweichungen von dieser Verfügbarkeitsregel für beispielsweise Wartungsarbeiten werden mindestens eine Woche vorher an alle registrierten User bekannt gegeben.

[_Hinweis: An lokale Vorgehensweise anpassen._]

## 3 Kontinuierliche Verbesserung

Die OHDSI-Forschungsdatenbank wird stetig betrieben und auf dem aktuellen Stand gehalten. Berechtigungen und Nutzende werden entsprechend in den Anlagen des Berechtigungskonzepts dokumentiert. Weitere Informationen finden sich in den Betriebs- und Informationssicherheitsdokumenten. Alle Dokumente werden stets auf dem neuesten Stand gehalten und mindestens einmal jährlich aktualisiert.

## 4 Referenzen

[1] Verfahrensbeschreibung: OHDSI-Forschungsdatenbank.

[2] Berechtigungskonzept: OHDSI-Forschungsdatenbank.

[3] OHDSI-Broadsea Dokumentation. https://github.com/OHDSI/Broadsea.