---
title: Teams für Education Richtlinien-Assistent zum einfachen Anwenden von Richtlinien für sicheres Lernen
author: serdars
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie den Richtlinien-Assistenten Teams für Education verwenden, um Richtlinien für Schüler/Studenten und Lehrkräfte einfach anzuwenden, um Ihre Lernumgebung zu schützen.
f1keywords: ''
ms.openlocfilehash: 245739f06d86459f119d9f5d0a37e67ac4098953
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675917"
---
# <a name="use-the-teams-for-education-policy-wizard-to-easily-apply-policies-for-a-safe-learning-environment"></a>Verwenden des Teams für Education Richtlinien-Assistenten zum einfachen Anwenden von Richtlinien für eine sichere Lernumgebung

## <a name="overview"></a>Übersicht

Der Microsoft Teams für Education Richtlinien-Assistent vereinfacht das Verwalten von Richtlinien für Ihre Schüler/Studenten und Lehrkräfte. Verwenden Sie sie, um die wichtigsten Richtlinien, die für die Erstellung einer sicheren und produktiven Lernerfahrung relevant sind, einfach und schnell anzuwenden.

Mithilfe von Richtlinien in Teams können Sie steuern, wie sich Teams in Ihrer Umgebung verhalten und welche Features benutzern zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen, und jeder Richtlinienbereich kann an die Anforderungen Ihrer Organisation angepasst werden.

Um eine sichere und fokussierte Lernumgebung zu erhalten, ist es wichtig, Richtlinien festzulegen, um zu steuern, was Schüler in Teams tun können. Mithilfe von Richtlinien können Sie beispielsweise steuern, wer privaten Chat und private Anrufe verwenden kann, wer Besprechungen planen kann und welche Inhaltstypen freigegeben werden können. Sie können richtlinien auch verwenden, um Teams Features zu aktivieren, die die Lernerfahrung bereichern.

Die Richtlinien müssen sowohl für Schüler/Studenten als auch für Lehrkräfte angepasst werden, um die Lernerfahrung zu schützen. Die Richtlinien für Kursteilnehmer müssen restriktiver sein, um ihr Risiko zu verringern, unangemessene Zugriffsebenen zu erhalten. Lehrkräfte und Mitarbeiter benötigen einen separaten Satz von Richtlinien, die eingeschränkter sein können, damit sie erfolgreich sein können. So können Lehrkräfte beispielsweise Besprechungen planen und die Kursteilnehmer daran hindern.

:::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot des Assistenten.":::

In diesem Artikel erfahren Sie, wie Sie den Assistenten ausführen.

> [!IMPORTANT]
> Die vom Assistenten angewendeten Richtlinien erfüllen die Anforderungen der Meisten Teams für Education Kunden. Der Assistent passt die globale Definition (organisationsweite Standardeinstellung) eines zentralen Richtliniensatzes mit Einstellungen an, die wir für die Sicherheit von Schülern/Studenten empfehlen, und wendet sie auf Kursteilnehmer an. Der Assistent erstellt und weist lehrkräften und Mitarbeitern auch eine Reihe von benutzerdefinierten Richtlinien zu. Die meisten Teams für Education Kunden müssen nach dem Ausführen dieses Assistenten keine anderen Richtlinienzuweisungsmethoden verwenden. Verwenden Sie andere Richtlinienzuweisungsmethoden *nur* , wenn Sie Richtlinien für Ihre Kursteilnehmer, Lehrkräfte und Mitarbeiter manuell erstellen und verwalten möchten.

## <a name="teams-for-education-policy-wizard"></a>Teams für Education-Richtlinien-Assistent

<a name="polwiz_intro"> </a>

Der Assistent wendet eine Reihe von grundlegenden Richtliniendefinitionen auf Schüler und Studenten und einen separaten Satz von Grundlegenden Richtliniendefinitionen auf Lehrkräfte und Mitarbeiter an, mit Einstellungen, die für jeden geeignet sind. Dies geschieht, wenn Sie den Assistenten ausführen.

Der Assistent richtet Richtlinien basierend auf dem Bildungseinrichtungstyp (**Primar-, Sekundar****- oder Hochschulbildung**) ein. Sie wählen Ihren Einrichtungstyp aus, und der Assistent führt folgende Aktionen aus:

- **Kursteilnehmer**: Der Assistent passt die globale Richtliniendefinition (organisationsweite Standardrichtlinie) für jeden vom Assistenten abgedeckten Richtlinienbereich mit neuen Standardeinstellungen an, die geeignet sind, ihre Schüler zu schützen. Dadurch wird sichergestellt, dass Ihre aktuellen Schüler und alle neuen Kursteilnehmer die restriktivsten Richtlinien erhalten.
- **Lehrkräfte und Mitarbeiter**: Der Assistent erstellt eine Reihe von benutzerdefinierten Richtliniendefinitionen für jeden Richtlinienbereich, der vom Assistenten abgedeckt wird, mit Einstellungen, die auf die Anforderungen von Lehrkräften und Mitarbeitern zugeschnitten sind. Anschließend werden die Richtliniendefinitionen der von Ihnen ausgewählten Gruppe von Lehrkräften und Mitarbeitern zugewiesen. Auf diese Weise erhalten Ihre Lehrkräfte und Mitarbeiter einen eingeschränkteren Satz von Richtlinien, damit sie erfolgreich sein können.

Sie müssen den Assistenten nur einmal ausführen. Neue Kursteilnehmer erhalten automatisch die vom Assistenten angewendeten globalen (organisationsweiten Standard)-Richtliniendefinitionen, und neuen Mitarbeitern, die Sie der ausgewählten Gruppe hinzufügen, werden automatisch die benutzerdefinierten Richtlinien zugewiesen.

Außerdem wird bei jedem Hinzufügen eines neuen Features zu Teams der entsprechende EDU-relevante Standardwert der Richtlinie für dieses Feature automatisch dem globalen (organisationsweiten Standard) hinzugefügt, ohne dass ein Administratoreingriff erforderlich ist. Dies trägt dazu bei, sicherzustellen, dass die richtigen Richtlinien vorhanden sind, um die Schüler sicher und engagiert zu halten.

> [!NOTE]
> Eine detaillierte Liste [der vom Assistenten angewendeten](#policies-applied-by-the-wizard) Richtliniendefinitionen finden Sie unter Richtlinien, die vom Assistenten angewendet wurden.

Jetzt fangen wir an!

## <a name="run-the-wizard"></a>Ausführen des Assistenten

<a name="polwiz_run"> </a>

Führen Sie die folgenden Schritte aus, um den Assistenten auszuführen.

1. Wenn Sie mit Teams noch nicht fertig sind, wird der Assistent automatisch gestartet. Andernfalls können Sie den Assistenten jederzeit über das Dashboard starten. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **"Start**", und wählen Sie dann in der Kachel "**Einfache Richtlinieneinrichtung für eine sichere Lernumgebung**" die Option **"Schnelleinrichtung"** aus.

    :::image type="content" source="media/easy-policy-setup-quick-setup.png" alt-text="Screenshot des Assistenten im Dashboard.":::

2. Wählen Sie den Typ Ihrer Bildungseinrichtung (**Primar- oder Sekundar****- oder Hochschulbildung**) und dann **"Weiter**" aus.

    :::image type="content" source="media/easy-policy-setup-institution-type.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen des Einrichtungstyps.":::

3. Suchen Sie nach Gruppen, die Ihre Lehrkräfte und Mitarbeiter enthalten, und wählen Sie dann **"Weiter**" aus. Wenn Sie noch keine Gruppen für Ihre Lehrkräfte und Mitarbeiter eingerichtet haben, [erstellen Sie eine Gruppe](/microsoft-365/admin/create-groups/create-groups), und führen Sie dann den Assistenten erneut aus. <br/><br/>Sie können bis zu drei Gruppen auswählen. Lehrkräften und Mitarbeitern in den von Ihnen ausgewählten Gruppen wird [eine Reihe von benutzerdefinierten Richtlinien](#policies-applied-by-the-wizard) zugewiesen, die auf ihre Anforderungen zugeschnitten sind. Denken Sie daran, dass dieser Richtliniensatz von den Richtlinien getrennt ist, die auf Kursteilnehmer angewendet werden.

    :::image type="content" source="media/edu-policy-wizard-add-3-groups.png" alt-text="Screenshot der Seite im Assistenten zum Auswählen von Lehrkräften und Mitarbeitergruppen.":::

4. Überprüfen Sie Ihre Auswahl.

    :::image type="content" source="media/edu-policy-wizard-3-groups-review.png" alt-text="Screenshot der Seite im Assistenten zum Überprüfen der Auswahl.":::

5. Wählen Sie **"Übernehmen"** aus, um Ihre Änderungen anzuwenden. Dies kann einige Minuten dauern.<br/><br/>Die globalen (organisationsweiten Standard)-Richtliniendefinitionen werden sofort auf Schüler/Studenten angewendet. Für Ihre Lehrkräfte und Mitarbeiter kann es je nach Größe der Gruppen einige Stunden dauern, bis die benutzerdefinierten Richtlinien jedem Mitglied der ausgewählten Gruppen zugewiesen wurden. Dies geschieht im Hintergrund, nachdem Sie diesen Schritt erfolgreich abgeschlossen haben.
6. Sie sind auf dem Weg, aber sie sind noch nicht fertig! Es gibt noch ein paar weitere Punkte, die Sie berücksichtigen sollten. Schauen Sie sich als Nächstes die Schritte im Abschnitt ["Was zu tun" an, nachdem Sie den Assistentenabschnitt](#what-to-do-after-running-the-wizard) in diesem Artikel ausgeführt haben.

    :::image type="content" source="media/easy-policy-setup-on-way.png" alt-text="Screenshot der Seite im Assistenten für die nächsten Schritte.":::

## <a name="what-to-do-after-running-the-wizard"></a>Vorgehensweise nach dem Ausführen des Assistenten

<a name="polwiz_remove"> </a>

### <a name="step-1-remove-existing-policy-assignments-that-conflict-with-policies-applied-by-the-wizard"></a>Schritt 1: Entfernen vorhandener Richtlinienzuweisungen, die mit vom Assistenten angewendeten Richtlinien in Konflikt treten

> [!IMPORTANT]
> **Führen Sie diesen Schritt nur aus, wenn Sie kursteilnehmern oder Lehrkräften und Mitarbeitern vorhandene Richtlinien zugewiesen haben, *bevor* Sie den Assistenten ausgeführt haben**. Wenn Sie noch nicht mit Teams und keine anderen Richtlinien als die vom Assistenten erstellten Richtlinien haben, überspringen Sie diese, und fahren Sie mit Schritt 2 fort.

In Teams kann für einen bestimmten Richtlinienbereich eine Richtlinie auf folgende Weise auf einen Benutzer angewendet werden:

- Direkte Zuweisung an den Benutzer
- Zuweisung zu einer Gruppe, in der der Benutzer Mitglied ist
- Wenn dem Benutzer nicht direkt eine Richtlinie zugewiesen ist oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen wurde, erhält der Benutzer automatisch die globale Richtlinie (organisationsweite Standardrichtlinie).

Wenn mehrere dieser Richtlinienzuweisungen für einen Benutzer vorhanden sind, verwendet Teams die folgende Reihenfolge, um zu bestimmen, welche Richtlinienzuweisung wirksam wird. Weitere Informationen finden Sie unter [Welche Richtlinie hat Vorrang](policy-assignment-overview.md#which-policy-takes-precedence) oder [Rangfolgenregeln für Gruppen](assign-policies-users-and-groups.md#precedence-rules).

|Richtlinienzuweisungen eines Benutzers|Richtlinie, die wirksam wird|
|---|---|
|Der Gruppe zugewiesene Richtlinie: Nein <p> Direkt dem Benutzer zugewiesene Richtlinie: Nein|Globale (organisationsweite) Standardrichtlinie|
|Der Gruppe zugewiesene Richtlinie: Nein <p> Richtlinie, die dem Benutzer direkt zugewiesen ist: Ja|Richtlinie, die dem Benutzer direkt zugewiesen ist|
|Der Gruppe zugewiesene Richtlinie: Ja <p> Richtlinie, die dem Benutzer direkt zugewiesen ist: Ja|Richtlinie, die dem Benutzer direkt zugewiesen ist|
|Der Gruppe zugewiesene Richtlinie: Ja <p> Direkt dem Benutzer zugewiesene Richtlinie: Nein|Der Gruppe zugewiesene Richtlinie <p> Wenn der Benutzer Mitglied mehrerer Gruppen ist und jeder Gruppe eine Richtlinie desselben Richtlinienbereichs zugewiesen ist, wird die Richtlinie mit der höchsten [Gruppenzuweisungsrangfolge](assign-policies-users-and-groups.md#group-assignment-ranking) wirksam.|

Aufgrund dieser Reihenfolge werden die vom Assistenten erstellten Richtlinien nicht wirksam, wenn ein Benutzer über vorhandene direkte Zuordnungen oder Gruppenzuweisungen verfügt. Dies bedeutet, dass Sie die vorhandenen Richtlinienzuweisungen vom Benutzer entfernen müssen, damit die vom Assistenten angewendete Richtlinie wirksam wird.

Führen Sie für jeden [vom Assistenten angewendeten Richtlinienbereich](#policies-applied-by-the-wizard) die folgenden Schritte aus:

- Entfernen Sie alle vorhandenen direkten Aufgaben und Gruppenzuweisungen von Ihren Kursteilnehmern, sodass die vom Assistenten angewendete globale (organisationsweite Standard)-Richtliniendefinition wirksam wird.
- Entfernen Sie alle widersprüchlichen direkten Zuweisungen für Ihre Lehrkräfte und Mitarbeiter, damit die vom Assistenten erstellte benutzerdefinierte Richtliniendefinition wirksam wird. Verwenden Sie die obige Tabelle, um die Szenarien zu ermitteln, die für Sie gelten. <p> Beachten Sie, dass der Assistent Ihren Lehrkräften und Ihrer Mitarbeitergruppe Richtlinien zuweist, wobei eine [Gruppenzuordnungsrangfolge](assign-policies-users-and-groups.md#group-assignment-ranking) von 1 verwendet wird, was die höchste Rangfolge ist. Wenn Ihren Lehrkräften und Ihrer Mitarbeitergruppe eine vorhandene Richtlinie desselben Richtlinienbereichs zugewiesen ist, wird diese vorhandene Richtlinie in eine niedrigere Rangfolge verschoben, und die vom Assistenten zugewiesene Richtlinie wird wirksam.

[Erfahren Sie mehr](batch-group-policy-assignment-edu.md#remove-a-policy-that-was-directly-assigned-to-users) darüber, wie Sie Richtlinien entfernen, die Benutzern direkt zugewiesen sind.

Sie haben beispielsweise Lehrkräften direkt eine Besprechungsrichtlinie zugewiesen, und Ihre Schüler/Studenten verfügen über die globale (organisationsweite Standard-) Besprechungsrichtlinie. Entfernen Sie in diesem Szenario die Besprechungsrichtlinie, die Sie Lehrkräften direkt zugewiesen haben, damit die benutzerdefinierte Richtliniendefinition für die vom Assistenten erstellte Besprechungsrichtlinie wirksam wird. Sie müssen nichts mit der vorhandenen globalen (organisationsweiten Standard-) Besprechungsrichtlinie für Schüler/Studenten tun, da keine anderen Besprechungsrichtlinien damit in Konflikt stehen.

<a name="polwiz_addmeasures"> </a>

### <a name="step-2-check-for-additional-measures-that-you-can-take-for-student-safety"></a>Schritt 2: Überprüfen Auf zusätzliche Maßnahmen, die Sie für die Sicherheit der Schüler ergreifen können

Der Assistent passt [diese Richtlinien](#policies-applied-by-the-wizard) automatisch an und wendet sie an. Es gibt einige zusätzliche Maßnahmen, die Sie möglicherweise auf der Grundlage der Bedürfnisse Ihrer Einrichtung ergreifen möchten, um sicher zu bleiben.

Weitere Sicherheitsempfehlungen finden Sie unter [Keeping students safe while using Teams for distance learning](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8#ID0EBBAAA).

<a name="polwiz_mc"> </a>

### <a name="step-3-check-message-center-for-policy-updates"></a>Schritt 3: Überprüfen des Nachrichtencenters auf Richtlinienupdates

Derzeit wendet der Assistent unsere empfohlenen Richtlinien an, wenn Sie ihn ausführen. Es ist wichtig zu wissen, dass die globalen (organisationsweiten Standardeinstellungen) für die Sicherheit von Schülern/Studenten automatisch vom Assistenten aktualisiert werden, sobald neue Richtlinien in Teams verfügbar sind.

Überprüfen Sie jedoch häufig das [Nachrichtencenter](https://admin.microsoft.com/AdminPortal/Home?#/MessageCenter) (im Microsoft 365 Admin Center), um über neue Features und deren Richtlinien und Richtlinieneinstellungen in Teams auf dem Laufenden zu bleiben.

## <a name="make-changes-in-the-wizard"></a>Vornehmen von Änderungen im Assistenten

<a name="polwiz_change"> </a>

Wenn Sie nach dem Ausführen des Assistenten Änderungen vornehmen müssen, können Sie ihn erneut ausführen und Ihre Auswahl ändern.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **"Start**", und wählen Sie dann in der Option "**Einfache Richtlinieneinrichtung für eine sichere Lernumgebung**" die Option **"Ändern"** aus.
2. Fahren Sie von hier aus mit jeder Seite des Assistenten fort, um Ihre Änderungen vorzunehmen. Sie können ihren Einrichtungstyp, die Gruppen von Lehrkräften und Mitarbeitern, denen Sie Richtlinien zuweisen möchten, oder beides ändern.

In der folgenden Tabelle wird zusammengefasst, was geschieht, wenn Sie eine Änderung im Assistenten vornehmen.

|Änderungstyp|Richtlinienverhalten|
|---|---|
|Ändern des Typs der Bildungseinrichtung und der Lehrkräfte und Mitarbeitergruppen|<ul><li>**Kursteilnehmer**: Die globalen (organisationsweiten Standard)-Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studenten angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: Eine Reihe von benutzerdefinierten Richtliniendefinitionen basierend auf dem neuen Bildungseinrichtungstyp wird erstellt und den neuen Lehrkräften und Mitarbeitergruppen zugewiesen. Die vorherigen benutzerdefinierten Richtliniendefinitionen werden aus den vorherigen Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>|
|Nur den Typ der Bildungseinrichtung ändern|<ul><li>**Kursteilnehmer**: Die globalen (organisationsweiten Standard)-Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, werden auf Schüler/Studenten angewendet.</li><li>**Lehrkräfte und Mitarbeiter**: Eine Reihe von benutzerdefinierten Richtliniendefinitionen, die auf dem neuen Bildungseinrichtungstyp basieren, wird erstellt und den Lehrkräften und Mitarbeitergruppen zugewiesen. Die benutzerdefinierten Richtliniendefinitionen, die für den vorherigen Bildungseinrichtungstyp erstellt wurden, werden aus den Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>|
|Nur die Lehrkräfte und Mitarbeitergruppen ändern|<ul><li>**Kursteilnehmer**: Keine Änderung an den globalen (organisationsweiten Standard)-Richtliniendefinitionen, die auf Schüler/Studenten angewendet werden.</li><li>**Lehrkräfte und Mitarbeiter**: Die benutzerdefinierten Richtliniendefinitionen werden den neuen Lehrkräften und Mitarbeitergruppen zugewiesen und aus den vorherigen Lehrkräften und Mitarbeitergruppen entfernt.</li></ul>|

## <a name="policies-applied-by-the-wizard"></a>Vom Assistenten angewendete Richtlinien

<a name="polwiz_policies"> </a>

### <a name="policy-areas"></a>Politikfelder

Hier sind die Richtlinienbereiche und die entsprechenden Richtliniennamen, die vom Assistenten behandelt werden. Um diese Richtlinien zu finden, wechseln Sie zum Microsoft Teams Admin Center, und wechseln Sie dann im linken Navigationsbereich zu den einzelnen Richtlinienbereichsseiten.

#### <a name="students"></a>[**Studenten**](#tab/students/)

|Richtlinienbereich|Primärer oder sekundärer Richtlinienname|Name der Hochschulrichtlinie|
|---|---|---|
|Teams-Richtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|Besprechungsrichtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|Richtlinie für Liveereignisse|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|App-Setuprichtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|App-Berechtigungsrichtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|Messagingrichtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|
|Anrufrichtlinie|Global (organisationsweite Standardeinstellung)|Global (organisationsweite Standardeinstellung)|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educators/)

|Richtlinienbereich|Primärer oder sekundärer Richtlinienname|Name der Hochschulrichtlinie|
|---|---|---|
|Teams-Richtlinie|Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Teams|Hochschullehrer und -mitarbeiter – Teams|
|Besprechungsrichtlinie|Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Besprechung|Hochschullehrer und -mitarbeiter – Besprechung|
|Richtlinie für Liveereignisse|Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Live Ereignisse|Hochschullehrer und -mitarbeiter – Live Veranstaltungen|
|Messagingrichtlinie|Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Messaging|Hochschullehrer und -mitarbeiter – Messaging|
|Anrufrichtlinie|Primäre oder sekundäre Lehrkräfte und Mitarbeiter – Anrufe|Hochschullehrer und -mitarbeiter – Anrufe|

### <a name="policy-settings"></a>Richtlinieneinstellungen

Hier ist eine Zusammenfassung der Vom Assistenten für jeden Richtlinienbereich angewendeten Einstellungen.

> [!NOTE]
> Nur Teambesitzer können freigegebene Kanäle erstellen.<br><br>Für gemeinsame Kanäle mit anderen Organisationen ist die Konfiguration von [Azure AD B2B Direct Connect](/azure/active-directory/external-identities/b2b-direct-connect-overview) erforderlich, die standardmäßig deaktiviert ist. Informationen zum Aktivieren dieses Features finden [Sie unter "Zusammenarbeit mit externen Teilnehmern in einem Kanal](/microsoft-365/solutions/collaborate-teams-direct-connect) ".

#### <a name="students"></a>[**Studenten**](#tab/student-settings/)

Hier ist eine Liste der globalen (organisationsweiten Standard-) Richtliniendefinitionen, die vom Assistenten angepasst und auf Kursteilnehmer angewendet wurden.

|Richtlinienbereich|Unterbereich|Richtlinieneinstellung|Primär oder sekundär|Hochschulbildung|
|---|---|---|---|---|
|Teams-Richtlinie||Erstellen privater Kanäle|Aus|Ein|
|||Erstellen freigegebener Kanäle|Ein|Ein|
|||Freigeben des Kanals für externe Teilnehmer|Ein|Ein|
|||Teilnehmen an einem externen freigegebenen Kanal|Ein|Ein|
|Besprechungsrichtlinie|Allgemein|Sofortbesprechungen in Kanälen zulassen|Aus|Ein|
|||Outlook-Add-In zulassen|Aus|Ein|
|||Planung von Kanalbesprechungen zulassen|Aus|Ein|
|||Planung privater Besprechungen zulassen|Aus|Ein|
|||Besprechungsregistrierung zulassen|Ein|Ein|
|||Wer können sich registrieren|Jeder in der Organisation|Jeder in der Organisation|
||Audio & Video|Transkription|Ein|Ein|
|||Cloudaufzeichnung|Aus|Ein|
|||Modus für IP-Audio|Ausgehendes und eingehendes Audio aktiviert|Ausgehendes und eingehendes Audio aktiviert|
|||Modus für IP-Video|Ausgehendes und eingehendes Video aktiviert|Ausgehendes und eingehendes Video aktiviert|
|||IP-Video|Ein|Ein|
|||NDI-Streaming zulassen|Aus|Aus|
|||Media-Bitrate (KBs)|50.000|50.000|
||Inhaltsfreigabe|Bildschirmübertragungsmodus|Gesamter Bildschirm|Gesamter Bildschirm|
|||Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert|Ein|Ein|
|||Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert|Ein|Ein|
|||PowerPoint Freigabe|Ein|Ein|
|||Whiteboard|Ein|Ein|
|||Freigegebene Notizen|Ein|Ein|
||Teilnehmer & Gäste|Anonymen Personen das Starten einer Besprechung gestatten|Aus|Ein|
|||Rollen mit Referentenrechten in Besprechungen|EveryoneUserOverride|EveryoneUserOverride|
|||Personen automatisch zulassen|EveryoneInCompany|EveryoneInCompany|
|||Einwahlbenutzern das Umgehen des Wartebereichs gestatten|Aus|Aus|
|||Jetzt in privaten Besprechungen besprechen|Aus|Ein|
|||Live Beschriftungen|Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen.|Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen.|
|||Chatten in Besprechungen|Ein|Ein|
|Richtlinie für Liveereignisse||Live der Ereignisplanung|Aus|Aus|
|||Transkription für Teilnehmer|Ein|Ein|
|||Wer an geplanten Liveereignissen teilnehmen kann|Jeder in der Organisation|Jeder in der Organisation|
|||Wer kann ein Ereignis aufzeichnen|Immer|Immer|
|Messagingrichtlinie||Besitzer können gesendete Nachrichten löschen|Aus|Ein|
|||Gesendete Nachrichten löschen|Aus|Ein|
|||Gesendete Nachrichten bearbeiten|Aus|Ein|
|||Lesebestätigungen|Benutzergesteuert|Benutzergesteuert|
|||Chat|Aus|Ein|
|||Giphys in Unterhaltungen|Aus|Ein|
|||Giphy-Inhaltsklassifikation|Streng|Streng|
|||Memes in Unterhaltungen|Ein|Ein|
|||Aufkleber in Unterhaltungen|Ein|Ein|
|||URL-Vorschau|Ein|Ein|
|||Übersetzen von Nachrichten|Ein|Ein|
|||Plastischer Reader für Nachrichten|Ein|Ein|
|||Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden|Aus|Ein|
|||Erstellen von Sprachnachrichten|In Chats und Kanälen zulässig|In Chats und Kanälen zulässig|
|||Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen|Aktiviert|Aktiviert|
|||Entfernen von Benutzern aus Gruppenchats|Aus|Ein|
|App-Berechtigungsrichtlinie||Microsoft-Apps|Blockieren bestimmter Apps und Zulassen, dass alle anderen > Walkie-Talkie blockiert sind|Alle Apps zulassen|
|||Drittanbieter-Apps|Alle Apps zulassen|Alle Apps zulassen|
|||Benutzerdefinierte Apps|Alle Apps zulassen|Alle Apps zulassen|
|App-Setuprichtlinie||Hochladen benutzerdefinierter Apps|Aus|Aus|
|||Benutzer-Pinning|Ein|Ein|
|||Installierte Apps|Keine|Keine|
|||Angeheftete Apps|Aktivität, Kalender, Teams|Aktivität, Chats, Teams, Kalender, Anrufe, Datei
|Anrufrichtlinie||Private Anrufe führen|Aus|Ein|
|||Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation|Aus|Ein|
|||Anrufweiterleitung und gleichzeitiges Klingeln an externen Telefonnummern|Aus|Ein|
|||Voicemail ist für das Routing eingehender Anrufe verfügbar.|Benutzergesteuert|Benutzergesteuert|
|||Eingehende Anrufe können an Anrufgruppen weitergeleitet werden.|Aus|Ein|
|||Delegierung für eingehende und ausgehende Anrufe zulassen|Aus|Ein|
|||Verhindern der gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN|Aus|Aus|
|||"Beschäftigt bei Beschäftigt" ist verfügbar, wenn ein Anruf ausgeführt wird.|Aus|Aus|
|||Web-PSTN-Anrufe zulassen|Aus|Ein|

#### <a name="educators-and-staff"></a>[**Lehrkräfte und Mitarbeiter**](#tab/educator-settings/)

Hier ist eine Liste der benutzerdefinierten Richtliniendefinitionen, die den Lehrkräften und Mitarbeitergruppen zugewiesen sind, die Sie im Assistenten auswählen.  

|Richtlinienbereich|Unterbereich|Richtlinieneinstellung|Primär oder sekundär|Hochschulbildung|
|---|---|---|---|---|
|Teams-Richtlinie||Erstellen privater Kanäle|Ein|Ein|
|||Erstellen freigegebener Kanäle|Ein|Ein|
|||Freigeben des Kanals für externe Teilnehmer|Ein|Ein|
|||Teilnehmen an einem externen freigegebenen Kanal|Ein|Ein|
|Besprechungsrichtlinie|Allgemein|Sofortbesprechungen in Kanälen zulassen|Ein|Ein|
|||Outlook-Add-In zulassen|Ein|Ein|
|||Planung von Kanalbesprechungen zulassen|Ein|Ein|
|||Planung privater Besprechungen zulassen|Ein|Ein|
|||Besprechungsregistrierung zulassen|Ein|Ein|
|||Wer können sich registrieren|Jeder in der Organisation|Jeder in der Organisation|
||Audio & Video|Transkription|Ein|Ein|
|||Cloudaufzeichnung|Ein|Ein|
|||Modus für IP-Audio|Ausgehendes und eingehendes Audio aktiviert|Ausgehendes und eingehendes Audio aktiviert|
|||Modus für IP-Video|Ausgehendes und eingehendes Video aktiviert|Ausgehendes und eingehendes Video aktiviert|
|||IP-Video|Ein|Ein|
|||NDI-Streaming zulassen|Aus|Aus|
|||Media-Bitrate (KBs)|50.000|50.000|
||Inhaltsfreigabe|Bildschirmfreigabemodus|Gesamter Bildschirm|Gesamter Bildschirm|
|||Zulassen, dass ein Teilnehmer die Steuerung erteilt oder anfordert|Ein|Ein|
|||Zulassen, dass ein externer Teilnehmer die Steuerung übergibt oder anfordert|Ein|Ein|
|||PowerPoint Freigabe|Ein|Ein|
|||Whiteboard|Ein|Ein|
|||Freigegebene Notizen|Ein|Ein|
||Teilnehmer & Gäste|Anonymen Personen das Starten einer Besprechung gestatten|Ein|Ein|
|||Rollen mit Referentenrechten in Besprechungen|OrganizerOnlyUserOverride|OrganizerOnlyUserOverride|
|||Personen automatisch zulassen|OrganizerOnly|OrganizerOnly|
|||Einwahlbenutzern das Umgehen des Wartebereichs gestatten|Aus|Aus|
|||Jetzt in privaten Besprechungen besprechen|Ein|Ein|
|||Live Beschriftungen|Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen.|Deaktiviert, der Benutzer kann dies jedoch außer Kraft setzen.|
|||Chatten in Besprechungen|Ein|Ein|
|Richtlinie für Liveereignisse||Live der Ereignisplanung|Ein|Ein|
|||Transkription für Teilnehmer|Ein|Ein|
|||Wer an geplanten Liveereignissen teilnehmen kann|Jeder in der Organisation|Jeder in der Organisation|
|||Wer kann ein Ereignis aufzeichnen|Immer aufzeichnen|Immer aufzeichnen|
|Messagingrichtlinie||Besitzer können gesendete Nachrichten löschen|Ein|Ein|
|||Gesendete Nachrichten löschen|Ein|Ein|
|||Gesendete Nachrichten bearbeiten|Ein|Ein|
|||Lesebestätigungen|Benutzergesteuert|Benutzergesteuert|
|||Chat|Ein|Ein
|||Giphys in Unterhaltungen|Ein|Ein|
|||Giphy-Inhaltsklassifikation|Streng|Streng|
|||Memes in Unterhaltungen|Ein|Ein|
|||Aufkleber in Unterhaltungen|Ein|Ein|
|||URL-Vorschau|Ein|Ein|
|||Übersetzen von Nachrichten|Ein|Ein|
|||Plastischer Reader für Nachrichten|Ein|Ein|
|||Dringende Nachrichten mittels Benachrichtigungen mit hoher Priorität senden|Ein|Ein|
|||Erstellen von Sprachnachrichten|In Chats und Kanälen zulässig|In Chats und Kanälen zulässig|
|||Auf Mobilgeräten bevorzugte Kanäle über aktuellen Chats anzeigen|Aktiviert|Aktiviert|
|||Entfernen von Benutzern aus Gruppenchats|Ein|Ein|
|Anrufrichtlinie||Private Anrufe führen|Ein|Ein|
|||Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation|Ein|Ein|
|||Anrufweiterleitung und gleichzeitiges Klingeln an externen Telefonnummern|Ein|Ein|
|||Voicemail ist für das Routing eingehender Anrufe verfügbar.|Benutzergesteuert|Benutzergesteuert|
|||Eingehende Anrufe können an Anrufgruppen weitergeleitet werden.|Ein|Ein|
|||Delegierung für eingehende und ausgehende Anrufe zulassen|Ein|Ein|
|||Verhindern der gebührenpflichtigen Umgehung und Senden von Anrufen über das PSTN|Aus|Aus|
|||"Beschäftigt bei Beschäftigt" ist verfügbar, wenn ein Anruf ausgeführt wird.|Aus|Aus|
|||Web-PSTN-Anrufe zulassen|Ein|Ein|

## <a name="related-topics"></a>Verwandte Themen

- [Teams-Richtlinien und Richtlinienpakete für Bildung](policy-packages-edu.md)
- [Zuweisen von Richtlinien zu großen Gruppen von Benutzern in Ihrer Schule](batch-group-policy-assignment-edu.md)
- [Sicherheit der Schüler bei der Nutzung von Teams für den Fernunterricht](https://support.microsoft.com/office/keeping-students-safe-while-using-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)
