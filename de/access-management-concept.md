<H1> Berechtigungskonzept OHDSI-Forschungsdatenbank </H1>

Verantwortlich(e):  
Autor(en):  
Version:  
Datum:  

# Inhalt

ToDO

# Anlagenverzeichnis

| Anlagenverzeichnis |                                                                            |
|--------------------|----------------------------------------------------------------------------|
| A1                 | Standardprozess für Einrichtung von Zugängen zur OHDSI-Forschungsdatenbank |

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

<span class="mark">\[Hier sind die Zugriffsberechtigungen der jeweiligen
Rollen pro System detailliert zu definieren. Wichtig ist zu beachten,
dass alle nachfolgenden Prozesse (z.B. in Bezug auf die
Berechtigungsvergabe und Passwortmanagement) auf den hier definierten
Rollen und Berechtigungen aufbauen. Die Prozesse müssen zwar je nach
Bedarf angepasst werden, jedoch auch stets im Einklang mit den hier
definierten Rollen und Rechten stehen.\]</span>

*A = Administrative Rechte, S = Schreibberechtigung, L =
Leseberechtigung*

| **Nr.** | **Zugriffsberechtigung und Zweck**                                         | <span class="mark">\[Technisch Administrierende\]</span> | <span class="mark">\[Fachlich Administrierende\]</span> | <span class="mark">\[Forschende\]</span> |
|---------|----------------------------------------------------------------------------|----------------------------------------------------------|---------------------------------------------------------|------------------------------------------|
| 1       | <span class="mark">\[Zugriff auf OHDSI-Daten; Zweck: Datenanalyse\]</span> | <span class="mark">\[…\]</span>                          | <span class="mark">\[…\]</span>                         | <span class="mark">\[…\]</span>          |
| 2       | <span class="mark">\[Zugriff auf … \]</span>                               | <span class="mark">\[…\]</span>                          | <span class="mark">\[…\]</span>                         | <span class="mark">\[…\]</span>          |
| 3       | <span class="mark">\[Zugriff auf … \]</span>                               | <span class="mark">\[…\]</span>                          | <span class="mark">\[…\]</span>                         | <span class="mark">\[…\]</span>          |

# Prozess zur Berechtigungsbeantragung

<span class="mark">\[Bitte beschreiben Sie den Prozess der
Berechtigungsbeantragung, wie er in Anlage A1 detailliert ist, in
zusammengefasster Form. Nachfolgend befindet sich ein Beispielprozess,
der nach Bedarf angepasst werden kann.\]</span>

Zur Nutzerfreigabe ist pro Datensatz ein Prozess vorgesehen, der in
Anlage A1 genauer beschrieben ist. Zusammenfassend:

1.  <span class="mark">\[Eine berechtigte Person (z.B. die Leitung der
    Fachabteilung)\]</span> benennt eine oder mehrere Personen für die
    fachliche Administration.

2.  Die technische Administration gewährt den benannten Personen die
    Berechtigungen für die fachliche Administration.

3.  Forschende Personen stellen einen Antrag auf Nutzung der
    Forschungsdatenbank bei der Leitung der Fachabteilung.

4.  <span class="mark">\[Eine berechtigte Person (z.B. die Leitung der
    Fachabteilung)\]</span> gibt diesen Antrag frei, nachdem Ethikvotum
    und Abstimmung mit den Datenschutzfunktionen erfolgt sind.

5.  Die forschende Person leitet den freigegebenen Antrag an die
    fachliche Administration weiter.

6.  Die fachliche Administration gewährt der forschenden Person Zugriff
    auf die Forschungsdatenbank.

Dabei findet eine Mandantentrennung statt. Dies bedeutet, dass
Forschende einer Fachabteilung ausschließlich Zugang zu Daten dieser
Fachabteilung erhalten. Eine Nutzerfreigabe kann immer nur bis zu einem
im Antrag definierten Ablaufdatum geschehen. Der Nutzungszeitraum pro
Studie ist auf maximal 6 Monate beschränkt. Weiterhin findet eine
regelmäßige Überprüfung der zugelassenen Personen durch die fachliche
Administration statt.

# Löschen, Einschränkung oder Entzug von Berechtigungen

<span class="mark">\[Bitte beschreiben Sie den Prozess, der nach dem
Abschluss einer Studie oder bei Änderungen im Studienpersonal in Bezug
auf die Zugriffsberechtigungen erfolgt. Nachfolgend befindet sich ein
Beispielprozess.\]</span>

Bei Abschluss einer Studie erfolgt eine Information durch die
Studienleitung an den/die fachlich Administrierende. Dieser/diese
entzieht den Forschenden die entsprechende Berechtigung. Bei Austritt
oder Wechsel eines/einer fachlich Administrierenden informiert die
<span class="mark">\[Eine berechtigte Person (z.B. die Leitung der
Fachabteilung)\]</span> die technisch Administrierenden, welche den
Austritt bzw. Wechsel prüfen und die Berechtigungen einschränken oder
anpassen.

#  Passwortprozess- und Richtlinien

<span class="mark">\[Bitte beschreiben Sie den Prozess der
Kennwortvergabe und -änderung für forschende Personen. Nachfolgend
befindet sich ein Beispielprozess.\]</span>

Die fachlich Administrierenden vergeben ein Initialkennwort für eine
forschende Person. Dieses Kennwort muss bei der ersten Nutzung durch die
forschende Person geändert werden. Bei der Änderung werden Nutzer auf
die Passwortrichtlinien der Organisation hingewiesen.

# Kontrolle von Berechtigungen

<span class="mark">\[Bitte beschreiben Sie den Prozess für die
regelmäßige Kontrolle der Berechtigungen der forschenden Personen.
Nachfolgend befindet sich ein Beispielprozess.\]</span>

Es findet zweimal pro Jahr eine Prüfung der Accounts der Forschenden
durch die fachlichen Administrierenden und einmal pro Jahr eine Prüfung
der Accounts der fachlich Administrierenden durch die technisch
Administrierenden statt.

# Namentliche Liste von technisch Administrierenden

- Anlage 1 – Liste von technisch Administrierenden

  - <span class="mark">\[Name und Kontaktdetails\]</span>

  - <span class="mark">\[…\]</span>
