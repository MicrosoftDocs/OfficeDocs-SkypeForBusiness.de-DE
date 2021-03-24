---
title: Videobasierte Bildschirmübertragung für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Planungs- und Konfigurationsinformationen von Skype for Business Server für die videobasierte Bildschirmfreigabe (VbSS)
ms.openlocfilehash: 9d2466a314876a4ce576727c7673474003994365
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103061"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Videobasierte Bildschirmübertragung für Skype for Business Server 
 
Videobasierte Bildschirmfreigabe (VbSS) in Skype For Business Server 2015 steht jetzt zum Download zur Verfügung: [Skype for Business Server 2015 Kumulatives Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS ist in Skype for Business Server 2019 enthalten.
  
Die videobasierte Bildschirmfreigabe oder VbSS ist aus der Lync-Bildschirmfreigabe geworden. Der Unterschied zwischen VbSS und der herkömmlichen Bildschirmfreigabe hat mit den verwendeten zugrunde liegenden Protokollen und ihren Hervorragenden zu tun. Bei der Bildschirmfreigabe wird das Remotedesktopprotokoll (RDP) verwendet, mit dem Tausende von 1:1-Sitzungen zwischen den Computern von Personen erstellt werden können. Neuere Technologien, VbSS, verwenden das User Datagram Protocol (UDP).
  
Skype for Business Server wollte die 1:1- und 1:n-Unterhaltungen und Besprechungserfahrungen von Personen verbessern. VbSS nutzt die Medienplattform (die auf UDP als zugrunde liegendes Protokoll basiert), mit dem Ziel, ihre Videostartzeiten zu verbessern, die Anzeigequalität der von Ihnen beobachteten Daten (insbesondere, wenn sie sich schnell bewegen) und die Zuverlässigkeit insgesamt.
  
Ein Teil des Ziels der Verbesserung der Bildschirmfreigabe ist, dass Übergänge zwischen VbSS und RDP so nahtlos wie möglich sind, wenn sie auftreten. Da VbSS ein Update der zugrunde liegenden Technologie ist, das bei der Bildschirmfreigabe für Skype for Business Server verwendet wird, ist es möglicherweise schwierig zu erkennen, welche Technologie Sie nutzen, es sei denn, Sie sehen sich SIP-Details im Netzwerkdatenverkehr an, oder Sie teilen Schnellleb- oder 3D-Inhalte. Wenn Ihr Arbeitsplatz beispielsweise über viele Legacyclients verfügt, steht RDP weiterhin als fehlersicher für Ihre Besprechungen und Unterhaltungen zur Verfügung. Skype for Business Server verwendet interne Logik, um zu entscheiden, welche der beiden Methoden (VbSS oder herkömmliche Bildschirmfreigabe) angewendet werden soll, wenn Clients eine Verbindung herstellen. RDP kann und wird durch VbSS ersetzt, wenn die Situation dies erfordert, damit Ihre Anzeigeerfahrung nicht unterbrochen wird.
  
## <a name="planning"></a>Planung

### <a name="vbss-pros-and-cons"></a>VbSS-Vor- und Nachteile

Der Wechsel zu VbSS zielt auf drei wesentliche Verbesserungen ab:
  
1. Bildschirmfreigabe (bis zu 5 %) zuverlässiger im Vergleich zu RDP allein.

2. Beschleunigen Sie die Sitzungseinrichtung und Videoerfahrung im Vergleich zu RDP allein (setup in der Hälfte der Zeit, mit einer Verbesserung von 6:1 in Frames pro Sekunde).

3. Funktioniert viel besser als RDP unter Bedingungen mit niedriger Bandbreite, auch wenn Inhalte mit hoher Bewegung, z. B. 3D-Grafiken, gemeinsam verwendet werden.
    
Beachten Sie, dass diese Zahlen von der Integrität und der ordnungsgemäßen Leistungsoptimierung Ihres Netzwerks und möglicherweise auch von Außerhalb Ihrer Netzwerke in Verbindung stehen, wenn Sich Ihre Clients auf mobilen Geräten befinden.
  
Sie sollten auch beachten, dass einige Genauigkeit/Genauigkeit Ihrer freigegebenen Inhalte aus Zuverlässigkeit, Geschwindigkeit und Effizienz gehandelt wurde. In den meisten Fällen ist dies für Benutzer nicht leicht sichtbar.
  
### <a name="ports-and-protocols"></a>Ports und Protokolle

**Erforderliche Serverports**

|**Serverrolle**|**Dienstname**|**Port- oder Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server Application Sharing Service  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Abhöranforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Application Sharing Service  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Medienportbereich, der für die Anwendungsfreigabe verwendet wird.  <br/> |
   
**Erforderliche Clientports**

|**Komponente**|**Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden Medienports aktiviert ist und VbSS ebenfalls aktiviert ist, verwendet die AS MCU während einer Konferenz, die die Desktopfreigabe umfasst, die unten fett dargestellten Videoporteinstellungen für den Bildschirmfreigabedatenverkehr. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Sonderfall, und diese genauen Einstellungen müssen bei der Implementierung beider Features verwendet werden. Dadurch werden andere empfohlene Einstellungen in der Dokumentation [für QoS außer Kraft setzen.](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos) Für die Anwendungsfreigabe müssen Sie zusätzlich zum Definieren dieser Portwerte ASMCUSVC.exe im GPO für QoS angeben. 
  
**Erforderliche Anwendungsserver-QoS/VbSS-Einstellungen**

|**Eigenschaft**|**Portwert**|**Protocol**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jeder Front-End-Server mit Skype for Business Server 2015 Kumulatives Update 2 (CU2) oder höher unterstützt bis zu 375 Teilnehmer für die Bildschirmfreigabe mithilfe von RDP (allerdings nur 250 pro Besprechung). Diese Kapazität ändert sich nach cu3 nicht, wenn VbSS eingeführt und verwendet wird.
  
Darüber hinaus haben wir leistungs- und belastungstests in unserem Labor durchgeführt, und die folgenden Messungen sollten auch im Hinblick auf Ihre eigene Bereitstellung (natürlich abhängig von der Nutzung) berücksichtigt werden.
  
Es wird davon ausgegangen, dass:
  
- Sie verwenden Skype for Business Server 2015 CU2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype for Business Server-Umgebung verfügen über Bildschirmauflösungen von mehr als 1920 x 1080.
    
Bei voller Kapazität (die wie oben erwähnt 375 Bildschirmfreigabeteilnehmer pro Front-End-Server insgesamt beträgt, aber nur 250 pro Besprechung), nutzt Ihr Front-End-Server möglicherweise ca. 89 % der 1 Gigabit-Netzwerkkarte. Dies liegt daran, dass die vorhandene Bildschirmfreigabetechnologie in Skype for Business Server CU2 (RDP) die Inhalte auf dem Bildschirm mit der systemeigenen Auflösung des PC des Presenters überträgt. Da also höhere Bildschirmauflösungen mit einbeh nen sind, können bereits Netzwerkengpässe für die Bildschirmfreigabe mit Skype for Business Server 2015 KU2 auftreten.
  
Um dies zu verhindern, kann eine oder mehrere der folgenden Optionen hilfreich sein:
  
- Aktualisieren Sie Ihren Front-End-Server von einer 1 Gigabit-Netzwerkkarte auf eine 10-Gigabit-Ethernet-Karte.

- Erhöhen Sie die Anzahl der Front-End-Server, um den Datenverkehr lastenausgleichen zu können.

- Begrenzen Sie die Bandbreite (Bitrate), die für VbSS und RDP verwendet wird, indem Sie die maximale Bandbreite, die von beiden Kanälen verwendet wird, begrenzen.
    
Die Zahlen in dieser Tabelle werden von einzelnen Netzwerken und von den freigegebenen Inhalten beeinflusst. Testen Sie, um Basiswerte für Ihr Netzwerk oder Ihre Netzwerke zu erstellen.
  
|**1080p-Inhalt**|**RDP-Durchschnitt**|**RDP Peak**|**VbSS-Durchschnitt**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 KBit/s  <br/> |12 Mb/s  <br/> |100 KBit/s  <br/> |3 MB/s  <br/> |
|CAD  <br/> |3 MB/s  <br/> |7 MB/s  <br/> |1 Mbit/s  <br/> |3 MB/s  <br/> |
|Video  <br/> |5 MB/s  <br/> |7 MB/s  <br/> |1,3 Mb/s  <br/> |2,2 MBit/s  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Netzwerkbandbreitenanforderungen für Mediendatenverkehr

Die VbSS-Bandbreite ist:
  
|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Videonutzlastbitrate (KBit/s)**|**Minimale Bitrate (KBit/s) für die Videonutzlast**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (Das Seitenverhältnis hängt von der Monitorauflösung des Mitteilers ab und ist nicht immer 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Unterstützung von Clients und Servern

Für die videobasierte Bildschirmfreigabe ist Skype for Business Server 2015 CU3 oder höher sowie eine aktuelle Version der unterstützenden Clients erforderlich, die im Vergleich zu [mobilen](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) Clientfeatures für Skype for Business und Besprechungen aufgeführt [sind.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
Es gibt Situationen, in denen die Bildschirmfreigabe zu RDP überzugehen hat, wie die folgenden:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der die ASMCU nicht den minimalen Build erfüllt, der VbSS unterstützt.
- Wenn eine Person, die eine ältere Version des Skype for Business-Clients verwendet, Ihrer Sitzung beitritt, z. B. jeder, der eine windows-Clientversion verwendet, die unter 16.0.6330.1000, Skype for Business Room System Devices oder Skype for Business Mobile Apps liegt. 
- Wenn ein Benutzer die Freigabe über die Skype for Business Web App vor sich hat.
- Wenn jemand Skype for Business auf Dem Mac verwendet und nicht mit dem kumulativen Update vom Juli 2018 (oder höher) auf Skype for Business Online oder Skype for Business Server 2015 gespeichert ist.
- Wenn jemand ein Programm/eine Windows-Freigabe startet.
- Wenn eine Person mit der Aufzeichnung der Sitzung beginnt.
- Wenn während der Sitzung ein Benutzer die Remotebildschirmsteuerung aufruft. 
- Besprechungen mit mehr als 250 Teilnehmern (wobei VbSS derzeit nicht unterstützt wird).

Beachten Sie, dass die Sitzung nach dem Übergang zu RDP nicht wieder zu VbSS überwechselt wird. Auch hier ist der Übergang von VbSS nahtlos und hoffentlich in den meisten Situationen nicht leicht zu erkennen.
    
> [!NOTE]
> Es wird nicht unterstützt, den Übergang von VbSS zu RDP in Der Skype for Business-Bildschirmfreigabe zu blockieren oder zu blockieren. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, Deaktivieren und Konfigurieren von VbSS

Die großartige Sache ist, dass nach der Installation des kumulativen Skype for Business Server 2015-Updates 3 (CU3) oder höher alle Ihre Benutzer standardmäßig für 1:1- und mehrstufige VbSS aktiviert sind. Dies kann für Sie problematisch sein, wenn Sie einen Grund haben, diese Funktionalität nicht für alle Benutzer aktiviert zu haben. In diesem Fall können Sie die folgenden Schritte ausführen, um Benutzer zu deaktivieren (die Schritte zum Aktivieren von Benutzern folgen):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Deaktivieren der Verwendung von VbSS durch Benutzer

- Sie können benutzern, die VbSS nicht verwenden sollten, eine Benutzerrichtlinie zuweisen, die VbSS nicht zulassen soll, indem Sie dieses Cmdlet in der Skype for Business Management Console ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirken wird:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS vollständig deaktivieren müssen, können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business-Besprechung mit mehrerenPartys respektieren alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Aktivieren der Verwendung von VbSS durch Benutzer

- Sie können eine bestimmte Benutzerrichtlinie zuweisen, die VbSS allen Benutzern zulässt, die VbSS verwenden müssen, indem Sie dieses Cmdlet in der Skype for Business Management Console ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirken wird:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS nach dem Deaktivieren wieder aktivieren müssen (standardmäßig aktiviert), können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business-Besprechung mit mehreren Parteien respektieren alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015 Kumulatives Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Videobasierte Bildschirmfreigabe (VBSS) ist in Skype for Business Server 2015 verfügbar](https://support.microsoft.com/kb/3170163)