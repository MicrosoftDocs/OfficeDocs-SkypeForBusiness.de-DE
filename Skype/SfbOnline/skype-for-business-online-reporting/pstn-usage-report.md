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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: Im neuen Bereich Berichte im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht PSTN-Verwendungsdetails in Skype for Business die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
ms.openlocfilehash: dafe072cb327cde15cf4a02ca9e1c71a30f4431b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493987"
---
# <a name="pstn-usage-report"></a>Bericht „PSTN-Verbrauch“

Im neuen Bereich **Berichte** im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht **PSTN-Verwendungsdetails in Skype for Business** die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
  
Weitere verfügbare Berichte finden Sie in der [Übersicht über Berichte](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) .
  
Dieser Bericht enthält zusammen mit den anderen Skype for Business-Berichten Informationen zu Aktivitäten, einschließlich der Anruf Nutzung in Ihrer Organisation. Diese Informationen sind sehr hilfreich, wenn Sie untersuchen, planen und andere geschäftliche Entscheidungen für Ihre Organisation treffen und [Kommunikationsguthaben](/microsoftteams/what-are-communications-credits) einrichten.
  
> [!NOTE]
> Sie können sich alle Skype for Business-Berichte ansehen, wenn Sie sich als Administrator beim Office 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Abrufen des Berichts zu den PSTN-Verbrauchsdetails in Skype for Business

![Ein Symbol mit dem Skype for Business-](../images/sfb-logo-30x30.png) Logo **im Skype for Business Admin Center**

- Wechseln Sie zu **Office 365 Admin Center** > **Admin** > Centers**Skype for Business Admin Center** > **meldet** > **Informationen zur PSTN-Nutzung**.
    
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
     *    **ucap_in** (ein eingehender PSTN-Anruf an die UC-Anwendung, beispielsweise eine automatische Telefonzentrale oder eine Anrufwarteschlange) 
     *    **ucap_out** (ein ausgehender PSTN-Anruf von der UC-Anwendung, beispielsweise eine automatische Telefonzentrale oder eine Anrufwarteschlange)
     *    **Hinweis:** Anrufe, die von der UC-Anwendung an einen Benutzer übertragen wurden, beispielsweise eine automatische Telefonzentrale oder eine Anrufwarteschlange, werden im PSTN-Nutzungsbericht nicht angezeigt, da diese Anruf Beine Peer-to-Peer-Audioanrufe (P2P) sind. Sie können im Skype for Business Admin Center unter "Tools > Skype for Business Call Analytics" auf die P2P-Anrufe zugreifen und nach Benutzer Name oder SIP-Adresse suchen, die den Anruf nach Datum/Uhrzeit und/oder Ursprungs gestensteuerunghttp://Office.Microsoft.com/de-de/fx102821959.aspx (Rufnummernanzeige) korreliert. 
*     
     **Inland/International** gibt an, ob der getätigte Anruf basierend auf dem Standort des Benutzers ein Inlandsanruf (innerhalb eines Lands bzw. einer Region) oder ein Auslandsanruf (außerhalb eines Lands bzw. einer Region) war.    
*    **Gewähltes Ziel** ist der Name des gewählten Lands bzw. der gewählten Region, beispielsweise Frankreich, Deutschland oder Vereinigte Staaten (USA).    
*    **Nummerntyp** ist der Typ der Telefonnummer, die von der Telefonnummer eines Benutzers, einem Dienst oder einer gebührenfreien Nummer ist.  
*    **Startzeit (UTC)** ist die Uhrzeit, zu der der Anruf gestartet bzw. getätigt wurde.    
*    **Dauer** gibt an, wie lange der Anruf verbunden war.  
*    **ConfID** (Konferenzkennung) ist die Konferenzkennung der Audiokonferenz. 
*    **Gebühren** ist der Betrag (Kosten des Anrufs), der Ihrem Konto für den Anruf belastet wird. 
*    **Währung** ist der Typ der Währung, der zum Berechnen der Kosten des Anrufs verwendet wird. 
*    **Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Folgende Lizenztypen sind möglich: 
     *    **MCOPSTNPP**: Guthaben für Kommunikationen <br/> **MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.) 
     *    **MCOPSTN2**: Plan für Auslandsanrufe 
     *    **MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.) 
     *    **MCOPSTN6** -Domestic Calling Plan (240 min Calling Plan) Hinweis: beschränkte Verfügbarkeit
     *    **MCOMEETADD**: Audiokonferenz
     *    **MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung
> [!NOTE]
> Wenn Sie einen Bericht ausführen möchten, um nur Minuten Anrufe einzuschließen, die nicht in Ihrem Anruf-oder Konferenz Abonnement enthalten sind, Filtern Sie den Bericht mit der Funktion "MCOPSTNPP". Auf diese Weise erhalten Sie eine Aufstellungs Möglichkeit für alle Pay-per-Minute-Anrufe.  Für Pay-per-Minute-Audiokonferenzen Filtern Sie nach "MCOMEETACPEA" anstelle von "MCOPSTNPP".  
***
> [!NOTE]
> Möglicherweise werden in einigen Feldern auch "keine Daten" angezeigt. "Keine Daten" bedeutet, dass das Feld nicht auf die Art oder Funktion des Anrufs anwendbar ist. 
***
> [!NOTE]
> Wenn Sie über einen Telstra-Anrufplan verfügen, werden in dem Bericht zur PSTN-Nutzung keine Anruf Detaildatensätze angezeigt. Bitte wenden Sie sich an Telstra für Ihre Berichterstattung. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Click to drag a column to **To group by a particular column, drag and drop the column header here** if you want to create a view that groups all of the data in one or more columns.
 ***
![Nummer 3](../images/sfbcallout3.png)<br/>Sie können die Berichtsdaten auch in eine durch tabstoppgetrennte Excel-Datei exportieren, indem Sie auf die Schaltfläche **nach Excel exportieren** klicken oder tippen. <br/><br/> Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen. Bei weniger als 2.000 Benutzern können Sie innerhalb der Tabelle im Bericht selbst sortieren und filtern. 
    > [!Note] 
    > Despite the export file named as .CSV (which implies a comma delimited export), as there may be commas in the data set, the file is actually delimited with **TABS** and not **COMMAS**.

## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Auswahl (Drittanbieter) und Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht "Skype for Business-Benutzer blockiert](users-blocked-report.md) " Sie können die Benutzer in Ihrer Organisation sehen, die für das tätigen von PSTN-anrufen gesperrt wurden.

- [Skype for Business-PSTN-Minuten Pools-Bericht](pstn-minute-pools-report.md) Sie können die Anzahl der Minuten anzeigen, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.

- [Bericht "Skype for Business-Sitzungsdetails](session-details-report.md) " Details zu den Anruf Erfahrungen einzelner Nutzer werden angezeigt.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Office 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
 
