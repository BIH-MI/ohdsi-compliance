# Informationssicherheitskonzept: OHDSI-Forschungsdatenbank

- **Verantwortlicher:** [Name]
- **Autor:** [Name]
- **Datum:** [TT.MM.YYYY]
- **Version:** [1.0]

## Inhalt

1. Übersicht
2. Schutzbedarfs- und Risikobewertung
   * 2.1 Schutzbedarf
   * 2.2 Risikobewertung
     - 2.2.1 Prozess 1: Datentransformation und -laden
     - 2.2.2 Prozess 2: Datennutzung
3. Maßnahmen
   * 3.1 Zugangskontrolle
   * 3.2 Datenträgerkontrolle
   * 3.3 Speicherkontrolle
   * 3.4 Benutzerkontrolle
   * 3.5 Zugriffskontrolle
   * 3.6 Übertragungskontrolle
   * 3.7 Eingabekontrolle
   * 3.8 Transportkontrolle
   * 3.9 Wiederherstellbarkeit
   * 3.10 Zuverlässigkeit
   * 3.11 Datenintegrität
   * 3.12 Auftragskontrolle
   * 3.13 Verfügbarkeitskontrolle
   * 3.14 Trennbarkeit
4. Referenzen

## 1 Übersicht

In der OHDSI-Forschungsdatenbank werden besondere Kategorien personenbezogener Daten, nämlich Gesundheitsdaten, verarbeitet. Ziel dieses Dokumentes ist es, die technischen und organisatorischen Maßnahmen zu beschreiben, die ergriffen wurden, um dabei die Sicherheitsziele Vertraulichkeit, Integrität sowie Verfügbarkeit zu gewährleisten.

## 2 Schutzbedarfs- und Risikobewertung

### 2.1 Schutzbedarf

Die OHDSI-Forschungsdatenbank verwaltet zwei wesentliche Arten personenbezogener Daten: (1) Gesundheitsdaten, (2) Nutzendendaten. Desweiteren existiert die OHDSI-Forschungsdatenbank für genau einen Zweck: Auswertungen für die medizinische Forschung ermöglichen. Beides ist in der Verfahrensbeschreibung genau dargelegt [4]. Aufgrund dieser engen Ausrichtung, wird der Schutzbedarf für alle Komponenten anhand der Skala "niedrig, mittel und hoch" gemeinsam erörtert.

Die Vertraulichkeit der gespeicherten Gesundheitsdaten ist von großer Wichtigkeit, da diese jedoch bereits vor Übernahme in die Forschungsdatenbank pseudonymisiert werden, wird ein mittlerer Scutzbedarf angenommen. Die Integrität der Daten ist wichtig, aber eine Verletzung hätte in der Forschung weniger gravierende Folgen, als beispielsweise in der Krankenversorgung (Schutzbedarf: mittel). Die Verfügbarkeit der Daten ist weniger wichtig, da Forschungsaktivitäten aufgeschoben werden können (Schutzbedarf: niedrig). Der Schutzbedarf der Nutzendendaten ist in Bezug auf Vertraulichkeit und Integrität hoch, da unbefugter Zugriff und Missbrauch verhindert werden müssen. Der Schutzbedarf in Bezug auf die Verfügbarkeit ist als niedrig einzustufen. Diese Anforderungen übertragen sich entsprechend an die eingesetzten System- und Softwarekomponenten.

### 2.2 Risikobewertung

Bei der Durchführung der Risikoanalyse zur Feststellung des Schutzbedarfs und notwendiger Maßnahmen für die Forschungsdatenbank wurde weitgehend den Methoden der Agentur der Europäischen Union für Cybersicherheit (ENISA) [1] sowie des IT-Grundschutzes des deutschen Bundesamtes für Sicherheit in der Informationstechnik (BSI), d.h. der Methodik des BSI-Standards 200-3, gefolgt [2]. Dies bedeutet u.a., dass Eintrittshäufigkeiten und Auswirkungsschweren der identifizierten Gefährdungen zunächst einzeln und anschließend zusammenfassend bewertet werden. Zur Risikobewertung auf Basis von Eintrittshäufigkeiten und Auswirkungen wird gemäß ENISA die folgende 3x3-Risikomatrix genutzt.

|                                 |         | **Grad der Auswirkung** | **Grad der Auswirkung** | **Grad der Auswirkung** |
|---------------------------------|---------|-------------------------|-------------------------|-------------------------|
|                                 |         | Niedrig                 | Mittel                  | Hoch                    |
| **Eintrittswahrscheinlichkeit** | Niedrig | Geringes Risiko         | Mittleres Risiko        | Hohes Risiko            |
| **Eintrittswahrscheinlichkeit** | Mittel  | Geringes Risiko         | Mittleres Risiko        | Hohes Risiko            |
| **Eintrittswahrscheinlichkeit** | Hoch    | Mittleres Risiko        | Hohes Risiko            | Hohes Risiko            |

[_Hinweis: Alternativ kann ein individuell geeigneter Ansatz für die Risikoanalyse gewählt werden. Es empfiehlt sich zunächst zu prüfen, ob eine unternehmensinterne Methodik exisiert._]

Bei den Auswirkungen kann es sich um technische (bspw. Verlust von Verfügbarkeit von Systemen) und geschäftliche (bspw. Reputationsverlust) Schäden handeln [1]. Im vorliegenden Dokument wird der Grad der Auswirkungen auf Basis der Ergebnisse der Schutzbedarfsfeststellung ermittelt. Zur Abschätzung der Eintrittswahrscheinlichkeit können verschiedene Aspekte, wie die gegebenen Umstände, bisherige organisations- oder unternehmensspezifische Erfahrungen, sowie allgemeine Statistiken berücksichtigt werden [1]. Eckpunkte für die Risikoanalyse ergeben sich aus den zu betrachtenden Gewährleistungszielen, Gefährdungen und Schutzmaßnahmen. Die wesentlichen Ziele der Informationssicherheit sowie wesentliche identifizierte Gefährdungen dieser Ziele sind im Folgenden dargestellt [1].

| Gewährleistungsziel | Gefährdung                                |
|---------------------|-------------------------------------------|
| Vertraulichkeit     | Unrechtmäßiger Datenzugriff.              |
| Integrität          | Unerwünschte Datenänderung.               |
| Verfügbarkeit       | Datenverlust bzw. Ausfall der IT-Systeme. |

Grundlage der Risikoanalyse bilden die wesentlichen Verarbeitungsprozesse, die im folgenden LINDDUN Data Flow Diagram [3] dargestellt sind:

![LINDDUN Diagram](./media/data-flow.png)

[_Hinweis: Das Diagramm ist an die lokalen Gegebenheiten anzupassen. Ein LINDDUN-Diagramm ist eine spezialisierte Form eines Datenflussdiagramms, das speziell für die Analyse und Visualisierung von Datenschutzrisiken in Softwarearchitekturen entwickelt wurde. Eine Einführung und eine Beschreibung der Syntax findet sich in [3]._]

### 2.2.1 Prozess 1: Datentransformation und -laden

In diesem Prozess werden die bereits an der Quelle pseudonymisierten Daten in das Schema des OMOP Common Data Model (CDM) transformiert, terminologisch kontrolliert und in die Forschungsdatenbank geladen.

- **Vertraulichkeit**: Die Wahrscheinlichkeit für eine Verletzung der Vertraulichkeit der Daten ist aufgrund der strengen Zugangs- und Zugriffskontrolle und des beschränkten Nutzerkreises als niedrig einzuschätzen. Die Schutzbedarfsfeststellung hat einen mittleren Grad der Ausiwrkung ergeben. Dies führt uzu einem mittleren Risiko.

- **Integrität**: Die Wahrscheinlichkeit für eine Verletzung der Integrität der Daten ist als niedrig einzuschätzen, mit einem mittleren Grad der Auswirkungen. Dies führt insgesamt zu einem mittleren Risiko.

- **Verfügbarkeit**: Eine Einschränkung der Verfügbarkeit der Forschungsdatenbank ist beispielsweise durch Wartungsarbeiten und geringe Redundanz gelegentlich möglich. Die Eintrittswahrscheinlichkeit also mittelhoch. Der Grad der Auswirkung ist auf Basis der Schutzbedarfsfeststellung niedrig. Dies führt insgesamt zu einem mittleren Risiko.

Zusammenfassend ergibt sich die folgende Bewertung der Risiken für den Transformations- und Ladeprozess:

| Gewährleistungsziel | Eintrittshäufigkeit | Auswirkung       | Risiko           |
|---------------------|---------------------|------------------|------------------|
| Vertraulichkeit     | Niedrig             | Mittel           | Mittleres Risiko |
| Integrität          | Niedrig             | Mittel           | Mittleres Risiko |
| Verfügbarkeit       | Mittel              | Niedrig          | Mittleres Risiko |

[_Hinweis: Die Bewertung ist potenziell an die eigenen Einschätzungen anzupassen._]

### 2.2.2 Prozess 2: Datennutzung

In diesem Prozess kommt es zur Nutzung der pseudonymisierten Daten und OHDSI-Datenanalysetools zu Forschungszwecken.

- **Vertraulichkeit**: Die Wahrscheinlichkeit für eine Verletzung der Vertraulichkeit der Daten ist aufgrund der strengen Zugangs- und Zugriffskontrolle und des beschränkten Nutzerkreises als niedrig einzuschätzen. Die Schutzbedarfsfeststellung hat einen mittleren Grad der Ausiwrkung ergeben. Dies führt uzu einem mittleren Risiko.

- **Integrität**: Die Wahrscheinlichkeit für eine Verletzung der Integrität der Daten ist als niedrig einzuschätzen, mit einem mittleren Grad der Auswirkungen. Dies führt insgesamt zu einem mittleren Risiko.

- **Verfügbarkeit**: Eine Einschränkung der Verfügbarkeit der Forschungsdatenbank ist beispielsweise durch Wartungsarbeiten und geringe Redundanz gelegentlich möglich. Die Eintrittswahrscheinlichkeit also mittelhoch. Der Grad der Auswirkung ist auf Basis der Schutzbedarfsfeststellung niedrig. Dies führt insgesamt zu einem mittleren Risiko.

Zusammenfassend ergibt sich die folgende Bewertung der Risiken für den Datennutzungsprozess:

| Gewährleistungsziel | Eintrittshäufigkeit | Auswirkung       | Risiko           |
|---------------------|---------------------|------------------|------------------|
| Vertraulichkeit     | Niedrig             | Mittel           | Mittleres Risiko |
| Integrität          | Niedrig             | Mittel           | Mittleres Risiko |
| Verfügbarkeit       | Mittel              | Niedrig          | Mittleres Risiko |

[_Hinweis: Die Bewertung ist potenziell an die eigenen Einschätzungen anzupassen._]

## 3 Maßnahmen

Die OHDSI-Forschungsdatenbank wird im stark gesicherten Intranet der Organisation betrieben und ist nur durch Mitarbeitende der Organisation zugängig. Es greifen also alle zentralen organisatorischen und technischen Maßnahmen, die bereits einen starken grundlegenden Schutz bieten.

[_Hinweis: Dieser Absatz muss entsprechend der lokalen Gegebenheiten und den in der Verfahrensbeschreibung dargelegten technischen Eigenschaften der Installation angepasst werden._]

Dieses Dokument listet im Folgenden ausschließlich spezifische technische und organisatorische Maßnahmen für die OHDSI-Forschungsdatenbank auf. 

[_Hinweis: Der Rest dieses Absatzes und die weiteren Inhalte bauen auf dem in Deutschland besonders relevanten BSI IT-Grundschutz auf und muss entsprechend der lokalen Gegebenheiten möglicherweise angepasst werden._]

Der IT-Grundschutz des BSI [2] fasst gängige Sicherheitsmaßnahmen in verschiedene Bausteine zusammen, von denen die für die Forschungsdatenbank wichtigsten im Folgenden kurz beschrieben werden:

- **Baustein Organisation und Personal – „ORP“:** Der Baustein beschreibt Sicherheitsmaßnahmen wie beispielsweise Organisation (ORP.1), Personal (ORP.2) und Sensibilisierung und Schulung zur Informationssicherheit (ORP.3).

- **Baustein Konzeption und Vorgehensweise – „CON“:** Der Baustein beschreibt Sicherheitsmaßnahmen wie Datenschutz (CON.2) oder Löschen und Vernichten (CON.6).

- **Baustein Betrieb – „OPS“:** Der Baustein beschreibt Sicherheitsmaßnahmen wie Ordnungsgemäße IT-Administration (OPS.1.1.2), Patch- und Änderungsmanagement (OPS.1.1.3) und Schutz vor Schadprogrammen (OPS.1.1.4)

- **Baustein Detektion und Reaktion – „DER“:** Der Baustein beschreibt Sicherheitsmaßnahmen wie Detektion von sicherheitsrelevanten Ereignissen (DER.1) und Behandlung von Sicherheitsvorfällen (DER.2.1).

- **Baustein Anwendungen – „APP“:** Der Baustein beschreibt Sicherheitsmaßnahmen für verschiedenen Anwendungskomponenten wie Webanwendungen (APP.3.1) oder Active Directory (APP.2.2)

- **Baustein IT-System – „SYS“:** Der Baustein beschreibt Sicherheitsmaßnahmen für verschiedene IT-Systeme wie etwa Server unter Linux und Unix (SYS.1.3) oder Virtualisierung (SYS.1.5)

- **Baustein Netze und Kommunikation – „NET“:** Der Baustein beschreibt Sicherheitsmaßnahmen für Netzwerke wie Netzmanagement (NET.1.2) oder VPN (NET.3.3).

- **Baustein Infrastruktur – „INF“:** Der Baustein beschreibt Sicherheitsmaßnahmen für die Infrastruktur wie etwa allgemein für Gebäude (INF.1) oder Rechenzentren sowie Serverraum (INF.2).

### 3.1 Zugangskontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Identitäts- und Berechtigungsmanagement (ORP.4) sowie Active Directory (APP.2.2). Für die Zugriffsregelung auf das Betriebssystem, die Datenbank sowie die Web-Oberfläche wird ein zentrales Gruppenkonzept verwendet. Die Gruppen verfügen über differenzierte Berechtigungen für Lesen, Löschen und Bearbeiten, sowie differenzierte Berechtigungen für das Betriebssystem, die Datenbank sowie die Web-Oberfläche. Die Implementation dieses Konzeptes zum Zugriff auf Betriebssystem und Web-Oberfläche findet unter Nutzung von Active Directory statt. Die Zugriffsrechte werden projektintern dokumentiert und nur persönlich vergeben [6]. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.2 Datenträgerkontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Datensicherungskonzept (CON.3) sowie Speicherlösungen (SYS.18). Für die Speicherinfrastruktur der Forschungsdatenbank werden ausschließlich die zentral bereitgestellten Services genutzt. Nicht-elektronische Datenträger sind für die Datenbank nicht vorgesehen. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.3 Speicherkontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Datensicherungskonzept (CON.3) sowie Speicherlösungen (SYS.18). Für die Speicherinfrastruktur der Forschungsdatenbank werden ausschließlich die zentral bereitgestellten Dienste genutzt. Zugriff auf die für die Forschungsdatenbank relevanten Speicher erfolgt nur für Berechtigte Forscherinnen und Forscher sowie Administratorinnen und Administratoren auf strenger „need-to-know“ Basis. Eine Pseudonymisierung der Daten erfolgt bereits in einem dieser Verarbeitungstätigkeit vorhergehenden Schritt. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.4 Benutzerkontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Identitäts- und Berechtigungsmanagement (ORP.4) sowie Protokollierung (OPS.1.1.5). Aus den bislang beschrieben Maßnahmen sind die in Abschnitt Zugangskontrollen beschriebenen für dieses Schutzziel ebenfalls relevant. Ferner werden folgende Maßnahmen ergriffen: Zur Benutzerkontrolle verfügt die Forschungsdatenbank über Protokolle für das Hinzufügen und Löschen von Nutzern. Zugriff erfolgt nur auf Antragsbasis. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen wie etwa das Sperren von Benutzeraccounts für Anwendungen mit Kenntnisnahme des Ausscheidens oder bei Kompromittieren des Accounts sowie die zentrale Passwortrichtlinie.

[_Hinweis: Bei Bedarf anpassen._]

### 3.5 Zugriffskontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Sensibilisierung und Schulung zur Informationssicherheit (ORP.4) sowie ordnungsgemäße IT-Administration (OPS.1.1.2). Die Zugriffskontrolle stellt sicher, dass die korrekten Rechte an die entsprechenden Rollen zugewiesen werden. Aus den bislang beschriebenen Maßnahmen sind die im Abschnitt Zugangskontrollen beschriebenen für dieses Schutzziel ebenfalls relevant. Ferner werden folgende Maßnahmen implementiert: Berechtigungen werden feingranular vergeben und der Zugriff auf personenbezogene Daten auf das notwendige Maß zu reduziert („need-to-know“); Es wurde ein definierter On- und Offboarding-Prozess für Zugänge zur Forschungsdatenbank eingerichtet. Auch findet eine Trennung der Rollen in Administrierende und Nutzende statt. Nutzende besitzen lediglich Benutzerrechte, Administrierende nutzen die administrativen Rechte nur für diesbezügliche Tätigkeiten. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.6 Übertragungskontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Protokollierung (OPS.1.1.5) sowie Kryptoschutz (CON.1). In der Übertragungskontrolle soll protokolliert werden, wer wann welche (bereits bestehenden) personenbezogenen Daten an andere Stellen übertragen hat. Es werden folgende Maßnahmen implementiert, um dies zu gewährleisten: Die Übertragung der personenbezogenen Daten erfolgt nur an definierten Verarbeitungssystemen. Die Übertragung zwischen diesen Systemen findet stets verschlüsselt statt. Die betrifft sowohl den automatischen Austausch zwischen Systemen („ETL-Prozess“), als auch Anfrage von Nutzenden. Es findet keine Weitergabe von Daten statt, die über die definierten Wege für Forschende zur Datenanalyse hinausgeht. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.7 Eingabekontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Protokollierung (OPS.1.1.5) sowie ordnungsgemäße IT-Administration (OPS.1.1.2). Eine Dateneingabe findet ausschließlich automatisch zwischen Systemen statt („ETL-Prozess“). Änderungen der Daten werden in entsprechenden Audit-Trails beschrieben und der Zugriff auf Änderungen der ETL-Prozesse unterliegt strengen Zugriffsregeln (siehe Abschnitt 3.1). Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.8 Transportkontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Kryptoschutz (CON.1) sowie Netzmanagement (NET.1.2). Zur Sicherstellung der Vertraulichkeit erfolgt eine Datenübertragung stets verschlüsselt. Es werden Serverzertifikate eingesetzt, um die Authentizität der zu erstellenden Server sicherzustellen. Ein physischer Transport von Datenträgern ist nicht vorgesehen. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen wie etwa die Erreichbarkeit der Server nur aus dem Netz der Organisation.

[_Hinweis: Bei Bedarf anpassen._]

### 3.9 Wiederherstellbarkeit

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Datensicherheitskonzept (CON.3) sowie Archivierung (OPS.1.2.2). Es wird der zentrale Backup-Dienst der virtuellen Serverumgebung genutzt. Darüber hinaus definiert ein systemspezifisches Betriebskonzept (siehe [5]) wie die Wiederherstellung aus den Sicherungen der zentrale Backup-Dienst erfolgen kann. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.10 Zuverlässigkeit

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Patch- und Änderungsmanagement (OPS.1.1.3) sowie Behandlung von Sicherheitsvorfällen (DER 2.1). Die Forschungsdatenbank ist so konfiguriert, dass Sicherheitspatches regelmäßig automatisch eingespielt werden, um zum Beispiel Systemausfälle durch die Behebung eines Sicherheitsvorfalls zu minimieren. Details regelt das Betriebskonzept [5]. Auch wird der zentrale Backup-Dienst der virtuellen Serverumgebung genutzt. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen, wie etwa die automatische Überwachung der Systeme mit geeigneten Tools sowie die Absicherung der Rechenzentren mit unterbrechungsfreien Stromversorgungen und Notstromaggregaten.

[_Hinweis: Bei Bedarf anpassen._]

### 3.11 Datenintegrität

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Virtualisierung (SYS.1.5) sowie Speicherlösungen (SYS.1.8). Aus den bislang beschriebenen Maßnahmen sind die in Abschnitt Zuverlässigkeit beschriebenen für dieses Schutzziel ebenfalls relevant. Weiterhin werden auf Datenbankebene ausschließlich transaktionssichere Systeme verwendet werden. Zusätzlich werden fehlertolerante Übertragungsprotokolle eingesetzt, sodass bei einer fehlgeschlagenen Übertragung Daten erneut versendet werden können. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen wie etwa die Minimierung von Fehlfunktionen auf Server-/Hardwareebene durch die Nutzung der virtuellen Infrastruktur oder die Nutzung einer sicheren zentralen Speicherung.

[_Hinweis: Bei Bedarf anpassen._]

### 3.12 Auftragskontrolle

Es werden keine externen Dienstleister eingesetzt.

[_Hinweis: Wenn externe Dienstleister eingesetzt werden, können hier apskete wie sichere Serverzugänge und Auftragsdatenverarbeitungsverträge genannt werden._]

### 3.13 Verfügbarkeitskontrolle

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Virtualisierung (OPS.1.5) sowie Notfallmanagement (DER.4). Die Verfügbarkeitskontrolle wird durch die oben genannten Maßnahmen bezüglich Wiederherstellbarkeit, Datenintegrität und Zuverlässigkeit sichergestellt. Die virtuelle Infrastruktur als hochverfügbares System einschließlich der dafür notwendigen Rechenzentren und Netzwerkinfrastruktur bilden die Basis dafür. Ein Berechtigungskonzept trägt ebenfalls zur Verfügbarkeitskontrolle bei, da durch dieses die unbeabsichtigte Löschung oder Zerstörung von personenbezogenen Daten verhindert wird. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen._]

### 3.14 Trennbarkeit

Es kommen unter anderem Maßnahmen der folgenden Bausteine zum Einsatz: Datenschutz (CON.2) sowie Entwicklung von Webanwendungen (CON.10). Aus den bislang beschriebenen Maßnahmen sind die im Abschnitt Zugangskontrolle beschriebenen ebenfalls für dieses Schutzziel relevant. Die Verarbeitung der Daten erfolgt zweckgebunden, da die Datenbank ausschließlich für Forschungszwecke genutzt wird. Ebenfalls findet eine Pseudonymisierung der Daten bereits im Vorfeld statt. Weiterhin gelten die zentralen technischen und organisatorischen Maßnahmen.

[_Hinweis: Bei Bedarf anpassen. Falls eine Mandandtentrennung umgesetzt ist, beispielsweise für verschiedene Fachbereiche, so kann dies hier eingebracht werden._]

## 4 Referenzen

[1] European Union Agency For Network and Information Security, Handbook on Security of Personal Data Processing. 2017.

[2] Bundesamt für Sicherheit und Informationstechnik, Informationssicherheit und IT-Grundschutz, Bonn: Reguvis Fachmedien, 2017.

[3] Deng, M., Wuyts, K., Scandariato, R., Preneel, B., & Joosen, W. (2011). A privacy threat analysis framework: supporting the elicitation and fulfillment of privacy requirements. Requirements Engineering, 16(1), 3-32.

[4] Verfahrensbeschreibung: OHDSI-Forschungsdatenbank.

[5] Betriebskonzept: OHDSI-Forschungsdatenbank.

[6] Berechtigungskonzept: OHDSI-Forschungsdatenbank.
