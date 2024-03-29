---
title: Microsoft 365-Gruppen und Microsoft Teams
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
description: Erfahren Sie, wie Microsoft 365 Gruppen und Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125430"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365-Gruppen und Microsoft Teams

Microsoft 365-Gruppen ist der anwendungsübergreifende Mitgliedschaftsdienst in Microsoft 365. Auf einer grundlegenden Ebene ist eine Microsoft 365 Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer Kopplung mit verwandten Workloads, einschließlich einer SharePoint Teamwebsite, freigegebenem Exchange Postfach, Planner und OneNote Notizbuch. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

![Diagramm mit Microsoft 365-Gruppen und zugehörigen Diensten](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Standardmäßig können Benutzer in Microsoft 365 Gruppen erstellen und verwalten. Weitere Informationen zu Microsoft 365-Gruppen finden [Sie auf dem Poster "Informationen zu Microsoft 365-Gruppen](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) und den [Gruppen in Microsoft 365 für IT-Architekten](teams-architecture-solutions-posters.md#groups-in-microsoft-365)".

## <a name="how-microsoft-365-groups-work-with-teams"></a>Wie Microsoft 365-Gruppen mit Teams arbeiten

Wenn Sie ein Team erstellen, wird eine Microsoft 365 Gruppe erstellt, um die Teammitgliedschaft zu verwalten. Die zugehörigen Dienste der Gruppe, z. B. eine SharePoint Website, ein Postfach usw., werden gleichzeitig erstellt.

Personen, die Teams erstellen, können eine vorhandene Microsoft 365 Gruppe verwenden, wenn sie Besitzer dieser Gruppe sind. Jeder Kanal im Team verfügt über einen separaten Ordner in der Dokumentbibliothek. Durch das Erstellen von Ordnern direkt in der Dokumentbibliothek werden keine Kanäle im Team erstellt.

Beim Erstellen einer Microsoft 365 Gruppe in Outlook oder SharePoint wird das Gruppenpostfach in Outlook angezeigt. Beim Erstellen eines Teams in Teams ist das Gruppenpostfach standardmäßig ausgeblendet. Sie können das [Cmdlet Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) mit dem Parameter **HiddenFromExchangeClientsEnabled** verwenden, um ein Postfach sichtbar zu machen.

## <a name="group-membership"></a>Gruppenmitgliedschaft

Wenn Sie ein Mitglied eines Teams entfernen, wird es auch aus der Microsoft 365 Gruppe entfernt. Durch das Entfernen aus der Gruppe werden das Team und die Kanäle unmittelbar vom Teams-Client entfernt. Wenn Sie eine Person aus einer Gruppe über das Microsoft 365-Admin Center entfernen, hat diese keinen Zugriff mehr auf die anderen kollaborativen Elementen wie die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder freigegebene OneNote. Sie haben jedoch weiterhin ca. zwei Stunden Lang Zugriff auf die Chatfunktionen des Teams.

Als bewährte Methode zum Verwalten von Teammitgliedern sollten Sie diese dem Teams-Client hinzufügen und daraus entfernen, um sicherzustellen, dass Berechtigungsupdates für andere mit einer Gruppe verbundene Workloads schnell erfolgen. Wenn Sie Teammitglieder außerhalb des Teams-Clients hinzufügen oder entfernen (mithilfe der Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell), kann es bis zu 24 Stunden dauern, bis Änderungen in Teams widergespiegelt werden.

## <a name="deleting-groups-and-teams"></a>Löschen von Gruppen und Teams

Durch das Löschen einer Microsoft 365 Gruppe wird der Postfachalias für beständige Outlook/OWA-Unterhaltungen und Teams Besprechungseinladungen entfernt und die SharePoint Website zum Löschen markiert. Es dauert ungefähr 20 Minuten, bis sich die Entfernung eines Teams auf Outlook auswirkt. Durch das Löschen eines Teams vom Teams-Client wird dieses sofort für alle Mitglieder des Teams ausgeblendet. Wenn Sie Mitglieder einer Microsoft 365 Gruppe entfernen, für die Teams Funktionen aktiviert wurden, kann es zu einer Verzögerung von etwa zwei Stunden kommen, bevor das Team im Teams Client für die betroffenen Personen, die entfernt wurden, aus der Ansicht entfernt wird.

Ausführliche Informationen zu den Optionen für das Ende des Lebenszyklus von Gruppen und Teams finden Sie unter "[Ende des Lebenszyklus" für Gruppen, Teams und Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) und ["Archiven" oder "Löschen eines Teams in Microsoft Teams](./archive-or-delete-a-team.md)".

## <a name="related-topics"></a>Verwandte Themen

[Grundlagen der Microsoft Teams (Video)](https://aka.ms/teams-foundations)

[Wiederherstellen einer gelöschten Gruppe](/microsoft-365/admin/create-groups/restore-deleted-group)
