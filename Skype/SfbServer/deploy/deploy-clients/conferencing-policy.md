---
title: Konferenzrichtlinie für Skype Room System-Konten
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lesen Sie dieses Thema und erfahren Sie, wie Konferenzrichtlinien für Skype Room System-Konten zugewiesen werden.
ms.openlocfilehash: 5662778c14d8f987e26b36eaca252fbd8a6ea98c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286524"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Konferenzrichtlinie für Skype Room System-Konten
 
Lesen Sie dieses Thema und erfahren Sie, wie Konferenzrichtlinien für Skype Room System-Konten zugewiesen werden.
  
## <a name="conferencing-policy-features"></a>Konferenzrichtlinienfunktionen

Die dem Skype Room-System Konto zugewiesenen Konferenzrichtlinien müssen bestimmte Merkmale aufweisen. In der Regel wird der Skype Room-System Client an einer geplanten Besprechung Teil, und daher wirkt sich die konferenzrichtlinie des Besprechungsorganisators auf die Konferenz aus. In Skype for Business Server hängen bestimmte Funktionen jedoch von der Konfiguration des Teilnehmers ab. Wenn beispielsweise die Richtlinie des Teilnehmers eine maximale Videoauflösung von 1080p zulässt, können die Teilnehmer diese Videofunktion mit höherer Auflösung in der Konferenz erleben, selbst wenn die Richtlinie des Organisators dies nicht zulässt. In der folgenden Tabelle werden einige solcher Einstellungen beschrieben, die Sie beim Einrichten von Konferenzrichtlinien für Skype Room-System Konten in Ihrer Organisation beachten sollten. 
  
|Funktion  <br/> |Wert  <br/> |Kommentar  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Muss für Skype Room-System-Audio wahr sein  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Muss wahr sein, damit Skype Room System Audio in "jetzt besprechen" (Ad-hoc) Whiteboard-Sitzungen in Skype Room System funktioniert  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Ermöglicht es dem Skype Room-System, Multi-View-, mehrere Video-Streams zu rendern  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto Enterprise Voice (EV) aktiviert ist (siehe Abschnitt Aktivieren von Skype Room-System Konten für Skype for Business).  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto für Enterprise-VoIP (EV) aktiviert ist  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |N/A in Besprechungen (Ad-hoc-Besprechungen), aber Skype Room System kann auf Abstimmungen auf dem Bildschirm auf der Vorderseite des Chatrooms reagieren  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |N/A in Besprechungen (Ad-hoc-Besprechungen), aber Skype Room System kann auf Abstimmungen auf dem Bildschirm auf der Vorderseite des Chatrooms reagieren  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |N/A für Skype-Raum System. Wenn „TRUE“ (WAHR), könnte eine ferne Partei aufzeichnen  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |N/A für Skype-Raum System. Wenn „TRUE“ (WAHR), könnte eine ferne Partei aufzeichnen  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Ermöglicht es dem Skype Room-System Client, an Peer-to-Peer-Videositzungen teilzunehmen  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |-  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Von Skype for Business Server ignoriert, verwendet Skype Room System HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Auswirkungen auf "jetzt besprechen" (Ad-hoc)-Whiteboard-Sitzungen in Skype Room System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Dies ist die maximal zulässige ausgehende Video-Bitrate. Skype Room System kann 1 1080-Datenstrom zusammen mit Pano (wenn Roundtable verwendet wird) zu dieser Bitrate senden. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |-  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Es wird empfohlen, dass Sie diesen Wert so hoch wie möglich einstellen. Die effektive Bandbreite hängt von den Netzwerkbedingungen zum Zeitpunkt der Konferenz ab.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Muss für Skype Room System wahr sein, um Videostreams mit mehreren Ansichten zu gewährleisten  <br/> |
   
* Informationen zur Bandbreitenplanung finden Sie unter Anforderungen an die [Netzwerkbandbreite für Mediendatenverkehr](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Wenn der Skype Room-System Client versucht, an einer geplanten Besprechung teilzunehmen, die von einem Benutzer organisiert wird, der sich in einem lync Server 2010-Pool befindet, kann die konferenzrichtlinie des Besprechungsorganisators den Skype Room-System Client daran hindern, eine Zusammenarbeit durchzuführen. 
  
## <a name="meeting-authentication"></a>Besprechungsauthentifizierung

Skype Room System fordert Benutzer zur Authentifizierung auf, wenn Sie den Link "Besprechungsteilnahme" verwenden, um an einer eingeschränkten Besprechung teilzunehmen. Beispiel: eine Besprechung, für die die Optionen für die Besprechungslobby in Outlook konfiguriert wurden. Diese Einstellung ist für angepasste Besprechungen immer aktiviert und Nutzer werden immer zur Authentifizierung aufgefordert. Bei uneingeschränkten Besprechungen können Nutzer allerdings ohne Authentifizierung an der Besprechung teilnehmen. 
  
Der folgende Befehl versetzt Administratoren in die Lage, Authentifizierungen für alle Besprechungen zu verlangen, auch für uneingeschränkte Besprechungen: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Standardmäßig ist RequireRoomSystemsAuthorization „FALSE“ (FALSCH). 
  

