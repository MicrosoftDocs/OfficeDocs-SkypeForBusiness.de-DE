---
title: Skype for Business Online-Berichterstellung
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, wlooney
ms.topic: article
ms.assetid: 4935cddf-fafa-442d-91a3-246af01f8373
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
description: 'Verwenden Sie dieses Referenzhandbuch, um informationen zu Skype for Business Online-Berichterstellung zu erhalten und zu erfahren, welche Informationen verfügbar sind. '
ms.openlocfilehash: f7e1f5ff50763b224269a9fd9410f372da5cf9b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589157"
---
# <a name="skype-for-business-online-reporting"></a>Skype for Business Online-Berichterstellung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Als Administrator für Ihre Organisation wäre es praktisch, eine vollständige Liste aller verschiedenen Berichte zur Verfügung zu haben, die in Skype for Business Online verfügbar sind. Dazu gehören alle verschiedenen Berichte und die Informationen, die in den einzelnen Berichten enthalten sein können.
  
Um auf die Skype for Business Online-Berichte zu zugreifen, melden Sie sich bei der Microsoft 365 Admin Center mit Ihrem Benutzerkonto und Kennwort an. Dem für die Anmeldung verwendeten Konto muss entweder die globale Administratorrolle zugewiesen sein, oder Sie müssen die Rolle des Dienstadministrators für Skype for Business delegieren, um die Berichte anzuzeigen.
  
> [!NOTE]
> Um Berechtigungen zu überprüfen, müssen Sie im Admin Center > **Aktive**  >  **Benutzer zuweisen.** Klicken Sie auf den Anzeigenamen des Benutzers, und klicken Sie dann auf **Bearbeiten.** Klicken Sie anschließend auf der Seite mit den Kontoeigenschaften auf **Rollen.**
  
## <a name="skype-for-business-online-reporting-reference"></a>Skype for Business Online-Berichterstellungsreferenz

In den Admin Center können Sie verschiedene Arten von Berichten verwenden, einschließlich Berichte für Skype for Business Online.
  
 **So zeigen Sie die Berichte an**
  
1. Wechseln Sie zum Admin Center oder **Skype for Business Admin Center**  >  **Berichte**.
    
2. Klicken Sie im Fenster „Dashboards" auf das Widget „Berichte", oder wählen Sie den gewünschten Bericht aus der Liste aus.
    
|**Bericht**|**Was wird gemessen?**|
|:-----|:-----|
|[Skype for Business-Aktivitätsbericht](activity-report.md) <br/> | Aktive Benutzer <br/>  Aktive Chatbenutzer <br/>  Aktive Audiobenutzer <br/>  Aktive Videobenutzer <br/>  Aktive Anwendungsfreigabenutzer <br/>  Aktive Dateiübertragungsbenutzer <br/> |
|[Skype for Business - Bericht über Peer-zu Peer-Aktivitäten](peer-to-peer-activity-report.md) <br/> | Gesamt <br/>  Chat <br/>  Audio <br/>  Video <br/>  Anwendungsfreigabe <br/>  Dateiübertragung <br/> |
|[Skype for Business: Konferenzteilnehmer-Aktivitätsbericht](conference-participant-activity-report.md) <br/> | Gesamt <br/>  Chat <br/>  Audio/Video <br/>  Anwendungsfreigabe <br/>  Web <br/>  Einwahl <br/> |
|[Bericht „Skype for Business - Aktivitäten zum Organisieren von Konferenzen"](conference-organizer-activity-report.md) <br/> | Audiominuten <br/>  Videominuten <br/>  Audio/Videokonferenzminuten <br/>  Einwahlkonferenzminuten <br/>  Auswahlkonferenzminuten <br/> |
|[Bericht „Skype for Business - verwendete Clients"](device-usage-report.md) <br/> | Windows-Benutzer: <br/>  Windows Phone-Benutzer <br/>  Android-Benutzer <br/>  iPhone-Benutzer <br/>  iPad-Benutzer <br/> |
|[Skype for Business-Aktivitätsbericht](activity-report.md) <br/> | Benutzername <br/>  Zeit der letzten Anmeldung <br/>  Zeit der letzten Aktivität <br/>  Peer-to-Peer-Sitzungen insgesamt <br/>  Peer-to-Peer-Chatsitzungen insgesamt <br/>  Peer-to-Peer-Audiositzungen insgesamt <br/>  Peer-to-Peer-Videositzungen insgesamt <br/>  Peer-to-Peer-Anwendungsfreigabesitzungen insgesamt <br/>  Gesamtdauer der Peer-to-Peer-Audiositzung in Minuten <br/>  Gesamtdauer der Peer-to-Peer-Videositzung in Minuten <br/>  Organisierte Konferenzen insgesamt <br/>  Organisierte Chatkonferenzen insgesamt <br/>  Organisierte Audio-/Videokonferenzen insgesamt <br/>  Organisierte Anwendungsfreigabekonferenzen insgesamt <br/>  Organisierte Webkonferenzen insgesamt <br/>  Organisierte Einwahlaudiokonferenzen insgesamt <br/>  Organisierte Audio-/Videokonferenzminuten insgesamt <br/>  Gesamtzahl der Konferenzteilnahmen <br/>  Gesamtzahl der Chatkonferenzteilnahmen <br/>  Gesamtzahl der Audio-/Videokonferenzteilnahmen <br/>  Gesamtzahl der Teilnahmen an Anwendungsfreigabekonferenzen <br/>  Gesamtzahl der Webkonferenzteilnahmen <br/>  Gesamtzahl der Teilnahmen an Einwahlaudiokonferenzen <br/>  Teilnahme an Audio-/Videokonferenzen in Minuten insgesamt <br/>  Getätigte PSTN-Anrufe insgesamt <br/>  Empfangene PSTN-Anrufe insgesamt <br/>  Getätigte PSTN-Anrufe in Minuten insgesamt <br/>  Empfangene PSTN-Anrufminuten insgesamt <br/>  Nachrichten gesamt <br/>  Übertragene Dateien gesamt <br/> |
|[Bericht zum PSTN-Verbrauch in Skype for Business](pstn-usage-report.md) <br/>  | Benutzername <br/>  Datum/Zeit des Anrufs <br/>  Telefonnummer <br/>  CallID <br/>  Anruftyp <br/>  Ort <br/>  Verbindungsdauer <br/>  Währung <br/>  Verbindungskosten <br/> |
|[Skype for Business von Benutzern gesperrter Bericht](users-blocked-report.md) <br/> | Aktionsdatum <br/>  Benutzername <br/>  Aktionstyp <br/>  Telefonnummer <br/>  Grund <br/> |
|[Skype for Business Bericht über PSTN-Minutenpools](pstn-minute-pools-report.md) <br/> | Funktion ist der für den Anruf verwendete Lizenz-/Serviceplan. <br/> Lizenztyp <br/> Beschreibung der Funktionen <br/> Country Minute Pool  <br/> Verwendete Minuten <br/> Gesamtminuten <br/> Prozent der Minuten, die für den Monat verwendet wurden <br/> |
|[Skype for Business Sitzungsdetails](session-details-report.md) <br/> | Benutzeralias <br/> Dialogfeld-ID  <br/> Medientypen  <br/> Start- und Endzeiten <br/> An- und von-URI <br/> Konferenz-URL <br/> Telefon-Nummer <br/> |
 
## <a name="related-topics"></a>Verwandte Themen
[Aktivitätsberichte im Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

  
 
