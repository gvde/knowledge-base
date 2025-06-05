---
title: Objekt Beziehungen
description: Objekt Beziehungen
icon: relations
status:
lang: de
---

# Objekt Beziehungen

[Objekte](struktur-it-dokumentation.md) stehen in i-doit in der Regel nicht für sich allein, sondern in Relation zueinander. Server stehen in Racks, Admins betreuen Server, auf einem Server läuft ein Betriebssystem mit Software. Die grundsätzlichen Konzepte der Objekt-Beziehungen erläutern wir in diesem Artikel.

## Objekt Beziehungsarten

Objekte können auf die unterschiedlichste Art in Beziehung stehen. Um hier Klarheit zu schaffen, erhält jede Beziehung eine Art. i-doit bringt in der Standardinstallation bereits viele vordefinierte Beziehungsarten mit. Eine Auflistung aller Arten gibt es unter **Verwaltung → Vordefinierte Inhalte → Objekt Beziehungsarten**.

[![Beziehungen](../assets/images/de/grundlagen/objekt-beziehungen/1-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/1-ob.png)

Unter der Auflistung der Beziehungsarten kann über den Button **Neuen Wert Hinzufügen** eine neue Art erstellt werden. Möchten Sie diese Beziehung in einer benutzerdefinierten Kategorie verwenden, müssen Sie diese als "Implizit" definieren.

[![Beziehung-hinzufügen](../assets/images/de/grundlagen/objekt-beziehungen/2-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/2-ob.png)

Bereits dokumentierte Objekt-Beziehungen werden unter **Extras → CMDB → Beziehungen** je nach Art aufgelistet. Klickt man im linken Navigationsbaum auf Alle, werden alle Objekt-Beziehungen unabhängig von der Art geladen. Das Laden der Liste kann bei einer größeren IT-Dokumentation etwas dauern.

[![vorhandene-beziehungsarten](../assets/images/de/grundlagen/objekt-beziehungen/3-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/3-ob.png)

## Beziehungs-Objekte

Wenn eine Beziehung zwischen zwei Objekten erstellt wird, wird im Hintergrund automatisch ein drittes Objekt vom [Typ](struktur-it-dokumentation.md) **Beziehungen** angelegt. Dieses erhält den Objekt-Titel des Master-Objekts, gefolgt von der Beschreibung und dem Objekt-Titel des Slave-Objekts.

Beispiel:

| Master-Objekt      | Beschreibung der Beziehung | Slave-Objekt |
| ------------------ | -------------------------- | ------------ |
| PDU-HQ-Intern-01-A | **liefert Strom an**       | ESX1         |

Das Beziehungs-Objekt ist nötig, um Eigenschaften der Beziehung als [Attribute](struktur-it-dokumentation.md) zu speichern. Dazu gehören unter anderem:

-   **Beziehungsart**: siehe oben
-   **Gewichtung**: siehe unten
-   **Service** (optional): Die Objekt-Beziehung kann direkt einem Service zugewiesen werden.

Wie bereits ersichtlich besteht eine Objekt-Beziehung aus einem Master- und einem Slave-Objekt. Es handelt sich also um eine gerichtete Beziehung. Das Slave-Objekt ist abhängig vom Master-Objekt.

[![beziehungsobjekt](../assets/images/de/grundlagen/objekt-beziehungen/4-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/4-ob.png)

Die Richtung der Beziehung - also welches ist Objekt Master, welches Slave - hat Auswirkungen auf den [CMDB-Explorer](../auswertungen/cmdb-explorer/index.md). In der Baumansicht werden Objekt-Beziehungen entweder nach oben oder unten rekursiv aufgebaut. Im [Standard-Profil](../auswertungen/cmdb-explorer/profile-im-cmdb-explorer.md) stehen Master-Objekte unter den Slave-Objekten.

!!! info "Beziehungs-Objekte sind nicht [lizenzpflichtig](../wartung-und-betrieb/lizenzierung.md)."

## Kategorie Beziehungen

Pro Objekt werden Beziehungen zu anderen Objekten in der [Kategorie](struktur-it-dokumentation.md) **Beziehungen** gesammelt. Diese ist jedem Objekttyp fest zugeordnet und über das Pfeile-Icon aufzurufen.

[![Kategorie-beziehungen](../assets/images/de/grundlagen/objekt-beziehungen/5-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/5-ob.png)

## Implizite vs. explizite Beziehungen

Beziehungen unterscheiden sich nicht nur nach ihrer Art (siehe oben), sondern auch, ob diese implizit oder explizit erstellt worden sind. Implizite Beziehungen stammen aus den Kategorien. Wird beispielsweise die Kategorie **Standort** bearbeitet und im Attribut **Standort** ein übergeordnetes Objekt ausgewählt, entsteht automatisch im Hintergrund eine implizite Beziehung der Art **Standort**. Diese implizite Beziehung wird zudem in der Kategorie **Beziehungen** und unter **Extras → CMDB → Beziehungen → Standort** angezeigt.

Soll unabhängig von den Kategorien und ihren Attributen eine Beziehung zwischen zwei Objekten gesetzt werden, wird eine explizite Beziehung erstellt. Diese explizite Beziehung wird in der Kategorie **Beziehungen** erstellt. Das Objekt, in dem man sich befindet, ist als **Objekt 1** vorausgewählt. Das Objekt, mit dem **Objekt 1** in Beziehung stehen soll, wird unter **Objekt 2** ausgewählt. Zudem muss zwischen beiden die Richtung gewählt werden. Als Beziehungsart ist standardmäßig **Abhängigkeit** vorausgewählt, weil diese Art unter **Verwaltung → Vordefinierte Inhalte → Objekt Beziehungen** bereits als explizit ausgewiesen ist. Es ist hier aber auch problemlos möglich eine neue explizite Beziehung zu definieren und direkt zu verwenden. Dies kann über das Zettel-Icon, wie bei Dialog+-Feldern, gemacht werden.

[![explizite-beziehungsart](../assets/images/de/grundlagen/objekt-beziehungen/6-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/6-ob.png)

Beim Anlegen einer neuen expliziten Beziehungsart können die Art und die Beschreibungen aus den jeweiligen Objektsichten definiert werden.

!!! success "Implizit oder explizit?"
    Was ist nun besser? Implizite oder explizite Beziehungen verwenden? Die Antwort lautet: implizite. Kategorien und Attribute sind zentrale Elemente zur Strukturierung der IT-Dokumentation. In Kategorien dokumentieren die Benutzer und dort suchen die Benutzer Informationen. Daher ist es besser, unspezifische Beziehungen der Art Abhängigkeit explizit in einer Kategorie zu dokumentieren, in der im- und explizite Beziehungen bunt miteinander gemischt sind. Auswertbar sind beide Möglichkeiten, aber gut nachzuvollziehen sind nur die impliziten.

## Gewichtung

Wie weiter oben bereits erwähnt, erhält jede Beziehung eine Gewichtung. Diese wird im Beziehungsobjekt als Attribut angegeben. Als Gewichtung sind Werte zwischen **1** und **10** möglich. Sie drücken aus, wie abhängig das Slave- vom Master-Objekt ist. **1** bedeutet **sehr wichtig**, **10** hingegen **unwichtig**, **5** ist die goldene Mitte mit **wichtig** und stellt den Standard dar.

Beispiel: Bekommt ein nicht redundant ausgelegtes Netzteil Strom von einer USV, dann könnte die Gewichtung bei **1 (sehr wichtig)** liegen, denn ohne funktionierende USV funktioniert das Netzteil nicht. Fällt stattdessen eine Node im Web Cluster aus, übernehmen andere Nodes ihren Job. Die Abhängigkeit zu übergeordneten Services ist also nicht ganz so hart, sondern könnte zwischen **5 (wichtig)** und **10 (nicht wichtig)** liegen.

Das Analyse-Modul verwendet diese Gewichtung in Kombination mit Services und [Network Monitoring](../automatisierung-und-integration/network-monitoring/index.md), um Aussagen treffen zu können, welche Services von Ausfällen betroffen sind.

## Gleichgerichtete Beziehungen

Neben den gerichteten Beziehungen mit Master- und Slave-Objekten, existieren in i-doit noch die gleichgerichteten Beziehungen. Diese stellen ebenfalls zwei Objekte in Beziehung zueinander, doch ohne eine Abhängigkeit voneinander auszudrücken.

Beispiel: Ist in i-doit ein Web Cluster mit mehreren Nodes dokumentiert, agieren die Nodes unabhängig voneinander. Lediglich das Funktionieren des Clusters hängt von allen Nodes ab. Die Kategorie **Clustermitglieder** (beziehungsweise die [rückwärtige Kategorie](struktur-it-dokumentation.md) **Clustermitgliedschaften**) erstellt im Hintergrund gleichgerichtete Objekt-Beziehungen zwischen den Cluster-Mitgliedern.

Eine Auflistung aller gleichgerichteter Beziehungen befindet sich unter **Extras → Vordefinierte Inhalte → Objekt Beziehungen → Gleichgerichtete Beziehungen**. Sie können nicht vom Benutzer erstellt werden, sondern werden implizit, automatisch im Hintergrund erstellt.

[![gleichberechtigte-beziehungen](../assets/images/de/grundlagen/objekt-beziehungen/7-ob.png)](../assets/images/de/grundlagen/objekt-beziehungen/7-ob.png)

## Objekt-Beziehung in benutzerdefinierter Kategorie

In [benutzerdefinierten Kategorien](benutzerdefinierte-kategorien.md) können Objekt-Beziehungen dokumentiert werden. Hierbei ist zwischen zwei Feldtypen zu unterscheiden:

-   **Objekt-Browser**: Es wird kein Beziehungs-Objekt erzeugt. Die hier zu dokumentierende Beziehung zwischen zwischen zwei Objekten wird in der Kategorie Beziehungen nicht aufgelistet und der [CMDB-Explorer](../auswertungen/cmdb-explorer/index.md) wertet diese Beziehung nicht aus.
-   **Objekt-Beziehung**: Als **Zusatz** kann hier nur eine implizite Beziehungsart angegeben werden. Explizite Beziehungen werden hier nicht angezeigt.

!!! success "Objekt-Browser oder -Beziehung?"
    Wie bei den impliziten und expliziten Beziehungen stellt sich hier ebenfalls die Frage: Welcher Feldtyp ist besser? Auch hier fällt die Antwort wieder eindeutig aus: Die **Objekt-Beziehung** hat einen zusätzlichen Nutzen und ist daher dem Feldtyp **Objekt-Browser** zu bevorzugen.

## FAQs

### Richtung der Beziehung

In `v35` wird die Richtung der Beziehung durch die Objekttyp Konfiguration bestimmt. Dort wird Konfiguriert ob ein Objekt der [Beziehungsmaster](./benutzerdefinierte-objekttypen.md#felder-in-der-konfiguration) ist oder nicht. Diese Einstellung wird die Einstellung [Standard Richtung](#objekt-beziehungsarten) überschreiben.
