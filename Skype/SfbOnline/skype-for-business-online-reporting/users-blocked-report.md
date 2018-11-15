---
title: Bericht „Benutzer gesperrt“
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: 'Dieser Bericht bietet Ihnen mit den anderen Skype for Business-Berichten nähere Einzelheiten zur jeweiligen Aktivität, einschließlich der PSTN-Nutzung in der gesamten Organisation. '
ms.openlocfilehash: 789f881aff2f80603ac440250bc769d6c7b989c0
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532685"
---
# <a name="users-blocked-report"></a>Bericht „Benutzer gesperrt“

Im neuen Skype for Business-Dashboard **Berichte** wird eine Aktivitätsübersicht für die Skype for Business-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. Beispielsweise können Sie den Bericht **Skype für Unternehmensbenutzer blockiert** verwenden, sehen die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden. Dieser Bericht bietet Ihnen mit den anderen Skype for Business-Berichten nähere Einzelheiten zur jeweiligen Aktivität, einschließlich der PSTN-Nutzung in der gesamten Organisation.
  
 Checken Sie der [Übersicht über die Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) für weitere Berichte, die verfügbar sind.
  
> [!NOTE]
> Sie können beim Anmelden als Administrator, um das Office 365 Administrationscenter alle der Skype für Business Berichte angezeigt. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Wie abgerufen, der Skype für Unternehmensbenutzer blockiert Bericht

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

- Wechseln Sie zu **Office 365 Administrationscenter** > **Admin zentriert** > **Skype für Business Administrationscenter** > **Berichte** > **Benutzer blockiert**.
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretieren der Skype für Business Benutzer blockiert Bericht

Betrachten jede der Spalten angezeigt, um eine Ansicht in blockierte Benutzer zu erhalten.
  
Der Bericht sieht folgendermaßen aus: 
  
![Blockierte Benutzer Bericht](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

Die Tabelle zeigt eine Untergliederung aller Benutzer, die für das Tätigen von Anrufen gesperrt sind. Sie zeigt alle Benutzer an, denen Telefonsystem or Audiokonferenz zugewiesen ist. Sie können in der Tabelle Spalten hinzufügen bzw. entfernen.
***
![Nummer 1](../images/sfbcallout1.png)
*   Unter **Benutzer-ID** finden Sie die Anmeldeinformationen des Benutzers.
*   **Telefonnummer** ist die Nummer, die einem Benutzer zugewiesen wird. 
*   **Zeit für Blockierung** ist die Zeit (UTC), während der der Benutzer für das Tätigen von Anrufen gesperrt wurde.
*   **Aktion blockieren** ist die Art der Aktion, die für das Blockieren des Benutzers ergriffen wurde.
*   **Grund für Blockierung** ist der Grund, aus dem der Benutzer für das Tätigen von Anrufen gesperrt wurde.
***
![Nummer 2](../images/sfbcallout2.png)<br/>
Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns.
***
![Nummer 3](../images/sfbcallout3.png)<br/>
Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype für Teilnehmer Business-konferenzaktivitätsbericht](conference-participant-activity-report.md) Sie können sehen, wie viele Sofortnachrichten, Audio/Video, Anwendungsfreigabe, Web und Konferenzen/Dial-Out Konferenz sind beteiligt wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.

- [Skype für Business PSTN Minute Pools Bericht](pstn-minute-pools-report.md) sehen Sie die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht.

- [Skype für Business Sitzung Detailbericht](session-details-report.md) Sie können die Details zu einzelnen Benutzers Anruf Erfahrungen sehen.
   
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 