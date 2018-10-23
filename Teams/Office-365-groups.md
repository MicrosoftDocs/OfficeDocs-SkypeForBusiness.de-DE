---
title: Office 365-Gruppen und Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: article
ms.service: msteams
description: Erfahren Sie, wie Office 365-Gruppen und -Gruppenmitgliedschaften mit Microsoft Teams funktionieren.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: bbb71a7b2d941abc57315b0f6dfb2c309facaf4f
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699252"
---
<a name="office-365-groups-and-microsoft-teams"></a>Office 365-Gruppen und Microsoft-Teams
=====================================

> [!Tip]
> Sehen Sie sich die folgenden Sitzung um zu erfahren, wie Teams interagiert mit Azure Active Directory (AD Azure), Gruppen von Office 365, Exchange, SharePoint und OneDrive für Unternehmen: [Grundlagen der Microsoft-Teams](https://aka.ms/teams-foundations)

Office 365 Gruppen ist der anwendungsübergreifender Mitgliedschaft in Office 365. Ebene der grundlegenden ist eine Office 365-Gruppe an, dass ein Objekt mit einer Liste der Elemente und eine Kopplung an eine SharePoint-Teamwebsite Yammer-Gruppe, einschließlich verwandte Arbeitslasten in Azure Active Directory Exchange-Postfach-Ressourcen, Planner, Power BI und OneNote gemeinsam genutzt. Sie können hinzufügen oder entfernen Personen zu der Gruppe, genau wie alle anderen rollenbasierten Sicherheit-Objekts in Active Directory.

Ein Office 365-Administrator kann Definieren einer Office 365-Gruppe, Hinzufügen von Mitgliedern und Features profitieren, z. B. auf einem Exchange-Postfach, SharePoint-Dokumentbibliothek, Yammer Gruppe usw. freigegebene. Weitere Informationen zu Office 365-Gruppen finden Sie unter [Informationen zu Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

<a name="how-office-365-groups-work"></a>Funktionsweise von Office 365-Gruppen
--------------------------

Beim Erstellen eines Teams für die Back-End-erstellen Sie eine Office 365-Gruppe und die zugeordneten SharePoint-Dokumentbibliothek und OneNote-Notizbuch zusammen mit Einbindung in anderen Office 365-Cloud-Anwendungen. Wenn die Person, die das Team erstellt einen Besitzer einer vorhandenen Office 365 öffentlichen oder privaten Gruppe ist, können sie der Gruppe Teams Funktionen hinzufügen mit weniger als 2500 Personen und Teams nie hinzugefügt wurde. Erstellt einen **allgemeinen** Standard-Kanal Nachrichten, Dokumente, OneNote und andere Objekte in der befinden. Anzeigen der Dokumentbibliothek für den DDE-Kanal informiert, auf den Ordner **Allgemein** , den Kanal im Team darstellt. Wichtiger, wenn Sie Ihre eigene Ordnerstruktur in einem Dokumentbibliothek **werden nicht weitergegeben** , Teams als Kanal; erstellen für den Moment fließt er nur von Teams in SharePoint.

> [!NOTE]
> Basierend auf Feedback von Kunden, neue Office 365 Gruppen infolge einer erstellen ein Team in Microsoft-Teams, nicht mehr in Outlook standardmäßig angezeigt. Für Kunden, die das vorhandene Verhalten der mit diesen Gruppen in Outlook fortsetzen möchten, wird die Gruppe die für die benutzerfreundlichkeit von Outlook ermöglichen können ein Exchange Online PowerShell-Cmdlet bereitgestellt werden. Gruppen über Outlook erstellt und dann später für Teams aktiviert werden weiterhin in Outlook und Teams angezeigt. Dieses Update wird schrittweise Roll out über Outlook und Teams in den nächsten Monaten.

> [!NOTE]
> Löschen einer Office 365-Gruppe wird entfernen Sie das Postfach alias für persistent Outlook/OWA-Unterhaltungen und Teams Besprechung eingeladen, und markieren Sie die SharePoint zum Löschen site. Es dauert ungefähr 20 Minuten zwischen das Entfernen eines Teams und ihre Auswirkung auf Outlook. Löschen ein Team aus der Teams Client wird sofort aus der Ansicht zu allen entfernt, die Mitglieder des Teams sind. Wenn Sie Mitglieder einer Office 365-Gruppe, die Teams Funktionalität aktiviert wurde entfernen, werden konnte eine Verzögerung von etwa zwei Stunden, bevor das Team aus Ansicht im Client Teams für die betroffenen Personen entfernt wird, die entfernt wurden.
>
>Lesen Sie [diese](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) Informationen zum Wiederherstellen einer Office 365-Gruppe, die Sie gelöscht.

<a name="group-membership"></a>Gruppenmitgliedschaft:
----------------

Gruppenfunktionen und Funktionen für Ihre Benutzer hängen davon ab, wobei Sie Gruppenmitgliedschaft aus Laufwerk. Wenn Sie ein Mitglied eines Teams entfernen, werden diese beispielsweise aus der Office 365 Gruppe ebenfalls entfernt. Entfernen aus der Gruppe entfernt das Team sofort und Kanäle auf dem Client Teams. Wenn Sie eine Person aus einer Gruppe mithilfe der Office 365-Verwaltungskonsole entfernen möchten, sie nicht mehr Zugriff auf andere gemeinsame Aspekte wie SharePoint Online-Dokumentbibliothek verfügen Yammer Gruppe oder freigegebenen OneNote. Jedoch haben sie Zugriff auf das Team gruppenchatfunktion weiterhin ungefähr 2 Stunden.

Als bewährte Methode für die Verwaltung von Teams Mitglieder hinzufügen und Entfernen von Mitgliedern aus der Client Teams, um sicherzustellen, dass die richtigen cascading Steuerung des Zugriffs auf anderen Applikationen abhängigen Cloud angewendet wird. Vermeiden Sie darüber hinaus einen getrennten Erfahrung verlassen Personen mit den Eindruck, dass sie über Zugriff auf die Ressourcen verfügen gewohnte (bis nächste Sync Zyklus hinzugefügt oder Zugriff auf eine bestimmte Komponente des Diensts entzogen). Wenn Sie hinzufügen oder Entfernen von Teammitgliedern außerhalb des Teams-Clients (mithilfe von Office 365 Administrationscenter, Azure AD oder Exchange Online PowerShell), dauert bis zu zwei Stunden bei Änderungen in Teams übernommen werden.
