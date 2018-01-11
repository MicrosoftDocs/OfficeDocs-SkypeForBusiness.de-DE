---
title: Benutzer, die blockiert Bericht
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 0ac844b2-1b08-4e5a-addf-03cde7af7a40
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Reporting
description: "In diesem Bericht, zusammen mit anderen Skype für Business-Berichte, erhalten Sie Details auf Aktivität, einschließlich PSTN-Verwendung in Ihrer Organisation. "
ms.openlocfilehash: 462018abc071c990fa89c226081d4bae78213b04
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="users-blocked-report"></a>Benutzer, die blockiert Bericht

Die neue Skype für geschäftliche **Berichte** Dashboard zeigt, über die Skype für Business-Produkte in Ihrer Organisation der Übersicht über die Aktivität. Sie können Sie auf einzelne Stufe Produkt Berichte zur Verfügung, bieten mehr Granularität Aufschluss über die Aktivitäten innerhalb jedes Produkt einen Drilldown ausführen. Beispielsweise können Sie den Bericht **Skype für Unternehmensbenutzer blockiert** verwenden, sehen die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden. In diesem Bericht, zusammen mit anderen Skype für Business-Berichte, erhalten Sie Details auf Aktivität, einschließlich PSTN-Verwendung in Ihrer Organisation.
  
 Checken Sie der [Übersicht über die Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) für weitere Berichte, die verfügbar sind.
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>Wie abgerufen, der Skype für Unternehmensbenutzer blockiert Bericht

- Wechseln Sie zu **Office 365 Administrationscenter** > **Admin zentriert** > **Skype für Business Administrationscenter** > **Berichte** > **Benutzer blockiert**.
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretieren der Skype für Business Benutzer blockiert Bericht

Betrachten jede der Spalten angezeigt, um eine Ansicht in blockierte Benutzer zu erhalten.
  
Der Bericht sieht wie folgt aus: 
  
![Blockierte Benutzer Bericht](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

Die Tabelle zeigt Sie eine Aufschlüsselung der alle Benutzer, die Aufrufe daran gehindert werden. Zeigt alle Benutzer, die Telefonsystem oder Audiokonferenzen zugewiesen haben. Sie können hinzufügen/Spalten der Tabelle entfernen.
***
![Nummer 1](../images/sfbcallout1.png)
*   **Benutzer-ID** ist der Benutzer anmelden.
*   **Telefonnummer** ist die Nummer, die einem Benutzer zugewiesen ist. 
*   **Block** ist-Aktion die Zeit (UTC), die der Benutzer für das Tätigen von Anrufen abgehalten wurde.
*   **Block-Aktion** ist der Typ der Aktion, die den Benutzer blockieren ausgeführt wurde.
*   **Block Aktion Grund** ist der Grund dafür, dass der Benutzer anrufen gesperrt wurde.
***
![Nummer 2](../images/sfbcallout2.png)<br/>
Klicken Sie auf diese Option, um eine Spalte **zum Gruppieren nach einer bestimmten Spalte,** Drag & drop hier die Spaltenüberschrift ziehen, wenn eine Ansicht zu erstellen, die alle Daten in eine oder mehrere Spalten gruppiert werden soll.
***
![Nummer 3](../images/sfbcallout3.png)<br/>
Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen.

Exportiert die Daten aller Benutzer, und ermöglicht es Ihnen, führen Sie einfache sortieren und zur weiteren Analyse filtern. Wenn Sie weniger als 2.000 Benutzern haben, können Sie zum Sortieren und Filtern in der Tabelle im Bericht selbst. Wenn Sie mehr als 2.000 Benutzern in Reihenfolge zum Filtern und Sortieren haben, müssen Sie die Daten exportiert werden.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Skype für Business Organisator konferenzaktivitätsbericht](conference-organizer-activity-report.md) Sie können sehen, wie viel Ihre Benutzer Konferenzen organisieren, die Sofortnachrichten, Audio/Video, Anwendungsfreigabe, Web, Dial-in/Out - 3rd Party, und Dial-in/Out - Microsoft verwenden.
    
- [Skype für Teilnehmer Business-konferenzaktivitätsbericht](conference-participant-activity-report.md) Sie können sehen, wie viele Sofortnachrichten, Audio/Video, Anwendungsfreigabe, Web und und Konferenzen/Dial-Out Konferenz sind beteiligt wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Skype für Business PSTN-Verwendungsbericht](pstn-usage-report.md) Sie können die Anzahl der Minuten in eingehenden und ausgehenden Anrufe verbracht und Kosten für diese Anrufe sehen.

- [Skype für Business PSTN Minute Pools Bericht](pstn-minute-pools-report.md) sehen Sie die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht.

- [Skype für Business Sitzung Detailbericht](session-details-report.md) Sie können die Details zu einzelnen Benutzers Anruf Erfahrungen sehen.
   
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
