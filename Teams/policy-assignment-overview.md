---
title: Zuweisen von Richtlinien in Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über die verschiedenen Methoden zum Zuweisen von Richtlinien und Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: c618653199a41bc358f4b2a14bdf1c0e8923d9b7
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646414"
---
# <a name="assign-policies-in-teams--getting-started"></a>Zuweisen von Richtlinien in Teams – erste Schritte

Als Administrator verwenden Sie Richtlinien, um die Teams Features zu steuern, die Benutzern in Ihrer Organisation zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.

Organisationen haben unterschiedliche Arten von Benutzern mit eindeutigen Anforderungen. Mit benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, können Sie Richtlinieneinstellungen auf unterschiedliche Gruppen von Benutzern basierend auf diesen Anforderungen anpassen.

Um Richtlinien in Ihrer Organisation einfach zu verwalten, bietet Teams mehrere Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern. Weisen Sie eine Richtlinie benutzern direkt zu, entweder einzeln oder skaliert über eine Batchzuweisung, oder einer Gruppe, der die Benutzer angehören. Sie können Richtlinienpakete auch verwenden, um Benutzern in Ihrer Organisation, die ähnliche Rollen haben, eine vordefinierte Sammlung von Richtlinien zuzuweisen. Die von Ihnen ausgewählte Option hängt von der Anzahl der Richtlinien ab, die Sie verwalten, und der Anzahl der Benutzer, denen Sie Richtlinien zuweisen. Globale Richtlinien (organisationsweite Standardrichtlinien) gelten für die größte Anzahl von Benutzern in Ihrer Organisation. Sie müssen nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, und die empfohlenen Szenarien für die Verwendung der elemente beschrieben.

Ausführliche Informationen zum Zuweisen von **Richtlinien zu Benutzern und Gruppen** finden Sie unter [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md). Ausführliche Informationen zum Zuweisen von **Richtlinienpaketen** finden Sie unter [Zuweisen von Richtlinienpaketen](assign-policy-packages.md).

## <a name="which-policy-takes-precedence"></a>Welche Richtlinie hat Vorrang?

Ein Benutzer verfügt über eine effektive Richtlinie für jeden Richtlinientyp. Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer direkt eine Richtlinie zugewiesen ist und auch Mitglied einer oder mehrerer Gruppen ist, denen eine Richtlinie desselben Typs zugewiesen ist. Welche Richtlinie hat in solchen Szenarien Vorrang? Die effektive Richtlinie eines Benutzers wird wie folgt nach Rangfolgeregeln bestimmt.

Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batchzuweisung), hat diese Richtlinie Vorrang. Im folgenden visuellen Beispiel ist die effektive Richtlinie des Benutzers die Lincoln Square-Besprechungsrichtlinie, die dem Benutzer direkt zugewiesen wird.

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat.](media/assign-policies-example-directly-assigned.png)

Wenn einem Benutzer nicht direkt eine Richtlinie eines bestimmten Typs zugewiesen wird, hat die Richtlinie, die einer Gruppe zugewiesen ist, in der der Benutzer Mitglied ist, Vorrang. Wenn ein Benutzer Mitglied mehrerer Gruppen ist, hat die Richtlinie, die die höchste ([Gruppenzuordnungsrangfolge](assign-policies-users-and-groups.md#group-assignment-ranking)) für den angegebenen Richtlinientyp hat, Vorrang.

In diesem visuellen Beispiel ist die effektive Richtlinie des Benutzers die Richtlinie "Exec Teams" und "HD", die im Verhältnis zu anderen Gruppen, bei denen der Benutzer Mitglied ist und denen auch eine Richtlinie desselben Richtlinientyps zugewiesen ist, die höchste Zuordnungsrangfolge aufweist.  

![Diagramm, das zeigt, wie eine von der Gruppe geerbte Richtlinie Vorrang hat.](media/assign-policies-example-group.png)

Wenn einem Benutzer keine Richtlinie direkt zugewiesen ist oder kein Mitglied von Gruppen ist, denen eine Richtlinie zugewiesen ist, erhält der Benutzer die globale Richtlinie (organisationsweite Standardrichtlinie) für diesen Richtlinientyp. Hier ist ein visuelles Beispiel.

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat.](media/assign-policies-example-global.png)

Weitere Informationen finden Sie unter ([Rangfolgeregeln](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Methoden zum Zuweisen von Richtlinien

Hier ist eine Übersicht über die Möglichkeiten, wie Sie Benutzern Richtlinien zuweisen können, und die empfohlenen Szenarien für jeden Benutzer. Wählen Sie die Links aus, um mehr zu erfahren.

Bevor Sie einzelnen Benutzern oder Gruppen Richtlinien zuweisen, legen [Sie zunächst die globalen Richtlinien (organisationsweite Standardrichtlinien) so fest](#set-the-global-policies) , dass sie für die größte Anzahl von Benutzern in Ihrer Organisation gelten.  Nachdem die globalen Richtlinien festgelegt wurden, müssen Sie nur den Benutzern Richtlinien zuweisen, für die spezielle Richtlinien erforderlich sind.

|Gehen Sie wie folgt vor:  |Wenn...  | Mit...
|---------|---------|----|
|[Zuweisen einer Richtlinie zu einzelnen Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Sie sind mit Teams noch nicht fertig, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen. |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul
|[Zuweisen einer Richtlinie zu einer Gruppe](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Weisen Sie Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zu. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zu.| Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen einer Richtlinie zu einer Gruppe von Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Weisen Sie Richtlinien großen Gruppen von Benutzern zu. Weisen Sie beispielsweise Hunderte oder Tausende von Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zu. |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu Benutzern](assign-policy-packages.md#assign-a-policy-package-to-users)  |Weisen Sie bestimmten Gruppen von Benutzern in Ihrer Organisation, die die gleichen oder ähnliche Rollen haben, mehrere Richtlinien zu. Weisen Sie beispielsweise lehrern in Ihrer Schule das Richtlinienpaket "Bildung" (Lehrer) zu, um ihnen Vollzugriff auf Chats, Anrufe und Besprechungen zu gewähren. Weisen Sie das Richtlinienpaket für Bildungseinrichtungen (Schüler/Studenten der Sekundarstufe II) sekundären Schülern zu, um bestimmte Funktionen wie private Anrufe einzuschränken.  |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Ein Richtlinienpaket einer Gruppe zuweisen](assign-policy-packages.md#assign-a-policy-package-to-a-group)  |Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation, die die gleichen oder ähnliche Rollen haben, mehrere Richtlinien zu. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste ein Richtlinienpaket zu. |Das Microsoft Teams Admin Center (in Kürze verfügbar) oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation, die die gleichen oder ähnliche Rollen haben, mehrere Richtlinien zu. Weisen Sie z. B. das Richtlinienpaket "Bildung" (Lehrer) allen Lehrkräften in Ihrer Schule mithilfe von Batchzuweisungen zu, um ihnen Vollzugriff auf Chats, Anrufe und Besprechungen zu gewähren. Weisen Sie das Richtlinienpaket für Bildungseinrichtungen (Schüler/Studenten der Sekundarstufe II) einer Reihe von Schülern/Studenten zu, um bestimmte Funktionen wie private Anrufe einzuschränken.|PowerShell-Cmdlets im Teams PowerShell-Modul|

## <a name="set-the-global-policies"></a>Festlegen der globalen Richtlinien

Führen Sie die folgenden Schritte aus, um die globalen (organisationsweiten Standard)-Richtlinien für jeden Richtlinientyp festzulegen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zur Richtlinienseite für den Richtlinientyp, den Sie aktualisieren möchten. Beispielsweise **Teams** >  **Teams-Richtlinien**, **MeetingsMeetings-Richtlinien** > , **Messaging-Richtlinien** oder **VoiceCalling-Richtlinien** > .
2. Wählen Sie die **globale Richtlinie (organisationsweite Standardrichtlinie)** aus, um die aktuellen Einstellungen anzuzeigen.
3. Aktualisieren Sie die Richtlinie nach Bedarf, und wählen Sie dann **"Übernehmen"** aus.

![Aktualisieren Sie die globale Richtlinie im Teams Admin Center.](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Verwendung von PowerShell

Verwenden Sie den globalen Bezeichner, um die globalen Richtlinien mithilfe von PowerShell festzulegen.  Überprüfen Sie zunächst die aktuelle globale Richtlinie, um zu bestimmen, welche Einstellung Sie ändern möchten.

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

Aktualisieren Sie als Nächstes die globale Richtlinie nach Bedarf.  Sie müssen nur Werte für die Einstellungen angeben, die Sie ändern möchten.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im [Aktivitätsprotokoll](https://admin.teams.microsoft.com/activitylog) anzeigen. Das Aktivitätsprotokoll zeigt Informationen zum Hochladen von Netzwerkdatensätzen, Gruppenrichtlinienvorgänge aus Teams Admin Center und PowerShell sowie Batchrichtlinienvorgänge (für mehr als 20 Benutzer) aus dem Teams Admin Center für die letzten 30 Tage.

![Screenshot der Seite "Aktivitätsprotokoll".](media/Activity_Log.png)

So zeigen Sie Ihre Richtlinienvorgänge im Aktivitätsprotokoll an:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Center zum **Dashboard**, und wählen Sie dann unter **"Aktivitätsprotokoll**" die Option "**Details anzeigen"** aus.
2. Zu jedem Richtlinienvorgang werden die folgenden Informationen angezeigt:
    - **Aktivität**: Der Name des Richtlinienvorgangs. Beispiel: **Gruppenrichtlinienzuweisung**
    - **Gruppenname**: Der Name der Gruppe, für die der Richtlinienvorgang abgeschlossen wurde.
    - **Richtlinientyp**: Der Typ der Richtlinie.
    - **Richtlinienname**: Der Name des Richtlinienvorgangs. Für Batchrichtlinienzuweisungen können Sie den Link auswählen, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, der die Richtlinie zugewiesen wurde, und die Anzahl der abgeschlossenen Aufgaben, die ausgeführt und nicht gestartet wurden. Außerdem werden die Liste der Benutzer im Batch sowie der Status und das Ergebnis für jeden Benutzer angezeigt.
    - **Übermittelt von**: Der Name des Benutzers, der den Richtlinienvorgang übermittelt hat.
    - **Übermittelt am**: Datum und Uhrzeit der Übermittlung des Richtlinienvorgangs.
    - **Abgeschlossen am**: Datum und Uhrzeit, zu dem der Richtlinienvorgang abgeschlossen wurde.
    - **Betroffen**: Anzahl der Benutzer im Batch oder in der Gruppe.
    - **Gesamtstatus**: Status des Richtlinienvorgangs. Eine Richtlinie kann einen der folgenden Status aufweisen:
        - **Nicht gestartet**: Der Richtlinienvorgang wurde vom Administrator übermittelt.
        - **In Bearbeitung**: Der Richtlinienvorgang wurde mit der Verarbeitung begonnen.
        - **Rollout für Benutzer**: Das System hat mit der Anwendung des Richtlinienupdates auf Benutzer begonnen.
        - **Abgeschlossen**: Das Richtlinienupdate wurde auf alle Benutzer angewendet.
        - **Abgeschlossen mit X-Fehlern**: Der Richtlinienvorgang ist abgeschlossen, es gibt jedoch Fehler.

> [!NOTE]
> Sie können auch über die Seite **"Benutzer** " zum Aktivitätsprotokoll gelangen. Nachdem Sie " **Übernehmen"** ausgewählt haben, um eine Massenrichtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Wählen Sie im Banner den Link " **Aktivitätsprotokoll"** aus.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md)
- [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
