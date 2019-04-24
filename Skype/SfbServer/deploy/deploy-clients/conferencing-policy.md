---
title: Konferenzrichtlinie für Skype Room System-Konten
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: Lesen Sie dieses Thema und erfahren Sie, wie Konferenzrichtlinien für Skype Room System-Konten zugewiesen werden.
ms.openlocfilehash: a56bf9f6b8ba70a4f9ec1f28e84dfa67b1e71aa9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219465"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Konferenzrichtlinie für Skype Room System-Konten
 
Lesen Sie dieses Thema und erfahren Sie, wie Konferenzrichtlinien für Skype Room System-Konten zugewiesen werden.
  
## <a name="conferencing-policy-features"></a>Konferenzrichtlinienfunktionen

Die dem Konto Skype Raum System zugeordnete konferenzrichtlinie muss bestimmte Merkmale aufweisen. In den meisten Fällen, der Skype Raum System Client eine geplante Besprechung teilnimmt, und daher die konferenzrichtlinie des Besprechungsorganisators wirkt sich der Konferenz. Jedoch in Skype für Business Server, bestimmte Funktionen des Teilnehmers Konfiguration abhängig. Beispielsweise wenn Richtlinie für die Teilnehmer eine maximale Auflösung von 1080p zulässt, werden die Teilnehmer einer höheren Auflösung video Funktion in der Konferenz bemerken, auch wenn der Organisator Richtlinie nicht zulässt. Die folgende Tabelle beschreibt mehrere diese Einstellung, die Sie beim Einrichten von konferenzrichtlinien für Skype Raum Systemkonten in Ihrer Organisation berücksichtigen sollten. 
  
|Funktion  <br/> |Wert  <br/> |Kommentar  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Für Audio Skype Raum System wahr sein müssen  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |Für Audio in "Jetzt besprechen" (ad-hoc-) Whiteboardsitzungen in Skype Raum System arbeiten Skype Raum System wahr sein müssen  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |Skype Raum System zum Rendern mit mehreren Ansicht mehrere Videostreams ermöglicht  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|DisablePowerPointAnnotations  <br/> |FALSE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |FALSE  <br/> |Gibt an, ob das Konto für Enterprise-VoIP (EV) aktiviert (siehe die aktivieren Skype Raum Systemkonten für Skype für Business Abschnitt) ist, hängt  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |FALSE  <br/> |Hängt davon ab, ob das Konto für Enterprise-VoIP (EV) aktiviert ist  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowExternalUserControl  <br/> |FALSE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |FALSE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |Nicht zutreffend in sofort-Besprechungen (ad-hoc-), aber Skype Raum System kann auf Umfragen auf dem Bildschirm am Anfang der Raum reagieren.  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |Nicht zutreffend in sofort-Besprechungen (ad-hoc-), aber Skype Raum System kann auf Umfragen auf dem Bildschirm am Anfang der Raum reagieren.  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|EnableAppDesktopSharing  <br/> |Desktop  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AllowConferenceRecording  <br/> |FALSE  <br/> |Nicht zutreffend für Raum Skype-System. Wenn „TRUE“ (WAHR), könnte eine ferne Partei aufzeichnen  <br/> |
|EnableP2PRecording  <br/> |FALSE  <br/> |Nicht zutreffend für Raum Skype-System. Wenn „TRUE“ (WAHR), könnte eine ferne Partei aufzeichnen  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |Nicht zutreffend  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |Ermöglicht dem Client Skype Raum System zur Teilnahme an Peer-zu-Peer-videositzungen  <br/> |
|AllowLargeMeetings  <br/> |FALSE  <br/> |-  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |Von Skype für Business Server ignoriert, verwendet Skype Raum System HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |Wirkt sich auf Jetzt besprechen (ad-hoc-) Whiteboardsitzungen in Skype Raum System  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |Dies ist die maximale ausgehende Videobitrate zulässig. Skype Raum System senden 1080 stream zusammen mit Zusammenheften (wenn RoundTable verwendet wird) dieser Bit Rate. \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |Siehe Hinweis am Ende der Tabelle\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |-  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |Es wird empfohlen, dass Sie diesen Wert so hoch wie möglich einstellen. Effektive Bandbreite hängt netzwerkbedingungen zum Zeitpunkt der Konferenzen.\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Muss auf TRUE festgelegt sein für Skype Raum System, um sicherzustellen, dass Videostreams mit mehreren Ansichten  <br/> |
   
* Informationen zur Planung der Bandbreite finden Sie unter [Anforderungen an die Netzwerkbandbreite für Mediendatenverkehr](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic).
  
> [!NOTE]
> Wenn der Client Skype Raum System versucht, teilnehmen an einer geplanten Besprechung organisiert, die von einem Benutzer, der auf einem Lync Server 2010-Pool verwaltet wird, konnte der Besprechungsorganisator konferenzrichtlinie verhindern, dass den Skype Raum System Client ausführen für die Zusammenarbeit. 
  
## <a name="meeting-authentication"></a>Besprechungsauthentifizierung

Skype Raum System fordert die Benutzer für die Authentifizierung bei der Verwendung der Besprechung teilnahmelink teilnehmen an einer Besprechung eingeschränkte; Beispiel einer Besprechung, für welche Besprechungslobby Optionen in Outlook konfiguriert wurden. Diese Einstellung ist für angepasste Besprechungen immer aktiviert und Nutzer werden immer zur Authentifizierung aufgefordert. Bei uneingeschränkten Besprechungen können Nutzer allerdings ohne Authentifizierung an der Besprechung teilnehmen. 
  
Der folgende Befehl versetzt Administratoren in die Lage, Authentifizierungen für alle Besprechungen zu verlangen, auch für uneingeschränkte Besprechungen: 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

Standardmäßig ist RequireRoomSystemsAuthorization „FALSE“ (FALSCH). 
  

