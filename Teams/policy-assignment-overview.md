---
title: Zuweisen von Richtlinien in Teams
author: KarliStites
ms.author: kastites
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
localization_priority: Normal
search.appverid: MET150
description: Lernen Sie die verschiedenen Methoden zum Zuweisen von Richtlinien und Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 9d0f82ab377b1c09f60db7f953c1016f396b2e706417f0f7acb17903ad83c8bf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329000"
---
# <a name="assign-policies-in-teams--getting-started"></a>Zuweisen von Richtlinien in Teams – Erste Schritte

Als Administrator steuern Sie mithilfe von Richtlinien die Teams Features, die Benutzern in Ihrer Organisation zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.

Organisationen haben verschiedene Arten von Benutzern mit eindeutigen Anforderungen. Benutzerdefinierte Richtlinien, die Sie erstellen und zuweisen, ermöglichen Ihnen das Anpassen von Richtlinieneinstellungen an verschiedene Benutzergruppen basierend auf diesen Anforderungen.

Zum einfachen Verwalten von Richtlinien in Ihrer Organisation bietet Teams verschiedene Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern. Weisen Sie eine Richtlinie direkt den Benutzern zu, entweder einzeln oder mit einem Maßstab über eine Batchzuweisung, oder einer Gruppe, deren Mitglieder die Benutzer sind. Sie können auch Richtlinienpakete verwenden, um Benutzern in Ihrer Organisation, die ähnliche Rollen haben, eine vordefinierte Sammlung von Richtlinien zuzuordnen. Welche Option Sie auswählen, hängt von der Anzahl der Richtlinien ab, die Sie verwalten, und von der Anzahl der Benutzer, der Sie Richtlinien zuweisen. Globale Richtlinien (Organisationsweite Standardrichtlinien) gelten für die größte Anzahl von Benutzern in Ihrer Organisation. Sie müssen nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von was.

Details zum Zuweisen von Richtlinien **zu Benutzern** und Gruppen finden Sie unter Zuweisen von Richtlinien zu Benutzern und [Gruppen.](assign-policies-users-and-groups.md) Details zum Zuweisen von **Richtlinienpaketen finden Sie** unter [Zuweisen von Richtlinienpaketen.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>Welche Richtlinie hat Vorrang?

Ein Benutzer verfügt über eine effektive Richtlinie für jeden Richtlinientyp. Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer eine Richtlinie direkt zugewiesen wird und außerdem Mitglied einer oder mehreren Gruppen ist, denen eine Richtlinie desselben Typs zugewiesen ist. Welche Richtlinie hat in solchen Szenarien Vorrang? Die effektive Richtlinie eines Benutzers wird anhand der Rangfolgeregeln wie folgt bestimmt.

Wenn einem Benutzer eine Richtlinie direkt zugewiesen wird (entweder einzeln oder über eine Batchzuweisung), hat diese Richtlinie Vorrang. Im folgenden visuellen Beispiel ist die effektive Richtlinie des Benutzers die Besprechungsrichtlinie "Square Square", die dem Benutzer direkt zugewiesen wird.

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

Wenn einem Benutzer eine Richtlinie eines bestimmten Typs nicht direkt zugewiesen wurde, hat die einer Gruppe zugewiesene Richtlinie, deren Mitglied er ist, Vorrang. Wenn ein Benutzer ein Mitglied mehrerer Gruppen ist, hat die Richtlinie mit der höchsten[Rangfolge](assign-policies-users-and-groups.md#group-assignment-ranking)(Gruppenzuweisungsrangfolge) für den angegebenen Richtlinientyp Vorrang.

In diesem visuellen Beispiel ist die effektive Richtlinie des Benutzers die Richtlinie exec Teams und HD, die im Vergleich zu anderen Gruppen, denen der Benutzer gehört, die höchste Zuweisungsrangfolge hat und denen auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.  

![Diagramm, das zeigt, wie eine von einer Gruppe geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

Wenn einem Benutzer eine Richtlinie nicht direkt zugewiesen wurde oder kein Mitglied von Gruppen ist, denen eine Richtlinie zugewiesen wurde, erhält der Benutzer die globale (organisationsweite Standard)-Richtlinie für diesen Richtlinientyp. Hier sehen Sie ein visuelles Beispiel.

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

Weitere Informationen finden Sie unter ([Rangfolgeregeln).](assign-policies-users-and-groups.md#precedence-rules)

## <a name="ways-to-assign-policies"></a>Möglichkeiten zum Zuweisen von Richtlinien

Im Folgenden finden Sie eine Übersicht über die Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern und die empfohlenen Szenarien für die einzelnen Szenarien. Wählen Sie die Links aus, um mehr zu erfahren.

Bevor Sie Richtlinien einzelnen Benutzern oder Gruppen zuweisen, beginnen Sie, indem Sie die globalen [(organisationsweiten)](#set-the-global-policies) Standardrichtlinien so festlegen, dass sie für die größte Anzahl von Benutzern in Ihrer Organisation gelten.  Nachdem Sie die globalen Richtlinien festgelegt haben, müssen Sie nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

|So geht's  |Wenn...  | Verwendung von ...
|---------|---------|----|
|[Zuweisen einer Richtlinie zu einzelnen Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Sie sind neu bei Teams und beginnen gerade, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen. |Die Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell Teams Modul
|[Zuweisen einer Richtlinie zu einer Gruppe](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Weisen Sie Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zu. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zu.| Die Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell Teams Modul|
|[Zuweisen einer Richtlinie zu einer Gruppe von Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Weisen Sie Richtlinien großen Gruppen von Benutzern zu. Weisen Sie beispielsweise Hunderten oder Tausenden von Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zu. |Die Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell Teams Modul|
|[Zuweisen eines Richtlinienpakets zu Benutzern](assign-policy-packages.md#assign-a-policy-package-to-users)  |Weisen Sie bestimmten Gruppen von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zu. Weisen Sie beispielsweise Lehrkräften in Ihrer Bildungseinrichtungen das Richtlinienpaket für Bildungseinrichtungen zu, um ihnen Vollzugriff auf Chats, Anrufe und Besprechungen zu geben. Weisen Sie das Richtlinienpaket für Bildungseinrichtungen (Schüler/Studenten sekundärer Bildungseinrichtungen) sekundären Schülern/Studenten zu, um bestimmte Funktionen wie private Anrufe zu beschränken.  |Die Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell Teams Modul|
|[Zuweisen eines Richtlinienpakets zu einer Gruppe](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in der privaten Vorschau)   |Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zu. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste ein Richtlinienpaket zu. |Das Microsoft Teams Admin Center (in Kürze verfügbar) oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zu. Weisen Sie beispielsweise allen Lehrkräften in Ihrer Schule das Richtlinienpaket für "Education (Lehrer)" mithilfe einer Batchzuweisung zu, um ihnen Vollzugriff auf Chats, Anrufe und Besprechungen zu geben. Weisen Sie das Richtlinienpaket für Bildungseinrichtungen (Sekundäre Bildungseinrichtungen) einer Gruppe von sekundären Schülern/Studenten zu, um bestimmte Funktionen wie private Anrufe zu beschränken.|PowerShell-Cmdlets im Teams PowerShell-Modul|

## <a name="set-the-global-policies"></a>Festlegen der globalen Richtlinien

Führen Sie die folgenden Schritte aus, um die globalen (organisationsweiten Standard)-Richtlinien für jeden Richtlinientyp festlegen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie in der linken Navigationsleiste Microsoft Teams Admin Center zur Richtlinienseite für den Richtlinientyp, den Sie aktualisieren möchten. Beispielsweise können sie **Teams** Teams , Besprechungsbesprechungsrichtlinien  >     >  , **Messaging-Richtlinien** oder **Voice**  >  **Calling-Richtlinien verwenden.**
2. Wählen Sie **die Richtlinie Global (Organisationsweit Standard)** aus, um die aktuellen Einstellungen anzeigen.
3. Aktualisieren Sie die Richtlinie nach Bedarf, und wählen Sie dann **Anwenden aus.**

![Aktualisieren der globalen Richtlinie im Teams Admin Center](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Verwendung von PowerShell

Zum Festlegen der globalen Richtlinien mithilfe von PowerShell verwenden Sie den globalen Bezeichner.  Überprüfen Sie zunächst die aktuelle globale Richtlinie, um zu bestimmen, welche Einstellung Sie ändern möchten.

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

Aktualisieren Sie als Nächstes die Globale Richtlinie nach Bedarf.  Sie müssen nur Werte für die Einstellungen angeben, die Sie ändern möchten.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungen im Aktivitätsprotokoll

Wenn Sie den Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuweisungen im Aktivitätsprotokoll anzeigen. Im Aktivitätsprotokoll werden Richtlinienzuweisungen für Batches von mehr als 20 Benutzern im Microsoft Teams Admin Center der letzten 30 Tage angezeigt. Beachten Sie, dass im Aktivitätsprotokoll über das Microsoft Teams Admin Center keine Richtlinienpaketzuweisungen, keine Richtlinienzuweisungen für Batches von weniger als 20 Benutzern oder keine Richtlinienzuweisungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuweisungsaktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuweisungen im Aktivitätsprotokoll an:

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams **Admin Center** zu Dashboard , und wählen Sie dann unter Aktivitätsprotokoll die Option Details anzeigen **aus.** 
2. Sie können alle Richtlinienzuweisungen anzeigen oder die Liste nach Status filtern, um nur Die Aufgaben "Nicht **gestartet",** **"In Bearbeitung"** oder **"Abgeschlossen" angezeigt zu werden.** Zu jeder Aufgabe werden die folgenden Informationen zu sehen:
    - **Name:** Der Name der Richtlinienzuweisung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, sowie die Anzahl der abgeschlossenen, in Bearbeitung und nicht begonnenen Zuordnungen. Außerdem sehen Sie die Liste der Benutzer im Batch sowie den Status und das Ergebnis für jeden Benutzer. Nachfolgend ein Beispiel:

        ![Screenshot der](media/activity-log-policy-assignment-detail.png)

    - **Übermittelt:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Fertigstellungszeit:** Datum und Uhrzeit der Richtlinienzuweisung.
    - **Auswirkungen auf**: Anzahl der Benutzer im Batch.
    - **Gesamtstatus:** Status der Richtlinienzuweisung.

> [!NOTE]
> Sie können das Aktivitätsprotokoll auch über die Seite **Benutzer** öffnen. Nachdem Sie auf **Übernehmen geklickt** haben, um eine Massenrichtlinienzuweisung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie **im Banner** auf den Link Aktivitätsprotokoll.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md)
- [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
- [Verwalten Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)