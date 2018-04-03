---
title: PSTN-Minute Pools-Bericht
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Die neue Skype für Bereich Business Admin Center Berichte zeigt Sie aufrufende und audio Conferencing Aktivität in Ihrer Organisation. Sie können in Berichte bieten mehr Granularität Aufschluss über die Aktivitäten der einzelnen Benutzer zur Verfügung, der Drilldown erfolgen soll. Die Skype für Business PSTN Minute Pools Bericht können Sie beispielsweise die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht finden Sie unter.
ms.openlocfilehash: 3db3e0394bc7af9394b4b6988bc28fbaa1da42a5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="pstn-minute-pools-report"></a>PSTN-Minute Pools-Bericht

>[!NOTE]
>Dieser Bericht ist nur für die Vorschau von Kunden zur Verfügung.

Die neue Skype für Bereich Business Admin Center **Berichte** zeigt Sie aufrufende und audio Conferencing Aktivität in Ihrer Organisation. Sie können in Berichte bieten mehr Granularität Aufschluss über die Aktivitäten der einzelnen Benutzer zur Verfügung, der Drilldown erfolgen soll. Den Bericht **Skype für Minute Business PSTN-Pools** können Sie beispielsweise die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht finden Sie unter.
  
Checken Sie der [Übersicht über die Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) für weitere Berichte, die verfügbar sind.
  
In diesem Bericht, zusammen mit den anderen Skype für Business-Berichte, erhalten Sie Details auf Aktivität innerhalb Ihrer Organisation. Diese Angaben sind sehr hilfreich beim Untersuchen von, zur Planung und andere treffen für Ihre Organisation und für das Einrichten von [Communications haben](../skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits.md)
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>Wie Sie auf die Skype für Business PSTN Minute Pools Bericht abrufen

- Wechseln Sie zu **Office 365 Administrationscenter** > **Admin zentriert** > **Skype für Business Administrationscenter** > **Berichte** > **Minute PSTN-Pools**.
    
> [!NOTE]
> Je nach Office 365-Abonnements, die Ihnen, möglicherweise nicht Details hier gezeigte dieselben angezeigt werden. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretieren der Skype für Business PSTN Minute Pools Bericht

Sie können eine Ansicht in Skype für Business Minute Pools des Benutzers abrufen, indem Sie betrachten jede der Spalten, die angezeigt werden.
  
Der Bericht sieht folgendermaßen aus:
  
## 

![Skype für Business PSTN Minute pools Bericht](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>Die Tabelle zeigt Sie eine Aufschlüsselung der Minute Pools nach Lizenz (Funktion) und Speicherort der Verwendungsanalyse. 
*    **Funktion** ist die Lizenz/Dienstplan für den Anruf verwendet. Die Lizenz-Dienst-Pläne, die in diesem Bericht angezeigt werden umfassen:
     * MCOPSTNPP - Communications haben
     * MCOPSTN1 - nationalen aufrufen planen (3000-minütigen US/1200-minütigen EU-Pläne
     * MCOPSTN2 - internationaler Plan
     * MCOPSTN5 - nationalen aufrufen Plan (aufrufende Plan 120 Minuten)
     * MCOMEETADD - Audiokonferenzen
     * MCOMEETACPEA - Bezahlung pro Minute Audiokonferenzen
*    **Beschreibung der Funktion** ist eine Beschreibung des Typs Lizenz für den Anruf verwendet.
*    **Land Minute Pool** ist der Lizenz Usage-Speicherort den Benutzer, die den Minuten Pool gemeinsam nutzen. 
*    **Minuten verwendet,** ist die Anzahl der Minuten pro Monat verwendet.
*    **Gesamtzahl der Minuten** ist die Gesamtzahl der Minuten, die für den Monat zur Verfügung. 
*    **Prozent verwendet** , ist der Prozentsatz der Minuten für den Monat verwendet. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns. 
***
![Nummer 3](../images/sfbcallout3.png)<br/>Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Auswahl (Drittanbieter) und Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Skype für Unternehmensbenutzer blockiert Bericht](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden, finden Sie unter.

- [Skype für Business Sitzung Detailbericht](session-details-report.md) Sie können die Details zu einzelnen Benutzers Anruf Erfahrungen sehen.
    
## <a name="related-topics"></a>See Also
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   