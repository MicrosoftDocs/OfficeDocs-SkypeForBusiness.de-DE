---
title: Konferenzrichtlinie für Skype Room System-Konten
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: In diesem Thema erfahren Sie, wie Sie Konferenzrichtlinien für Skype Room System-Konten zuweisen.
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812725"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Konferenzrichtlinie für Skype Room System-Konten
 
In diesem Thema erfahren Sie, wie Sie Konferenzrichtlinien für Skype Room System-Konten zuweisen.
  
## <a name="conferencing-policy-features"></a>Konferenzrichtlinienfeatures

Die dem Skype Room System-Konto zugewiesene Konferenzrichtlinie muss bestimmte Merkmale aufweisen. In den meisten Zeiten tritt der Skype Room System-Client einer geplanten Besprechung bei, und daher wirkt sich die Konferenzrichtlinie des Besprechungsorganisators auf die Konferenz aus. In Skype for Business Server hängen bestimmte Funktionen jedoch von der Konfiguration des Teilnehmers ab. Wenn die Richtlinie des Teilnehmers beispielsweise eine maximale Videoauflösung von 1080p zulässt, können die Teilnehmer diese Videofunktion mit höherer Auflösung in der Konferenz nutzen, auch wenn die Richtlinie des Organisators dies nicht zulässt. In der folgenden Tabelle werden verschiedene einstellungen beschrieben, die Sie beim Einrichten von Konferenzrichtlinien für Skype Room System-Konten in Ihrer Organisation beachten sollten. 
  
|Feature  <br/> |Wert  <br/> |Kommentar  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Muss für Skype Room System Audio "true" sein  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Muss wahr sein, damit Skype Room System Audio in Ad-hoc-Whiteboardsitzungen (Meet Now) in Skype Room System funktioniert  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Ermöglicht Skype Room System das Rendern mehrerer Videostreams mit mehreren Ansichtsansichten  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Enterprise-VoIP (EV) aktiviert ist (siehe Abschnitt "Aktivieren von Skype Room System Accounts for Skype for Business").  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto Enterprise-VoIP (EV) aktiviert ist.  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A in Sofortbesprechungen (Ad-hoc-Besprechungen), aber Skype Room System kann auf Umfragen auf dem Bildschirm vor dem Raum antworten  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A in Sofortbesprechungen (Ad-hoc-Besprechungen), aber Skype Room System kann auf Umfragen auf dem Bildschirm vor dem Raum antworten  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A für Skype Room System. Wenn TRUE, könnte eine Remoteparty aufzeichnen  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A für Skype Room System. Wenn TRUE, könnte eine Remoteparty aufzeichnen  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Ermöglicht dem Skype Room System-Client die Teilnahme an Peer-zu-Peer-Videositzungen  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |Nicht zutreffend  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Skype Room System wird von Skype for Business Server ignoriert und verwendet HD1080.  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Betrifft Sofortsitzungen (Ad-hoc-Whiteboardsitzungen) in Skype Room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Dies ist die maximal zulässige Bitrate für ausgehende Videos. Skype Room System kann einen 1080-Stream zusammen mit Pano (wenn RoundTable verwendet wird) mit dieser Bitrate senden. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |Nicht zutreffend  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Es wird empfohlen, dies so hoch wie möglich zu legen. Die effektive Bandbreite hängt von den Netzwerkbedingungen zum Zeitpunkt von Konferenzen ab.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Muss TRUE sein, damit Skype Room System Videostreams mit mehreren Ansichtsansichten sicherstellen kann  <br/> |
   
* Informationen zur Bandbreitenplanung finden Sie unter ["Netzwerkbandbreitenanforderungen für Mediendatenverkehr".](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)
  
> [!NOTE]
> Wenn der Skype Room System-Client versucht, an einer geplanten Besprechung teil zu nehmen, die von einem Benutzer organisiert wurde, der in einem Lync Server 2010-Pool gespeichert ist, könnte die Konferenzrichtlinie des Besprechungsorganisators verhindern, dass der Skype Room System-Client zusammenarbeiten kann. 
  
## <a name="meeting-authentication"></a>Besprechungsauthentifizierung

Skype Room System fordert Benutzer zur Authentifizierung auf, wenn sie den Link zum Beitreten zu einer Besprechung verwenden, um an einer eingeschränkten Besprechung teil zu nehmen. Beispielsweise eine Besprechung, für die Optionen für die Besprechungslobby in Outlook konfiguriert wurden. Diese Einstellung ist für angepasste Besprechungen immer verfügbar, und Benutzer werden immer aufgefordert. Bei uneingeschränkten Besprechungen können Benutzer jedoch ohne Authentifizierung an der Besprechung teilnehmen. 
  
Der folgende Befehl ermöglicht Administratoren die Authentifizierung für alle Besprechungen, einschließlich uneingeschränkter Besprechungen: 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

RequireRoomSystemsAuthorization ist standardmäßig FALSE. 
  

