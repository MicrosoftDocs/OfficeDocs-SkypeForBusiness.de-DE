---
title: Office 365-Gruppen und Microsoft Teams
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
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834335"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365-Gruppen und Microsoft Teams
=====================================

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um zu erfahren, wie Teams mit Azure Active Directory (Azure AD), Office 365 Groups, Exchange, SharePoint und OneDrive for Business interagieren: [Grundlagen von Microsoft Teams](https://aka.ms/teams-foundations)

Office 365 Groups ist der Anwendungsübergreifende Mitgliedschaftsdienst in Office 365. Auf der grundlegenden Ebene ist eine Office 365-Gruppe ein Objekt in Azure Active Directory mit einer Liste von Mitgliedern und einer losen Kopplung an Verwandte Arbeitsauslastungen, einschließlich einer SharePoint-Teamwebsite, einer Gruppe "jammern", freigegebene Exchange-Postfachressourcen, Planner, Power BI und OneNote. Sie können der Gruppe genauso wie jedes andere Gruppenbasierte Sicherheitsobjekt in Active Directory Personen hinzufügen oder daraus entfernen.

Ein Office 365-Administrator kann eine Office 365-Gruppe definieren, Mitglieder hinzufügen und von Features wie einem freigegebenen Exchange-Postfach, einer SharePoint-Dokumentbibliothek, einer Gruppe "jammern" usw. profitieren. Weitere Informationen zu Office 365-Gruppen finden Sie unter Informationen [zu Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

Verpassen Sie nicht die Plakat [Gruppen in Microsoft 365 für IT-Architekten](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

<a name="how-office-365-groups-work"></a>Funktionsweise von Office 365-Gruppen
--------------------------

Wenn Sie ein Team erstellen, erstellen Sie im Back-End eine Office 365-Gruppe und die zugehörige SharePoint-Dokumentbibliothek und das OneNote-Notizbuch sowie Verbindungen zu anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt, ein Besitzer einer vorhandenen öffentlichen oder privaten Gruppe von Office 365 ist, können Sie der Gruppe Team Funktionalität hinzufügen, wenn Sie weniger als 5000 Personen hat und Teams nie hinzugefügt wurde. Dadurch wird ein **allgemeiner** Standardkanal erstellt, in dem sich Chatnachrichten, Dokumente, OneNote und andere Objekte befinden. Beim Anzeigen der Dokumentbibliothek für den Kanal wird der Ordner " **Allgemein** " angezeigt, der den Kanal im Team darstellt. Und noch wichtiger: Wenn Sie eine eigene Ordnerstruktur innerhalb einer Dokumentbibliothek erstellen, **wird Sie nicht** als Kanal an Teams weitergegeben. im Moment fließt sie nur aus Teams in SharePoint.

> [!NOTE]
> Basierend auf Kundenfeedback werden neue Office 365-Gruppen, die als Ergebnis des Erstellens eines Teams in Microsoft Teams erstellt wurden, nicht mehr standardmäßig in Outlook angezeigt. Für Kunden, die das vorhandene Verhalten des Anzeigens dieser Gruppen in Outlook fortsetzen möchten, wird ein Exchange Online PowerShell-Cmdlet bereitgestellt, das die Gruppe für die Outlook-Umgebung aktivieren kann. Gruppen, die über Outlook erstellt und später für Teams aktiviert wurden, werden weiterhin sowohl in Outlook als auch in Teams angezeigt. Dieses Update wird in den nächsten Monaten schrittweise in Outlook und Teams bereitgestellt.

> [!NOTE]
> Beim Löschen einer Office 365-Gruppe wird der Post Fach Alias für beständige Outlook/OWA-Unterhaltungen und Teams-Besprechungseinladungen entfernt, und die SharePoint-Website wird zum Löschen markiert. Zwischen dem Entfernen eines Teams und dessen Auswirkungen auf Outlook dauert es ungefähr 20 Minuten. Wenn Sie ein Team aus dem Teams-Client löschen, wird es sofort aus der Ansicht an alle Mitglieder des Teams entfernt. Wenn Sie Mitglieder einer Office 365-Gruppe entfernen, für die die Funktion Teams aktiviert war, kann es eine Verzögerung von etwa zwei Stunden geben, bevor das Team für die betroffenen Personen aus der Ansicht entfernt wird, die entfernt wurden.
>
>Informationen zum Wiederherstellen einer gelöschten Office 365-Gruppe finden Sie [hier](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) .

<a name="group-membership"></a>Gruppenmitgliedschaft:
----------------

Die Gruppenfeatures und-Funktionen für Ihre Benutzer hängen davon ab, von wo aus Sie die Gruppenmitgliedschaft steuern. Wenn Sie beispielsweise ein Mitglied eines Teams entfernen, werden diese auch aus der Office 365-Gruppe entfernt. Durch das Entfernen aus der Gruppe werden die Teams und Kanäle sofort aus dem Team-Client entfernt. Wenn Sie eine Person aus einer Gruppe mit dem Microsoft 365 Admin Center entfernen, haben Sie keinen Zugriff mehr auf die anderen kollaborativen Aspekte wie die SharePoint Online-Dokumentbibliothek, die Gruppe "jammern" oder "Freigegebene OneNote". Sie haben jedoch für etwa zwei Stunden weiterhin Zugriff auf die Chatfunktion des Teams.

Als bewährte Methode für die Verwaltung von Teammitgliedern können Sie Mitglieder des Teams-Clients hinzufügen und entfernen, um sicherzustellen, dass die richtige kaskadierende Zugriffssteuerung für andere abhängige Cloud-Anwendungen angewendet wird. Darüber hinaus vermeiden Sie eine unzusammenhängende Vorgehensweise, wenn Sie den Eindruck haben, dass Sie weiterhin Zugriff auf die Ressourcen haben, die Sie verwendet haben (bis der nächste Synchronisierungszyklus den Zugriff auf eine bestimmte Komponente des Diensts hinzufügt oder wider ruft). Wenn Sie Teammitglieder außerhalb des Teams-Clients (mithilfe von Microsoft 365 Admin Center, Azure AD oder Exchange Online PowerShell) hinzufügen oder entfernen, kann es bis zu zwei Stunden dauern, bis Änderungen in Teams wiedergegeben werden.
