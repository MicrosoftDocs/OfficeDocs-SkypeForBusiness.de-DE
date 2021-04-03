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
description: Erfahren Sie mehr über die verschiedenen Methoden zum Zuweisen von Richtlinien und Richtlinienpaketen zu Benutzern und Gruppen in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574323"
---
# <a name="assign-policies-in-teams--getting-started"></a>Zuweisen von Richtlinien in Teams – erste Schritte

Als Administrator steuern Sie mithilfe von Richtlinien die Teams-Features, die Benutzern in Ihrer Organisation zur Verfügung stehen. Beispielsweise gibt es Anrufrichtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.

Organisationen haben verschiedene Arten von Benutzern mit eindeutigen Anforderungen. Mit benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, können Sie Richtlinieneinstellungen auf unterschiedliche Benutzergruppen basierend auf diesen Anforderungen anpassen.

Zum einfachen Verwalten von Richtlinien in Ihrer Organisation bietet Teams verschiedene Möglichkeiten zum Zuweisen von Richtlinien zu Benutzern. Weisen Sie benutzern eine Richtlinie direkt zu, entweder einzeln oder im Maßstab über eine Batchzuordnung, oder zu einer Gruppe, der die Benutzer mitglieder sind. Sie können Richtlinienpakete auch verwenden, um Benutzern in Ihrer Organisation, die ähnliche Rollen haben, eine vordefinierte Sammlung von Richtlinien zuzuordnen. Welche Option Sie auswählen, hängt von der Anzahl der Richtlinien ab, die Sie verwalten, und von der Anzahl der Benutzer, der Sie Richtlinien zuweisen. Globale Richtlinien (Organisationsweite Standardrichtlinien) gelten für die größte Anzahl von Benutzern in Ihrer Organisation. Sie müssen nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

In diesem Artikel werden die verschiedenen Methoden beschrieben, mit denen Sie Benutzern Richtlinien zuweisen können, und die empfohlenen Szenarien für die Verwendung von was beschrieben.

Details zum Zuweisen von **Richtlinien zu Benutzern** und Gruppen finden Sie unter Zuweisen von Richtlinien zu Benutzern und [Gruppen.](assign-policies-users-and-groups.md) Details zum Zuweisen von **Richtlinienpaketen finden Sie** unter [Zuweisen von Richtlinienpaketen.](assign-policy-packages.md)

## <a name="which-policy-takes-precedence"></a>Welche Richtlinie hat Vorrang?

Ein Benutzer verfügt über eine effektive Richtlinie für jeden Richtlinientyp. Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer eine Richtlinie direkt zugewiesen wurde und er auch Mitglied einer oder mehreren Gruppen ist, denen eine Richtlinie desselben Typs zugewiesen ist. Welche Richtlinie hat in solchen Szenarien Vorrang? Die effektive Richtlinie eines Benutzers wird wie folgt anhand von Rangfolgeregeln festgelegt.

Wenn einem Benutzer eine Richtlinie direkt zugewiesen wird (entweder einzeln oder über eine Batchzuordnung), hat diese Richtlinie Vorrang. Im folgenden visuellen Beispiel ist die effektive Richtlinie des Benutzers die Besprechungsrichtlinie "Lincoln Square", die dem Benutzer direkt zugewiesen ist.

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

Wenn einem Benutzer keine Richtlinie eines bestimmten Typs direkt zugewiesen ist, hat die Richtlinie, die einer Gruppe zugewiesen ist, der der Benutzer gehört, Vorrang. Wenn ein Benutzer Mitglied mehrerer Gruppen ist, hat die Richtlinie mit der höchsten[Rangfolge](assign-policies-users-and-groups.md#group-assignment-ranking)(Gruppenzuordnungsrangfolge) für den angegebenen Richtlinientyp Vorrang.

In diesem visuellen Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams- und HD-Richtlinie, die im Vergleich zu anderen Gruppen, denen der Benutzer mitglied ist und denen auch eine Richtlinie desselben Richtlinientyps zugewiesen ist, die höchste Zuordnungsrangliste hat.  

![Diagramm, das zeigt, wie eine von einer Gruppe geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

Wenn einem Benutzer keine Richtlinie direkt zugewiesen ist oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp. Hier sehen Sie ein visuelles Beispiel.

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

Weitere Informationen finden Sie unter ([Rangfolgeregeln](assign-policies-users-and-groups.md#precedence-rules)).

## <a name="ways-to-assign-policies"></a>Methoden zum Zuweisen von Richtlinien

Im Folgenden finden Sie eine Übersicht über die Möglichkeiten, wie Sie Benutzern Richtlinien zuweisen können, und die empfohlenen Szenarien für die einzelnen Szenarien. Wählen Sie die Links aus, um weitere Informationen zu erhalten.

Bevor Sie einzelnen Benutzern oder Gruppen Richtlinien zuweisen, beginnen Sie mit dem Festlegen der globalen [Richtlinien (Organisationsweite](#set-the-global-policies) Standardrichtlinien), damit sie für die größte Anzahl von Benutzern in Ihrer Organisation gelten.  Nachdem die globalen Richtlinien festgelegt wurden, müssen Sie nur den Benutzern Richtlinien zuweisen, die spezielle Richtlinien erfordern.

|Gehen Sie dazu vor  |Wenn...  | Verwenden...
|---------|---------|----|
|[Zuweisen einer Richtlinie zu einzelnen Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | Sie sind neu in Teams und beginnen gerade erst, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen. |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul
|[Zuweisen einer Richtlinie zu einer Gruppe](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |Weisen Sie Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zu. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zu.| Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen einer Richtlinie zu einer Gruppe von Benutzern](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | Weisen Sie Großen Gruppen von Benutzern Richtlinien zu. Weisen Sie beispielsweise Hunderte oder Tausende von Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zu. |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu Benutzern](assign-policy-packages.md#assign-a-policy-package-to-users)  |Weisen Sie bestimmten Benutzergruppen in Ihrer Organisation mehrere Richtlinien zu, die über dieselben oder ähnliche Rollen verfügen. Weisen Sie beispielsweise lehrkräften Lehrkräften in Ihrer Schule das Richtlinienpaket Für Bildungseinrichtungen zu, damit sie voll auf Chats, Anrufe und Besprechungen zugreifen können. Weisen Sie den Sekundärschülern das Richtlinienpaket Für Bildungseinrichtungen (Sekundarstufe) zu, um bestimmte Funktionen wie private Anrufe zu beschränken.  |Die Microsoft Teams Admin Center- oder PowerShell-Cmdlets im Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu einer Gruppe](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in der privaten Vorschau)   |Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation mehrere Richtlinien zu, die über dieselben oder ähnliche Rollen verfügen. Weisen Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Verteilerliste ein Richtlinienpaket zu. |Das Microsoft Teams Admin Center (in Kürze verfügbar) oder PowerShell-Cmdlets im Microsoft Teams PowerShell-Modul|
|[Zuweisen eines Richtlinienpakets zu einer Gruppe von Benutzern](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|Weisen Sie einer Gruppe von Benutzern in Ihrer Organisation mehrere Richtlinien zu, die über dieselben oder ähnliche Rollen verfügen. Weisen Sie beispielsweise allen Lehrkräften in Ihrer Schule das Richtlinienpaket "Bildung (Lehrer) " zu, indem Sie Batchzuweisungen verwenden, um ihnen vollständigen Zugriff auf Chats, Anrufe und Besprechungen zu geben. Weisen Sie das Richtlinienpaket Für Bildungseinrichtungen (Sekundarstufe) einer Gruppe von Sekundärschülern zu, um bestimmte Funktionen wie private Anrufe zu beschränken.|PowerShell-Cmdlets im Teams PowerShell-Modul|

## <a name="set-the-global-policies"></a>Festlegen der globalen Richtlinien

Führen Sie die folgenden Schritte aus, um die globalen Richtlinien (organisationsweite Standardrichtlinien) für jeden Richtlinientyp zu festlegen.

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zur Richtlinienseite für den Richtlinientyp, den Sie aktualisieren möchten. Beispielsweise Teams   >  **Teams-Richtlinien,** **Besprechungsbesprechungsrichtlinien,**  >   **Messagingrichtlinien** oder **Sprachanrufrichtlinien.**  >  
2. Wählen Sie **die Richtlinie Global (Organisationsweite Standardrichtlinie)** aus, um die aktuellen Einstellungen anzeigen zu können.
3. Aktualisieren Sie die Richtlinie nach Bedarf, und wählen Sie dann **Übernehmen aus.**

![Aktualisieren der globalen Richtlinie im Teams Admin Center](media/assign-globalpolicy.png)

### <a name="using-powershell"></a>Verwendung von PowerShell

Zum Festlegen der globalen Richtlinien mit PowerShell verwenden Sie den globalen Bezeichner.  Überprüfen Sie zunächst die aktuelle globale Richtlinie, um zu ermitteln, welche Einstellung Sie ändern möchten.

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

## <a name="view-your-policy-assignments-in-the-activity-log"></a>Anzeigen Ihrer Richtlinienzuordnungen im Aktivitätsprotokoll

Wenn Sie Benutzern im Microsoft Teams Admin Center Richtlinien zuweisen, können Sie den Status dieser Richtlinienzuordnungen im Aktivitätsprotokoll anzeigen. Im Aktivitätsprotokoll werden Richtlinienzuordnungen zu Batches von mehr als 20 Benutzern über das Microsoft Teams Admin Center aus den letzten 30 Tagen angezeigt. Beachten Sie, dass im Aktivitätsprotokoll keine Richtlinienpaketzuordnungen, Richtlinienzuordnungen für Batches von weniger als 20 Benutzern über das Microsoft Teams Admin Center oder Richtlinienzuordnungen über PowerShell angezeigt werden.

![Screenshot der Seite "Aktivitätsprotokoll"](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a>Anzeigen ihrer Richtlinienzuordnungsaktivitäten im Aktivitätsprotokoll

So zeigen Sie Ihre Richtlinienzuordnungen im Aktivitätsprotokoll an:

1. Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Dashboard,** und wählen Sie dann unter Aktivitätsprotokoll die Option **Details anzeigen aus.**
2. Sie können alle Richtlinienzuordnungen anzeigen oder die Liste nach Status filtern, um nur Zuordnungen anzeigen zu können, die **nicht** gestartet, **In Bearbeitung** oder **Abgeschlossen sind.** Zu jeder Aufgabe werden die folgenden Informationen zu sehen sein:
    - **Name:** Der Name der Richtlinienzuordnung. Klicken Sie auf den Link, um weitere Details anzuzeigen. Dies umfasst die Anzahl der Benutzer, denen die Richtlinie zugewiesen wurde, und die Anzahl der abgeschlossenen, in Bearbeitung und nicht begonnenen Aufgaben. Außerdem werden die Liste der Benutzer im Batch sowie der Status und das Ergebnis für jeden Benutzer angezeigt. Nachfolgend ein Beispiel:

        ![Screenshot der](media/activity-log-policy-assignment-detail.png)

    - **Übermittelt:** Datum und Uhrzeit der Richtlinienzuordnung.
    - **Fertigstellungszeit:** Datum und Uhrzeit der Richtlinienzuordnung.
    - **Auswirkung auf**: Anzahl der Benutzer im Batch.
    - **Gesamtstatus:** Status der Richtlinienzuordnung.

> [!NOTE]
> Sie können auch über die Seite Benutzer auf das **Aktivitätsprotokoll** gelangen. Nachdem Sie auf **Übernehmen geklickt** haben, um eine Massenrichtlinienzuordnung zu übermitteln, wird oben auf der Seite ein Banner angezeigt. Klicken Sie **im** Banner auf den Link Aktivitätsprotokoll.

## <a name="related-topics"></a>Verwandte Themen

- [Zuweisen von Richtlinien zu Benutzern und Gruppen](assign-policies-users-and-groups.md)
- [Zuweisen von Richtlinienpaketen zu Benutzern und Gruppen](assign-policy-packages.md)
- [Verwalten von Teams mit Richtlinien](manage-teams-with-policies.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)