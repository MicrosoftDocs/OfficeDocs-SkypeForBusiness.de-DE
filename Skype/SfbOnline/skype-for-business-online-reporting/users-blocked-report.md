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
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: 'Dieser Bericht bietet Ihnen mit den anderen Skype for Business-Berichten nähere Einzelheiten zur jeweiligen Aktivität, einschließlich der PSTN-Nutzung in der gesamten Organisation. '
ms.openlocfilehash: f2708512dfb1cf03e367af09abb288e62329eaf0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606724"
---
# <a name="users-blocked-report"></a>Bericht „Benutzer gesperrt“

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Im neuen Skype for Business-Dashboard **Berichte** wird eine Aktivitätsübersicht für die Skype for Business-Produkte in Ihrer Organisation angezeigt. Mit dieser können Sie einzelne Berichte auf Produktebene näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten in jedem Produkt erhalten. Sie können z.  B. den Bericht Skype for Business Benutzer gesperrt verwenden, um die Benutzer in Ihrer Organisation zu sehen, die für das Erstellen von PSTN-Anrufen gesperrt wurden. Dieser Bericht bietet Ihnen mit den anderen Skype for Business-Berichten nähere Einzelheiten zur jeweiligen Aktivität, einschließlich der PSTN-Nutzung in der gesamten Organisation.
  
 Weitere verfügbare [Berichte finden](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) Sie unter Übersicht über Berichte.
  
> [!NOTE]
> Sie können alle Berichte Skype for Business, wenn Sie sich als Administrator bei der Microsoft 365 Admin Center. 
  
## <a name="how-to-get-to-the-skype-for-business-users-blocked-report"></a>So erhalten Sie den Bericht Skype for Business gesperrten Benutzern

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

- Wechseln Sie zum Admin Center, > **Admin Center Skype for Business** Admin  >  **Center**  >  **Meldet**  >  **Benutzer blockiert .**
    
## <a name="interpret-the-skype-for-business-users-blocked-report"></a>Interpretieren des berichts Skype for Business gesperrten Benutzern

Sie können blockierte Benutzer anzeigen, indem Sie sich die einzelnen angezeigten Spalten ansehen.
  
Der Bericht sieht folgendermaßen aus: 
  
![Bericht "Blockierte Benutzer"](../images/df50a413-7a51-4340-a59b-3f83de941762.png)

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
Klicken Sie, um eine Spalte nach Zu gruppieren nach einer bestimmten Spalte zu **ziehen,** ziehen Sie die Spaltenüberschrift hier, und legen Sie sie dort ab, wenn Sie eine Ansicht erstellen möchten, in der alle Daten in einer oder mehreren Spalten angeordnet sind.
***
![Nummer 3](../images/sfbcallout3.png)<br/>
Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.
***

## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Ein-/Auswahl (Drittanbieter) und Ein-/Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) Sie können sehen, an wie vielen Ein-/Einwahlkonferenzen, Audio/Video-, Anwendungsfreigabe-, Web- und Ein-/Aus-Konferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) : Sie können die Anzahl der Minuten sehen, die für eingehende/ausgehende Anrufe aufgewendet wurden, sowie die Kosten für diese Anrufe.

- [Skype for Business Bericht zu PSTN-Minutenpools](pstn-minute-pools-report.md) können Sie die Anzahl der Minuten sehen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.

- [Skype for Business Sitzungsdetails](session-details-report.md) Sie können Details zu den Anruferfahrungen einzelner Benutzer anzeigen.
   
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
