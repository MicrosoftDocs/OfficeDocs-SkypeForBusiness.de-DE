---
title: Office 365-Gruppen und Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Erfahren Sie, wie Office 365-Gruppen und -Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365-Gruppen und Microsoft Teams
=====================================

Office 365-Gruppen ist der programmübergreifende Mitgliederdienst in Office 365. Grundsätzlich ist eine Office 365-Gruppe ein Objekt im Azure Active Directory mit einer Liste von Mitgliedern und einer losen Kopplung zu verwandten Arbeitsauslastungen. Dazu zählen eine SharePoint-Teamsite, Yammer-Gruppe, freigegebene Exchange-Postfachressourcen, Planner, PowerBI und OneNote. Sie können Personen zur Gruppe hinzufügen oder daraus entfernen, genau so, wie Sie es mit anderen gruppenbasierten Sicherheitsobjekten in Active Directory tun würden.

Ein Office 365-Administrator kann eine Office 365-Gruppe definieren, Mitglieder hinzufügen und die Vorteile von Funktionen nutzen, wie zum Beispiel das freigegebene Exchange-Postfach, die SharePoint-Dokumentbibliothek, die Yammer-Gruppe usw. Weitere Informationen zu Gruppen finden Sie unter: [Informationen zu Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Funktionsweise von Office 365-Gruppen
--------------------------

Wenn Sie ein Microsoft Team erstellen, erstellen Sie am Backend eine Office 365-Gruppe zusammen mit der zugehörigen SharePoint-Dokumentbibliothek, dem OneNote-Notizbuch sowie Verbindungen zu anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt, ein Besitzer einer vorhandenen öffentlichen oder privaten Office 365-Gruppe ist, kann diese Person Teamfunktionen zur Gruppe hinzufügen. Dadurch wird ein standardmäßiger „allgemeiner“ Kanal erstellt, in dem sich Chatnachrichten, Dokumente, OneNote-Notizbücher und andere Objekte befinden. Bei der Anzeige der Dokumentbibliothek für den Kanal wird der Ordner „Allgemein“ angezeigt, der den Kanal im Team repräsentiert. Wenn Sie darüber hinaus Ihre eigene Ordnerstruktur innerhalb einer Dokumentbibliothek erstellen, **wird diese nicht** an Teams als ein Kanal übertragen. Zum gegenwärtigen Zeitpunkt findet nur eine Übertragung von Teams nach SharePoint statt.




> [!NOTE]
> Beim Löschen einer Office 365-Gruppe wird der Postfach-Alias für permanente Outlook/OWA-Unterhaltungen und Teams-Besprechungseinladungen entfernt, und die SharePoint-Site wird zum Löschen markiert. Es dauert ungefähr 20 Minuten, bis sich das Löschen eines Teams in Outlook auswirkt. Beim Löschen eines Teams aus dem Teams-Client wird dieses sofort aus allen Ansichten der Mitglieder des Teams entfernt. Wenn Sie ein Mitglied aus einer Office 365-Gruppe entfernen, in der die Teams-Funktionen aktiviert sind, kann es zu einer Verzögerung von ungefähr einer Stunde kommen, bevor das Team aus der Ansicht im Teams-Client entfernt wird.

<a name="group-membership"></a>Gruppenmitgliedschaft:
----------------

Gruppe Features und Funktionen für Ihre Benutzer hängt davon ab, wobei Sie Gruppenmitgliedschaft aus Laufwerk. Wenn Sie ein Mitglied eines Teams entfernen, werden diese beispielsweise aus der Office 365 Gruppe ebenfalls entfernt. Entfernen aus der Gruppe entfernt das Team sofort und Kanäle auf dem Client Teams. Wenn Sie eine Person aus einer Gruppe mithilfe der Office 365-Verwaltungsportals entfernen möchten, müssen sie nicht mehr Zugriff auf andere gemeinsame Aspekte wie SharePoint Online-Dokumentbibliothek Yammer-Gruppe oder freigegebenen OneNote. Jedoch haben sie Zugriff auf das Team Chat Funktionen weiterhin für eine Stunde.

Bewährte Methode für die Verwaltung von Teams Mitglieder: Hinzufügen und Entfernen von Mitgliedern aus der Client Teams, um sicherzustellen, dass die richtigen cascading Steuerung des Zugriffs auf anderen Applikationen abhängigen Cloud angewendet wird. Vermeiden Sie darüber hinaus einen getrennten Erfahrung verlassen Personen mit den Eindruck, dass sie über Zugriff auf die Ressourcen verfügen gewohnte (bis nächste Sync Zyklus hinzugefügt oder Zugriff auf eine bestimmte Komponente des Diensts entzogen). Wenn Sie hinzufügen oder Entfernen von Teammitgliedern außerhalb des Teams-Clients (mithilfe von Office 365 Admin Center, Azure AD oder Exchange Online PowerShell), unter Umständen dauert es bis zu einer Stunde, damit die Änderungen in Teams widergespiegelt werden.
