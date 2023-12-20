# Berechtigungskonzept OHDSI-Forschungsdatenbank

Verantwortlich(e):  
Autor(en):  
Version:  
Datum:  

# Inhaltsverzeichnis

ToDo

# Zielsetzung

Dieses Konzept regelt die Rollen und Berechtigungen bei der Nutzung der
OHDSI-Forschungsdatenbank. Hier werden Zugriffsregeln für einzelne
Beschäftigte zum Zugriff auf Datensätze des genutzten IT-Systems
festgelegt. Außerdem werden die Prozesse, die die Umsetzung des
Berechtigungskonzepts betreffen beschrieben, wie z.B. das Löschen und
Erstellen von Nutzern, oder Passwortrestriktionen. Sind Rollen und
Berechtigungen nicht oder nur unzureichend definiert, kann es dazu
führen, dass Beschäftigte Zugriff auf Systeme und Daten erhalten, zu
denen sie keine Berechtigung benötigen. Dies kann zu einer Verletzung
der Vertraulichkeit und Integrität der Daten führen.

# Übersicht der Rollen und Rechte pro System

\[Hier sind die Zugriffsberechtigungen der jeweiligen
Rollen pro System detailliert zu definieren. Wichtig ist zu beachten,
dass alle nachfolgenden Prozesse (z.B. in Bezug auf die
Berechtigungsvergabe und Passwortmanagement) auf den hier definierten
Rollen und Berechtigungen aufbauen. Die Prozesse müssen zwar je nach
Bedarf angepasst werden, jedoch auch stets im Einklang mit den hier
definierten Rollen und Rechten stehen. Die nachfolgende Tabelle ist als Beispiel zu vestehen\]

*A = Administrative Rechte, S = Schreibberechtigung, L =
Leseberechtigung*

| Nr.     | System | Zugriffsberechtigung und Zweck                                          | \[Administrierende\] | \[Forschende\] |
|---------|--------|-------------------------------------------------------------------------|----------------------|----------------|
| 1       | OHDSI  |   Zugriff auf OHDSI-Daten; Zweck: Datenanalyse                          | (A/S/L)              | A/S/L          |
| 2       | OHDSI  | Zugriff auf OHDSI-Accountverwaltung                                     | A/S/L                | -              |
| 3       | OHDSI  | Zugriff auf Betriebssystem                                              | A/S/L                | -              |
| 4       |\[...\] | \[Zugriff auf … \]                                                      | \[…\]                | \[…\]          |

# Prozess zur Berechtigungsbeantragung

\[Bitte beschreiben Sie den Prozess der
Berechtigungsbeantragung, wie er in [\[1\]] detailiert beschrieben ist, in
zusammengefasster Form. Nachfolgend befindet sich ein Beispielprozess,
der nach Bedarf angepasst werden kann.\]

Zur Nutzerfreigabe ist pro Datensatz ein Prozess vorgesehen, der in [\[1\]] 
 genauer beschrieben ist. Zusammenfassend:

1.  Forschende Personen stellen einen Antrag auf Nutzung der Forschungsdatenbank bei der  fachlich verantwortlichen Person (siehe [\[2\]).

1.  Die fachlich verantwortliche Person gibt diesen Antrag frei, nachdem Ethikvotum
    und Abstimmung mit den Datenschutzfunktionen erfolgt sind.

1.  Die forschende Person leitet den freigegebenen Antrag an die Administration weiter.

1.  Die Administration gewährt der forschenden Person Zugriff auf die Forschungsdatenbank.

Dabei findet eine Mandantentrennung statt. Dies bedeutet, dass
Forschende eines Bereiches ausschließlich Zugang zu Daten dieses
Bereichs erhalten. Eine Nutzerfreigabe kann immer nur bis zu einem
im Antrag definierten Ablaufdatum geschehen. Der Nutzungszeitraum pro
Studie ist auf maximal 6 Monate beschränkt. Weiterhin findet eine
regelmäßige Überprüfung der zugelassenen Personen durch die Administration statt.

# Löschen, Einschränkung oder Entzug von Berechtigungen

\[Bitte beschreiben Sie den Prozess, der nach dem
Abschluss einer Studie oder bei Änderungen im Studienpersonal in Bezug
auf die Zugriffsberechtigungen erfolgt. Nachfolgend befindet sich ein
Beispielprozess.\]

Bei Abschluss einer Studie erfolgt eine Information durch die
Studienleitung an den/die Administrierende. Dieser/diese
entzieht den Forschenden die entsprechende Berechtigung.

#  Passwortprozess- und Richtlinien

\[Bitte beschreiben Sie den Prozess der
Kennwortvergabe und -änderung für forschende Personen. Nachfolgend
befindet sich ein Beispielprozess.\]

Die Administrierenden vergeben ein Initialkennwort für eine
forschende Person. Dieses Kennwort muss bei der ersten Nutzung durch die
forschende Person geändert werden. Bei der Änderung werden Nutzer auf
die Passwortrichtlinien der Organisation hingewiesen \[3\]. \[Alternativ kann eine Integration von OHDSI in die organisationsweite  AAI in Betracht gezogen werden. Siehe die entsprechende Dokumentation \[4\]\].

# Kontrolle von Berechtigungen

\[Bitte beschreiben Sie den Prozess für die
regelmäßige Kontrolle der Berechtigungen der forschenden Personen.
Nachfolgend befindet sich ein Beispielprozess.\]

Es findet zweimal pro Jahr eine Prüfung der Accounts der Forschenden
durch die Administrierenden statt.

# Namentliche Liste von Administrierenden

- Anlage 1 – Liste von Administrierenden

  - \[Name und Kontaktdetails\]

  - \[…\]

# Referenzen
\[1\] Standardprozess für Einrichtung von Zugängen zur OHDSI-Forschungsdatenbank  
\[2\] Betriebskonzept  
\[3\] \[ Verweis auf Passwortrichtlinien der Organisation\]  
\[4\] Sicherheitskonfiguration von OHDSI WebAPI. https://github.com/OHDSI/webapi-wiki/blob/master/Security-Configuration.md
