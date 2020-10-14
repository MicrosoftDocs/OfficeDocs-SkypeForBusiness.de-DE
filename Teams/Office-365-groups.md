---
title: Microsoft 365-Gruppen und Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Microsoft 365-Gruppen und Gruppenmitgliedschaften mit Microsoft Teams zusammenarbeiten.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456079"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365-Gruppen und Microsoft Teams

Microsoft 365 Groups ist der Anwendungsübergreifende Mitgliedschaftsdienst in Microsoft 365. Auf grundlegender Ebene ist eine Microsoft 365-Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer Kopplung mit zugehörigen Arbeitslasten, einschließlich einer SharePoint-Teamwebsite, einem freigegebenen Exchange-Postfach, Planner und Power BI-Arbeitsbereich. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

![Diagramm mit Microsoft 365-Gruppen und zugehörigen Diensten](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Standardmäßig können Benutzer in Microsoft 365 Gruppen erstellen und verwalten. Weitere Informationen zu Microsoft 365-Gruppen finden Sie unter Informationen [zu Microsoft 365-Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) und den [Gruppen in Microsoft 365 für IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) -Poster.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Funktionsweise von Microsoft 365-Gruppen mit Teams

Wenn Sie ein Team erstellen, wird eine Microsoft 365-Gruppe erstellt, um die Teammitgliedschaft zu verwalten. Die zugehörigen Dienste der Gruppe, beispielsweise eine SharePoint-Website, Power BI-Arbeitsbereich usw., werden gleichzeitig erstellt.

Personen, die Teams erstellen, können eine vorhandene Microsoft 365-Gruppe verwenden, wenn Sie ein Besitzer dieser Gruppe sind. Jeder Kanal im Team verfügt über einen separaten Ordner in der Dokumentbibliothek. Durch das direkte Erstellen von Ordnern in der Dokumentbibliothek werden keine Kanäle im Team erstellt.

Wenn Sie eine Microsoft 365-Gruppe in Outlook oder SharePoint erstellen, wird das Gruppenpostfach in Outlook angezeigt. Wenn Sie ein Team in Teams erstellen, ist das Gruppenpostfach standardmäßig ausgeblendet. Sie können das Cmdlet " [Satz-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) " mit dem **HiddenFromExchangeClientsEnabled** -Parameter verwenden, um ein Postfach sichtbar zu machen.

## <a name="group-membership"></a>Gruppenmitgliedschaft

Wenn Sie ein Mitglied eines Teams entfernen, werden diese auch aus der Microsoft 365-Gruppe entfernt. Durch das Entfernen aus der Gruppe werden das Team und die Kanäle unmittelbar vom Teams-Client entfernt. Wenn Sie eine Person aus einer Gruppe über das Microsoft 365-Admin Center entfernen, hat diese keinen Zugriff mehr auf die anderen kollaborativen Elementen wie die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder freigegebene OneNote. Sie haben jedoch für etwa zwei Stunden weiterhin Zugriff auf die Chatfunktion des Teams.

Als bewährte Methode zum Verwalten von Teammitgliedern können Sie Sie dem Teams-Client hinzufügen und daraus entfernen, um sicherzustellen, dass Berechtigungs Updates für andere mit der Gruppe verbundene Arbeitslasten schnell erfolgen. Wenn Sie Teammitglieder außerhalb des Teams-Clients (mithilfe von Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell) hinzufügen oder entfernen, kann es bis zu 24 Stunden dauern, bis Änderungen in Teams wiedergegeben werden.

## <a name="deleting-groups-and-teams"></a>Löschen von Gruppen und Teams

Wenn Sie eine Microsoft 365-Gruppe löschen, wird der Post Fach Alias für beständige Outlook/OWA-Unterhaltungen und Teams-Besprechungseinladungen entfernt, und die SharePoint-Website wird zum Löschen markiert. Es dauert ungefähr 20 Minuten, bis sich die Entfernung eines Teams auf Outlook auswirkt. Durch das Löschen eines Teams vom Teams-Client wird dieses sofort für alle Mitglieder des Teams ausgeblendet. Wenn Sie Mitglieder einer Microsoft 365-Gruppe entfernen, für die die Funktion Teams aktiviert war, kann es eine Verzögerung von etwa zwei Stunden geben, bevor das Team für die betroffenen Personen aus der Ansicht entfernt wird, die entfernt wurden.

Details zu den Optionen für das Ende des Lebenszyklus von Gruppen und Teams finden Sie unter  [Optionen für das Ende des Lebenszyklus für Gruppen, Teams und jammern](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) sowie zum [archivieren oder Löschen eines Teams in Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Verwandte Themen

[Grundlagen von Microsoft Teams (Video)](https://aka.ms/teams-foundations)

[Wiederherstellen einer gelöschten Gruppe](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)