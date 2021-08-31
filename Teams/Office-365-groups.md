---
title: Microsoft 365 Gruppen und Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, Microsoft 365 Gruppen und Gruppenmitgliedschaften mit anderen Microsoft Teams.
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729734"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Gruppen und Microsoft Teams

Microsoft 365 Gruppen ist der anwendungsübergreifende Mitgliedschaftsdienst in Microsoft 365. Auf einer grundlegenden Ebene ist eine Microsoft 365-Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer Kopplung für verwandte Arbeitslasten, einschließlich einer SharePoint-Teamwebsite, eines freigegebenen Exchange-Postfachs, eines Planner- und Power BI-Arbeitsbereichs. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

![Diagramm, das Microsoft 365 Gruppen und zugehörige Dienste zeigt.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Standardmäßig können Benutzer in Microsoft 365 Gruppen erstellen und verwalten. Weitere Informationen zu Microsoft 365 Gruppen finden Sie unter Weitere Informationen [zu Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) Gruppen und den Postern "Gruppen in Microsoft 365 for [IT Architects".](teams-architecture-solutions-posters.md#groups-in-microsoft-365)

## <a name="how-microsoft-365-groups-work-with-teams"></a>Zusammenarbeit Microsoft 365 Gruppen mit Teams

Wenn Sie ein Team erstellen, wird Microsoft 365 Gruppe erstellt, um die Teammitgliedschaft zu verwalten. Die zugehörigen Dienste der Gruppe, z. B. eine SharePoint-Website, ein Power BI usw., werden gleichzeitig erstellt.

Personen, die Teams erstellen, können sich entscheiden, eine vorhandene Microsoft 365-Gruppe zu verwenden, wenn sie der Besitzer dieser Gruppe sind. Jeder Kanal im Team verfügt über einen eigenen Ordner in der Dokumentbibliothek. Durch das Erstellen von Ordnern direkt in der Dokumentbibliothek werden im Team keine Kanäle erstellt.

Beim Erstellen einer Microsoft 365 Gruppe in Outlook oder SharePoint Gruppenpostfachs wird das Gruppenpostfach im Outlook. Wenn Sie ein Team in Teams erstellen, ist das Gruppenpostfach standardmäßig ausgeblendet. Sie können das [Cmdlet "Set-UnifiedGroup"](/powershell/module/exchange/users-and-groups/set-unifiedgroup) mit dem **Parameter HiddenFromExchangeClientsEnabled** verwenden, um ein Postfach sichtbar zu machen.

## <a name="group-membership"></a>Gruppenmitgliedschaft

Wenn Sie ein Mitglied eines Teams entfernen, wird es auch aus Microsoft 365 Gruppe entfernt. Durch das Entfernen aus der Gruppe werden das Team und die Kanäle unmittelbar vom Teams-Client entfernt. Wenn Sie eine Person aus einer Gruppe über das Microsoft 365-Admin Center entfernen, hat diese keinen Zugriff mehr auf die anderen kollaborativen Elementen wie die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder freigegebene OneNote. Sie haben jedoch für etwa zwei Stunden weiterhin Zugriff auf die Chatfunktionen des Teams.

Als bewährte Methode zum Verwalten von Teammitgliedern fügen Sie diese dem Teams-Client hinzu, und entfernen Sie sie, um sicherzustellen, dass Die Berechtigungen für andere mit einer Gruppe verbundene Workloads schnell aktualisiert werden. Wenn Sie Teammitglieder außerhalb des Teams-Clients hinzufügen oder entfernen (mithilfe von Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell), kann es bis zu 24 Stunden dauern, bis Änderungen in den Teams.

## <a name="deleting-groups-and-teams"></a>Löschen von Gruppen und Teams

Beim Löschen einer Microsoft 365-Gruppe wird der Postfachalias für beständige Outlook/OWA-Unterhaltungen und Teams-Besprechungs-Einladungen entfernt und die SharePoint-Website zum Löschen markiert. Es dauert ungefähr 20 Minuten, bis sich die Entfernung eines Teams auf Outlook auswirkt. Durch das Löschen eines Teams vom Teams-Client wird dieses sofort für alle Mitglieder des Teams ausgeblendet. Wenn Sie Mitglieder einer Microsoft 365-Gruppe entfernen, für die die Teams-Funktionalität aktiviert war, kann es zu einer Verzögerung von etwa zwei Stunden kommen, bevor das Team für die betroffenen Personen, die entfernt wurden, aus der Ansicht im Teams-Client entfernt wird.

Details zu den Optionen für das Ende des Lebenszyklus von Gruppen und Teams finden Sie unter Lebenszyklusendeoptionen für [Gruppen, Teams](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) und Yammer und Archivieren oder Löschen eines Teams [in Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Verwandte Themen

[Grundlagen der Microsoft Teams (Video)](https://aka.ms/teams-foundations)

[Wiederherstellen einer gelöschten Gruppe](/microsoft-365/admin/create-groups/restore-deleted-group)