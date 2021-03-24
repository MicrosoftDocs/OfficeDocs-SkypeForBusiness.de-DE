---
title: Teams for Education Policy Wizard zum einfachen Anwenden von Richtlinien für sicheres Lernen
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: shajohri, angch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe des Richtlinien-Assistenten für Teams für Bildungseinrichtungen Richtlinien für Kursteilnehmer und Lehrkräfte auf einfache Weise anwenden können, um Ihre Lernumgebung sicher zu halten.
f1keywords: ''
ms.openlocfilehash: 7eca1fca8a4c054d2787b205c5e57ced274416da
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111091"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Verwenden des Assistenten für Bildungsrichtlinien von Teams zum einfachen Anwenden von Richtlinien für eine sichere Lernumgebung

## <a name="overview"></a>Übersicht

Der Microsoft Teams for Education Policy Wizard vereinfacht die Verwaltung von Richtlinien für Ihre Kursteilnehmer und Lehrkräfte. Verwenden Sie sie, um die wichtigsten Richtlinien, die für die Erstellung einer sicheren und produktiven Lernerfahrung relevant sind, einfach und schnell anzuwenden.

Mit Richtlinien in Teams können Sie steuern, wie sich Teams in Ihrer Umgebung verhält und welche Features den Benutzern zur Verfügung stehen. So gibt es beispielsweise Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen, und jeder Richtlinienbereich kann an die Anforderungen Ihrer Organisation angepasst werden.

Um eine sichere und fokussierte Lernumgebung zu erhalten, ist es wichtig, Richtlinien zu festlegen, um zu steuern, was Kursteilnehmer in Teams tun können. Mithilfe von Richtlinien können Sie beispielsweise steuern, wer private Chats und private Anrufe verwenden kann, wer Besprechungen planen und welche Inhaltstypen freigegeben werden können. Sie können auch Richtlinien verwenden, um Teams-Features zu aktivieren, die die Lernerfahrung bereichern.

Richtlinien müssen sowohl für Schüler als auch für Lehrkräfte angepasst werden, damit die Lernerfahrung sicher bleibt. Richtlinien für Kursteilnehmer müssen restriktiver sein, um das Risiko zu verringern, unangemessene Zugriffsebenen zu erhalten. Lehrkräfte und Mitarbeiter benötigen einen separaten Satz von Richtlinien, die ihnen einen erfolgversprechenden Erfolg ermöglichen können. Ermöglichen Sie beispielsweise Lehrkräften, Besprechungen zu planen und die Schüler/Studenten davon zu unterschränken.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot des Assistenten":::

In diesem Artikel erfahren Sie, wie Sie den Assistenten ausführen.

> [!IMPORTANT]
> Die vom Assistenten angewendeten Richtlinien entsprechen den Anforderungen der meisten Teams for Education-Kunden. Der Assistent passt die globale (organisationsweite Standardeinstellung) Definition eines Kernsatzs von Richtlinien mit Einstellungen an, die wir für die Sicherheit von Kursteilnehmern empfehlen, und wendet sie auf Kursteilnehmer an. Der Assistent erstellt und weist außerdem eine Reihe benutzerdefinierter Richtlinien für Lehrkräfte und Mitarbeiter zu. Die meisten Teams for Education-Kunden müssen nach dem Ausführen dieses Assistenten keine anderen Methoden zur Richtlinienzuweisung verwenden. Verwenden Sie andere Methoden zur *Richtlinienzuweisung* nur, wenn Sie Richtlinien für Schüler/ Studenten, Lehrkräfte und Mitarbeiter manuell erstellen und verwalten möchten.

## <a name="teams-for-education-policy-wizard"></a>Teams for Education Policy Wizard

<a name="polwiz_intro"> </a>

Der Assistent wendet eine Reihe von grundlegenden Richtliniendefinitionen auf Kursteilnehmer und eine separate Gruppe von grundlegenden Richtliniendefinitionen auf Lehrkräfte und Mitarbeiter mit Einstellungen an, die für die einzelnen Richtlinien geeignet sind. Dies geschieht, wenn Sie den Assistenten ausführen.

Der Assistent richtet Richtlinien basierend auf dem Bildungseinrichtungstyp **(Primär- oder Sekundär-** oder Höhere Bildungseinrichtung) **ein.** Sie wählen Ihren Einrichtungstyp aus, und der Assistent führt die folgenden Schritte aus:

- **Kursteilnehmer:** Der Assistent passt die globale Richtliniendefinition (organisationsweite Standardrichtlinie) für jeden vom Assistenten abgedeckten Richtlinienbereich mit neuen Standardeinstellungen an, die geeignet sind, ihre Kursteilnehmer zu schützen. Dadurch wird sichergestellt, dass Ihre aktuellen Kursteilnehmer und alle neuen Kursteilnehmer die restriktivsten Richtlinien erhalten.
- **Lehrkräfte und Mitarbeiter:** Der Assistent erstellt eine Reihe benutzerdefinierter Richtliniendefinitionen für jeden Richtlinienbereich, der vom Assistenten abgedeckt wird, mit Einstellungen, die auf die Anforderungen von Lehrkräften und Mitarbeitern zugeschnitten sind. Anschließend werden die Richtliniendefinitionen der gruppe von Lehrkräften und Mitarbeitern zugewiesen, die Sie auswählen. Auf diese Weise erhalten Ihre Lehrkräfte und Mitarbeiter eine reihe von Richtlinien, die ihnen einen erfolgversprechenden Erfolg ermöglichen.

Sie müssen den Assistenten nur einmal ausführen. Neue Kursteilnehmer erhalten automatisch die globalen Richtliniendefinitionen (organisationsweite Standardrichtliniendefinitionen), die vom Assistenten angewendet werden, und neuen Mitarbeitern, die Sie der ausgewählten Gruppe hinzufügen, werden automatisch die benutzerdefinierten Richtlinien zugewiesen.

> [!NOTE]
> Eine [detaillierte Liste der](#policies-applied-by-the-wizard) richtliniendefinitionen, die vom Assistenten angewendet wurden, finden Sie unter Vom Assistenten angewendete Richtlinien.

Jetzt geht's los!

## <a name="run-the-wizard"></a>Ausführen des Assistenten

<a name="polwiz_run"> </a>

Führen Sie die folgenden Schritte aus, um den Assistenten ausführen zu können.

1. Wenn Sie noch nicht mit Teams arbeiten, wird der Assistent automatisch gestartet. Andernfalls können Sie den Assistenten jederzeit über das Dashboard starten. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams  Admin Centers zu **Dashboard,** und wählen Sie dann in der Kachel Einfache Richtlinieneinrichtung für eine sichere Lernumgebung die Option **Schnelleinrichtung aus.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Assistenten im Dashboard":::

2. Wählen Sie Ihren Bildungseinrichtungstyp **(Primär- oder** Sekundar- oder **Höhere** Bildungseinrichtung) und dann Weiter **aus.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen des Einrichtungstyps":::

3. Suchen Sie nach einer Gruppe, die Ihre Lehrkräfte und Mitarbeiter enthält, und wählen Sie dann **Weiter aus.** Wenn Sie noch keine Gruppen für Ihre Lehrkräfte und Mitarbeiter eingerichtet [haben,](/microsoft-365/admin/create-groups/create-groups)erstellen Sie eine Gruppe, und führen Sie dann den Assistenten erneut aus. <br/><br/>Derzeit können Sie nur eine Gruppe auswählen. Lehrkräften und Mitarbeitern in der ausgewählten Gruppe wird eine Reihe von benutzerdefinierten Richtlinien zugewiesen, [die](#policies-applied-by-the-wizard) auf ihre Anforderungen zugeschnitten sind. Denken Sie daran, dass dieser Satz von Richtlinien von den Richtlinien getrennt ist, die für Kursteilnehmer angewendet werden.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen von Lehrkräften und Mitarbeitergruppen":::

4. Überprüfen Sie Ihre Auswahl.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Screenshot der Seite im Assistenten zum Überprüfen der Auswahl":::

5. Wählen **Sie Übernehmen** aus, um Ihre Änderungen anzuwenden. Dies kann einige Minuten dauern.<br/><br/>Die Richtliniendefinitionen global (organisationsweit) werden sofort auf Kursteilnehmer angewendet. Für Ihre Lehrkräfte und Mitarbeiter kann es einige Stunden dauern, bis die benutzerdefinierten Richtlinien je nach Größe der Gruppe jedem Mitglied der ausgewählten Gruppe zugewiesen wurden. Dies geschieht im Hintergrund, nachdem Sie diesen Schritt erfolgreich abgeschlossen haben.
6. Sie sind auf dem Weg, aber noch nicht fertig! Es gibt ein paar weitere Dinge, die Sie berücksichtigen sollten. Als Nächstes sehen Sie sich die Schritte im Abschnitt [Was zu tun](#what-to-do-after-running-the-wizard) ist nach dem Ausführen des Assistenten in diesem Artikel an.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot der Seite im Assistenten für die nächsten Schritte":::

## <a name="what-to-do-after-running-the-wizard"></a>Was nach dem Ausführen des Assistenten zu tun ist

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Schritt 1: Entfernen vorhandener Richtlinienzuordnungen, die mit Richtlinien im Konflikt stehen, die vom Assistenten angewendet wurden

> [!IMPORTANT]
> **Führen Sie diesen Schritt nur aus,  wenn** Ihnen vor dem Ausführen des Assistenten Richtlinien für Kursteilnehmer oder Lehrkräfte und Mitarbeiter zugewiesen sind. Wenn Sie noch nicht mit Teams arbeiten und über keine anderen Richtlinien als die richtlinien verfügen, die vom Assistenten erstellt wurden, überspringen Sie diesen Schritt, und fahren Sie mit Schritt 2 fort.

In Teams kann für einen bestimmten Richtlinienbereich eine Richtlinie auf einen Benutzer auf die folgende Weise angewendet werden:

- Direkte Zuweisung an den Benutzer
- Zuordnung zu einer Gruppe, deren Mitglied der Benutzer ist
- Wenn dem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen wurde, erhält der Benutzer automatisch die Richtlinie "Global( Organisationsweite Standardrichtlinie)

Wenn mehrere dieser Richtlinienzuordnungen für einen Benutzer vorhanden sind, verwendet Teams die folgende Reihenfolge, um zu bestimmen, welche Richtlinienzuordnung wirksam wird. Weitere Informationen finden Sie unter [Welche Richtlinie hat Vorrang?](assign-policies.md#which-policy-takes-precedence) und [Rangfolgeregeln.](assign-policies.md#precedence-rules)

|Richtlinienzuweisungen eines Benutzers|Richtlinie, die wirksam wird |
|---------|---------|
|Der Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Nein    |Globale Standardrichtlinie (organisationsweit)      |
|Der Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Ja    |Richtlinie, die dem Benutzer direkt zugewiesen wurde         |
|Der Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Ja     |Richtlinie, die dem Benutzer direkt zugewiesen wurde         |
|Der Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Nein     |Der Gruppe zugewiesene Richtlinie<br/><br/>Wenn der Benutzer Mitglied mehrerer Gruppen ist und jeder Gruppe eine Richtlinie desselben Richtlinienbereichs zugewiesen ist, tritt die Richtlinie mit der höchsten Gruppenzuordnungsrangfolge in Kraft. [](assign-policies.md#group-assignment-ranking)       |

Aufgrund dieser Reihenfolge werden die vom Assistenten erstellten Richtlinien nicht wirksam, wenn ein Benutzer über vorhandene direkte Zuordnungen oder Gruppenzuordnungen verfügt. Dies bedeutet, dass Sie die vorhandenen Richtlinienzuordnungen vom Benutzer entfernen müssen, damit die vom Assistenten angewendete Richtlinie wirksam wird.

Gehen Sie [für jeden vom Assistenten angewendeten](#policies-applied-by-the-wizard)Richtlinienbereich wie folgt vor:

- Entfernen Sie alle vorhandenen direkten Aufgaben und Gruppenzuordnungen von Ihren Kursteilnehmern, damit die vom Assistenten angewendete globale (organisationsweite Standard)-Richtliniendefinition wirksam wird.
- Entfernen Sie alle widersprüchlichen direkten Aufgaben für Ihre Lehrkräfte und Mitarbeiter, damit die vom Assistenten erstellte benutzerdefinierte Richtliniendefinition wirksam wird. Verwenden Sie die obige Tabelle, um die Szenarien zu ermitteln, die für Sie gelten. <br/><br/>Denken Sie daran, dass der Assistent Ihren Lehrkräften [](assign-policies.md#group-assignment-ranking) und der Mitarbeitergruppe Richtlinien mit der Gruppenzuordnungsrangfolge 1 zu weist, was die höchste Bewertung ist. Wenn Ihren Lehrkräften und Ihrer Mitarbeitergruppe eine Richtlinie desselben Richtlinienbereichs zugewiesen ist, wird diese vorhandene Richtlinie in eine niedrigere Rangfolge verschoben, und die vom Assistenten zugewiesene Richtlinie wird wirksam.

[Erfahren Sie mehr](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) darüber, wie Sie Richtlinien entfernen, die Benutzern direkt zugewiesen sind.

Sie haben beispielsweise Lehrkräften eine Besprechungsrichtlinie direkt zugewiesen, und Ihre Kursteilnehmer verfügen über die globale (organisationsweite Standard)-Besprechungsrichtlinie. Entfernen Sie in diesem Szenario die Besprechungsrichtlinie, die Sie Lehrkräften direkt zugewiesen haben, damit die benutzerdefinierte Richtliniendefinition für die vom Assistenten erstellte Besprechungsrichtlinie wirksam wird. Sie müssen nichts mit der vorhandenen globalen (organisationsweiten Standard)-Besprechungsrichtlinie für Kursteilnehmer unternehmen, da keine anderen Besprechungsrichtlinien mit ihr in Konflikt stehen.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Schritt 2: Überprüfen Auf zusätzliche Maßnahmen, die Sie zur Sicherheit von Kursteilnehmern ergreifen können

Der Assistent passt diese Richtlinien automatisch [an und wendet diese an.](#policies-applied-by-the-wizard) Es gibt nur wenige zusätzliche Maßnahmen, die Sie möglicherweise basierend auf den Anforderungen Ihrer Einrichtung ergreifen möchten, um sicher zu bleiben.

Weitere [Sicherheitsempfehlungen finden](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) Sie unter Schützen von Kursteilnehmern bei der Verwendung von Teams für fernunterricht.

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Schritt 3: Überprüfen des Nachrichtencenters auf Richtlinienupdates

Derzeit wendet der Assistent unsere empfohlenen Richtlinien an, wenn Sie ihn ausführen. Es ist wichtig zu wissen, dass die globalen (organisationsweiten Standardeinstellungen) für die Sicherheit von Kursteilnehmern nicht automatisch vom Assistenten hinzugefügt werden, sobald neue Richtlinien in Teams verfügbar werden. Diese Funktion wird in einer zukünftigen Version verfügbar sein.

Bis diese Funktion verfügbar ist, überprüfen Sie häufig [das Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (im Microsoft 365 Admin Center), um über neue Richtlinien und Richtlinieneinstellungen in Teams auf dem laufenden zu bleiben. Sobald neue Features verfügbar werden, müssen Sie Ihre Richtlinien möglicherweise manuell aktualisieren, um Ihre Lernumgebung sicher zu halten.

## <a name="make-changes-in-the-wizard"></a>Vornehmen von Änderungen im Assistenten

<a name="polwiz_change"> </a>

Wenn Sie nach dem Ausführen des Assistenten Änderungen vornehmen müssen, können Sie ihn erneut ausführen und Ihre Auswahl ändern.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams  Admin Centers zu **Dashboard,** und wählen Sie dann in der Kachel Einfache Richtlinieneinrichtung für eine Kachel für eine sichere Lernumgebung die Option **Ändern aus.**
2. Fahren Sie von hier aus auf jeder Seite des Assistenten fort, um Ihre Änderungen vorzunehmen. Sie können Ihren Bildungseinrichtungstyp, die Gruppe der Lehrkräfte und Mitarbeiter, denen Sie Richtlinien zuweisen möchten, oder beides ändern.

In der folgenden Tabelle wird zusammengefasst, was geschieht, wenn Sie eine Änderung am Assistenten ausführen.

|Änderungstyp  |Richtlinienverhalten  |
|---------|---------|
|Ändern des Bildungseinrichtungstyps und der Gruppe "Lehrkräfte und Mitarbeiter"    |<ul><li>**Kursteilnehmer:** Die globalen Richtliniendefinitionen (organisationsweit) basierend auf dem neuen Bildungseinrichtungstyp werden auf Kursteilnehmer angewendet.</li><li>**Lehrkräfte und Mitarbeiter:** Eine Reihe benutzerdefinierter Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und der neuen Lehrkräfte- und Mitarbeitergruppe zugewiesen. Die vorherigen benutzerdefinierten Richtliniendefinitionen werden aus den vorherigen Lehrkräften und der Mitarbeitergruppe entfernt.</li></ul>    |
|Ändern nur des Bildungseinrichtungstyps    |<ul><li>**Kursteilnehmer:** Die globalen Richtliniendefinitionen (organisationsweit) basierend auf dem neuen Bildungseinrichtungstyp werden auf Kursteilnehmer angewendet.</li><li>**Lehrkräfte und Mitarbeiter:** Eine Reihe benutzerdefinierter Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und den Lehrkräften und der Mitarbeitergruppe zugewiesen. Die benutzerdefinierten Richtliniendefinitionen, die für den vorherigen Bildungseinrichtungstyp erstellt wurden, werden aus der Gruppe "Lehrkräfte und Mitarbeiter" entfernt.</li></ul>         |
|Ändern nur der Lehrkräfte und der Mitarbeitergruppe   |<ul><li>**Kursteilnehmer:** Keine Änderung an den globalen Richtliniendefinitionen (Organisationsweite Standarddefinitionen), die auf Kursteilnehmer angewendet wurden.</li><li>**Lehrkräfte und Mitarbeiter:** Die benutzerdefinierten Richtliniendefinitionen werden der neuen Lehrkräfte- und Mitarbeitergruppe zugewiesen und aus der vorherigen Lehrkräfte- und Mitarbeitergruppe entfernt.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Vom Assistenten angewendete Richtlinien

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Richtlinienbereiche

Hier sind die Richtlinienbereiche und die entsprechenden Richtliniennamen, die vom Assistenten behandelt werden. Um diese Richtlinien zu finden, wechseln Sie zum Microsoft Teams Admin Center, und wechseln Sie dann in der linken Navigationsleiste zu den einzelnen Richtlinienbereichsseiten.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/students/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Hochschulrichtlinie  |
|---------|---------|---------|
|Teams-Richtlinie    |Global (Organisationsweite Standardeinstellung)         |Global (Organisationsweite Standardeinstellung)           |
|Besprechungsrichtlinie    |Global (Organisationsweite Standardeinstellung)           |Global (Organisationsweite Standardeinstellung)           |
|Richtlinie für Liveereignisse     |Global (Organisationsweite Standardeinstellung)          |  Global (Organisationsweite Standardeinstellung)          |
|App-Setuprichtlinie     |Global (Organisationsweite Standardeinstellung)           |Global (Organisationsweite Standardeinstellung)           |
|App-Berechtigungsrichtlinie    |Global (Organisationsweite Standardeinstellung)           |Global (Organisationsweite Standardeinstellung)           |
|Messagingrichtlinie     |Global (Organisationsweite Standardeinstellung)           |Global (Organisationsweite Standardeinstellung)           |
|Anrufrichtlinie    |Global (Organisationsweite Standardeinstellung)           |Global (Organisationsweite Standardeinstellung)           |

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educators/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Hochschulrichtlinie |
|---------|---------|---------|
|Teams-Richtlinie   |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Teams         |Lehrkräfte und Mitarbeiter in höheren Bildungseinrichtungen – Teams         |
|Besprechungsrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Besprechung         |Lehrkräfte und Mitarbeiter für Höhere Bildungseinrichtungen – Besprechung         |
|Richtlinie für Liveereignisse   | Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Liveereignisse         |Lehrkräfte und Mitarbeiter für Höhere Bildungseinrichtungen – Liveereignisse         |
|Messagingrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Messaging         | Lehrkräfte und Mitarbeiter in höheren Bildungseinrichtungen – Messaging         |
|Anrufrichtlinie    |Primäre oder Sekundärpädagogen und Mitarbeiter – Anrufe         |Lehrkräfte und Mitarbeiter für Höhere Bildungseinrichtungen – Anrufe         |

* * *

### <a name="policy-settings"></a>Richtlinieneinstellungen

Hier finden Sie eine Zusammenfassung der Einstellungen, die vom Assistenten für jeden Richtlinienbereich angewendet wurden.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/student-settings/)

Hier finden Sie eine Liste der vom Assistenten angepassten und auf Kursteilnehmer angewendeten globalen (organisationsweiten Standard)-Richtliniendefinitionen.

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder Sekundär |Höhere Bildungseinrichtungen |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Aus       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Sofortbesprechungen in Kanälen zulassen         |Aus      |Ein|
|  |        |Outlook-Add-In zulassen         |Aus       |Ein|
|  |        |Planung von Kanalbesprechungen zulassen        |Aus      |Ein|
|  |        |Planung privater Besprechungen zulassen       |Aus      |Ein|
|  |Audio & Video        |Transkription zulassen        |Ein       |Ein|
|  |        |Cloud-Aufnahme zulassen         |Aus      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audio aktiviert        |Ausgehendes und eingehendes Audio aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video zulassen         |Ein         |Ein|
|  |       |Zulassen des NDI-Streamings         |Aus         |Aus|
|  |       |Media-Bitrate (KBs)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmübertragungsmodus         |Gesamter Bildschirm         |Gesamter Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert         |Ein         |Ein|
|  |       |Teilen von PowerPoint zulassen        |Ein         |Ein|
|  |       |Whiteboard zulassen         |Ein         |Ein|
|  |       |Geteilte Notizen zulassen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Anonymen Personen das Starten einer Besprechung gestatten       |Aus         |Ein|
|  |       |Rollen mit Presenterrechten in Besprechungen        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Personen automatisch zulassen        |EveryoneInCompany|EveryoneInCompany|
|  |       |Einwahlbenutzern das Umgehen des Wartebereichs gestatten        |Aus         |Aus|
|  |       |Sofortbesprechungen in privaten Besprechungen zulassen        |Aus         |Ein|
|  |       |Liveuntertitel aktivieren       |Deaktiviert, aber Benutzer können außer Kraft setzen         |Deaktiviert, aber Benutzer können außer Kraft setzen|
|  |       |Chat in Besprechungen zulassen         |Ein         |Ein|
|Richtlinie für Liveereignisse  |       |Planung erlauben         |Aus         |Aus|
|  |       |Transkription für Teilnehmer zulassen          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Wer kann ein Ereignis aufzeichnen?         |Immer         |Immer|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Aus|Ein|
|  |       |Gesendete Nachrichten löschen         |Aus         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Aus         |Ein|
|  |       |Lesebestätigungen         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Chat         |Aus         |Ein|
|  |       |Giphys in Unterhaltungen verwenden         |Aus         |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Verwenden von Memes in Unterhaltungen         |Ein         |Ein|
|  |       |Verwenden von Aufklebern in Unterhaltungen         |Ein         |Ein|
|  |       |URL-Vorschau zulassen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Plastischen Reader zum Anzeigen von Nachrichten zulassen        |Ein      |Ein|
|  |       |Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden  |Aus         |Ein|
|  |       |Erstellen von Sprachnachrichten         |Zulässig in Chats und Kanälen         |Zulässig in Chats und Kanälen|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Aus         |Ein|
|App-Berechtigungsrichtlinie  |       |Microsoft-Apps         |Blockieren bestimmter Apps und Zulassen von > Von Walkie Talkie blockiert         |Alle Apps zulassen|
|  |       |Apps von Drittanbietern         |Alle Apps zulassen         |Alle Apps zulassen|
|  |       |Benutzerdefinierte Apps         |Alle Apps zulassen         |Alle Apps zulassen|
|App-Setuprichtlinie  |           |Hochladen benutzerdefinierter Apps           |Aus         |Aus|
|  |       |Benutzer anheften zulassen |Ein         |Ein|
|  |       |Installierte Apps         |Keine         |Keine|
|  |       |Angeheftet Apps         |Aktivität, Kalender, Teams         |Aktivität, Chats, Teams, Kalender, Anrufe, Datei
|Anrufrichtlinie  |       |Private Anrufe führen         |Aus        |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an Personen in Ihrer Organisation         |Aus         |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Klingeln an externe Telefonnummern         |Aus         |Ein|
|  |       |Voicemail ist für die Weiterleitung eingehender Anrufe verfügbar.         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Aus        |Ein|
|  |       |Zulassen der Delegierung für eingehende und ausgehende Anrufe         |Aus         |Ein|
|  |       |Verhindern der Umgehung der Gebühren und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |Beschäftigt bei beschäftigt ist verfügbar, wenn in einem Anruf         |Aus         |Aus|
|  |       |Zulassen von Web-PSTN-Anrufen         |Aus         |Ein|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educator-settings/)

Hier ist eine Liste der benutzerdefinierten Richtliniendefinitionen, die den Lehrkräften und der Mitarbeitergruppe zugewiesen sind, die Sie im Assistenten auswählen.  

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder Sekundär |Höhere Bildungseinrichtungen |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Ein       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Sofortbesprechungen in Kanälen zulassen         |Ein      |Ein|
|  |        |Outlook-Add-In zulassen         |Ein       |Ein|
|  |        |Planung von Kanalbesprechungen zulassen        |Ein      |Ein|
|  |        |Planung privater Besprechungen zulassen       |Ein      |Ein|
|  |Audio & Video        |Transkription zulassen        |Ein       |Ein|
|  |        |Cloud-Aufnahme zulassen         |Ein      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audio aktiviert        |Ausgehendes und eingehendes Audio aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video zulassen         |Ein         |Ein|
|  |       |Zulassen des NDI-Streamings         |Aus         |Aus|
|  |       |Media-Bitrate (KBs)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmübertragungsmodus         |Gesamter Bildschirm         |Gesamter Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert         |Ein         |Ein|
|  |       |Teilen von PowerPoint zulassen        |Ein         |Ein|
|  |       |Whiteboard zulassen         |Ein         |Ein|
|  |       |Geteilte Notizen zulassen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Anonymen Personen das Starten einer Besprechung gestatten       |Ein        |Ein|
|  |       |Rollen mit Presenterrechten in Besprechungen        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Personen automatisch zulassen        |OrganizerOnly|OrganizerOnly|
|  |       |Einwahlbenutzern das Umgehen des Wartebereichs gestatten        |Aus         |Aus|
|  |       |Sofortbesprechungen in privaten Besprechungen zulassen        |Ein         |Ein|
|  |       |Liveuntertitel aktivieren       |Deaktiviert, aber Benutzer können außer Kraft setzen         |Deaktiviert, aber Benutzer können außer Kraft setzen|
|  |       |Chat in Besprechungen zulassen         |Ein         |Ein|
|Richtlinie für Liveereignisse  |       |Planung erlauben         |Ein         |Ein|
|  |       |Transkription für Teilnehmer zulassen          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Wer kann ein Ereignis aufzeichnen?         |Immer aufzeichnen         |Immer aufzeichnen|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Ein|Ein|
|  |       |Gesendete Nachrichten löschen         |Ein         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Ein         |Ein|
|  |       |Lesebestätigungen         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Chat         |Ein         |Ein
|  |       |Giphys in Unterhaltungen verwenden         |Ein        |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Verwenden von Memes in Unterhaltungen         |Ein         |Ein|
|  |       |Verwenden von Aufklebern in Unterhaltungen         |Ein         |Ein|
|  |       |URL-Vorschau zulassen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Plastischen Reader zum Anzeigen von Nachrichten zulassen        |Ein      |Ein|
|  |       |Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden  |Ein         |Ein|
|  |       |Erstellen von Sprachnachrichten         |Zulässig in Chats und Kanälen         |Zulässig in Chats und Kanälen|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Ein        |Ein|
|Anrufrichtlinie  |       |Private Anrufe führen         |Ein       |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an Personen in Ihrer Organisation         |Ein        |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Klingeln an externe Telefonnummern         |Ein        |Ein|
|  |       |Voicemail ist für die Weiterleitung eingehender Anrufe verfügbar.         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Ein        |Ein|
|  |       |Zulassen der Delegierung für eingehende und ausgehende Anrufe         |Ein         |Ein|
|  |       |Verhindern der Umgehung der Gebühren und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |Beschäftigt bei beschäftigt ist verfügbar, wenn in einem Anruf         |Aus         |Aus|
|  |       |Zulassen von Web-PSTN-Anrufen         |Ein      |Ein|

* * *

## <a name="related-topics"></a>Verwandte Themen

- [Teams-Richtlinien und Richtlinienpakete für Bildungseinrichtungen](policy-packages-edu.md)
- [Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](batch-group-policy-assignment-edu.md)
- [Schützen von Kursteilnehmern während der Verwendung von Teams für fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)