---
title: Verwalten der Suche von privaten Teams in Microsoft-Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie gesteuert wird, ob private Teams durch Microsoft-Teams, Benutzer über Vorschläge in die Team-Katalog und die Suchergebnisse ermittelt werden können.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262758"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a>Verwalten der Suche von privaten Teams in Microsoft-Teams

Administratoren und Team Besitzer können gesteuert wird, ob private Teams von Benutzern in Ihrer Organisation Microsoft-Teams, der ermittelt werden können. Wenn eine private Team sichtbar ist, wird in den Suchergebnissen und in Vorschläge im Katalog Team zusammen mit öffentlichen Teams in Teams enthalten ist. Dies erleichtert Benutzern suchen, und suchen Sie nach der privaten Teams, die sie teilnehmen möchten. Benutzer können auf einem privaten Team stoßen, das Teambesitzer einer genehmigen oder verweigern kann anfordern.

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a>Übersicht über öffentliche Teams, private Teams und Erkennung in Teams

Die meisten Organisationen verfügen über die folgenden Arten von Teams - öffentliche Teams, eDiscovery-fähigen private Teams und nicht erkennbaren private Teams.

![Team-Katalog](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a>Öffentliche teams

Öffentliche Teams stehen für alle Benutzer in Ihrer Organisation zur Teilnahme an. Öffentliche Teams für alle Benutzer in der Galerie Teams sichtbar sind, und Benutzer können eine öffentliche Team teilnehmen, ohne Genehmigung vom Teambesitzer erhalten möchten. Beispiele für Öffentliche Teams sind ein Team um Neuigkeiten in Technologie, ein Team, Dogfood Feedback für Ihre Produkte zu erhalten und ein Team für Personen Fahrgemeinschaften zu besprechen.

### <a name="discoverable-private-teams"></a>EDiscovery-fähigen private teams

EDiscovery-fähigen private Teams können nur hinzugefügt werden, wenn der Teambesitzer für diese Benutzer hinzugefügt. Wenn Sie einen privaten Team auffindbar sind, ist das Team in der Liste der vorgeschlagenen Teams und der Suchergebnisse im Katalog Teams enthalten. Verwenden Sie eDiscovery-fähigen private Teams für Projekte und Gruppen in Ihrer Organisation, die jeder kennt und dabei den Zugriff auf Unterhaltungen und Dateien in das Team gesteuert werden müssen. Beispiele sind ein Team für die HR-Abteilung, ein Team für alle Führungskräfte in Ihrer Organisation und ein Team für einen Manager und ihre Mitarbeiter.

### <a name="non-discoverable-private-teams"></a>Nicht sichtbar private teams

Nicht sichtbar private Teams können nur hinzugefügt werden, wenn der Teambesitzer für diese Benutzer hinzugefügt. Wenn Sie einen privaten Team nicht auffindbar zu machen, hat sie aus der Liste der vorgeschlagenen Teams ausgeblendet und aus den Suchergebnissen in der Galerie Teams entfernt. Verwenden Sie nicht erkennbaren Teams, um vertrauliche und streng vertraulich Themen zusammenzuarbeiten. Beispiele: ein Team, um eine bevorstehende Übernahme zu besprechen und ein Team eine Änderung in Ihrer Organisation strategische Ausrichtung besprechen.

## <a name="set-whether-new-private-teams-are-discoverable"></a>Festlegen Sie, ob neue private Teams erkannt werden.

Wenn ein Teambesitzer ein privates Teams erstellt, können sie es sichtbar machen, indem Sie das Team Discovery-Einstellung konfigurieren. Standardmäßig sind neue private Teams durchsuchbar und sichtbar. Wenn Teambesitzer das private Team in den Suchergebnissen und Vorschläge angezeigt wird nicht möchte, können sie die Einstellung deaktivieren, durch Auswählen der **Einstellung ändern** **dieses Team durchsuchbar und sichtbar ist**.

![Discovery-Einstellung für neue private teams](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a>Festlegen Sie, ob die vorhandenen privaten Teams erkannt werden.

Team Besitzer können die Discovery-Einstellung für eine vorhandene private Team direkt in die Team-Einstellungen und Administratoren können dazu mithilfe von PowerShell.

### <a name="in-team-settings"></a>In den Team-Einstellungen

Wechseln Sie in Teams, an das Team der private, klicken Sie auf **Weitere Optionen ˙˙˙** > **Team verwalten**. Auf der Registerkarte **Einstellungen** **Team Discovery**, erweitern und deaktivieren oder aktivieren Sie das Kontrollkästchen **Auffindbarkeit zu aktivieren** .

![Discovery-Einstellung für vorhandene private teams](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a>Verwenden von PowerShell

Verwenden Sie das Cmdlet " **Set-Team** " zu deaktivieren oder aktivieren auf der Discovery-Einstellung für eine vorhandene private Team. Es folgt ein Beispiel dafür, wie Sie ein Team auffindbar sind:

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
Dieses Cmdlet können in einem Skript Sie die Ermittlung der vorhandenen privaten Teams in einer Sammeloperation eingestellt.

## <a name="set-whether-users-can-discover-private-teams"></a>Festlegen Sie, ob Benutzer private Teams erkennen können

Als Administrator können Sie auch steuern, private Teams in den Suchergebnissen und Vorschläge in Teams ermitteln können, welche Benutzer in Ihrer Organisation zulässig sind. Erstellen Sie eine Richtlinie mit dem Cmdlet **New-CsTeamsChannelsPolicy** , und weisen Sie die Richtlinie für Benutzer.
 
Legen Sie den **AllowPrivateTeamDiscovery** -Parameter auf **true fest,** um Benutzern zu ermöglichen, die die Richtlinie für eDiscovery-fähigen private Teams in Suchergebnissen und Vorschläge finden Sie unter zugewiesen sind. Den Parameter **AllowPrivateTeamDiscovery** auf **false** festlegen entfernt alle eDiscovery-fähigen private Teams aus den Suchergebnissen und Vorschläge für Benutzer, die die Richtlinie zugewiesen werden.

**AllowPrivateTeamDiscovery** ist standardmäßig auf **"true"** für alle Benutzer in einer Organisation festgelegt.

In diesem Beispiel erstellen wir eine Richtlinie mit dem Namen VendorPolicy, die verhindert, dass Benutzer ermitteln private Teams, die sichtbar gemacht werden, und klicken Sie dann weisen wir die Richtlinie für einen Benutzer mit dem Namen vendoruser1. 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> Private Teams, die nicht sichtbar sind werden nie in den Suchergebnissen und Vorschläge, ungeachtet der richtlinieneinstellung angezeigt. Beispielsweise wenn Sie die Discovery-Einstellung für eine private Team deaktivieren, können Benutzer nicht ermitteln können, das Team, obwohl der **AllowPrivateTeamDiscovery** -Parameter auf **"true"** in der richtlinieneinstellung für diesen Benutzer festgelegt ist.

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)