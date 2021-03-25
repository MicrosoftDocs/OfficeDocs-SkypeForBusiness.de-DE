---
title: Bericht "PSTN-Verbrauch"
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
f1.keywords:
- NOCSH
ms.custom:
- Reporting
description: Im neuen Bereich Berichte im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht PSTN-Verwendungsdetails in Skype for Business die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
ms.openlocfilehash: 831c1e7168bcffc72acb8ef1573167fe63ff44f5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106471"
---
# <a name="pstn-usage-report"></a>Bericht "PSTN-Verbrauch"

Im neuen Bereich **Berichte** im Skype for Business Admin Center wird die Anruf- und Audiokonferenzaktivität in Ihrer Organisation angezeigt. Sie können einzelne Berichte näher analysieren, damit Sie einen genaueren Einblick in die Aktivitäten der einzelnen Benutzer erhalten. Sie können beispielsweise mit dem Bericht **PSTN-Verwendungsdetails in Skype for Business** die Dauer (in Minuten) der eingehenden bzw. ausgehenden Anrufe sowie die damit verbundenen Kosten anzeigen. Sie können PSTN-Verwendungsdetails für Audiokonferenzen einschließlich der Kosten eines Anrufs anzeigen, sodass Sie die Verwendungs- und Abrechnungsdetails des Anrufs zum Ermitteln der Verwendung in Ihrer Organisation nachvollziehen können.
  
Weitere verfügbare [Berichte finden](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263) Sie in der Übersicht Berichte.
  
Dieser Bericht enthält zusammen mit den anderen Skype for Business-Berichten Details zu Aktivitäten, einschließlich Anrufnutzung in ihrer gesamten Organisation. Diese Details sind sehr hilfreich beim Untersuchen, Planen und Treffen anderer Geschäftsentscheidungen für Ihre Organisation und beim Einrichten von [Guthaben für Kommunikationen.](/microsoftteams/what-are-communications-credits)
  
> [!NOTE]
> Sie können alle Skype for Business-Berichte anzeigen, wenn Sie sich als Administrator beim Microsoft 365 Admin Center anmelden. 
  
## <a name="how-to-get-to-the-skype-for-business-pstn-usage-details-report"></a>Abrufen des Berichts zu den PSTN-Verbrauchsdetails in Skype for Business

![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

- Wechseln Sie zum Admin Center > **Admin Center** Skype for Business  >  **Admin Center** Meldet  >    >  **PSTN-Nutzungsdetails.**
    
    > [!NOTE]
    > Je nach Ihrem Microsoft 365- oder Office 365-Abonnement werden möglicherweise nicht alle hier angezeigten Produkte und Berichte angezeigt.
  
## <a name="interpret-the-skype-for-business-pstn-usage-report"></a>Interpretieren des Berichts zur Skype for Business PSTN-Verwendung

Sie können die Skype for Business PSTN-Verwendung des Benutzers anzeigen, indem Sie sich alle angezeigten Spalten ansehen.
  
Der Bericht sieht wie folgt aus:
  
[![Skype for Business PSTN-Nutzungsbericht ](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png)](../images/79d7aadf-c69e-4d6a-8179-ab69dbbb2472.png#lightbox)

***
![Nummer 1](../images/sfbcallout1.png)<br/>Die Tabelle zeigt die gesamte PSTN-Verwendung pro Benutzer an. Diese Auflistung enthält alle Benutzer, denen Skype for Business zugewiesen ist, sowie ihre PSTN-Verwendung. Sie können Spalten zur Tabelle hinzufügen bzw. daraus entfernen.
*    **Anruf-ID** ist die ID für einen Anruf. Es ist ein Bezeichner für den Anruf, der beim Aufrufen des Microsoft-Dienstsupports verwendet wird.
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
     *    **conf_in** (ein eingehender Anruf an die Audiokonferenzbrücke). Bei Datensätzen dieses Anruftyps entspricht der in der Spalte **Benutzer-ID** angegebene Benutzer dem Organisator der Besprechung.
     *    **conf_out** (ein ausgehender Anruf von der Audiokonferenzbrücke, in der Regel zum Hinzufügen einer PSTN-Nummer zur Konferenz). Bei Datensätzen dieses Anruftyps entspricht der in der Spalte **Benutzer-ID** angegebene Benutzer dem Organisator der Besprechung.

     **Unified Communication Applications (UCAP)** 
     *    **ucap_in** (ein eingehender PSTN-Anruf bei der UC-Anwendung, z. B. automatische Telefonkonferenz oder Anrufwarteschlange) 
     *    **ucap_out** (ein ausgehender PSTN-Anruf aus der UC-Anwendung, z. B. automatische Telefonkonferenz oder Anrufwarteschlange)
         > [!NOTE]
         > Anrufe, die aus der UC-Anwendung an einen Benutzer übertragen wurden, z. B. eine automatische Telefonkonferenz oder Anrufwarteschlange, werden nicht im PstN-Nutzungsbericht angezeigt, da es sich bei diesen Anrufbeinen um P2P-Audioanrufe (Peer-to-Peer)-Audioanrufe handelt. Sie können im Skype for Business Admin Center unter "Tools > Skype for Business Call Analytics" auf die P2P-Anrufe zugreifen und nach Benutzername oder SIP-Adresse suchen, die den Anruf nach Datum/Uhrzeit und/oder Ursprung der CLID (Anrufleitungs-ID) korreliert. 

     **Inland/International** gibt an, ob der getätigte Anruf basierend auf dem Standort des Benutzers ein Inlandsanruf (innerhalb eines Lands bzw. einer Region) oder ein Auslandsanruf (außerhalb eines Lands bzw. einer Region) war.    
*    **Gewähltes Ziel** ist der Name des gewählten Lands bzw. der gewählten Region, beispielsweise Frankreich, Deutschland oder Vereinigte Staaten (USA).    
*    **Der Nummerntyp** ist der Typ der Telefonnummer, die von der Telefonnummer eines Benutzers, einem Dienst oder einer gebührenfreien Rufnummer abhing.  
*    **Startzeit (UTC)** ist die Uhrzeit, zu der der Anruf gestartet bzw. getätigt wurde.    
*    **Dauer** gibt an, wie lange der Anruf verbunden war.  
*    **ConfID** (Konferenzkennung) ist die Konferenzkennung der Audiokonferenz. 
*    **Gebühren** ist der Betrag (Kosten des Anrufs), der Ihrem Konto für den Anruf belastet wird. 
*    **Währung** ist der Typ der Währung, der zum Berechnen der Kosten des Anrufs verwendet wird. 
*    **Capability** (Funktion) ist die für den Anruf verwendete Lizenz. Folgende Lizenztypen sind möglich: 
     *    **MCOPSTNPP**: Guthaben für Kommunikationen <br/> **MCOPSTN1**: Plan für Inlandsanrufe (US-Plan mit 3.000 Min./EU-Plan mit 1.200 Min.) 
     *    **MCOPSTN2**: Plan für Auslandsanrufe 
     *    **MCOPSTN5**: Plan für Inlandsanrufe (Anrufplan mit 120 Min.) 
     *    **MCOPSTN6** – Plan für Inlandsrufe (240 Minuten Anrufplan) Hinweis: Eingeschränkte Verfügbarkeit
     *    **MCOMEETADD**: Audiokonferenz
     *    **MCOMEETACPEA**: Audiokonferenz mit Minutenabrechnung
     
> [!NOTE]
> Wenn Sie einen Bericht ausführen möchten, der nur Anrufe pro Minute enthält, die nicht in Ihrem Anruf- oder Konferenzabonnement enthalten sind, filtern Sie den Bericht mit der Funktion "MCOPSTNPP". Dadurch erhalten Sie eine Itemisierung aller Anrufe per Minutenlohn.  Filtern Sie für Audiokonferenzen pro Minute nach "MCOMEETACPEA" statt nach "MCOPSTNPP".  

> [!NOTE]
> Möglicherweise wird in einigen Feldern auch "keine Daten" angezeigt. "Keine Daten" bedeutet, dass das Feld nicht auf den Anruftyp oder die -funktion anwendbar ist. 

> [!NOTE]
> Wenn Sie über einen Anrufplan für Telstra oder Softbank verfügen, werden im Bericht pstN-Nutzung keine Anrufdetailsesätze dargestellt. Wenden Sie sich für Ihre Berichterstellungsanforderungen an Telstra oder Softbank. 
***
![Nummer 2](../images/sfbcallout2.png)<br/>Klicken Sie, um eine Spalte nach einer bestimmten Spalte in Die Gruppe An zu ziehen, ziehen Sie die Spaltenüberschrift hier, und legen Sie sie **ab,** wenn Sie eine Ansicht erstellen möchten, die alle Daten in einer oder mehreren Spalten gruppieren soll.
 ***

## <a name="exporting-pstn-usage-report"></a>Exportieren des PstN-Nutzungsberichts

Wenn Sie auf die Schaltfläche **Exportieren nach Excel** klicken oder tippen, können Sie den PstN-Nutzungsbericht herunterladen. Sie können Daten bis zu einem Jahr ab dem aktuellen Datum exportieren, es sei denn, länderspezifische Vorschriften verbieten die Aufbewahrung der Daten für 12 Monate.

Dadurch werden Daten aller Benutzer exportiert, und Sie können einfache Sortier- und Filtervorgänge zur weiteren Analyse ausführen.

Der Exportvorgang kann je nach Datenmenge einige Sekunden bis mehrere Minuten dauern. Wenn der Server den Export abgeschlossen hat, erhalten Sie eine ZIP-Datei mit dem Namen "**Calls.Export.[ `identifier` ]. zip**", bei dem der Bezeichner eine eindeutige ID für den Export ist, die zur Problembehandlung verwendet werden kann.

Wenn Sie über Anrufpläne und Direktes Routing verfügen, enthält die exportierte Datei möglicherweise Daten für beide Produkte. Die #A0 hat den Dateinamen "**PSTN.calls.[ `UTC date` ]. csv".** Zusätzlich zu PSTN- und Direct Routing-Dateien enthält das Archiv die Datei "**parameters.jsauf**", mit dem ausgewählten Exportzeitbereich und -funktionen (sofern aktiviert).

Die exportierte Datei ist eine CSV-Datei (Comma Separated Values), die dem [RFC 4180-Standard](https://tools.ietf.org/html/rfc4180) entspricht. Die Datei kann in Excel oder einem anderen standardkonformen Editor geöffnet werden, ohne dass Transformationen erforderlich sind.

Die erste Zeile der CSV enthält Spaltennamen.

### <a name="fields-in-the-export"></a>Felder im Export

Die exportierte Datei enthält zusätzliche Felder, die im Onlinebericht nicht verfügbar sind. Diese können für die Problembehandlung und automatisierte Workflows verwendet werden.

> [!div class="has-no-wrap"]  
> | #  | Name | [Datentyp (SQL Server)](/sql/t-sql/data-types/data-types-transact-sql) | Beschreibung |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | Eindeutiger Anrufbezeichner |
> | 1 | Anruf-ID | `nvarchar(64)` | Anrufbezeichner. Nicht garantiert eindeutig |
> | 2 | Konferenz-ID | `nvarchar(64)` | ID der Audiokonferenz |
> | 3 | Benutzerspeicherort | `nvarchar(2)` | Ländercode des Benutzers, [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | Aufrufen der Benutzer-ID in Azure Active Directory.<br/> Diese und andere Benutzerinformationen sind für Botanruftypen null/leer (ucap_in, ucap_out) |
> | 5 | UPN | `nvarchar(128)` | UserPrincipalName (Anmeldename) in Azure Active Directory.<br/>Dies entspricht in der Regel der SIP-Adresse des Benutzers und kann mit der E-Mail-Adresse des Benutzers identisch sein. |
> | 6 | Anzeigename des Benutzers | `nvarchar(128)` | Anzeigename des Benutzers |
> | 7 | Anrufer-ID | `nvarchar(128)` | Nummer, die den Anruf für eingehende Anrufe erhalten hat, oder die Nummer, die für ausgehende Anrufe gewählt wurde. [E.164-Format](https://en.wikipedia.org/wiki/E.164) |
> | 8 | Anruftyp | `nvarchar(32)` | Ob es sich bei dem Anruf um einen ausgehenden oder eingehenden Festnetzanruf und die Art des Anrufs wie einen Anruf eines Benutzers oder eine Audiokonferenz |
> | 9 | Zahlentyp | `nvarchar(16)` | Telefonnummerntyp des Benutzers, z. B. gebührenfreier Dienst |
> | 10 | Inland/International | `nvarchar(16)` | Unabhängig davon, ob der Anruf im Inland (innerhalb eines Landes oder einer Region) oder international (außerhalb eines Landes oder einer Region) basierend auf dem Standort des Benutzers war |
> | 11 | Ziel wählt | `nvarchar(64)` | Land oder Region gewählt |
> | 12 | Zielnummer | `nvarchar(32)` | Im [E.164-Format gewählte Nummer](https://en.wikipedia.org/wiki/E.164) |
> | 13 | Startzeit | `datetimeoffset` | Anrufstartzeit (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 14 | Endzeit | `datetimeoffset` | Anrufendezeit (UTC, [ISO 8601)](https://en.wikipedia.org/wiki/ISO_8601) |
> | 15 | Dauer Sekunden | `int` | Wie lange der Anruf verbunden war |
> | 16 | Verbindungsgebühr | `numeric(16, 2)` | Verbindungsgebührenpreis |
> | 17 | Aufladen | `numeric(16, 2)` | Betrag oder Kosten des Anrufs, der Ihrem Konto in Rechnung gestellt wird |
> | 18 | Währung | `nvarchar(3)` | Zum Berechnen der Kosten des Anrufs verwendete Währung ([ISO 4217](https://en.wikipedia.org/wiki/ISO_4217)) |
> | 19 | Funktion | `nvarchar(32)` | Die für den Anruf verwendete Lizenz |

    
## <a name="want-to-see-other-skype-for-business-reports"></a>Möchten Sie andere Skype for Business-Berichte anzeigen?

- [Skype for Business-Aktivitätsbericht](activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Peer-zu-Peer-Konferenzsitzungen nutzen, organisieren und daran teilnehmen.
    
- [Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) : Sie können die Geräte einschließlich Windows-basierter Betriebssysteme und mobiler Geräte anzeigen, auf denen die Skype for Business-App installiert ist, und die für Chats und Besprechungen verwendet werden.
    
- [Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) : Sie können sehen, in welchem Umfang Ihre Benutzer Konferenzen organisieren, für die Chat, Audio/Video, Anwendungsfreigabe, Web, Auswahl (Drittanbieter) und Auswahl (Microsoft) verwendet werden.
    
- [Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) : Sie können sehen, an wie vielen Chats, Audio/Video-Übertragungen, Anwendungsfreigaben, Webkonferenzen und Auswahlkonferenzen teilgenommen wird.
    
- [Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) : Sie können sehen, in welchem Umfang die Benutzer Chat, Audio/Video, Anwendungsfreigabe sowie Dateiübertragung verwenden.
    
- [Bericht "Blockierte Skype for Business-Benutzer"](users-blocked-report.md) Sie können die Benutzer in Ihrer Organisation sehen, die für pstN-Anrufe gesperrt wurden.

- [Skype for Business PSTN-Minutenpools](pstn-minute-pools-report.md) melden, dass Sie die Anzahl der Minuten sehen können, die während des aktuellen Monats in Ihrer Organisation verbraucht wurden.

- [Skype for Business-Sitzungsdetailssbericht](session-details-report.md) Sie können Details zu den Anruferfahrungen einzelner Benutzer anzeigen.
    
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)
  
  
