---
title: Verwalten der Erkennung privater Teams in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
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
description: Erfahren Sie, wie Sie steuern können, ob private Teams von Microsoft Teams-Benutzern mithilfe von Vorschlägen im Team Katalog und in den Suchergebnissen ermittelt werden können.
ms.openlocfilehash: e2e0ec956b40ff5e84bb29874c0dc567edefd034
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992010"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Verwalten der Erkennung privater Teams in Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Administratoren und Teambesitzer können steuern, ob private Teams von Microsoft Teams-Benutzern in Ihrer Organisation gefunden werden können. Wenn ein privates Team auffindbar ist, wird es in den Suchergebnissen angezeigt und in den Vorschlägen des Team Katalogs sowie in den öffentlichen Teams in Teams aufgeführt. Dadurch ist es für Benutzer einfach, die privaten Teams zu suchen und zu finden, denen Sie beitreten möchten. Benutzer können die Teilnahme an einem privaten Team anfordern, und ein Teambesitzer kann die Anforderung dann genehmigen oder ablehnen.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Übersicht über öffentliche Teams, private Teams und Discovery in Teams

Die meisten Organisationen verfügen über die folgenden Arten von Teams: öffentliche Teams, auffindbare private Teams und nicht auffindbare private Teams.

![Screenshot des Team Katalogs](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Öffentliche Teams

Öffentliche Teams stehen allen Benutzern in Ihrer Organisation für die Teilnahme zur Verfügung. Öffentliche Teams sind für jeden im Katalog "Teams" sichtbar, und Benutzer können an einem öffentlichen Team teilnehmen, ohne die Genehmigung des Team Besitzers zu erhalten. Beispiele für öffentliche Teams sind ein Team, in dem technologische Neuigkeiten besprochen werden, ein Team, das Feedback für Ihre Produkte erhält, und ein Team für Personen, die mit Fahrgemeinschaften zusammenarbeiten.

### <a name="discoverable-private-teams"></a>Auffindbare private Teams

Erkennbare private Teams können nur verbunden werden, wenn der Teambesitzer Ihnen Benutzer hinzufügt. Wenn Sie ein privates Team auffindbar machen, ist das Team in der Liste der vorgeschlagenen Teams und Suchergebnisse im Katalog "Teams" enthalten. Verwenden Sie auffindbare private Teams für Projekte und Gruppen in Ihrer Organisation, die jeder kennt und für die der Zugriff auf Unterhaltungen und Dateien im Team kontrolliert werden muss. Beispiele sind ein Team für Ihre Personalabteilung, ein Team für alle Manager in Ihrer Organisation sowie ein Team für einen Manager und deren direkte Berichte.

### <a name="non-discoverable-private-teams"></a>Nicht auffindbare private Teams

Nicht auffindbare private Teams können nur verbunden werden, wenn der Teambesitzer Benutzer hinzugefügt hat. Wenn Sie ein privates Team nicht auffindbar machen, wird es in der Liste der vorgeschlagenen Teams ausgeblendet und im Katalog "Teams" aus den Suchergebnissen entfernt. Verwenden Sie nicht auffindbare Teams, um an vertraulichen und hochgradig vertraulichen Themen zusammenzuarbeiten. Beispiele sind ein Team, das eine bevorstehende Akquisition und ein Team besprechen soll, um eine Änderung der strategischen Ausrichtung Ihres Unternehmens zu besprechen.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Festlegen, ob neue private Teams auffindbar sind

Wenn ein Teambesitzer ein privates Team erstellt, kann er durch Konfigurieren der Discovery-Einstellung des Teams feststellen, ob es auffindbar ist. Neue private Teams können standardmäßig durchsucht und auffindbar sein. Wenn der Teambesitzer nicht möchte, dass das private Team in Suchergebnissen und Vorschlägen angezeigt wird, kann der Besitzer die Einstellung deaktivieren, indem er die Einstellung **ändern** neben **diesem Team ist durchsuchbar und**auffindbar.

![Screenshot der Ermittlungs Einstellung für neue private Teams](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Festlegen, ob vorhandene private Teams erkennbar sind

Teambesitzer können die Ermittlungs Einstellung für ein vorhandenes privates Team direkt in den Team Einstellungen festlegen, und Administratoren können dies mithilfe von PowerShell tun.

### <a name="in-team-settings"></a>In Team Einstellungen

Wechseln Sie in Microsoft Teams zum privaten Team, und klicken Sie auf **Weitere Optionen** > **Team verwalten**. Erweitern Sie auf der Registerkarte **Einstellungen** die Option **Team Ermittlung**, und deaktivieren oder aktivieren Sie das Kontrollkästchen Verfüg **barkeit aktivieren** .

![Screenshot der Ermittlungs Einstellung für vorhandene private Teams](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>Verwenden von PowerShell

Verwenden Sie das Cmdlet " **[Satz-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** ", um die Ermittlungs Einstellung für ein vorhandenes privates Team zu deaktivieren oder zu aktivieren. Im folgenden finden Sie ein Beispiel dafür, wie Sie ein Team auffindbar machen können:
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
Sie können dieses Cmdlet in einem Skript verwenden, um die Ermittlungs Einstellung für vorhandene private Teams massenhaft festzulegen.

## <a name="set-whether-users-can-discover-private-teams"></a>Festlegen, ob Benutzer private Teams entdecken können

Als Administrator können Sie auch steuern, welche Benutzer in Ihrer Organisation private Teams in Suchergebnissen und Vorschlägen in Teams entdecken dürfen. Erstellen Sie eine Richtlinie mit dem Cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** , und weisen Sie die Richtlinie Benutzern zu.
 
Legen Sie den **AllowPrivateTeamDiscovery** -Parameter auf " **true** " fest, damit Benutzern, denen die Richtlinie zugewiesen ist, auffindbare private Teams in Suchergebnissen und Vorschlägen angezeigt werden. Durch Festlegen des **AllowPrivateTeamDiscovery** -Parameters auf " **false** " werden alle erkennbaren privaten Teams aus Suchergebnissen und Vorschlägen für Benutzer entfernt, denen die Richtlinie zugewiesen ist.

Standardmäßig ist **AllowPrivateTeamDiscovery** für alle Benutzer in einer Organisation auf **true** festgelegt.

In diesem Beispiel erstellen wir eine Richtlinie mit dem Namen "VendorPolicy", die verhindert, dass Benutzer alle privaten Teams entdecken können, die erkennbar sind, und weisen dann die Richtlinie einem Benutzer mit dem Namen "vendoruser1" zu.
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> Private Teams, die nicht auffindbar sind, werden unabhängig von der Richtlinieneinstellung nie in Suchergebnissen und Vorschlägen angezeigt. Wenn Sie beispielsweise die Ermittlungs Einstellung für ein privates Team deaktivieren, können Benutzer das Team nicht ermitteln, obwohl der **AllowPrivateTeamDiscovery** -Parameter in der Richtlinieneinstellung für diese Benutzer auf **true** festgelegt ist.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
