---
title: Bericht „PSTN-Verbrauch“
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 74eda791-c41f-4fd9-ae0b-913342e7ab04
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
description: Im neuen Bereich Berichte im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht PSTN-Verwendungsdetails in Skype for Business die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
ms.openlocfilehash: e4af77832cca1cd2a9d9de49aa83f4400c359277
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561646"
---
# <a name="pstn-usage-report"></a>Bericht „PSTN-Verbrauch“

Im neuen Bereich **Berichte** im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht **PSTN-Verwendungsdetails in Skype for Business** die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
  
Checken Sie der [Übersicht über die Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) für weitere Berichte, die verfügbar sind.
  
In diesem Bericht, zusammen mit den anderen Skype für Business-Berichte, erhalten Sie Details auf Aktivität, einschließlich aufrufen Verwendung in Ihrer Organisation. Diese Angaben sind sehr hilfreich, wenn Sie untersuchen, für Ihre Organisation und für das Einrichten von [Communications haben](/microsoftteams/what-are-communications-credits) planen und Durchführen von anderen Business Entscheidungen
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Abrufen des Berichts zu den PSTN-Verbrauchsdetails in Skype for Business

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

- Wechseln Sie zu **Office 365 Administrationscenter** > **Admin zentriert** > **Skype für Business Administrationscenter** > **Berichte** > **PSTN-Verwendungsdetails**.
    
    > [!NOTE]
    > Je nach vorhandenem Office 365-Abonnement werden möglicherweise nicht alle Produkte und Berichte angezeigt, die in diesem Artikel besprochen werden. 
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretieren des Berichts zur Skype for Business PSTN-Verwendung

Sie können die Skype for Business PSTN-Verwendung des Benutzers anzeigen, indem Sie sich alle angezeigten Spalten ansehen.
  
Der Bericht sieht wie folgt aus:
  
![Bericht zum PSTN-Verbrauch in Skype for Business](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Die Tabelle zeigt die gesamte PSTN-Verwendung pro Benutzer an. Diese Auflistung enthält alle Benutzer, denen Skype for Business zugewiesen ist, sowie ihre PSTN-Verwendung. Sie können Spalten zur Tabelle hinzufügen bzw. daraus entfernen.
*    **Anruf-ID** ist die ID für einen Anruf. Damit wird der Anruf eindeutig identifiziert, wenn Sie beim Microsoft-Support anrufen.
*    **Benutzer-ID** ist der Anmeldename des Benutzers.
*    **Rufnummer** ist die Skype for Business-Rufnummer, unter der ein eingehender Anruf empfangen wurde, oder die Nummer, die für einen ausgehenden Anruf gewählt wurde.
*    **Benutzerstandort** ist das Land/die Region, in dem bzw. der sich der Benutzer befindet.  
*    **Anrufer-ID** ist die Telefonnummer des Anrufers (Anrufer-ID). Bei eingehenden Anrufen handelt es sich um die Nummer, von der der Anruf ausging, und bei ausgehenden Anrufen um die Skype for Business-Nummer, von der der Anruf ausging.  
*    **Anruftyp** gibt an, ob es sich um einen aus- oder eingehenden PSTN-Anruf handelte und um welchen Anruftyp es sich handelte (z. B. von einem Benutzer getätigter Anruf oder Audiokonferenz). Die folgenden Anruftypen sind möglich: 

     **Anrufplan-Anruftypen** 
     *    **user_in** (Der Benutzer hat einen eingehenden PSTN-Anruf erhalten.) 
     *    **user_out** (Der Benutzer hat einen ausgehenden PSTN-Anruf getätigt.) 
     *    **user_out_conf** (Der Benutzer hat zwei oder mehr PSTN-Teilnehmer zum Anruf hinzugefügt, beispielsweise in einer Dreier-Telefonkonferenz.) 
     *    **user_out_transfer** (Der Benutzer hat den Anruf an eine PSTN-Nummer durchgestellt.) 
     *    **user_out_forwarding** (Der Benutzer hat den Anruf an eine PSTN-Nummer weitergeleitet.)

     **Audiokonferenz-Anruftypen**
     *    **conf_in** (Ein eingehender Anruf an die Audiokonferenzbrücke) 
     *    **conf_out** (Ein ausgehender Anruf von der Audiokonferenzbrücke, normalerweise um eine PSTN-Nummer zur Konferenz hinzuzufügen)

     **Unified Communication Applications (UCAP)** 
     *    **ucap_in** (eine eingehende PSTN-Anruf an die UC-Anwendung wie automatische Telefonzentrale oder ein Anruf Warteschlange) 
     *    **ucap_out** (eine ausgehende PSTN-Anruf aus der UC-Anwendung wie automatische Telefonzentrale oder ein Anruf Warteschlange)
     *    **Hinweis:** Anrufe, die aus der UC-Anwendung an einen Benutzer übertragen wurden, wie eine automatische Telefonzentrale oder ein Anruf Warteschlange nicht in den Nutzungsbericht PSTN, da diese erscheint anrufabschnitte Audioanrufe für Peer-zu-Peer (P2P) sind. Wählen Sie Zugriff auf die P2P-Anrufe in die Skype für Business Admin Center unter "Tools > Skype für aufrufen BA" und zum Suchen nach Benutzername oder SIP-Adresse den Aufruf von Datum/Uhrzeit Korrelieren und/oder Ursprung CLID (Aufrufen von Zeile-ID). 
*     
     **Inland/International** gibt an, ob der getätigte Anruf basierend auf dem Standort des Benutzers ein Inlandsanruf (innerhalb eines Lands bzw. einer Region) oder ein Auslandsanruf (außerhalb eines Lands bzw. einer Region) war.   
*    **Gewähltes Ziel** ist der Name des gewählten Lands bzw. der gewählten Region, beispielsweise Frankreich, Deutschland oder Vereinigte Staaten (USA).   
*    **Zahl** ist der Typ der Telefonnummer, die Telefonnummer des Benutzers ein Dienst oder eine gebührenfreie Telefonnummer stammt.  
*    **Startzeit (UTC)** ist die Uhrzeit, zu der der Anruf gestartet bzw. getätigt wurde.   
*    **Dauer** gibt an, wie lange der Anruf verbunden war.  
*    **ConfID** (Konferenzkennung) ist die Konferenzkennung der Audiokonferenz. 
*    **Gebühren** ist der Betrag (Kosten des Anrufs), der Ihrem Konto für den Anruf belastet wird. 
*    **Währung** ist der Typ der Währung, der zum Berechnen der Kosten des Anrufs verwendet wird. 
*    **Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Folgende Lizenztypen sind möglich: 
     *    **MCOPSTNPP**: Guthaben für Kommunikationen <br/> **MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.) 
     *    **MCOPSTN2**: Plan für Auslandsanrufe 
     *    **MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.) 
     *    **MCOPSTN6** - nationalen aufrufen Plan (240 min aufrufende Plan) Hinweis: eingeschränkter Verfügbarkeit
     *    **MCOMEETADD**: Audiokonferenz
     *    **MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung
> [!NOTE]
> Sie können auch "keine Daten" in einigen Feldern finden Sie unter. "Keine Daten" bedeutet, dass das Feld nicht auf den Anruftyp oder Funktion angewendet ist. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns.
 ***
![Nummer 3](../images/sfbcallout3.png)<br/>Sie können auch den Bericht exportieren der Daten auf einer Registerkarte getrennt Excel-Datei durch Klicken oder tippen auf die Schaltfläche **nach Excel exportieren** . <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Auswahl (Drittanbieter) und Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Skype für Unternehmensbenutzer blockiert Bericht](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation, die vom PSTN-Anrufe tätigen blockiert wurden, finden Sie unter.

- [Skype für Business PSTN Minute Pools Bericht](pstn-minute-pools-report.md) sehen Sie die Anzahl der Minuten, die während des aktuellen Monats innerhalb Ihrer Organisation verbraucht.

- [Skype für Business Sitzung Detailbericht](session-details-report.md) Sie können die Details zu einzelnen Benutzers Anruf Erfahrungen sehen.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
