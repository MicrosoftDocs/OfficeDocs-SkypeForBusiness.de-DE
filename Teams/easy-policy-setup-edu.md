---
title: Assistent für "Teams für Bildungsrichtlinien" zur einfachen Anwendung von Richtlinien für sicheres lernen
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie mithilfe des Assistenten für Bildungsrichtlinien auf einfache Weise Richtlinien für Schüler und Pädagogen anwenden, um Ihre Lernumgebung zu schützen.
f1keywords: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: d72ef20a8ae56fba67534944d229d01468531207
ms.sourcegitcommit: 80c1ec1d5a43b9259a4da6db3e462f6d4257bfa7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49564254"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Verwenden des Assistenten "Teams für Bildungsrichtlinien", um einfach Richtlinien für eine sichere Lernumgebung anzuwenden

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Übersicht

Der Microsoft Teams für Bildungsrichtlinien-Assistent vereinfacht das Verwalten von Richtlinien für Schüler und Pädagogen. Verwenden Sie diese Methode, um die wichtigsten Richtliniensätze, die für die Schaffung einer sicheren und produktiven Lernerfahrung relevant sind, schnell und einfach anzuwenden.

Mit Richtlinien in Teams können Sie steuern, wie sich Teams in Ihrer Umgebung Verhalten und welche Features für die Benutzer verfügbar sind. So gibt es beispielsweise Anruf Richtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen, und jeder Richtlinienbereich kann angepasst werden, um die Anforderungen Ihrer Organisation zu erfüllen.

Um eine sichere und fokussierte Lernumgebung zu erhalten, ist es wichtig, Richtlinien festzulegen, um zu steuern, was Schüler in Teams tun können. Sie können beispielsweise Richtlinien verwenden, um zu steuern, wer private Chats und private Anrufe verwenden kann, wer Besprechungen planen kann und welche Inhaltstypen freigegeben werden können. Sie können auch Richtlinien verwenden, um Teams-Features zu aktivieren, die die Lernerfahrung bereichern.

Richtlinien müssen sowohl Schülern als auch Pädagogen angepasst werden, damit die Lernerfahrung sicher bleibt. Richtlinien für Kursteilnehmer müssen restriktiver sein, um das Risiko für den Empfang unangemessener Zugriffsebenen zu verringern. Lehrkräfte und Mitarbeiter benötigen eine separate Gruppe von Richtlinien, die flexibler sein können, damit Sie erfolgreich sind. So können Sie beispielsweise Lehrern erlauben, Besprechungen zu planen und die Schüler daran zu hindern.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot des Assistenten":::

In diesem Artikel erfahren Sie, wie Sie den Assistenten ausführen.

> [!IMPORTANT]
> Die vom Assistenten angewendeten Richtlinien erfüllen die Anforderungen der meisten Teams für Education-Kunden. Der Assistent passt die globale (org-weite Standard Definition) einer zentralen Gruppe von Richtlinien mit Einstellungen an, die wir für die Sicherheit von Kursteilnehmern empfehlen, und wendet diese auf Schüler an. Der Assistent erstellt und ordnet auch eine Reihe benutzerdefinierter Richtlinien für Lehrkräfte und Mitarbeiter zu. Die meisten Teams für Education-Kunden müssen nach der Ausführung dieses Assistenten keine weiteren Richtlinien Zuordnungsmethoden verwenden. Verwenden Sie andere Richtlinien Zuweisungsmethoden *nur* , wenn Sie Richtlinien für Schüler, Pädagogen und Mitarbeiter manuell erstellen und verwalten möchten.

## <a name="teams-for-education-policy-wizard"></a>Assistent für "Teams für Bildungsrichtlinien"

<a name="polwiz_intro"> </a>

Der Assistent wendet eine Reihe von grundlegenden Richtlinien Definitionen auf Schüler und einen separaten Satz von zentralen Richtlinien Definitionen für Lehrkräfte und Mitarbeiter an, die jeweils den jeweiligen Einstellungen entsprechen. Hier erfahren Sie, was passiert, wenn Sie den Assistenten ausführen.

Der Assistent richtet Richtlinien ein, die auf dem Typ der Bildungseinrichtung basieren (**Primar-, Sekundar** -oder **Hochschulbildung**). Sie wählen Ihren Institutions aus, und der Assistent führt die folgenden Schritte aus:

- **Kursteilnehmer**: der Assistent passt die globale (organisationsweite Standard-) Richtliniendefinition für jeden vom Assistenten behandelten Richtlinienbereich mit neuen Standardeinstellungen an, die geeignet sind, um Ihre Schüler zu schützen. Dadurch wird sichergestellt, dass Ihre aktuellen Kursteilnehmer und alle neuen Kursteilnehmer die restriktivsten Richtliniensätze erhalten.
- **Lehrkräfte und Mitarbeiter**: der Assistent erstellt eine Reihe von benutzerdefinierten Richtlinien Definitionen für jeden vom Assistenten behandelten Richtlinienbereich mit Einstellungen, die auf die Anforderungen von Pädagogen und Mitarbeitern zugeschnitten sind. Anschließend werden die Richtlinien Definitionen der Gruppe von Pädagogen und Mitarbeitern zugewiesen, die Sie auswählen. Auf diese Weise erhalten Ihre Pädagogen und Mitarbeiter eine freizügigere Gruppe von Richtlinien, damit Sie erfolgreich sein können.

Sie müssen den Assistenten nur einmal ausführen. Neue Kursteilnehmer erhalten automatisch die globalen (organisationsweiten Standardrichtlinien Definitionen), die vom Assistenten angewendet werden, und neue Mitarbeiter, die Sie der ausgewählten Gruppe hinzufügen, werden automatisch den benutzerdefinierten Richtlinien zugewiesen.

> [!NOTE]
> Eine detaillierte Liste der vom Assistenten angewendeten Richtlinien Definitionen finden Sie unter [vom Assistenten angewendete Richtlinien](#policies-applied-by-the-wizard) .

Fangen wir jetzt an!

## <a name="run-the-wizard"></a>Ausführen des Assistenten

<a name="polwiz_run"> </a>

Führen Sie die folgenden Schritte aus, um den Assistenten auszuführen. 

1. Wenn Sie in Microsoft Teams neu sind, wird der Assistent automatisch gestartet. Andernfalls können Sie den Assistenten jederzeit vom Dashboard aus starten. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams admin Centers zu **Dashboard**, und wählen Sie dann in der Kachel **einfache Richtlinie für eine sichere Lernumgebung** die Option **schnell Setup** aus.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Assistenten im Dashboard":::

2. Wählen Sie den Typ Ihrer Bildungseinrichtung (**Primar-oder Sekundarbereich** oder **Hochschulausbildung**) aus, und klicken Sie dann auf **weiter**.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot der Seite im Assistenten zur Auswahl des institutions Typs":::

3. Suchen Sie eine Gruppe, die ihre Pädagogen und Mitarbeiter enthält, und wählen Sie Sie aus, und klicken Sie dann auf **weiter**. Wenn Sie noch keine Gruppen für Ihre Erzieher und Mitarbeiter eingerichtet haben, [Erstellen Sie eine Gruppe](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups), und führen Sie den Assistenten dann erneut aus. <br/><br/>Derzeit können Sie nur eine Gruppe auswählen. Für Lehrkräfte und Mitarbeiter in der ausgewählten Gruppe wird eine Gruppe [benutzerdefinierter Richtlinien](#policies-applied-by-the-wizard) zugewiesen, die auf Ihre Anforderungen zugeschnitten sind. Beachten Sie, dass dieser Satz von Richtlinien von den für die Kursteilnehmer angewendeten Richtlinien getrennt ist.

    :::image type="content" source="media/easy-policy-setup-group.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen der Gruppe "Erzieher und Mitarbeiter"":::

4. Überprüfen Sie Ihre Auswahl.

    :::image type="content" source="media/easy-policy-setup-review-selections.png" alt-text="Screenshot der Seite im Assistenten zum Überprüfen der Auswahl":::

5. Wählen Sie über **nehmen** aus, um Ihre Änderungen zu übernehmen. Dieser Vorgang kann einige Minuten dauern.<br/><br/>Die globalen Standardrichtlinien Definitionen (org-Wide) werden sofort auf Schüler angewendet. Für Ihre Pädagogen und Mitarbeiter kann es bis zu 48 Stunden dauern, bis die benutzerdefinierten Richtlinien je nach Größe der Gruppe jedem Mitglied der ausgewählten Gruppe zugewiesen werden. Dies geschieht im Hintergrund, nachdem Sie diesen Schritt erfolgreich abgeschlossen haben.
6. Sie sind auf dem Weg, aber Sie sind noch nicht fertig! Es gibt ein paar weitere Dinge zu bedenken. Lesen Sie als nächstes die Schritte im Abschnitt [Was ist nach dem Ausführen des Assistenten](#what-to-do-after-running-the-wizard) in diesem Artikel.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot der Seite im Assistenten für die nächsten Schritte":::

## <a name="what-to-do-after-running-the-wizard"></a>Vorgehensweise nach dem Ausführen des Assistenten

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Schritt 1: Entfernen vorhandener Richtlinienzuweisungen, die mit den vom Assistenten angewendeten Richtlinien in Konflikt stehen

> [!IMPORTANT]
> **Führen Sie diesen Schritt nur aus, wenn Sie den Kursteilnehmern oder Lehrkräften und Mitarbeitern vorhandene Richtlinien zugewiesen haben, *bevor* Sie den Assistenten ausführen**. Wenn Sie neu in Teams sind und keine anderen Richtlinien als die vom Assistenten erstellten Richtlinien besitzen, überspringen Sie diese, und wechseln Sie zu Schritt 2.

In Teams kann eine Richtlinie für einen bestimmten Richtlinienbereich auf folgende Weise auf einen Benutzer angewendet werden:

- Direkte Zuweisung an den Benutzer
- Zuordnung zu einer Gruppe, der der Benutzer angehört
- Wenn dem Benutzer nicht direkt eine Richtlinie zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer automatisch die globale (organisationsweite Standardrichtlinie).

Wenn mehr als eine dieser Richtlinienzuweisungen für einen Benutzer vorhanden ist, ermittelt Teams anhand der folgenden Reihenfolge, welche Richtlinienzuweisung wirksam wird. Weitere Informationen finden Sie unter [welche Richtlinie hat Vorrang?](assign-policies.md#which-policy-takes-precedence) und [Vorrangregeln](assign-policies.md#precedence-rules).

|Richtlinienzuweisungen eines Benutzers|Richtlinie, die wirksam wird |
|---------|---------|
|Der Gruppe zugewiesene Richtlinie: Nein<br/>Direkt dem Benutzer zugewiesene Richtlinie: Nein    |Globale (organisationsweite) Standardrichtlinie      |
|Der Gruppe zugewiesene Richtlinie: Nein<br/>Direkt dem Benutzer zugewiesene Richtlinie: Ja    |Direkt dem Benutzer zugewiesene Richtlinie         |
|Der Gruppe zugewiesene Richtlinie: Ja<br/>Direkt dem Benutzer zugewiesene Richtlinie: Ja     |Direkt dem Benutzer zugewiesene Richtlinie         |
|Der Gruppe zugewiesene Richtlinie: Ja<br/>Direkt dem Benutzer zugewiesene Richtlinie: Nein     |Der Gruppe zugewiesene Richtlinie<br/><br/>Wenn der Benutzer ein Mitglied mehrerer Gruppen ist und jeder Gruppe eine Richtlinie desselben Richtlinien Bereichs zugewiesen ist, wird die Richtlinie mit der höchsten [Gruppen Zuordnungs Rangfolge](assign-policies.md#group-assignment-ranking) wirksam.       |

Aufgrund dieser Reihenfolge werden die vom Assistenten erstellten Richtlinien nicht wirksam, wenn ein Benutzer über vorhandene direkte Zuordnungen oder Gruppenzuweisungen verfügt. Das bedeutet, dass Sie die vorhandenen Richtlinienzuweisungen vom Benutzer entfernen müssen, damit die vom Assistenten angewendete Richtlinie wirksam wird.

Gehen Sie für jeden [vom Assistenten angewendeten Richtlinienbereich](#policies-applied-by-the-wizard)wie folgt vor:

- Entfernen Sie alle vorhandenen direkten Zuordnungen und Gruppenaufgaben von ihren Kursteilnehmern, damit die vom Assistenten angewendete globale Standardrichtlinien Definition (org-Wide) wirksam wird.
- Entfernen Sie alle in Konflikt stehenden direkten Aufgaben für Ihre Pädagogen und Mitarbeiter, damit die vom Assistenten erstellte benutzerdefinierte Richtliniendefinition wirksam wird. Verwenden Sie die obige Tabelle, um die für Sie geltenden Szenarien zu ermitteln. <br/><br/>Beachten Sie, dass der Assistent Ihren Pädagogen und ihrer Mitarbeitergruppe Richtlinien mithilfe einer [Gruppen Zuordnungs Rangfolge](assign-policies.md#group-assignment-ranking) von 1 zuordnet, bei der es sich um die höchste Rangfolge handelt. Wenn für Ihre Pädagogen und ihre Mitarbeitergruppe eine Richtlinie desselben Richtlinien Bereichs zugewiesen ist, wird die vorhandene Richtlinie in eine niedrigere Rangfolge verschoben, und die vom Assistenten zugewiesene Richtlinie wird wirksam.

[Weitere](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) Informationen zum Entfernen von Richtlinien, die Benutzern direkt zugewiesen werden.

Sie haben beispielsweise Pädagogen eine Besprechungsrichtlinie direkt zugewiesen, und ihre Schüler haben die globale (org-Wide Standard)-Besprechungsrichtlinie. Entfernen Sie in diesem Szenario die Besprechungsrichtlinie, die Sie den Pädagogen direkt zugewiesen haben, damit die benutzerdefinierte Richtliniendefinition für die vom Assistenten erstellte Besprechungsrichtlinie wirksam wird. Sie müssen mit der vorhandenen globalen (org-Wide Standard)-Besprechungsrichtlinie für Schüler nichts zu tun haben, da keine anderen Besprechungsrichtlinien damit in Konflikt stehen.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Schritt 2: Überprüfen Sie, ob zusätzliche Maßnahmen für die Sicherheit von Kursteilnehmern ergriffen werden können.

Der Assistent passt [Diese Richtlinien](#policies-applied-by-the-wizard)automatisch an und wendet diese an. Es gibt nur wenige zusätzliche Maßnahmen, die Sie möglicherweise auf der Grundlage der Anforderungen Ihrer Institution treffen sollten, um sicher zu bleiben.

Weitere Sicherheitsempfehlungen finden Sie unter [sicher halten von Kursteilnehmern während der Verwendung von Teams für Fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA) .

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Schritt 3: Überprüfen des Nachrichten Centers auf Richtlinienupdates

Zurzeit wendet der Assistent die empfohlenen Richtlinien an, wenn Sie ihn ausführen. Es ist wichtig zu wissen, dass die globalen (org-weiten Standardeinstellungen) für die Sicherheit von Kursteilnehmern nicht automatisch vom Assistenten hinzugefügt werden, wenn neue Richtlinien in Teams zur Verfügung stehen. Diese Funktion steht in einer zukünftigen Version zur Verfügung.

Bis diese Funktion verfügbar ist, überprüfen Sie das [Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (im Microsoft 365 Admin Center) häufig, um über neue Richtlinien und Richtlinieneinstellungen in Teams auf dem neuesten Stand zu bleiben. Wenn neue Funktionen zur Verfügung stehen, müssen Sie möglicherweise Ihre Richtlinien manuell aktualisieren, damit Ihre Lernumgebung sicher bleibt.

## <a name="make-changes-in-the-wizard"></a>Vornehmen von Änderungen im Assistenten

<a name="polwiz_change"> </a>

Wenn Sie Änderungen vornehmen müssen, nachdem Sie den Assistenten ausgeführt haben, können Sie ihn erneut ausführen und Ihre Auswahl ändern.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams admin Centers zu **Dashboard**, und wählen Sie dann in der Kachel **einfache Richtlinie für eine sichere Lernumgebung** die Option **ändern** aus.
2. Fahren Sie von hier aus auf jeder Seite des Assistenten fort, um Ihre Änderungen vorzunehmen. Sie können Ihren Institutions-Typ, die Gruppe von Pädagogen und Mitarbeitern, denen Sie Richtlinien zuweisen möchten, oder beides ändern.

In der folgenden Tabelle wird zusammengefasst, was passiert, wenn Sie eine Änderung im Assistenten vornehmen.

|Art der Änderung  |Richtlinien Verhalten  |
|---------|---------|
|Ändern des Typs der Bildungseinrichtung und der Gruppe "Pädagogen und Mitarbeiter"    |<ul><li>**Kursteilnehmer**: die globalen (organisationsweiten Standardrichtlinien Definitionen), die auf dem neuen Bildungs Institutions basieren, werden auf Schüler angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: eine Gruppe von benutzerdefinierten Richtlinien Definitionen, die auf dem neuen Bildungs Institutions basieren, wird erstellt und der neuen Gruppe "Erzieher und Mitarbeiter" zugewiesen. Die vorherigen benutzerdefinierten Richtlinien Definitionen werden aus der vorherigen Gruppe "Pädagogen und Mitarbeiter" entfernt.</li></ul>    |
|Nur den Typ der Bildungseinrichtung ändern    |<ul><li>**Kursteilnehmer**: die globalen (organisationsweiten Standardrichtlinien Definitionen), die auf dem neuen Bildungs Institutions basieren, werden auf Schüler angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: eine Gruppe von benutzerdefinierten Richtlinien Definitionen, die auf dem neuen Bildungs Institutions basieren, wird erstellt und der Gruppe "Pädagogen und Mitarbeiter" zugewiesen. Die benutzerdefinierten Richtlinien Definitionen, die für den vorherigen Bildungseinrichtung-Typ erstellt wurden, werden aus der Gruppe "Pädagogen und Mitarbeiter" entfernt.</li></ul>         |
|Nur die Gruppe "Pädagogen und Mitarbeiter" ändern   |<ul><li>**Kursteilnehmer**: keine Änderung an den globalen (org-weiten Standardrichtlinien Definitionen), die auf Schüler angewendet werden.</li><li>**Lehrkräfte und Mitarbeiter**: die benutzerdefinierten Richtlinien Definitionen werden den neuen Pädagogen und der Gruppe "Mitarbeiter" zugewiesen und aus der vorherigen Gruppe "Pädagogen und Mitarbeiter" entfernt.</li></ul>         |

## <a name="policies-applied-by-the-wizard"></a>Vom Assistenten angewendete Richtlinien

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Richtlinienbereiche

Hier sind die Richtlinienbereiche und die entsprechenden Richtliniennamen, die vom Assistenten behandelt werden. Wenn Sie diese Richtlinien finden möchten, wechseln Sie zum Microsoft Teams Admin Center, und wechseln Sie dann in der linken Navigationsleiste zu jeder Seite des Richtlinien Bereichs.

#### <a name="students"></a>[**Kursteilnehmer**](#tab/students/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Hochschul Richtlinie  |
|---------|---------|---------|
|Teams-Richtlinie    |Global (organisationsweit Standard)         |Global (organisationsweit Standard)           |
|Besprechungsrichtlinie    |Global (organisationsweit Standard)           |Global (organisationsweit Standard)           |
|Richtlinie für Liveereignisse     |Global (organisationsweit Standard)          |  Global (organisationsweit Standard)          |
|App-Setup Richtlinie     |Global (organisationsweit Standard)           |Global (organisationsweit Standard)           |
|App-Berechtigungsrichtlinie    |Global (organisationsweit Standard)           |Global (organisationsweit Standard)           |
|Messagingrichtlinie     |Global (organisationsweit Standard)           |Global (organisationsweit Standard)           |
|Anrufrichtlinie    |Global (organisationsweit Standard)           |Global (organisationsweit Standard)           |

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educators/)

|Richtlinienbereich  |Name der primären oder sekundären Richtlinie |Name der Hochschul Richtlinie |
|---------|---------|---------|
|Teams-Richtlinie   |Primäre oder sekundäre Pädagogen und Mitarbeiter Teams         |Lehrkräfte und Mitarbeiter Teams für Hochschulbildung         |
|Besprechungsrichtlinie    |Primäre oder sekundäre Pädagogen und Personalbesprechungen         |Hochschullehrer und Mitarbeiter – Besprechung         |
|Richtlinie für Liveereignisse   | Primäre oder sekundäre Pädagogen und Mitarbeiter – Live-Events         |Lehrkräfte und Mitarbeiter in der Hochschulbildung – Live-Events         |
|Messagingrichtlinie    |Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Nachrichten         | Lehrkräfte und Mitarbeiter im Hochschulbereich – Nachrichten         |
|Anrufrichtlinie    |Primäre oder sekundäre Pädagogen und Mitarbeitergespräche         |Hochschullehrer und Mitarbeitergespräche         |

* * *

### <a name="policy-settings"></a>Richtlinieneinstellungen

Nachfolgend finden Sie eine Zusammenfassung der Einstellungen, die vom Assistenten für die einzelnen Richtlinienbereiche angewendet wurden.

#### <a name="students"></a>[**Kursteilnehmer**](#tab/student-settings/)

Nachfolgend finden Sie eine Liste der globalen Standardrichtlinien Definitionen, die vom Assistenten angepasst und auf Schüler angewendet werden.

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder sekundär |Hochschulbildung |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Aus       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Sofortbesprechung in Kanälen zulassen         |Aus      |Ein|
|  |        |Zulassen des Outlook-Add-ins         |Aus       |Ein|
|  |        |Planen der Kanal Besprechung zulassen        |Aus      |Ein|
|  |        |Planen privater Besprechungen zulassen       |Aus      |Ein|
|  |Audio & Video        |Transkription zulassen        |Ein       |Ein|
|  |        |Cloud-Aufzeichnung zulassen         |Aus      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audiosignal aktiviert        |Ausgehendes und eingehendes Audiosignal aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video zulassen         |Ein         |Ein|
|  |       |NDI-Streaming zulassen         |Aus         |Aus|
|  |       |Medien-Bitrate (KBS)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmübertragungsmodus         |Ganzer Bildschirm         |Ganzer Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |PowerPoint-Freigabe zulassen        |Ein         |Ein|
|  |       |Whiteboard zulassen         |Ein         |Ein|
|  |       |Zulassen von freigegebenen Notizen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Zulassen, dass anonyme Personen eine Besprechung starten       |Aus         |Ein|
|  |       |Rollen mit Referenten rechten in Besprechungen        |EveryoneUserOverride         |EveryoneUserOverride|
|  |       |Automatisches zulassen von Personen        |EveryoneInCompany|EveryoneInCompany|
|  |       |Zulassen, dass Einwahlbenutzer die Lobby umgehen können        |Aus         |Aus|
|  |       |"Besprechung jetzt in privaten Besprechungen zulassen"        |Aus         |Ein|
|  |       |Aktivieren von Live Beschriftungen       |Deaktiviert, aber der Benutzer kann außer Kraft gesetzt werden         |Deaktiviert, aber der Benutzer kann außer Kraft gesetzt werden|
|  |       |Chat in Besprechungen zulassen         |Ein         |Ein|
|  |Video Filtermodus       |VideoFiltersMode         |BlurandDefaultBackgrounds|Allfilters|
|  |Besprechungsanwesenheitsbericht       |AllowEngagementReport         |Aus         |Ein|
|Richtlinie für Liveereignisse  |       |Planung erlauben         |Aus         |Aus|
|  |       |Transkription für Teilnehmer zulassen          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Personen, die ein Ereignis aufzeichnen können         |Immer         |Immer|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Aus|Ein|
|  |       |Gesendete Nachrichten löschen         |Aus         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Aus         |Ein|
|  |       |Lesebestätigungen         |Benutzer gesteuert         |Benutzer gesteuert|
|  |       |Chat         |Aus         |Ein|
|  |       |Giphys in Unterhaltungen verwenden         |Aus         |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Verwenden von Memen in Konversationen         |Ein         |Ein|
|  |       |Verwenden von Aufklebern in Konversationen         |Ein         |Ein|
|  |       |URL-Vorschau zulassen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Plastischen Reader zum Anzeigen von Nachrichten zulassen        |Ein      |Ein|
|  |       |Senden dringender Nachrichten mithilfe von Prioritäts Benachrichtigungen  |Aus         |Ein|
|  |       |Erstellen von Sprachnachrichten         |Erlaubt in Chats und Kanälen         |Erlaubt in Chats und Kanälen|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppen-Chats         |Aus         |Ein|
|  |       |Vorgeschlagene Antworten         |Ein         |Ein|
|App-Berechtigungsrichtlinie  |       |Microsoft-apps         |Blockieren bestimmter apps und zulassen, dass alle anderen > Walkie-Talkie blockiert werden         |Alle apps zulassen|
|  |       |Drittanbieter-apps         |Alle apps zulassen         |Alle apps zulassen|
|  |       |Benutzerdefinierte apps         |Alle apps zulassen         |Alle apps zulassen|
|App-Setup Richtlinie  |           |Hochladen benutzerdefinierter apps           |Aus         |Aus|
|  |       |Benutzer anheften zulassen |Ein         |Ein|
|  |       |Installierte apps         |Keine         |Keine|
|  |       |Angeheftete apps         |Aktivität, Kalender, Teams         |Aktivitäten, Chats, Teams, Kalender, Anrufe, Datei
|Anrufrichtlinie  |       |Private Anrufe führen         |Aus        |Ein|
|  |       |Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Aus         |Ein|
|  |       |Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern         |Aus         |Ein|
|  |       |Voicemail steht zum Weiterleiten von eingehenden Anrufen zur Verfügung         |Benutzer gesteuert         |Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen weitergeleitet werden         |Aus        |Ein|
|  |       |Zulassen der Delegierung für eingehende und ausgehende Anrufe         |Aus         |Ein|
|  |       |Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |Busy on Busy steht während eines Anrufs zur Verfügung         |Aus         |Aus|
|  |       |Zulassen von webpstn-anrufen         |Aus         |Ein|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educator-settings/)

Nachfolgend finden Sie eine Liste der benutzerdefinierten Richtlinien Definitionen, die den Pädagogen und der Mitarbeitergruppe zugewiesen sind, die Sie im Assistenten auswählen.  

|Richtlinienbereich |Unterbereich  |Richtlinieneinstellung  |Primär oder sekundär |Hochschulbildung |
|---------|---------|---------|---------|---------|
|Teams-Richtlinie   |         |Erstellen privater Kanäle         |Ein       |Ein|
|Besprechungsrichtlinie    |Allgemein         |Sofortbesprechung in Kanälen zulassen         |Ein      |Ein|
|  |        |Zulassen des Outlook-Add-ins         |Ein       |Ein|
|  |        |Planen der Kanal Besprechung zulassen        |Ein      |Ein|
|  |        |Planen privater Besprechungen zulassen       |Ein      |Ein|
|  |Audio & Video        |Transkription zulassen        |Ein       |Ein|
|  |        |Cloud-Aufzeichnung zulassen         |Ein      |Ein|
|  |        |Modus für IP-Audio       |Ausgehendes und eingehendes Audiosignal aktiviert        |Ausgehendes und eingehendes Audiosignal aktiviert|
|  |        |Modus für IP-Video         |Ausgehendes und eingehendes Video aktiviert     |Ausgehendes und eingehendes Video aktiviert|
|  |       |IP-Video zulassen         |Ein         |Ein|
|  |       |NDI-Streaming zulassen         |Aus         |Aus|
|  |       |Medien-Bitrate (KBS)         |50.000         |50.000|
|  |Inhaltsfreigabe       |Bildschirmübertragungsmodus         |Ganzer Bildschirm         |Ganzer Bildschirm|
|  |       |Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |Zulassen, dass ein externer Teilnehmer die Steuerung erteilt oder anfordert         |Ein         |Ein|
|  |       |PowerPoint-Freigabe zulassen        |Ein         |Ein|
|  |       |Whiteboard zulassen         |Ein         |Ein|
|  |       |Zulassen von freigegebenen Notizen         |Ein        |Ein|
|  |Teilnehmer & Gäste       |Zulassen, dass anonyme Personen eine Besprechung starten       |Ein        |Ein|
|  |       |Rollen mit Referenten rechten in Besprechungen        |OrganizerOnlyUserOverride         |OrganizerOnlyUserOverride|
|  |       |Automatisches zulassen von Personen        |Organisatornur|Organisatornur|
|  |       |Zulassen, dass Einwahlbenutzer die Lobby umgehen können        |Aus         |Aus|
|  |       |"Besprechung jetzt in privaten Besprechungen zulassen"        |Ein         |Ein|
|  |       |Aktivieren von Live Beschriftungen       |Deaktiviert, aber der Benutzer kann außer Kraft gesetzt werden         |Deaktiviert, aber der Benutzer kann außer Kraft gesetzt werden|
|  |       |Chat in Besprechungen zulassen         |Ein         |Ein|
|  |Video Filtermodus       |VideoFiltersMode         |Allfilters|Allfilters|
|  |Besprechungsanwesenheitsbericht       |AllowEngagementReport         |Ein         |Ein|
|Richtlinie für Liveereignisse  |       |Planung erlauben         |Ein         |Ein|
|  |       |Transkription für Teilnehmer zulassen          |Ein       |Ein|
|  |       |Wer an geplanten Liveereignissen teilnehmen kann        |Jeder in der Organisation        |Jeder in der Organisation|
|  |       |Personen, die ein Ereignis aufzeichnen können         |Immer aufzeichnen         |Immer aufzeichnen|
|Messagingrichtlinie  |       |Besitzer können gesendete Nachrichten löschen         |Ein|Ein|
|  |       |Gesendete Nachrichten löschen         |Ein         |Ein|
|  |       |Gesendete Nachrichten bearbeiten         |Ein         |Ein|
|  |       |Lesebestätigungen         |Benutzer gesteuert         |Benutzer gesteuert|
|  |       |Chat         |Ein         |Ein
|  |       |Giphys in Unterhaltungen verwenden         |Ein        |Ein|
|  |       |Giphy-Inhaltsklassifikation         |Streng        |Streng|
|  |       |Verwenden von Memen in Konversationen         |Ein         |Ein|
|  |       |Verwenden von Aufklebern in Konversationen         |Ein         |Ein|
|  |       |URL-Vorschau zulassen        |Ein         |Ein|
|  |       |Übersetzen von Nachrichten         |Ein         |Ein|
|  |       |Plastischen Reader zum Anzeigen von Nachrichten zulassen        |Ein      |Ein|
|  |       |Senden dringender Nachrichten mithilfe von Prioritäts Benachrichtigungen  |Ein         |Ein|
|  |       |Erstellen von Sprachnachrichten         |Erlaubt in Chats und Kanälen         |Erlaubt in Chats und Kanälen|
|  |       |Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen     |Aktiviert         |Aktiviert|
|  |       |Entfernen von Benutzern aus Gruppen-Chats         |Ein        |Ein|
|  |       |Vorgeschlagene Antworten         |Ein         |Ein|
|Anrufrichtlinie  |       |Private Anrufe führen         |Ein       |Ein|
|  |       |Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation         |Ein        |Ein|
|  |       |Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern         |Ein        |Ein|
|  |       |Voicemail steht zum Weiterleiten von eingehenden Anrufen zur Verfügung         |Benutzer gesteuert         |Benutzer gesteuert|
|  |       |Eingehende Anrufe können an Anrufgruppen weitergeleitet werden         |Ein        |Ein|
|  |       |Zulassen der Delegierung für eingehende und ausgehende Anrufe         |Ein         |Ein|
|  |       |Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN        |Aus         |Aus|
|  |       |Busy on Busy steht während eines Anrufs zur Verfügung         |Aus         |Aus|
|  |       |Zulassen von webpstn-anrufen         |Ein      |Ein|

* * *

## <a name="related-topics"></a>Verwandte Themen

- [Teamrichtlinien und Richtlinien Pakete für Bildungseinrichtungen](policy-packages-edu.md)
- [Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule](batch-group-policy-assignment-edu.md)
- [Sicher halten von Kursteilnehmern bei der Verwendung von Teams für Fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
