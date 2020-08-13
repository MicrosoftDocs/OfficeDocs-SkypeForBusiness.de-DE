---
title: Microsoft 365-Gruppen und Microsoft Teams
ms.reviewer: Kyle Blevins
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 04/16/2019
ms.topic: conceptual
audience: admin
ms.service: msteams
description: In diesem Artikel erfahren Sie, wie Microsoft 365-Gruppen und Gruppenmitgliedschaften mit Microsoft Teams zusammenarbeiten.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4861683d3c46eaa6122ffbac0d2ae17b4f3a7979
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655996"
---
<a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365-Gruppen und Microsoft Teams
=====================================

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (Azure AD), Microsoft 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Microsoft 365 Groups ist der Anwendungsübergreifende Mitgliedschaftsdienst in Office 365. Auf der grundlegenden Ebene ist eine Microsoft 365-Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer losen Kopplung an verwandte Arbeitslasten, einschließlich einer SharePoint-Teamwebsite, einer Gruppe "jammern", freigegebenen Exchange-Postfachressourcen, Planner, Power BI und OneNote. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

Ein Office 365-Administrator kann eine Microsoft 365-Gruppe definieren, Mitglieder hinzufügen und von Features wie einem freigegebenen Exchange-Postfach, einer SharePoint-Dokumentbibliothek, einer Gruppe "jammern" usw. profitieren. Weitere Informationen zu Microsoft 365-Gruppen finden Sie unter Informationen [zu Microsoft 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Das Poster [Gruppen in Microsoft 365 für IT-Architekten](teams-architecture-solutions-posters.md#groups-in-microsoft-365) dürfte Sie ebenfalls interessieren.

<a name="how-microsoft-365-groups-work"></a>Funktionsweise von Microsoft 365-Gruppen
--------------------------

Wenn Sie ein Team erstellen, erstellen Sie im Back-End eine Microsoft 365-Gruppe und die zugehörige SharePoint-Dokumentbibliothek und das OneNote-Notizbuch sowie Verbindungen zu anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt, ein Besitzer einer vorhandenen öffentlichen oder privaten Gruppe von Office 365 ist, können Sie der Gruppe Teamfunktionen hinzufügen, wenn die Anzahl der Mitglieder in der Gruppe innerhalb der in den [Grenzwerten und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) angegebenen Grenzwerte liegt und die Gruppe nie zu Teams hinzugefügt wurde. Dadurch wird ein **Allgemein**-Standardkanal erstellt, in dem sich Chatnachrichten, Dokumente, OneNote und andere Objekte befinden. Wenn Sie die Dokumentbibliothek für den Kanal anzeigen, wird der **Allgemein**- Ordner angezeigt, der den Kanal im Team darstellt. Noch wichtiger ist: Wenn Sie eine eigene Ordnerstruktur in einer Dokumentbibliothek erstellen, **wird diese nicht als Kanal an Teams weitergegeben**. Gegenwärtig ist die Flussrichtung ausschließlich von Teams zu SharePoint.

> [!NOTE]
> Basierend auf Kundenfeedback werden neue Microsoft 365-Gruppen, die als Ergebnis des Erstellens eines Teams in Microsoft Teams-Client generiert werden, standardmäßig nicht mehr in Outlook angezeigt. Verwenden Sie das Cmdlet " [Satz-Unifiedgroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) " mit dem **HiddenFromExchangeClientsEnabled** -Parameter, um die Anzeige von Gruppen in Outlook zu aktivieren oder zu deaktivieren. Gruppen, die über Outlook erstellt und dann später für Microsoft Teams aktiviert wurden, werden weiterhin in Outlook und in Microsoft Teams angezeigt. 

> [!NOTE]
> Wenn Sie eine Microsoft 365-Gruppe löschen, wird der Post Fach Alias für beständige Outlook/OWA-Unterhaltungen und Teams-Besprechungseinladungen entfernt, und die SharePoint-Website wird zum Löschen markiert. Es dauert ungefähr 20 Minuten, bis sich die Entfernung eines Teams auf Outlook auswirkt. Durch das Löschen eines Teams vom Teams-Client wird dieses sofort für alle Mitglieder des Teams ausgeblendet. Wenn Sie Mitglieder einer Microsoft 365-Gruppe entfernen, für die die Funktion Teams aktiviert war, kann es eine Verzögerung von etwa zwei Stunden geben, bevor das Team für die betroffenen Personen aus der Ansicht entfernt wird, die entfernt wurden.
>
>Informationen zum Wiederherstellen einer gelöschten Microsoft 365-Gruppe finden Sie [hier](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) .

<a name="group-membership"></a>Gruppenmitgliedschaft
----------------

Die Gruppenfeatures und -funktionen für Ihre Benutzer sind davon abhängig, von wo aus Sie die Gruppenmitgliedschaft verwalten. Wenn Sie beispielsweise ein Mitglied eines Teams entfernen, werden diese auch aus der Microsoft 365-Gruppe entfernt. Durch das Entfernen aus der Gruppe werden das Team und die Kanäle unmittelbar vom Teams-Client entfernt. Wenn Sie eine Person aus einer Gruppe über das Microsoft 365-Admin Center entfernen, hat diese keinen Zugriff mehr auf die anderen kollaborativen Elementen wie die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder freigegebene OneNote. Sie haben jedoch für etwa zwei Stunden weiterhin Zugriff auf die Chatfunktion des Teams.

Eine bewährte Methode zum Verwalten von Teammitgliedern besteht darin, Mitglieder über den Teams-Client hinzuzufügen und zu entfernen, um sicherzustellen, dass die Weitergabe der Zugriffssteuerung an andere abhängige Cloud-Anwendungen ordnungsgemäß angewendet wird. Darüber hinaus wird dadurch vermieden, dass Benutzer den Eindruck haben, weiterhin auf die gewohnten Ressourcen zugreifen zu können (bis beim nächsten Synchronisierungszyklus der Zugriff auf eine bestimmte Komponente des Dienstes hinzugefügt oder widerrufen wird).  Wenn Sie Teammitglieder außerhalb des Teams-Clients (mithilfe von Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell) hinzufügen oder entfernen, kann es bis zu 24 Stunden dauern (in einigen Fällen mehr), damit Änderungen in Teams widergespiegelt werden.

<a name="ability-to-add-group-as-attendee-while-scheduling-meetings"></a>Möglichkeit zum Hinzufügen einer Gruppe als Teilnehmer beim Planen von Besprechungen
----------------------------------------------------------

Ab Mai 2020 können Sie nun eine Gruppe zu einer geplanten Besprechung einladen, mit den folgenden Einschränkungen:
1. Alle vorhandenen Microsoft 365-Gruppen und-Teams, die aus vorhandenen Microsoft 365-Gruppen erstellt wurden, sind durchsuchbar und können der Besprechung hinzugefügt werden. Mitglieder erhalten die Besprechungseinladung jedoch auf Grundlage Ihres Abonnements für die Gruppe.
2. Teams, die vor dem 2018. Mai neu erstellt wurden, sind ebenfalls suchbar, aber die Mitglieder empfangen die Besprechungseinladung nicht aufgrund Ihres standardmäßigen gruppenabonnements, das "nur Antworten auf Sie" ist. Dies kann in Outlook geändert werden, indem die Gruppeneinstellungen geändert werden.
3. Teams, die nach Mai 2018 von Grund auf neu erstellt wurden, sind nicht durchsuchbar und werden mithilfe der Eigenschaft "HiddenFromAddressListsEnabled" ausgeblendet. Hierbei handelt es sich um eine vom Administrator gesteuerte Einstellung, die vom Administrator geändert werden kann.
