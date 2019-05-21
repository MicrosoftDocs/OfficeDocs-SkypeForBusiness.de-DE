---
title: Verwalten der Erkennung privater Teams in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie steuern können, ob private Teams von Microsoft Teams-Benutzern mithilfe von Vorschlägen im Team Katalog und in den Suchergebnissen ermittelt werden können.
ms.openlocfilehash: 55f127ff4dc9e5e0926e606c141b78f65c799de0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304402"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Verwalten der Erkennung privater Teams in Microsoft Teams

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

Administratoren und Teambesitzer können steuern, ob private Teams von Microsoft Teams-Benutzern in Ihrer Organisation gefunden werden können. Wenn ein privates Team auffindbar ist, wird es in den Suchergebnissen angezeigt und in den Vorschlägen des Team Katalogs sowie in den öffentlichen Teams in Teams aufgeführt. Dadurch ist es für Benutzer einfach, die privaten Teams zu suchen und zu finden, denen Sie beitreten möchten. Benutzer können die Teilnahme an einem privaten Team anfordern, das ein Teambesitzer genehmigen oder ablehnen kann.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Übersicht über öffentliche Teams, private Teams und Discovery in Teams

Die meisten Organisationen verfügen über die folgenden Arten von Teams: öffentliche Teams, auffindbare private Teams und nicht auffindbare private Teams.

![Team Katalog](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Öffentliche Teams

Öffentliche Teams stehen allen Benutzern in Ihrer Organisation für die Teilnahme zur Verfügung. Öffentliche Teams sind für alle Personen im Katalog "Teams" sichtbar, und Benutzer können einem öffentlichen Team beitreten, ohne die Genehmigung des Team Besitzers zu erhalten. Beispiele für öffentliche Teams sind ein Team, in dem Sie über Neuigkeiten in der Technologie diskutieren können, ein Team, das Dogfood-Feedback für Ihre Produkte erhält, und ein Team, in dem Personen mit Fahrgemeinschaften arbeiten können.

### <a name="discoverable-private-teams"></a>Auffindbare private Teams

Erkennbare private Teams können nur verbunden werden, wenn der Teambesitzer Ihnen Benutzer hinzufügt. Wenn Sie ein privates Team auffindbar machen, ist das Team in der Liste der vorgeschlagenen Teams und Suchergebnisse im Katalog "Teams" enthalten. Verwenden Sie auffindbare private Teams für Projekte und Gruppen in Ihrer Organisation, die jeder kennt und für die der Zugriff auf Unterhaltungen und Dateien im Team kontrolliert werden muss. Beispiele sind ein Team für Ihre Personalabteilung, ein Team für alle Manager in Ihrer Organisation sowie ein Team für einen Manager und deren direkte Berichte.

### <a name="non-discoverable-private-teams"></a>Nicht auffindbare private Teams

Nicht auffindbare private Teams können nur verbunden werden, wenn der Teambesitzer Benutzer hinzugefügt hat. Wenn Sie ein privates Team nicht auffindbar machen, wird es in der Liste der vorgeschlagenen Teams ausgeblendet und im Katalog "Teams" aus den Suchergebnissen entfernt. Verwenden Sie nicht auffindbare Teams, um an vertraulichen und hochgradig vertraulichen Themen zusammenzuarbeiten. Beispiele sind ein Team, das eine bevorstehende Akquisition und ein Team besprechen soll, um eine Änderung der strategischen Ausrichtung Ihres Unternehmens zu besprechen.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Festlegen, ob neue private Teams auffindbar sind

Wenn ein Teambesitzer ein privates Team erstellt, kann er durch Konfigurieren der Discovery-Einstellung des Teams feststellen, ob es auffindbar ist. Neue private Teams können standardmäßig durchsucht und auffindbar sein. Wenn der Teambesitzer nicht möchte, dass das private Team in Suchergebnissen und Vorschlägen angezeigt wird, können Sie die Einstellung deaktivieren, indem Sie die Einstellung " **ändern** " neben " **dieses Team ist durchsuchbar und**auffindbar" auswählen.

![Ermittlungs Einstellung für neue private Teams](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Festlegen, ob vorhandene private Teams erkennbar sind

Teambesitzer können die Ermittlungs Einstellung für ein vorhandenes privates Team direkt in den Team Einstellungen festlegen, und Administratoren können dies mithilfe von PowerShell tun.

### <a name="in-team-settings"></a>In Team Einstellungen

Wechseln Sie in Microsoft Teams zum privaten Team, klicken Sie auf **Weitere Optionen ̇ ̇ ̇** > **Team verwalten**. Erweitern Sie auf der Registerkarte **Einstellungen** die Option **Team Ermittlung**, und deaktivieren oder aktivieren Sie das Kontrollkästchen Verfüg **barkeit aktivieren** .

![Ermittlungs Einstellung für vorhandene private Teams](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a>Verwenden von PowerShell (in Kürze verfügbar)

Verwenden Sie das Cmdlet " **Satz-Team** ", um die Ermittlungs Einstellung für ein vorhandenes privates Team zu deaktivieren oder zu aktivieren. Im folgenden finden Sie ein Beispiel dafür, wie Sie ein Team auffindbar machen können:

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
Sie können dieses Cmdlet in einem Skript verwenden, um die Ermittlungs Einstellung für vorhandene private Teams massenhaft festzulegen.

## <a name="set-whether-users-can-discover-private-teams"></a>Festlegen, ob Benutzer private Teams entdecken können

Als Administrator können Sie auch steuern, welche Benutzer in Ihrer Organisation private Teams in Suchergebnissen und Vorschlägen in Teams entdecken dürfen. Erstellen Sie eine Richtlinie mit dem Cmdlet **New-CsTeamsChannelsPolicy** , und weisen Sie die Richtlinie Benutzern zu.
 
Legen Sie den **AllowPrivateTeamDiscovery** -Parameter auf " **true** " fest, damit Benutzern, denen die Richtlinie zugewiesen ist, auffindbare private Teams in Suchergebnissen und Vorschlägen angezeigt werden. Durch Festlegen des **AllowPrivateTeamDiscovery** -Parameters auf " **false** " werden alle erkennbaren privaten Teams aus Suchergebnissen und Vorschlägen für Benutzer entfernt, denen die Richtlinie zugewiesen ist.

Standardmäßig ist **AllowPrivateTeamDiscovery** für alle Benutzer in einer Organisation auf **true** festgelegt.

In diesem Beispiel erstellen wir eine Richtlinie mit dem Namen "VendorPolicy", die verhindert, dass Benutzer alle privaten Teams entdecken können, die erkennbar sind, und weisen dann die Richtlinie einem Benutzer mit dem Namen "vendoruser1" zu. 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> Private Teams, die nicht auffindbar sind, werden unabhängig von der Richtlinieneinstellung nie in Suchergebnissen und Vorschlägen angezeigt. Wenn Sie beispielsweise die Ermittlungs Einstellung für ein privates Team deaktivieren, können Benutzer das Team nicht ermitteln, obwohl der **AllowPrivateTeamDiscovery** -Parameter in der Richtlinieneinstellung für diese Benutzer auf **true** festgelegt ist.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)