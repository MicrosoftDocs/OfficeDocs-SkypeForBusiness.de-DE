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
description: Planungs- und Konfigurationsinformationen zu Skype for Business Server für die videobasierte Bildschirmfreigabe (VbSS)
ms.openlocfilehash: 6c24ad9e2f74495fc616a66472f338f1b0b281d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832765"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Videobasierte Bildschirmübertragung für Skype for Business Server 
 
Die videobasierte Bildschirmfreigabe (VbSS) in Skype for Business Server 2015 steht jetzt zum Download zur Verfügung: [Kumulatives Update KB3061064 für Skype for Business Server 2015.](https://www.microsoft.com/download/details.aspx?id=47690) VbSS ist in Skype for Business Server 2019 enthalten.
  
Die videobasierte Bildschirmfreigabe (VbSS) wird aus der Lync-Bildschirmfreigabe ausgeschlossen. Der Unterschied zwischen VbSS und der herkömmlichen Bildschirmfreigabe hat mit den verwendeten zugrunde liegenden Protokollen und ihren Funktionen zu tun. Bei der Bildschirmfreigabe wird das Remotedesktopprotokoll (RDP) verwendet, mit dem Tausende von 1:1-Sitzungen zwischen den Computern der Benutzer erstellt werden können. Neuere Technologie, VbSS, verwendet UDP (User Datagram Protocol).
  
Skype for Business Server wollte die 1:1- und 1:n-Unterhaltungen und Besprechungserfahrungen von 1:n (mehreren Parteien) verbessern. VbSS nutzt die Medienplattform (die UDP als zugrunde liegendes Protokoll verwendet), um die Videostartzeiten zu verbessern, die Qualität der Anzeige ihrer Aktivitäten (insbesondere, wenn sich das Beobachten schnell bewegt) und die Zuverlässigkeit insgesamt zu verbessern.
  
Teil des Ziels der Verbesserung der Bildschirmfreigabe ist, dass Übergänge zwischen VbSS und RDP so nahtlos wie möglich sind, wenn sie auftreten. Da VbSS eine Aktualisierung der zugrunde liegenden Technologie ist, die bei der Bildschirmfreigabe für Skype for Business Server verwendet wird, ist es möglicherweise schwierig zu erkennen, welche Technologie Sie nutzen, es sei denn, Sie sehen sich die SIP-Details im Netzwerkdatenverkehr an, oder Sie teilen schnell bewegte oder 3D-Inhalte. Wenn Ihr Arbeitsplatz beispielsweise viele Legacyclients hat, ist RDP weiterhin als fehlersicher für Ihre Besprechungen und Unterhaltungen verfügbar. Skype for Business Server verwendet interne Logik, um zu entscheiden, welche der beiden Methoden (VbSS oder herkömmliche Bildschirmfreigabe) angewendet werden soll, wenn Clients eine Verbindung herstellen. RDP kann und wird durch VbSS ersetzt, wenn die Situation dies erfordert, damit Ihre Anzeige nicht unterbrochen wird.
  
## <a name="planning"></a>Planung

### <a name="vbss-pros-and-cons"></a>Vor- und Nachteile von VbSS

Durch den Wechsel zu VbSS sollen drei wichtige Verbesserungen vorgenommen werden:
  
1. Bildschirmfreigabe (bis zu 5 %) zuverlässiger im Vergleich zu RDP allein.

2. Beschleunigen Sie die Sitzungseinrichtung und videoerfahrung im Vergleich zu RDP allein (Einrichtung in der Hälfte der Zeit, mit einer 6:1-Verbesserung in Frames pro Sekunde).

3. Funktioniert viel besser als RDP unter Bedingungen mit geringer Bandbreite, auch wenn Inhalte mit hoher Bewegung, z. B. 3D-Grafiken, gemeinsam verwendet werden.
    
Bitte beachten Sie, dass diese Zahlen von der Integrität und ordnungsgemäßen Leistungsoptimierung Ihres Netzwerks und möglicherweise von Außerhalb Ihrer Netzwerke in Verbindung stehen, wenn Sich Ihre Clients auf mobilen Geräten befinden.
  
Sie sollten auch beachten, dass eine gewisse Genauigkeit/Scharfheit Ihrer freigegebenen Inhalte aus Zuverlässigkeit, Geschwindigkeit und Effizienz weitergegeben wurde. In den meisten Fällen ist dies für Benutzer nicht ohne Weiteres sichtbar.
  
### <a name="ports-and-protocols"></a>Ports und Protokolle

**Erforderliche Serverports**

|**Serverrolle**|**Dienstname**|**Port- oder Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Abhöranforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
   
**Erforderliche Clientports**

|**Komponente**|**Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden Medienports aktiviert ist und VbSS ebenfalls aktiviert ist, werden während einer Konferenz, die die Desktopfreigabe der AS MCU umfasst, die unten fett dargestellten Videoporteinstellungen für den Datenverkehr der Bildschirmfreigabe verwendet. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Sonderfall, und diese genauen Einstellungen müssen bei der Implementierung dieser beiden Features verwendet werden. Dadurch werden andere empfohlene Einstellungen in der Dokumentation [für QoS außer Kraft setzen.](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx) Für die Anwendungsfreigabe müssen Sie zusätzlich ASMCUSVC.exe Portwerte im QoS-GPO angeben. 
  
**Erforderliche Einstellungen für den Anwendungsserver QoS/VbSS**

|**Eigenschaft**|**Portwert**|**Protocol**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jeder Front-End-Server, auf dem Skype for Business Server 2015 kumulatives Update 2 (CU2) oder höher ausgeführt wird, unterstützt bis zu 375 Teilnehmer für die Bildschirmfreigabe mithilfe von RDP (jedoch nur 250 pro Besprechung). Diese Kapazität ändert sich nach ku3 nicht, wenn VbSS eingeführt und verwendet wird.
  
Darüber hinaus haben wir in unserem Labor Leistungs- und Belastungstests durchgeführt, und die folgenden Messungen sollten auch im Hinblick auf Ihre eigene Bereitstellung (natürlich abhängig von der Nutzung) berücksichtigt werden.
  
Es wird davon ausgegangen, dass:
  
- Sie verwenden Skype for Business Server 2015 CU2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype for Business Server-Umgebung haben Bildschirmauflösungen über 1920 x 1080.
    
Bei voller Kapazität (wie oben erwähnt, 375 Teilnehmer an der Bildschirmfreigabe pro Front-End-Server, jedoch nur 250 pro Besprechung) nutzt Ihr Front-End-Server möglicherweise ca. 89 % der 1 Gigabit-Netzwerkkarte. Dies liegt daran, dass die vorhandene Bildschirmfreigabetechnologie in Skype for Business Server CU2 (RDP) die Inhalte auf dem Bildschirm mit der systemeigenen Auflösung des PC des Presenters überträgt. Da also höhere Bildschirmauflösungen mit einbeiert sind, können bereits Netzwerkengpässe bei der Bildschirmfreigabe mit Skype for Business Server 2015 CU2 auftreten.
  
Um dies zu verringern, kann eine oder mehrere der folgenden Optionen hilfreich sein:
  
- Aktualisieren Sie Ihren Front-End-Server von einer 1-Gigabit-Netzwerkkarte auf eine 10-Gigabit-Ethernet-Karte.

- Erhöhen Sie die Anzahl der Front-End-Server, um einen Lastenausgleich für den Datenverkehr zu erstellen.

- Beschränken Sie die bandbreite (Bitrate), die für VbSS und RDP verwendet wird, indem Sie eine Obergrenze für die maximale Bandbreite verwenden, die von beiden Kanälen verwendet wird.
    
Die Zahlen in dieser Tabelle werden durch einzelne Netzwerke und den freigegebenen Inhalt beeinflusst. Testen Sie die Basislinien für Ihr Netzwerk oder Ihre Netzwerke.
  
|**1080p-Inhalt**|**RDP Average**|**RDP Peak**|**VbSS Average**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200 KBit/s  <br/> |12 Mb/s  <br/> |100 KBit/s  <br/> |3Mbps  <br/> |
|CAD  <br/> |3Mbps  <br/> |7 Mb/s  <br/> |1 Mb/s  <br/> |3Mbps  <br/> |
|Video  <br/> |5 MBit/s  <br/> |7 MB/s  <br/> |1,3 MBit/s  <br/> |2,2 MBit/s  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Netzwerkbandbreitenanforderungen für Mediendatenverkehr

Die Bandbreite von VbSS ist:
  
|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate der Videonutzlast (KBit/s)**|**Minimale Bitrate der Videonutzlast (KBit/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x 1080 (16:9)  <br/> (Das Seitenverhältnis hängt von der Monitorauflösung des Mitteilers ab und ist nicht immer 16:9.)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Unterstützung von Clients und Servern

Für die videobasierte Bildschirmfreigabe ist Skype for Business Server 2015 CU3 oder höher sowie eine aktuelle Version der unterstützenden Clients erforderlich, die im Vergleich zu mobilen Clientfeatures für [Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) und Besprechungen aufgeführt [sind.](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing) 
  
Es gibt Situationen, in denen die Bildschirmfreigabe in RDP überzugehen ist, wie die folgenden:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der die ASMCU nicht den Minimal build erfüllt, der VbSS unterstützt.
- Wenn jemand, der eine ältere Version des Skype for Business-Clients verwendet, Ihrer Sitzung beitritt, z. B. jeder, der eine beliebige Windows-Clientversion verwendet, die niedriger als 16.0.6330.1000, Skype for Business Room System Devices oder Skype for Business Mobile Apps ist. 
- Wenn ein Benutzer die Freigabe über die Skype for Business Web App vor sich hat.
- Wenn jemand Skype for Business auf einem Mac verwendet und nicht in Skype for Business Online oder Skype for Business Server 2015 mit dem kumulativen Update vom Juli 2018 (oder höher) gespeichert ist.
- Wenn jemand eine Programm-/Windows-Freigabe startet.
- Wenn jemand mit der Aufzeichnung der Sitzung beginnt.
- Wenn während der Sitzung ein Benutzer die Remotebildschirmsteuerung aufruft. 
- Besprechungen mit mehr als 250 Teilnehmern (wobei VbSS derzeit nicht unterstützt wird).

Beachten Sie, dass nach dem Übergang der Sitzung zu RDP kein Wechsel zurück zu VbSS möglich ist. Auch hier ist der Übergang von VbSS nahtlos und hoffentlich in den meisten Situationen nicht leicht zu erkennen.
    
> [!NOTE]
> Es wird nicht unterstützt, den Übergang von VbSS zu RDP in Der Skype for Business-Bildschirmfreigabe zu blockieren oder zu blockieren. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, Deaktivieren und Konfigurieren von VbSS

Das Großartige ist: Nachdem Sie das kumulative Update 3 (CU3) für Skype for Business Server 2015 oder höher installiert haben, sind alle Ihre Benutzer standardmäßig für 1:1- und mehrteilige VbSS aktiviert. Dies kann für Sie problematisch sein, wenn Sie einen Grund haben, diese Funktion nicht für alle Benutzer aktiviert zu haben. In diesem Fall können Sie diese Schritte verwenden, um Benutzer zu deaktivieren (die Schritte zum Aktivieren von Benutzern folgen):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Deaktivieren der Verwendung von VbSS durch Benutzer

- Sie können benutzern, die VbSS nicht verwenden sollten, eine Benutzerrichtlinie zuweisen, die VbSS nicht zulassen soll, indem Sie dieses Cmdlet in der Skype for Business Management Console ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirken wird:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS vollständig deaktivieren müssen, können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business-Besprechung mit mehreren Besprechungen respektiert jeder Clientendpunkt die Richtlinieneinstellung für den Besprechungsorganisator. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>So aktivieren Sie Benutzern die Verwendung von VbSS

- Sie können allen Benutzern, die VbSS verwenden müssen, eine bestimmte Benutzerrichtlinie zuweisen, die VbSS zulässt, indem Sie dieses Cmdlet in der Skype for Business Management Console ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirken wird:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS nach dem Deaktivieren wieder aktivieren müssen (standardmäßig aktiviert), können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business-Besprechung mit mehreren Parteien respektiert jeder Clientendpunkt die Richtlinieneinstellung für den Besprechungsorganisator. 
  
## <a name="see-also"></a>Siehe auch

[Kumulatives Update KB3061064 für Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Videobasierte Bildschirmfreigabe (VBSS) ist in Skype for Business Server 2015 verfügbar](https://support.microsoft.com/kb/3170163)
