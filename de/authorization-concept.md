# Berechtigungskonzept: OHDSI-Forschungsdatenbank

- **Verantwortlicher:** [Name]
- **Autor:** [Name]
- **Datum:** [TT.MM.YYYY]
- **Version:** [1.0]

## Inhalt

Inhalt

1. Zielsetzung
2. Übersicht der Rollen und Rechte
3. Prozess zur Berechtigungsbeantragung
4. Löschen, Einschränkung oder Entzug von Berechtigungen
5. Passwortprozess- und Richtlinien
6. Kontrolle von Berechtigungen
7. Referenzen
8. Anlage: Liste von technisch und fachlich Administrierenden
9. Anlage: Antrag auf Gewährung eines Zugangs zur OHDSI-Forschungsdatenbank

## 1 Zielsetzung

Dieses Konzept regelt die Rollen und Berechtigungen bei der Nutzung der OHDSI-Forschungsdatenbank. Hier werden Zugriffsregeln für einzelne Personengruppen und Nutzer zum Zugriff auf Datensätze festgelegt. Außerdem werden die Prozesse, die die Umsetzung des Berechtigungskonzepts betreffen beschrieben, wie z.B. das Löschen und Erstellen von Nutzern, oder Passwortrestriktionen. Dies umfasst (1) eine Übersicht über Rollen und Rechte, (2) eine Beschreibung der Prozesse für die Beantragung eines Zugangs durch Forschende, sowie (3) weitere Regelungen und Prozesse zur Umsetzung.

Es werden unterschiedliche Datenarten zur Verfügung gestellt, für die unterschiedliche Einrichtungen fachlich verantwortlich sind:
- *Einrichtung 1*: Datenart 1, 2 und 3.
- *Einrichtung 2*: Datenart 3, 4 und 5.

[_Hinweis: Die OHDSI-Forschungsdatenbank kann in einem Multi-Tenancy-Modus betrieben werden, wo unterschiedliche Datensätze unterschiedlichen Gruppen zugängig gemacht werden können. Falls dies nicht der Fall ist, kann die Auflistung von verantwortlichen Einrichtungen entfallen, und eine einzelne Gruppe fachlich administrierender Personen genannt werden._]

## 2 Übersicht der Rollen und Rechte

Die folgende Tabelle enthält eine Übersicht über unterschiedliche Rechte für die in der Verfahrensbeschreibung beschriebenen Komponenten und Personengruppen.

*A = Administrative Rechte, S = Schreibberechtigung, L = Leseberechtigung*

| Komponenten         | Technisch Administrierende | Fachlich Administrierende | Forschende |
|---------------------|----------------------------|---------------------------|------------|
| Virtuelle Maschine  | A                          |                           |            |
| Betriebssystem      | A                          |                           |            |
| ETL-Tool            | A                          |                           |            |
| PostgreSQL-Datenbank| A                          |                           |            |
| Apache SOLR         | A                          |                           |            |
| OpenLDAP            | A                          | A                         |            |
| WebAPI              | A                          | A                         | S/L        |
| ATLAS               | A                          | A                         | S/L        |
| ARES                | A                          | A                         | S/L        |
| RStudio             | A                          | A                         | S/L        |

[_Hinweis: Die Tabelle muss entsprechend den Angaben in der Verfahrensbeschreibung angepasst werden._]

## 3 Prozess zur Berechtigungsbeantragung

Um eine Studie mit der Datenbank durchführen zu können ist zunächst die Zustimmung der entsprechenden fachlich verantwortlichen Abteilung einzuholen. Im Anschluss daran sind die üblichen Voraussetzungen für die Durchführung einer retrospektiven Studie zu schaffen.

Zur Gewährung eines Zugangs zur Gesundheitsdatenbank ist folgender Prozess definiert:

1.  Die forschende Person stellt mittels des entsprechenden Formulars (siehe Anlage) einen Antrag auf Nutzung der Forschungsdatenbank bei der Leitung der fachlich verantwortlichen Einrichtung (siehe [1]).
2.  Die Leitung der fachlich verantwortlichen Einrichtung gibt diesen Antrag frei.
3.  Die forschende Person leitet den freigegebenen Antrag an die entsprechenden fachlich Administrierenden weiter.
4.  Die Administration gewährt der forschenden Person Zugriff auf die Forschungsdatenbank.

[_Hinweis: Die OHDSI-Forschungsdatenbank kann in einem Multi-Tenancy-Modus betrieben werden, wo unterschiedliche Datensätze unterschiedlichen Gruppen zugängig gemacht werden können. Falls dies nicht der Fall ist, kann die Auflistung von verantwortlichen Einrichtungen entfallen, und eine einzelne Gruppe fachlich administrierender Personen genannt werden._]

Eine Freigabe kann immer nur bis zu einem im Antrag definierten Ablaufdatum erteilt werden. Dieses ist auf maximal 6 Monate beschränkt, kann aber verlängert werden.

## 4 Löschen, Einschränkung oder Entzug von Berechtigungen

Bei Abschluss einer Studie erfolgt eine Information durch die Studienleitung an den/die Administrierende. Dieser/diese entzieht den Forschenden die entsprechende Berechtigung.

## 5 Passwortprozess- und Richtlinien

Die Administrierenden vergeben ein Initialkennwort für eine forschende Person. Dieses Kennwort muss bei der ersten Nutzung durch die forschende Person geändert werden. Bei der Änderung werden Nutzer auf die Passwortrichtlinien der Organisation hingewiesen.

[_Hinweis: Alternativ kann eine Integration von OHDSI in die organisationsweite AAI in Betracht gezogen werden. Siehe die entsprechende Dokumentation [2]_.]

## 6 Kontrolle von Berechtigungen

Zusätzlich zur aktiven Deaktivierung abgelaufener Konten, kontrollieren die fachlich sowie technisch Administrierenden die aktiven Zugänge zur OHDSI-Forschungsdatenbank zweimal im Jahr und deaktivieren nicht mehr benötige bzw. abgelaufene Zugänge entsprechend.

## 7 Referenzen

[1] Betriebskonzept OHDSI-Forschungsdatenbank

[2] Sicherheitskonfiguration von OHDSI WebAPI. https://github.com/OHDSI/webapi-wiki/blob/master/Security-Configuration.md

## 8 Anlage: Liste von technisch und fachlich Administrierenden

Die folgende Liste enthält die Kontaktdaten aller technischen und fachlichen Administrierenden:

- *Name und Kontaktdetails 1:* Rollen
- *Name und Kontaktdetails 2:* Rollen
- *Name und Kontaktdetails 3:* Rollen

## 9 Anlage: Antrag auf Gewährung eines Zugangs zur OHDSI-Forschungsdatenbank

### Persönliche Daten
- *Vorname:* 
- *Nachname:*
- *Abteilung:*
- *Account:*
- *E-Mail-Adresse:*

## Datensatz und Unterschrift 

Hiermit beantrage ich einen Zugriff auf folgenden Datensatz der Forschungsdatenbank OHDSI:

Die damit verbundenen Regeln und Vorschriften im Bereich der Forschung und des Datenschutzes sind mir bekannt.  

Datum, Unterschrift

## Freigabe durch die fachlich verantwortlichen Einrichtung

Als Leiter der verantwortliche Einrichtung genehmige ich hiermit den Zugriff auf den genannten Datensatz durch die genannte Person.

Datum, Unterschrift