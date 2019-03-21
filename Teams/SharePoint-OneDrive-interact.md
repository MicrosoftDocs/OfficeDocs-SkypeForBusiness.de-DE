---
title: Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 11/12/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
search.appverid: MET150
description: Erfahren Sie, wie SharePoint Online und OneDrive for Business mit Microsoft Teams interagieren. Dies beinhaltet Informationen darüber, wie private Chatdateien gespeichert werden, sowie die Beziehung zwischen Teams, Kanälen und der Dokumentbibliothek.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 169008f7af8f52be60c7f15d7a4613f77ed161df
ms.sourcegitcommit: ff100b32fa92fc878f1404dace266d956262c24d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "30720323"
---
<a name="how-sharepoint-online-and-onedrive-for-business-interact-with-microsoft-teams"></a>Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams
=============================================================================

> [!Tip]
> Sehen Sie sich die folgenden Sitzung um zu erfahren, wie Teams interagiert mit Azure Active Directory (AAD), Gruppen von Office 365, Exchange, SharePoint und OneDrive für Unternehmen: [Grundlagen der Microsoft-Teams](https://aka.ms/teams-foundations)

Jedes Team in Microsoft Teams verfügt über eine Teamsite in SharePoint Online, und jeder Kanal in einem Team erhält einen Ordner innerhalb der Dokumentbibliothek der Standardteamsite. In einer Unterhaltung freigegebene Dateien werden automatisch zur Dokumentbibliothek hinzugefügt, und in SharePoint festgelegte Berechtigungen und Dateisicherheitsoptionen werden automatisch in Teams übernommen.

Private Chatdateien werden im OneDrive-Ordner des Absenders gespeichert, und Berechtigungen werden automatisch allen Teilnehmern als Teil des Dateifreigabevorgangs zugewiesen.

Wenn Benutzer sind nicht zugewiesen und mit SharePoint Online-Lizenzen aktiviert, verfügen nicht OneDrive for Business-Speicher in Office 365. Dateifreigabe wird in weiterhin, Kanäle, aber Benutzer werden nicht in der Lage, Freigeben von Dateien in Chats ohne OneDrive for Business-Speicher in Office 365.

Beim Speichern der Dateien in der SharePoint Online-Dokumentbibliothek und OneDrive for Business werden alle auf der Mandantenebene konfigurierten Complianceregeln eingehalten. 

> [!NOTE]
> Integration in lokale Sharepoint-wird für Microsoft-Teams, zu diesem Zeitpunkt nicht unterstützt.

Im Folgenden finden Sie ein Beispiel für die Beziehungen zwischen Team, Kanal und Dokumentbibliothek.

Für jedes Team wird eine SharePoint-Website und der Standardordner **Freigegebene Dokumente** erstellt. Für jeden Kanal, auch für den Kanal **Allgemein** (den Standardkanal für jedes Team), ist in **Freigegebene Dokumente** ein Ordner vorhanden.

![Diagramm des Ordners „Freigegebene Dokumente“ in SharePoint Online für ein Team und dessen Kanäle in Microsoft Teams](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image1.png)

> [!NOTE]
> Es ist zurzeit nicht möglich, die standardmäßige SharePoint-Website und -Dokumentbibliothek durch eine andere zu ersetzen. Sie haben uns mitgeteilt, dass Sie sich diese Möglichkeit wünschen, und wir ziehen sie in Erwägung. In der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap) oder auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website finden Sie Informationen zu geplanten Funktionen.

> [!TIP]
> Hinzufügen eine Registerkarte an Ihr Team, die zu einer vorhandenen SharePoint-Website-Seite oder in Ihrer vorhandenen SharePoint-Dokumentbibliothek verknüpft:
> 1. Wählen Sie das Pluszeichen (+) neben den Registerkarten.
> 2. Wählen Sie **SharePoint** für eine vorhandene Seite der SharePoint-Website oder **Dokumentbibliothek** für eine vorhandene Dokumentbibliothek.
> 3. Wählen Sie aus der entsprechenden Seite oder -Dokumentbibliothek.

Für jeden Benutzer wird der OneDrive-Ordner **Microsoft Teams-Chatdateien** zum Speichern aller innerhalb der in privaten Chats für andere Benutzer (1:1 oder 1:viele) freigegebenen Dateien mit automatisch konfigurierten Berechtigungen verwendet, um den Zugriff auf den gewünschten Benutzer zu beschränken.

![Diagramm des OneDrive-Ordners „Microsoft Teams-Chatdateien“ für die Chats der einzelnen Benutzer](media/Understand_how_SharePoint_Online_and_OneDrive_for_Business_interact_with_Microsoft_Teams_image2.png)

<a name="more-information"></a>Weitere Informationen
----------------

Weitere Informationen zur Funktionsweise von SharePoint mit den Teams, finden Sie unter [SharePoint und Teams: ein starkes Team](https://techcommunity.microsoft.com/t5/Microsoft-SharePoint-Blog/SharePoint-and-Teams-Better-Together/ba-p/189593).

Lesen Sie weitere Informationen zu den Gast Erfahrung in Teams zu finden, [Was die Erfahrung Gast ist, wie](guest-experience.md).

