---
title: Office 365-Gruppen und Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: article
ms.service: msteams
description: Erfahren Sie, wie Office 365-Gruppen und -Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c9d7c37a0aa53f45036388bdedfc5bdc87b1cc8a
ms.sourcegitcommit: 5fb3957b658b48edf3d9878a9d53a4002b8f55d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520062"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365-Gruppen und Microsoft-Teams
=====================================

Office 365 Gruppen ist der anwendungsübergreifender Mitgliedschaft in Office 365. Ebene der grundlegenden ist eine Office 365-Gruppe an, dass ein Objekt mit einer Liste der Elemente und eine Kopplung an eine SharePoint-Teamwebsite Yammer-Gruppe, einschließlich verwandte Arbeitslasten in Azure Active Directory Exchange-Postfach-Ressourcen, Planner, PowerBI und OneNote gemeinsam genutzt. Sie können hinzufügen oder entfernen Personen zu der Gruppe, genau wie alle anderen rollenbasierten Sicherheit-Objekts in Active Directory.

Ein Office 365-Administrator kann Definieren einer Office 365-Gruppe, Hinzufügen von Mitgliedern und Features profitieren, z. B. auf einem Exchange-Postfach, SharePoint-Dokumentbibliothek, Yammer Gruppe usw. freigegebene. Weitere Informationen zu Office 365-Gruppen, finden Sie unter: [informieren Sie sich über Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Funktionsweise von Office 365-Gruppen
--------------------------

Beim Erstellen von einem Microsoft-Team für die Back-End-erstellen Sie eine Office 365-Gruppe und die zugeordneten SharePoint-Dokumentbibliothek und OneNote-Notizbuch zusammen mit Einbindung in anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt einen Besitzer einer vorhandenen Office 365 öffentlichen oder privaten Gruppe ist, können sie Teams Funktionen zur Gruppe hinzufügen. Erstellt einen **allgemeinen** Standard-Kanal Nachrichten, Dokumente, OneNote und andere Objekte in der befinden. Anzeigen der Dokumentbibliothek für den DDE-Kanal informiert, auf den Ordner **Allgemein** , den Kanal im Team darstellt. Wichtiger, wenn Sie Ihre eigene Ordnerstruktur in einem Dokumentbibliothek **werden nicht weitergegeben** , Teams als Kanal; erstellen für den Moment fließt er nur von Teams in SharePoint.

> [!NOTE]
> Löschen einer Office 365-Gruppe wird entfernen Sie das Postfach alias für persistent Outlook/OWA-Unterhaltungen und Teams Besprechung eingeladen, und markieren Sie die SharePoint zum Löschen site. Es dauert ungefähr 20 Minuten zwischen das Entfernen eines Teams und ihre Auswirkung auf Outlook. Löschen ein Team aus der Teams Client wird sofort aus der Ansicht zu allen entfernt, die Mitglieder des Teams sind. Wenn Sie Mitglieder einer Office 365-Gruppe, die Teams Funktionalität aktiviert wurde entfernen, werden konnte eine Verzögerung von etwa zwei Stunden, bevor das Team aus Ansicht im Client Teams für die betroffenen Personen entfernt wird, die entfernt wurden.
>
>Lesen Sie [diese](https://support.office.com/en-us/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) Informationen zum Wiederherstellen einer Office 365-Gruppe, die Sie gelöscht.

<a name="group-membership"></a>Gruppenmitgliedschaft:
----------------

Gruppenfunktionen und Funktionen für Ihre Benutzer hängen davon ab, wobei Sie Gruppenmitgliedschaft aus Laufwerk. Wenn Sie ein Mitglied eines Teams entfernen, werden diese beispielsweise aus der Office 365 Gruppe ebenfalls entfernt. Entfernen aus der Gruppe entfernt das Team sofort und Kanäle auf dem Client Teams. Wenn Sie eine Person aus einer Gruppe mithilfe der Office 365-Verwaltungsportals entfernen möchten, müssen sie nicht mehr Zugriff auf andere gemeinsame Aspekte wie SharePoint Online-Dokumentbibliothek Yammer-Gruppe oder freigegebenen OneNote. Jedoch haben sie Zugriff auf das Team gruppenchatfunktion weiterhin ungefähr 2 Stunden.

Bewährte Methode für die Verwaltung von Teams Mitglieder: Hinzufügen und Entfernen von Mitgliedern aus der Client Teams, um sicherzustellen, dass die richtigen cascading Steuerung des Zugriffs auf anderen Applikationen abhängigen Cloud angewendet wird. Vermeiden Sie darüber hinaus einen getrennten Erfahrung verlassen Personen mit den Eindruck, dass sie über Zugriff auf die Ressourcen verfügen gewohnte (bis nächste Sync Zyklus hinzugefügt oder Zugriff auf eine bestimmte Komponente des Diensts entzogen). Wenn Sie hinzufügen oder Entfernen von Teammitgliedern außerhalb des Teams-Clients (mit dem Office 365 Admin Center, Azure AD oder Exchange Online PowerShell), kann es dauern, bis zu zwei Stunden bei Änderungen in Teams übernommen werden.
