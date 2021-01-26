---
title: Teams für Bildungsrichtlinien-Assistent zum einfachen Anwenden von Richtlinien für sicheres Lernen
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
description: Erfahren Sie, wie Sie mithilfe des Richtlinienassistenten für Teams für Bildungseinrichtungen auf einfache Weise Richtlinien für Schüler/Studierende und Lehrkräfte anwenden können, um Ihre Lernumgebung sicher zu halten.
f1keywords: ''
ms.openlocfilehash: 1ea7fb684bce3d59063f1a258d0db37fb75a4681
ms.sourcegitcommit: 95b85926d67cbf3159f58d9083d5813cc29074f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790419"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Verwenden des Assistenten für Richtlinien für Teams für Bildungseinrichtungen zum einfachen Anwenden von Richtlinien für eine sichere Lernumgebung

## <a name="overview"></a>Übersicht

Der Microsoft Teams für Bildungsrichtlinien-Assistent vereinfacht die Verwaltung von Richtlinien für Schüler/Studierende und Lehrkräfte. Verwenden Sie sie, um die wichtigsten Richtlinien, die für die Erstellung einer sicheren und produktiven Lernerfahrung relevant sind, einfach und schnell anzuwenden.

Mit Richtlinien in Teams können Sie steuern, wie sich Teams in Ihrer Umgebung verhält und welche Features den Benutzern zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen, und jeder Richtlinienbereich kann an die Anforderungen Ihrer Organisation angepasst werden.

Um eine sichere und fokussierte Lernumgebung zu erhalten, ist es wichtig, Richtlinien zu festlegen, um zu steuern, was Schüler/Studierende in Teams tun können. Beispielsweise können Sie mithilfe von Richtlinien steuern, wer private Chats und private Anrufe verwenden kann, wer Besprechungen planen kann und welche Inhaltstypen freigegeben werden können. Sie können auch Richtlinien verwenden, um Teams-Features zu aktivieren, die die Lernerfahrung bereichern.

Richtlinien müssen sowohl für Schüler/Studierende als auch für Lehrkräfte angepasst werden, um die Lernerfahrung sicher zu halten. Richtlinien für Schüler/Studierende müssen restriktiver sein, um das Risiko zu verringern, unangemessene Zugriffsebenen zu erhalten. Lehrkräfte und Mitarbeiter benötigen einen separaten Satz von Richtlinien, die möglicherweise einmischen, um erfolgversprechend zu sein. Lassen Sie beispielsweise Lehrkräften das Planen von Besprechungen zu und verhindern Sie, dass Schüler/Studierende dies tun.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot des Assistenten":::

Dieser Artikel führt Sie durch die Ausführung des Assistenten.

> [!IMPORTANT]
> Die vom Assistenten angewendeten Richtlinien entsprechen den Anforderungen der Mehrzahl der Teams für Education-Kunden. Der Assistent passt die globale Definition (organisationsweite Standarddefinition) einer Kernsatz von Richtlinien mit Einstellungen an, die wir für die Sicherheit von Kursteilnehmern empfehlen, und wendet sie auf Schüler/Studierende an. Der Assistent erstellt und weist außerdem einen Satz benutzerdefinierter Richtlinien für Lehrkräfte und Mitarbeiter zu. Die meisten Kunden von Teams für Bildungseinrichtungen müssen nach dem Ausführen dieses Assistenten keine anderen Richtlinienzuweisungsmethoden verwenden. Verwenden Sie andere  Richtlinienzuweisungsmethoden nur, wenn Sie Richtlinien für Ihre Kursteilnehmer, Lehrkräfte und Mitarbeiter manuell erstellen und verwalten möchten.

## <a name="teams-for-education-policy-wizard"></a>Teams for Education Policy Wizard

<a name="polwiz_intro"> </a>

Der Assistent wendet eine Reihe von grundlegenden Richtliniendefinitionen auf Schüler/Studierende und einen separaten Satz von grundlegenden Richtliniendefinitionen für Lehrkräfte und Mitarbeiter an, mit einstellungen, die jeweils geeignet sind. Dies geschieht, wenn Sie den Assistenten ausführen.

Der Assistent richtet Richtlinien basierend auf dem Typ der Bildungseinrichtung ein (primäre oder **sekundäre** oder **höhere Bildungseinrichtung).** Sie wählen den Typ Ihrer Einrichtung aus, und der Assistent führt die folgenden Schritte aus:

- **Schüler/Studenten:** Der Assistent passt die globale Richtliniendefinition (organisationsweite Standardrichtlinie) für jeden vom Assistenten abgedeckten Richtlinienbereich mit neuen Standardeinstellungen an, die geeignet sind, um die Sicherheit Ihrer Schüler/Studierenden zu gewährleisten. Dadurch wird sichergestellt, dass Ihre aktuellen Schüler/Studierenden und alle neuen Schüler/Studenten den restriktivsten Satz von Richtlinien erhalten.
- **Lehrkräfte und Mitarbeiter:** Der Assistent erstellt eine Reihe benutzerdefinierter Richtliniendefinitionen für jeden vom Assistenten abgedeckten Richtlinienbereich mit Einstellungen, die auf die Anforderungen von Lehrkräften und Mitarbeitern zugeschnitten sind. Anschließend werden die Richtliniendefinitionen der gruppe von Lehrkräften und Mitarbeitern zugewiesen, die Sie auswählen. Auf diese Weise erhalten Ihre Lehrkräfte und Mitarbeiter einen unzulässigeren Satz von Richtlinien, damit sie erfolgreich sein können.

Sie müssen den Assistenten nur einmal ausführen. Neuen Kursteilnehmern werden automatisch die vom Assistenten angewendeten globalen (organisationsweiten) Richtliniendefinitionen zugewiesen, und neuen Mitarbeitern, die Sie der ausgewählten Gruppe hinzufügen, werden automatisch die benutzerdefinierten Richtlinien zugewiesen.

> [!NOTE]
> Eine [detaillierte Liste der Richtliniendefinitionen,](#policies-applied-by-the-wizard) die vom Assistenten angewendet wurden, finden Sie unter "Vom Assistenten angewendete Richtlinien".

Los geht's!

## <a name="run-the-wizard"></a>Ausführen des Assistenten

<a name="polwiz_run"> </a>

Führen Sie zum Ausführen des Assistenten die folgenden Schritte aus.

1. Wenn Sie noch nicht mit Teams arbeiten, wird der Assistent automatisch gestartet. Andernfalls können Sie den Assistenten jederzeit über das Dashboard starten. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams  Admin Centers zum **Dashboard,** und wählen Sie dann in der Kachel "Einfache Richtlinieneinrichtung für eine sichere Lernumgebung" die Option **"Schnelles Setup" aus.**

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Assistenten im Dashboard":::

2. Wählen Sie den Typ Ihrer Bildungseinrichtung (primäre oder **sekundäre** oder höhere **Bildungseinrichtung)** und dann "Weiter" **aus.**

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen des Einrichtungstyps":::

3. Suchen Und wählen Sie eine Gruppe aus, die Ihre Lehrkräfte und Mitarbeiter enthält, und wählen Sie dann **"Weiter" aus.** Wenn Sie noch keine Gruppen für Ihre Lehrkräfte und Mitarbeiter eingerichtet [haben,](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)erstellen Sie eine Gruppe, und führen Sie dann den Assistenten erneut aus. <br/><br/>Derzeit können Sie nur eine Gruppe auswählen. Lehrkräften und Mitarbeitern in der von Ihnen ausgewählten Gruppe wird eine Reihe benutzerdefinierter Richtlinien zugewiesen, die [auf](#policies-applied-by-the-wizard) ihre Anforderungen zugeschnitten sind. Denken Sie daran, dass dieser Satz von Richtlinien von den auf Schüler/Studenten angewendeten Richtlinien getrennt ist.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen der Gruppe "Lehrkräfte und Mitarbeiter"":::

4. Überprüfen Sie Ihre Auswahl.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Screenshot der Seite im Assistenten zum Überprüfen der Auswahl":::

5. Wählen Sie **"Übernehmen"** aus, um Ihre Änderungen anzuwenden. Dies kann einige Minuten dauern.<br/><br/>Die globalen Richtliniendefinitionen (organisationsweite Standardrichtlinie) werden sofort auf Schüler/Studierende angewendet. Für Ihre Lehrkräfte und Mitarbeiter kann es je nach Größe der Gruppe einige Stunden dauern, bis die benutzerdefinierten Richtlinien jedem Mitglied der ausgewählten Gruppe zugewiesen wurden. Dies geschieht im Hintergrund, nachdem Sie diesen Schritt erfolgreich abgeschlossen haben.
6. Sie sind auf dem Weg, haben es aber noch nicht geschafft! Es gibt ein paar weitere Dinge, die Sie berücksichtigen sollten. Schauen Sie sich als Nächstes die Schritte im Abschnitt "Was zu tun [ist, nachdem](#what-to-do-after-running-the-wizard) Sie den Assistenten ausgeführt haben" in diesem Artikel an.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot der Seite im Assistenten für die nächsten Schritte":::

## <a name="what-to-do-after-running-the-wizard"></a>Was nach dem Ausführen des Assistenten zu tun ist

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Schritt 1: Entfernen vorhandener Richtlinienzuweisungen, die mit vom Assistenten angewendeten Richtlinien in Konflikt stehen

> [!IMPORTANT]
> Führen Sie diesen Schritt nur aus, wenn Sie Schülern/Studierenden, Lehrkräften und Mitarbeitern bereits Richtlinien zugewiesen haben, ***bevor* Sie den Assistenten ausgeführt haben.** Wenn Sie neu bei Teams sind und über keine anderen Richtlinien als die vom Assistenten erstellten Richtlinien verfügen, überspringen Sie dies, und fahren Sie mit Schritt 2 fort.

In Teams kann eine Richtlinie für einen bestimmten Richtlinienbereich auf einen Benutzer auf folgende Weise angewendet werden:

- Direkte Zuweisung an den Benutzer
- Zuweisung zu einer Gruppe, bei der der Benutzer Mitglied ist
- Wenn dem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen wurde, erhält der Benutzer automatisch die globale (organisationsweite Standard)-Richtlinie.

Wenn mehrere dieser Richtlinienzuweisungen für einen Benutzer vorhanden sind, bestimmt Teams in der folgenden Reihenfolge, welche Richtlinienzuweisung wirksam wird. Weitere Informationen finden Sie unter ["Welche Richtlinie hat Vorrang?"](assign-policies.md#which-policy-takes-precedence) und ["Rangfolgeregeln".](assign-policies.md#precedence-rules)

|Richtlinienzuweisungen eines Benutzers|Richtlinie, die wirksam wird |
|---------|---------|
|Einer Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Nein    |Globale Standardrichtlinie (organisationsweit)      |
|Einer Gruppe zugewiesene Richtlinie: Nein<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Ja    |Richtlinie, die dem Benutzer direkt zugewiesen wurde         |
|Einer Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Ja     |Richtlinie, die dem Benutzer direkt zugewiesen wurde         |
|Einer Gruppe zugewiesene Richtlinie: Ja<br/>Richtlinie, die dem Benutzer direkt zugewiesen wurde: Nein     |Einer Gruppe zugewiesene Richtlinie<br/><br/>Wenn der Benutzer Mitglied mehrerer Gruppen ist und jeder Gruppe eine Richtlinie desselben Richtlinienbereichs zugewiesen ist, wird die Richtlinie mit der höchsten Gruppenzuordnungsrangfolge wirksam. [](assign-policies.md#group-assignment-ranking)       |

Aufgrund dieser Reihenfolge werden die vom Assistenten erstellten Richtlinien nicht wirksam, wenn ein Benutzer über vorhandene direkte Zuordnungen oder Gruppenzuweisungen verfügt. Dies bedeutet, dass Sie die vorhandenen Richtlinienzuweisungen vom Benutzer entfernen müssen, damit die vom Assistenten angewendete Richtlinie wirksam wird.

Gehen Sie [für jeden vom Assistenten angewendeten](#policies-applied-by-the-wizard)Richtlinienbereich wie folgt vor:

- Entfernen Sie alle vorhandenen direkten Zuordnungen und Gruppenzuweisungen von den Kursteilnehmern, damit die vom Assistenten angewendete globale Richtliniendefinition (organisationsweite Standardrichtlinie) wirksam wird.
- Entfernen Sie alle widersprüchlichen direkten Zuweisungen für Ihre Lehrkräfte und Mitarbeiter, damit die vom Assistenten erstellte benutzerdefinierte Richtliniendefinition wirksam wird. Ermitteln Sie mithilfe der obigen Tabelle die Szenarien, die für Sie gelten. <br/><br/>Beachten Sie, dass der Assistent Richtlinien ihren Lehrkräften [](assign-policies.md#group-assignment-ranking) und Mitarbeitergruppen mit einer Gruppenzuweisungsrangfolge von 1 zulistet, die die höchste Bewertung ist. Wenn Ihren Lehrkräften und Ihrer Mitarbeitergruppe eine Richtlinie im gleichen Richtlinienbereich zugewiesen ist, wird diese vorhandene Richtlinie in eine niedrigere Bewertung verschoben, und die vom Assistenten zugewiesene Richtlinie wird wirksam.

[Erfahren Sie mehr](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) darüber, wie Sie Richtlinien entfernen, die Benutzern direkt zugewiesen sind.

Beispielsweise haben Sie Lehrkräften direkt eine Besprechungsrichtlinie zugewiesen, und Ihre Schüler haben die globale (organisationsweite Standard)-Besprechungsrichtlinie. Entfernen Sie in diesem Szenario die Besprechungsrichtlinie, die Sie Lehrkräften direkt zugewiesen haben, damit die benutzerdefinierte Richtliniendefinition für die vom Assistenten erstellte Besprechungsrichtlinie wirksam wird. Sie müssen nichts mit der vorhandenen globalen (organisationsweiten Standard)-Besprechungsrichtlinie für Schüler/Studierende unternehmen, da keine anderen Besprechungsrichtlinien damit in Konflikt stehen.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Schritt 2: Prüfen auf zusätzliche Maßnahmen, die Sie für die Sicherheit von Kursteilnehmern ergreifen können

Der Assistent passt diese Richtlinien automatisch an und [wendet diese an.](#policies-applied-by-the-wizard) Es gibt ein paar zusätzliche Maßnahmen, die Sie basierend auf den Anforderungen Ihrer Einrichtung zur Sicherheit ergreifen sollten.

Weitere [Sicherheitsempfehlungen finden Sie unter](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) "Sicherheit der Schüler bei der Verwendung von Teams für den Fernunterricht".

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Schritt 3: Überprüfen des Nachrichtencenters auf Richtlinienupdates

Derzeit wendet der Assistent unsere empfohlenen Richtlinien an, wenn Sie ihn ausführen. Es ist wichtig zu wissen, dass, sobald neue Richtlinien in Teams verfügbar werden, die globalen Einstellungen für die Sicherheit von Kursteilnehmern nicht automatisch vom Assistenten hinzugefügt werden. Diese Funktion wird in einer zukünftigen Version zur Verfügung stehen.

Bis diese Funktion verfügbar ist, überprüfen Sie das Nachrichtencenter [(im](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) Microsoft 365 Admin Center) häufig, um über neue Richtlinien und Richtlinieneinstellungen in Teams auf dem Laufenden zu bleiben. Sobald neue Features verfügbar sind, müssen Sie Ihre Richtlinien möglicherweise manuell aktualisieren, um Ihre Lernumgebung zu schützen.

## <a name="make-changes-in-the-wizard"></a>Vornehmen von Änderungen im Assistenten

<a name="polwiz_change"> </a>

Wenn Sie nach dem Ausführen des Assistenten Änderungen vornehmen müssen, können Sie ihn erneut ausführen und Ihre Auswahl ändern.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams  Admin Centers zum **Dashboard,** und wählen Sie dann im Setup der einfachen Richtlinie für eine Kachel für eine sichere Lernumgebung "Ändern" **aus.**
2. Von hier aus fahren Sie mit den einzelnen Seiten des Assistenten fort, um die Änderungen vorzunehmen. Sie können den Typ Ihrer Bildungseinrichtung, die Gruppe der Lehrkräfte und Mitarbeiter, denen Sie Richtlinien zuweisen möchten, oder beides ändern.

In der folgenden Tabelle ist zusammengefasst, was geschieht, wenn Sie im Assistenten eine Änderung ausführen.

|Änderungstyp  |Richtlinienverhalten  |
|---------|---------|
|Ändern des Typs der Bildungseinrichtung sowie der Gruppe "Lehrkräfte und Mitarbeiter"    |<ul><li>**Schüler/Studenten:** Die globalen Richtliniendefinitionen (organisationsweit standard), die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studierende angewendet.</li><li>**Lehrkräfte und Mitarbeiter:** Eine Reihe benutzerdefinierter Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und der neuen Gruppe für Lehrkräfte und Mitarbeiter zugewiesen. Die vorherigen benutzerdefinierten Richtliniendefinitionen werden aus den vorherigen Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>    |
|Nur den Bildungseinrichtungstyp ändern    |<ul><li>**Schüler/Studenten:** Die globalen Richtliniendefinitionen (organisationsweit standard), die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studierende angewendet.</li><li>**Lehrkräfte und Mitarbeiter:** Eine Reihe benutzerdefinierter Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und der Gruppe der Lehrkräfte und Mitarbeiter zugewiesen. Die für den vorherigen Bildungseinrichtungstyp erstellten benutzerdefinierten Richtliniendefinitionen werden aus der Gruppe "Lehrkräfte und Mitarbeiter" entfernt.</li></ul>         |
|Ändern nur der Gruppe "Lehrkräfte und Mitarbeiter"   |<ul><li>**Schüler/Studenten:** Keine Änderung an den globalen Richtliniendefinitionen (organisationsweite Standardrichtlinie), die auf Schüler/Studierende angewendet werden.</li><li>**Lehrkräfte und Mitarbeiter:** Die benutzerdefinierten Richtliniendefinitionen werden der neuen Gruppe der Lehrkräfte und Mitarbeiter zugewiesen und aus der vorherigen Gruppe der Lehrkräfte und Mitarbeiter entfernt.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Vom Assistenten angewendete Richtlinien

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Richtlinienbereiche

Hier sehen Sie die Richtlinienbereiche und die entsprechenden Richtliniennamen, die vom Assistenten abgedeckt werden. Um diese Richtlinien zu finden, wechseln Sie zum Microsoft Teams Admin Center, und wechseln Sie dann im linken Navigationsbereich zu jeder Seite des Richtlinienbereichs.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/students/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Richtlinie für höhere Bildungseinrichtungen  |
|---------|---------|---------|
|Teams-Richtlinie    |Global (organisationsweite Standardeinstellung)         |Global (organisationsweite Standardeinstellung)           |
|Besprechungsrichtlinie    |Global (organisationsweite Standardeinstellung)           |Global (organisationsweite Standardeinstellung)           |
|Richtlinie für Liveereignisse     |Global (organisationsweite Standardeinstellung)          |  Global (organisationsweite Standardeinstellung)          |
|App-Setup-Richtlinie     |Global (organisationsweite Standardeinstellung)           |Global (organisationsweite Standardeinstellung)           |
|Berechtigungsrichtlinie für Apps    |Global (organisationsweite Standardeinstellung)           |Global (organisationsweite Standardeinstellung)           |
|Messagingrichtlinie     |Global (organisationsweite Standardeinstellung)           |Global (organisationsweite Standardeinstellung)           |
|Anrufrichtlinie    |Global (organisationsweite Standardeinstellung)           |Global (organisationsweite Standardeinstellung)           |

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educators/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Richtlinie für höhere Bildungseinrichtungen |
|---------|---------|---------|
|Teams-Richtlinie   |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Teams         |Lehrkräfte und Mitarbeiter für höhere Bildungseinrichtungen – Teams         |
|Besprechungsrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Besprechung         |Lehrkräfte und Mitarbeiter für höhere Bildungseinrichtungen – Besprechung         |
|Richtlinie für Liveereignisse   | Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Liveereignisse         |Lehrkräfte und Mitarbeiter für höhere Bildungseinrichtungen – Liveereignisse         |
|Messagingrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Nachrichten         | Lehrkräfte und Mitarbeiter in höheren Bildungseinrichtungen – Messaging         |
|Anrufrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Anrufe         |Lehrkräfte und Mitarbeiter in höheren Bildungseinrichtungen – Anrufe         |

* * *

### <a name="policy-settings"></a>Richtlinieneinstellungen

Hier ist eine Zusammenfassung der Einstellungen, die vom Assistenten für jeden Richtlinienbereich angewendet werden.

#### <a name="students"></a>[**Schüler/Studenten**](#tab/student-settings/)

Hier ist eine Liste der globalen (organisationsweiten) Richtliniendefinitionen, die vom Assistenten angepasst und auf Schüler und Studenten angewendet wurden.

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |"Primär" oder "Sekundär" |Höhere Bildung |
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
|  |       |Senden von dringenden Nachrichten mithilfe von Prioritätsbenachrichtigungen  |Aus         |Ein|
|  |       |Erstellen von Sprachnachrichten         |In Chats und Kanälen zulässig         |In Chats und Kanälen zulässig|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Aus         |Ein|
|Berechtigungsrichtlinie für Apps  |       |Microsoft-Apps         |Blockieren bestimmter Apps und Zulassen, dass alle > "Walkie-Talkie" blockiert sind         |Alle Apps zulassen|
|  |       |Apps von Drittanbietern         |Alle Apps zulassen         |Alle Apps zulassen|
|  |       |Benutzerdefinierte Apps         |Alle Apps zulassen         |Alle Apps zulassen|
|App-Setup-Richtlinie  |           |Hochladen benutzerdefinierter Apps           |Aus         |Aus|
|  |       |Benutzer anheften zulassen |Ein         |Ein|
|  |       |Installierte Apps         |Keine         |Keine|
|  |       |Angeheftete Apps         |Aktivität, Kalender, Teams         |Aktivität, Chats, Teams, Kalender, Anrufe, Datei
|Anrufrichtlinie  |       |Private Anrufe führen         |Aus        |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Aus         |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an externe Telefonnummern         |Aus         |Ein|
|  |       |Voicemail ist für das Routing eingehender Anrufe verfügbar         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Aus        |Ein|
|  |       |Delegierung für ein- und ausgehende Anrufe zulassen         |Aus         |Ein|
|  |       |Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das FESTNETZ        |Aus         |Aus|
|  |       |"Beschäftigt" ist während eines Anrufs verfügbar         |Aus         |Aus|
|  |       |Zulassen von Web-PSTN-Anrufen         |Aus         |Ein|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educator-settings/)

Hier ist eine Liste der benutzerdefinierten Richtliniendefinitionen, die den Lehrkräften und Mitarbeitergruppen zugewiesen wurden, die Sie im Assistenten auswählen.  

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |"Primär" oder "Sekundär" |Höhere Bildung |
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
|  |       |Senden von dringenden Nachrichten mithilfe von Prioritätsbenachrichtigungen  |Ein         |Ein|
|  |       |Erstellen von Sprachnachrichten         |In Chats und Kanälen zulässig         |In Chats und Kanälen zulässig|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppenchats         |Ein        |Ein|
|Anrufrichtlinie  |       |Private Anrufe führen         |Ein       |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Ein        |Ein|
|  |       |Anruf weiterleitung und gleichzeitiges Anrufen an externe Telefonnummern         |Ein        |Ein|
|  |       |Voicemail ist für das Routing eingehender Anrufe verfügbar         |Vom Benutzer gesteuert         |Vom Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen geroutet werden         |Ein        |Ein|
|  |       |Delegierung für ein- und ausgehende Anrufe zulassen         |Ein         |Ein|
|  |       |Verhindern einer gebührenpflichtigen Umgehung und Senden von Anrufen über das FESTNETZ        |Aus         |Aus|
|  |       |"Beschäftigt" ist während eines Anrufs verfügbar         |Aus         |Aus|
|  |       |Zulassen von Web-PSTN-Anrufen         |Ein      |Ein|

* * *

## <a name="related-topics"></a>Verwandte Themen

- [Richtlinien und Richtlinienpakete für Teams für Bildungseinrichtungen](policy-packages-edu.md)
- [Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](batch-group-policy-assignment-edu.md)
- [Sicherheit der Schüler bei der Verwendung von Teams für den Fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
