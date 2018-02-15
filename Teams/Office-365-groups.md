---
title: Office 365-Gruppen und Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: Erfahren Sie, wie Office 365-Gruppen und -Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e21a776e9cb259b9a4e73a1bfc7df3e0b408a50
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
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

Die für Benutzer verfügbaren Funktionen richten sich danach, von wo aus die Gruppenmitgliedschaft gesteuert wird. Wenn Sie beispielsweise ein Mitglied eines Teams entfernen, wird dieses Mitglied auch aus der Office 365-Gruppe entfernt. Beim Entfernen aus einer Gruppe werden das Team und die Kanäle sofort auch vom Teams-Client entfernt. Wenn Sie Personen über das Office 365-Verwaltungsportal entfernen, haben diese keinen Zugriff mehr auf andere Aspekte der Zusammenarbeit, wie zum Beispiel auf die SharePoint Online-Dokumentbibliothek, die Yammer-Gruppe oder das freigegebene OneNote-Notizbuch. Sie haben aber nach wie vor ungefähr eine Stunde lang Zugriff auf die Chat-Funktionen in Teams.

Unsere Ausrichtung in Bezug auf die „Mitgliederverwaltung“ in Teams besteht darin, die Funktionen zum Hinzufügen bzw. Entfernen im Teams-Client zur Verfügung zu stellen, dass eine kaskadierende Zugriffssteuerung auf andere abhängige Cloud-Anwendungen angewendet wird. Zudem werden Benutzer vor dem Eindruck bewahrt, immer noch Zugriff auf die gewohnten Funktionen zu haben (bis zum nächsten Synchronisierungszyklus, bei der Zugriff auf eine bestimmte Komponente des Diensts hinzugefügt oder widerrufen wird).
