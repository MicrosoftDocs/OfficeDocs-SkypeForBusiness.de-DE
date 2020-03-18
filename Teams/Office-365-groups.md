---
title: Office 365-Gruppen und Microsoft Teams
ms.reviewer: phlouie
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: Erfahren Sie, wie Office 365-Gruppen und -Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1bd45d942784f9454acff5636359e172059f22cc
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834335"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365-Gruppen und Microsoft Teams
=====================================

> [!Tip]
> Erfahren Sie in der folgenden Sitzung, wie Teams mit Azure Active Directory (Azure AD), Office 365-Gruppen, Exchange, SharePoint und OneDrive for Business interagiert: [Microsoft Teams – Grundlagen](https://aka.ms/teams-foundations)

Bei Office 365-Gruppen handelt es sich um den anwendungsübergreifenden Mitgliedschaftsdienst in Office 365. Grundsätzlich ist eine Office 365-Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer losen Kopplung zu verwandten Workloads. Dazu zählen eine SharePoint-Teamwebsite, eine Yammer-Gruppe, freigegebene Exchange-Postfachressourcen, Planner, Power BI und OneNote. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

Ein Office 365-Administrator kann eine Office 365-Gruppe definieren, Mitglieder hinzufügen und die Vorteile von Funktionen nutzen, wie zum Beispiel das freigegebene Exchange-Postfach, die SharePoint-Dokumentbibliothek, die Yammer-Gruppe usw. Näheres über Office 365-Gruppen finden Sie unter [Weitere Informationen zu Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Das Poster [Gruppen in Microsoft 365 für IT-Architekten](teams-architecture-solutions-posters.md#groups-in-microsoft-365) dürfte Sie ebenfalls interessieren.

<a name="how-office-365-groups-work"></a>Funktionsweise von Office 365-Gruppen
--------------------------

Wenn Sie ein Team erstellen, erstellen Sie im Back-End eine Office 365-Gruppe, die zugeordnete SharePoint-Dokumentbibliothek und das OneNote-Notizbuch sowie Verbindungen zu anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt, Besitzer einer bestehenden öffentlichen oder privaten Office 365-Gruppe ist, kann sie dieser Gruppe Teams-Funktionen hinzufügen, sofern sie weniger als 5000 Personen umfasst und noch nie zu Microsoft Teams hinzugefügt wurde. Dadurch wird ein **Allgemein**-Standardkanal erstellt, in dem sich Chatnachrichten, Dokumente, OneNote und andere Objekte befinden. Wenn Sie die Dokumentbibliothek für den Kanal anzeigen, wird der **Allgemein**- Ordner angezeigt, der den Kanal im Team darstellt. Noch wichtiger ist: Wenn Sie eine eigene Ordnerstruktur in einer Dokumentbibliothek erstellen, **wird diese nicht als Kanal an Teams weitergegeben**. Gegenwärtig ist die Flussrichtung ausschließlich von Teams zu SharePoint.

> [!NOTE]
> Aufgrund von Kundenfeedback werden neue Office 365-Gruppen, die bei der Erstellung eines Teams in Microsoft Teams generiert werden, nicht mehr standardmäßig in Outlook angezeigt. Für Kunden, die das bisherige Verhalten (Anzeigen dieser Gruppen in Outlook) bevorzugen, wird ein Exchange Online PowerShell-Cmdlet bereitgestellt, mit dem sie Gruppen für Outlook aktivieren können. Gruppen, die über Outlook erstellt und dann später für Microsoft Teams aktiviert wurden, werden weiterhin in Outlook und in Microsoft Teams angezeigt. Dieses Update wird in den nächsten Monaten schrittweise in Outlook und Microsoft Teams eingeführt.

> [!NOTE]
> Beim Löschen einer Office 365-Gruppe wird der Postfachalias für beständige Outlook/OWA-Unterhaltungen und Teams-Besprechungseinladungen entfernt, und die SharePoint-Website wird als löschbar gekennzeichnet. Es dauert ungefähr 20 Minuten, bis sich die Entfernung eines Teams auf Outlook auswirkt. Durch das Löschen eines Teams vom Teams-Client wird dieses sofort für alle Mitglieder des Teams ausgeblendet. Wenn Sie Mitglieder einer Office 365-Gruppe entfernen, in der Teams-Funktionen aktiviert sind, kann es zu einer Verzögerung von ca. zwei Stunden kommen, bevor das Team für die Personen, die entfernt wurden, im Teams-Client ausgeblendet wird.
>
>[Hier](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) finden Sie Informationen zum Wiederherstellen einer gelöschten Office 365-Gruppe.

<a name="group-membership"></a>Gruppenmitgliedschaft
----------------

Die Gruppenfeatures und -funktionen für Ihre Benutzer sind davon abhängig, von wo aus Sie die Gruppenmitgliedschaft verwalten. Wenn Sie beispielsweise ein Mitglied aus einem Team entfernen, wird dieses auch aus der entsprechenden Office 365-Gruppe entfernt. Durch das Entfernen aus der Gruppe werden das Team und die Kanäle unmittelbar vom Teams-Client entfernt. Wenn Sie eine Person aus einer Gruppe über das Microsoft 365-Admin Center entfernen, hat diese keinen Zugriff mehr auf die anderen kollaborativen Elementen wie die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder freigegebene OneNote. Allerdings hat sie noch ca. zwei Stunden lang Zugriff auf die Chatfunktion des Teams.

Eine bewährte Methode zum Verwalten von Teammitgliedern besteht darin, Mitglieder über den Teams-Client hinzuzufügen und zu entfernen, um sicherzustellen, dass die Weitergabe der Zugriffssteuerung an andere abhängige Cloud-Anwendungen ordnungsgemäß angewendet wird. Darüber hinaus wird dadurch vermieden, dass Benutzer den Eindruck haben, weiterhin auf die gewohnten Ressourcen zugreifen zu können (bis beim nächsten Synchronisierungszyklus der Zugriff auf eine bestimmte Komponente des Dienstes hinzugefügt oder widerrufen wird).  Wenn Sie Teammitglieder außerhalb des Teams-Clients (mithilfe des Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell) hinzufügen oder entfernen, kann es bis zu zwei Stunden dauern, bis die entsprechenden Änderungen in Teams übernommen werden.
