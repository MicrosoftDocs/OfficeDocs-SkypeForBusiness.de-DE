---
title: Konferenzrichtlinie für Skype Raumsystemkonten
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: In diesem Thema erfahren Sie, wie Sie Konferenzrichtlinien für Skype Room System-Konten zuweisen.
ms.openlocfilehash: 202440953aedaa54ac69a7bd4549bf7dcbd8d865
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618201"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Konferenzrichtlinie für Skype Raumsystemkonten
 
In diesem Thema erfahren Sie, wie Sie Konferenzrichtlinien für Skype Room System-Konten zuweisen.
  
## <a name="conferencing-policy-features"></a>Konferenzrichtlinienfeatures

Die dem Skype Raumsystemkonto zugewiesene Konferenzrichtlinie muss bestimmte Merkmale aufweisen. In den meisten Jahren nimmt der Skype Room System-Client an einer geplanten Besprechung teil, und daher wirkt sich die Konferenzrichtlinie des Besprechungsorganisators auf die Konferenz aus. In Skype for Business Server hängen bestimmte Funktionen jedoch von der Konfiguration des Teilnehmers ab. Wenn die Richtlinie des Teilnehmers beispielsweise eine maximale Videoauflösung von 1080p zulässt, werden die Teilnehmer diese Videofunktion mit höherer Auflösung in der Konferenz erleben, auch wenn die Richtlinie des Organisators dies nicht zulässt. In der folgenden Tabelle werden mehrere dieser Einstellungen beschrieben, die Sie beim Einrichten von Konferenzrichtlinien für Skype Raumsystemkonten in Ihrer Organisation beachten sollten. 
  
|Feature  <br/> |Wert  <br/> |Kommentar  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Muss für Skype Raumsystemaudio "true" sein  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Muss "true" sein, damit Skype Raumsystem-Audio in Ad-hoc-Whiteboardsitzungen in Skype Raumsystem funktioniert  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Ermöglicht Skype Room System das Rendern mehrerer Videostreams mit mehreren Ansichten  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto Enterprise-VoIP aktiviert ist (siehe Abschnitt "Aktivieren Skype Raumsystemkonten für Skype for Business")  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto Enterprise-VoIP (EV) aktiviert ist.  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A in Besprechungen mit Sofortbesprechungen (ad hoc), aber Skype Raumsystem kann auf Umfragen auf dem Bildschirm am Anfang des Raums antworten.  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A in Besprechungen mit Sofortbesprechungen (ad hoc), aber Skype Raumsystem kann auf Umfragen auf dem Bildschirm am Anfang des Raums antworten.  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Nicht verfügbar für Skype Raumsystem. Wenn TRUE, kann eine Remotepartei aufzeichnen  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Nicht verfügbar für Skype Raumsystem. Wenn TRUE, kann eine Remotepartei aufzeichnen  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Ermöglicht dem Skype Room System-Client die Teilnahme an Peer-to-Peer-Videositzungen  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |Nicht zutreffend  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Von Skype for Business Server ignoriert, verwendet Skype Raumsystem HD1080.  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Wirkt sich auf Besprechungssitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System aus.  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Dies ist die maximal zulässige ausgehende Videobitrate. Skype Room System kann einen 1080-Stream zusammen mit Pano (wenn RoundTable verwendet wird) mit dieser Bitrate senden. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |Nicht zutreffend  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Es wird empfohlen, dies so hoch wie möglich festzulegen. Die effektive Bandbreite hängt von den Netzwerkbedingungen zum Zeitpunkt der Konferenzen ab.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Muss TRUE sein, damit Skype Room System Videostreams mit mehreren Ansichten sicherstellen kann.  <br/> |
   
* Informationen zur Bandbreitenplanung finden Sie unter [Netzwerkbandbreitenanforderungen für Mediendatenverkehr.](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Wenn der Skype Room System-Client versucht, an einer geplanten Besprechung teilzunehmen, die von einem Benutzer organisiert wird, der in einem Lync Server 2010-Pool verwaltet wird, könnte die Konferenzrichtlinie des Besprechungsorganisators verhindern, dass der Skype Room System-Client zusammenarbeitet. 
  
## <a name="meeting-authentication"></a>Besprechungsauthentifizierung

Skype Room System fordert Benutzer zur Authentifizierung auf, wenn sie den Link zum Beitreten zu einer Besprechung verwenden, um an einer eingeschränkten Besprechung teilzunehmen. Beispielsweise eine Besprechung, für die in Outlook Besprechungslobbyoptionen konfiguriert wurden. Diese Einstellung ist für angepasste Besprechungen immer aktiviert, und die Benutzer werden immer aufgefordert. Bei uneingeschränkten Besprechungen können Benutzer jedoch ohne Authentifizierung an der Besprechung teilnehmen. 
  
Der folgende Befehl ermöglicht Administratoren die Authentifizierung für alle Besprechungen, einschließlich uneingeschränkter Besprechungen: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Standardmäßig ist RequireRoomSystemsAuthorization FALSE. 
  

