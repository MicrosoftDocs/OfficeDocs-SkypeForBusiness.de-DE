---
title: Bericht „PSTN-Minutenpools“
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 51c2f7ac-2b72-488d-b1ea-f00e1e88ee7a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: Im neuen Skype for Business Admin Center-Berichte werden Anruf- und Audiokonferenzaktivitäten in Ihrer Organisation gezeigt. Sie können Drilldowns in Berichte erstellen, um genauere Einblicke in die Aktivitäten der einzelnen Benutzer zu erhalten. Sie können z. B. den Bericht Skype for Business PSTN-Minutenpools verwenden, um die Anzahl der Minuten zu sehen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.
ms.openlocfilehash: dae86688a5fb0204802f62d28504c3454613bb3d7f7d23f17d09972b94303390
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2021
ms.locfileid: "57850250"
---
# <a name="pstn-minute-pools-report"></a>Bericht „PSTN-Minutenpools“

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

>[!NOTE]
>Dieser Bericht ist nur für Vorschaukunden verfügbar.

Im neuen Skype for Business Admin **Center-Berichte** werden Anruf- und Audiokonferenzaktivitäten in Ihrer Organisation gezeigt. Sie können Drilldowns in Berichte erstellen, um genauere Einblicke in die Aktivitäten der einzelnen Benutzer zu erhalten. Sie können z.  B. den Bericht Skype for Business PSTN-Minutenpools verwenden, um die Anzahl der Minuten zu sehen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.
  
Weitere verfügbare [Berichte finden](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) Sie unter Übersicht über Berichte.
  
Dieser Bericht bietet Ihnen zusammen mit den Skype for Business Bericht Details zu den Aktivitäten in der gesamten Organisation. Diese Details sind beim Untersuchen, Planen und Treffen anderer Geschäftsentscheidungen für Ihre Organisation und zum Einrichten von Guthaben für [Kommunikationen sehr hilfreich.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Wenn Sie sich als Administrator bei der Skype for Business anmelden, können Sie alle Microsoft 365 Admin Center. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-minute-pools-report"></a>So erhalten Sie den Bericht Skype for Business PSTN-Minutenpools

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

- Wechseln Sie zum Admin Center > **Admin Center Skype for Business** Admin  >  **Center**  >  **meldet**  >  **PSTN-Minutenpools**.
    
> [!NOTE]
> Je nach Microsoft 365 oder Office 365 Abonnement, über das Sie verfügen, werden möglicherweise nicht alle hier gezeigten Details angezeigt. 
  
## <a name="interpret-the-skype-for-business-pstn-minute-pools-report"></a>Interpretieren des Berichts Skype for Business PSTN-Minutenpools

Sie können einen Einblick in die 1-Minuten Skype for Business pools des Benutzers erhalten, indem Sie sich die einzelnen angezeigten Spalten ansehen.
  
Der Bericht sieht folgendermaßen aus:

![Skype for Business Bericht über PSTN-Minutenpools](../images/f5da5ca9-3466-4234-8f33-ab50ac5eb781.png)
  
***
![Nummer 1](../images/sfbcallout1.png)<br/>Die Tabelle zeigt eine Aufschlüsselung der Minutenpools nach Lizenz (Funktion) und Verwendungsort. 
*    **Funktion** ist der für den Anruf verwendete Lizenz-/Serviceplan. Zu den Lizenz-/Serviceplänen, die in diesem Bericht möglicherweise enthalten sind, gehören:
     * MCOPSTN1: Plan für Inlandsrufe (EU-Pläne für 3000 Minuten/1200 Minuten)
     * MCOPSTN2 – Anrufplan für Inland & International Calling Plan, von dem aus ein Inlandspool (3.000 Minuten USA/Kanada/PR, europäische Länder mit 1200 Minuten) und ein internationaler Pool (600 Minuten) angezeigt werden. Die Minutengrenze wird erreicht, wenn die nationale oder internationale Obergrenze innerhalb des Kalendermonats erreicht wird. 
     * MCOPSTN5: Plan für Inlandsrufe (120-Minuten-Anrufplan)
     * MCOPSTN6: Plan für Inlandsrufe (240-Minuten-Anrufplan)
     * MCOMEETADD: Audiokonferenz
*    **Funktionsbeschreibung** ist eine Beschreibung des Lizenztyps, der für den Anruf genutzt wird.
*    **Country Minute Pool** ist der Lizenzverwendungsort der Benutzer, die den Minutenpool gemeinsam nutzen. 
*    **Verwendete Minuten** ist die Anzahl der Minuten, die jeden Monat verwendet werden.
*    **Gesamtminuten** ist die Gesamtzahl der für den Monat verfügbaren Minuten. 
*    **Prozent Verwendet ist** der Prozent der Minuten, die für den Monat verwendet werden. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Klicken Sie, um eine Spalte nach Zu gruppieren nach einer bestimmten Spalte zu **ziehen,** ziehen Sie die Spaltenüberschrift hier, und legen Sie sie dort ab, wenn Sie eine Ansicht erstellen möchten, in der alle Daten in einer oder mehreren Spalten angeordnet sind. 
***
![Nummer 3](../images/sfbcallout3.png)<br/>Sie können die Berichtsdaten auch im CSV-Format in eine Excel-Datei exportieren, indem Sie auf die Schaltfläche **Exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. Bei mehr als 2.000 Benutzern müssen Sie die Daten zum Filtern und Sortieren exportieren.
   
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Auswahl (Drittanbieter) und Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Skype for Business bericht für blockierte Benutzer](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation sehen, die für das Erstellen von PSTN-Anrufen gesperrt wurden.

- [Skype for Business Sitzungsdetails](session-details-report.md) Sie können Details zu den Anruferfahrungen einzelner Benutzer anzeigen.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
   
