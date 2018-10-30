---
title: Video basierten für Skype für Business Server Bildschirmfreigabe
ms.author: heidip
author: microsoftheidi
ms.date: 2/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype für Business Server planen und Konfigurationsinformationen zu Bildschirmfreigabe videobasierte (VbSS)
ms.openlocfilehash: 8541bb0dc3b5791c670a3beac77560b3c9663733
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839747"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Video basierten für Skype für Business Server Bildschirmfreigabe 
 
Video-basierte Bildschirmfreigabe (VbSS) in Skype für Business Server 2015 ist jetzt zum Download zur Verfügung: [Skype für Business Server 2015 kumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). VbSS gehört zum Lieferumfang von Skype für Business Server 2019.
  
Video-basierte Bildschirmfreigabe oder VbSS, stieg bei Lync-Bildschirmfreigabe. Der Unterschied zwischen VbSS und herkömmliche Bildschirmfreigabe mit der zugrunde liegenden Protokolle verwendet wurde, und was sie unter excel. Bildschirmfreigabe-verwendet das Remotedesktopprotokoll (RDP), was an Tausende von 1: 1 Sitzungen zwischen Personen Computern erstellen. Neuere Technologie, VbSS, wird der User Datagram Protocol (UDP) nutzen.
  
Skype für Business Server wollten Volksrepublik 1-1 und deren (mit mehreren Teilnehmern) 1: n-Unterhaltungen zu verbessern und meeting Erfahrungen. VbSS nutzt die Medienplattform (die sich auf UDP als zugrunde liegendes Protokoll stützt) mit dem Ziel, die Videostartzeiten, die Anzeigequalität (vor allem bei der Anzeige schneller Bewegungen) und die Zuverlässigkeit insgesamt zu verbessern.
  
Zum Teil besteht das Verbesserungsziel bei der Bildschirmübertragung darin, die auftretenden Wechsel zwischen VbSS und RDP so nahtlos wie möglich zu gestalten. Da VbSS eine Aktualisierung auf die zugrunde liegende Technologie, die im Bildschirm Freigabe für Skype für Business Server verwendet wird ist, kann es schwierig sein zu erkennen, welche Technologie, die Sie nutzen, sofern Sie SIP-Details in den Netzwerkverkehr sehen oder einsetzen Inhalts ist fast verschieben oder 3D gezeichnet. Wenn beispielsweise Ihrem Arbeitsplatz viel Legacyclients hat, verfügbar RDP weiterhin als ein Failsafe für Ihre Besprechungen und Unterhaltungen. Skype für Business Server verwendet internen Logik um zu entscheiden, welche die beiden Methoden (VbSS oder herkömmlichen Bildschirmfreigabe) angewendet, wenn Clients eine Verbindung herstellen. Wenn es die Situation erfordert, kann VbSS durch RDP ersetzt werden, sodass die Anzeigeerfahrung nicht unterbrochen wird.
  
## <a name="planning"></a>Planung

### <a name="vbss-pros-and-cons"></a>Vor- und Nachteile von VbSS

Mit der Umstellung auf VbSS werden drei wesentliche Verbesserungen angestrebt:
  
1. Höhere Zuverlässigkeit der Bildschirmübertragung (um bis zu 5 %) im Vergleich zu RDP allein.

2. Schnellere Sitzungseinrichtungs- und Videoerfahrung im Vergleich zu RDP allein (Einrichtung in der Hälfte der Zeit und eine 6:1-Verbesserung bei Bildern pro Sekunde).

3. Funktioniert bei niedriger Bandbreite wesentlich besser als RDP, auch wenn Inhalte mit vielen Bewegungen wie z. B. 3D-Grafiken übertragen werden.
    
Beachten Sie, dass diese Zahlen vom Zustand und der richtigen Leistungsfeineinstellung Ihres Netzwerks abhängen. Es können auch externe Netzwerke beteiligt sein, wenn sich Ihre Clients auf Mobilgeräten befinden.
  
Beachten Sie auch, dass auf einen Teil der Treue/Schärfe der übertragenen Inhalte im Gegenzug für mehr Zuverlässigkeit, Geschwindigkeit und Effizienz verzichtet werden musste. Das ist in den meisten Fällen für die Benutzer nicht sichtbar.
  
### <a name="ports-and-protocols"></a>Ports und Protokolle

**Erforderliche Serverports**

|**Serverrolle**|**Name des Diensts**|**Port oder Portbereich**|**Protokoll**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype für Business Server-anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
   
**Erforderliche Clientports**

|**Komponente**|**Portbereich**|**Protokoll**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden medienports aktiviert ist, und auch VbSS aktiviert ist, während einer Konferenz, die Desktopfreigabe AS MCU in gezeigten Einstellungen für die video-Port verwendet werden soll enthält fett unten für den Bildschirm freigeben Datenverkehr. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Spezialfall, und diese genauen Einstellungen müssen verwendet werden, wenn Sie diesen beiden Funktionen zu implementieren. Andere empfohlenen Einstellungen in der [Dokumentation für QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)außer Kraft gesetzt. Fo Anwendungsfreigabe Sie müssen auch ASMCUSVC.exe in der QoS-Gruppenrichtlinienobjekt zusätzlich zum Definieren von Werten für diesen Port angeben. 
  
**Application Server QoS/VbSS die erforderlichen Einstellungen**

|**Eigenschaft**|**Wert für Port**|**Protokoll**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |UDP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |UDP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jeder Front-End-Server, die mit Skype für Business Server 2015 kumulative Update 2 (CU2) oder höher unterstützt bis zu 375 Teilnehmer für Bildschirmfreigabe mit RDP (jedoch nur 250 pro Besprechung). Diese Kapazität ändert sich nach CU3 mit der Einführung und Verwendung von VbSS nicht.
  
Dies vorausgeschickt, haben wir im Labor Leistungs- und Stresstests durchgeführt, und die folgenden Messungen sollten in Ihrer eigenen Bereitstellung (natürlich nutzungsabhängig) berücksichtigt werden.
  
Annahmen:
  
- Skype verwenden für Business Server 2015 CU2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype für Business Server-Umgebung haben bildschirmauflösungen höher ist als 1920 x 1080.
    
Voller Auslastung betrieben (dies wie bereits erwähnt, 375 Bildschirm sharing Teilnehmer pro Front-End-Server in der gesamten, obwohl nur 250 pro Besprechung ist), dem Front-End-Server ~ 89 % der Netzwerkkarte mit 1 Gigabit gib werden kann. Dies ist die vorhandene Bildschirmfreigabe Skype-Technologie für Business Server CU2 (RDP) auf dem Bildschirm Content bei der systemeigenen Auflösung von der Referent PC übermittelt. So treten möglicherweise mit höheren Bildschirm Auflösung angepasst, Sie bereits Engpässe im Netzwerk für Bildschirmfreigabe mit Skype für Business Server 2015 CU2 auf.
  
Um dieses Problem zu beheben, können die folgenden Optionen hilfreich sein:
  
- Aktualisieren der Front-End-Server aus einer 1 Gigabit-Netzwerkkarte mit einem 10 Gigabit-Ethernet-Adapter.

- Erhöhen der Anzahl der Front-End-Servern zu verteilen-Datenverkehr.

- Beschränken Sie die Bandbreite (Bitrate), die für VbSS und RDP verwendet wird, indem Sie die maximal von den einzelnen Kanälen verwendete Bandbreite deckeln.
    
Die Zahlen in dieser Tabelle werden durch einzelne Netzwerke und den gemeinsam verwendeten Inhalten beeinflusst. Führen Sie Tests durch, um Baselines für Ihr Netzwerk bzw. Ihre Netzwerke zu erstellen.
  
|**1080p Inhalt **|**RDP Durchschnitt**|**RDP Spitzenauslastung**|**VbSS Durchschnittliche Auslastung**|**VbSS Spitzenauslastung**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12mbps  <br/> |100kbps  <br/> |3mbps  <br/> |
|CAD  <br/> |3mbps  <br/> |7mbps  <br/> |1mbps  <br/> |3mbps  <br/> |
|Video  <br/> |5mbps  <br/> |7mbps  <br/> |1.3mbps  <br/> |2.2mbps  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Anforderungen hinsichtlich der Netzwerkbandbreite für Mediendatenverkehr

Die VbSS-Bandbreite beträgt:
  
|**Videocodec**|**Auflösung und Seitenverhältnis**|**Bitrate bei maximaler Videonutzlast (KBit/s)**|**Bitrate bei minimaler Videonutzlast (KBit/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920x1080 (16:9)  <br/> (Das Bildseitenverhältnis hängt von der Bildschirmauflösung des Übertragenden ab und ist nicht immer 16:9.)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Client- und Serverunterstützung

Video-basierte Bildschirmfreigabe erfordert Skype für Business Server 2015 CU3 oder höher und eine aktuelle Version der unterstützenden Clients in [mobilen Client Featurevergleich für Skype für Unternehmen](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) und [Besprechungen unterstützen](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)aufgeführt. 
  
Es gibt Situationen, in dem Bildschirmfreigabe-auf RDP, wie diese Übergang wird:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der das ASMCU nicht den Mindest-Build aufweist, der VbSS unterstützt.
- Wenn eine Person, die eine ältere Version von der Skype für Business-Client verwendet die Sitzung beigetreten ist, verwenden beispielsweise jeder eine Windows-Client-Version, die 16.0.6330.1000, Skype für Business Raum Systemgeräte oder Skype für Mobile-Geschäfts-Apps niedriger ist. 
- Wenn ein Benutzer aus der Skype für Business Web App gemeinsam verwendet.
- Wenn jemand Skype für Unternehmen auf Mac und nicht für Business Online auf Skype verwaltet wird.
- Wenn jemand eine beliebige Anwendung/Windows Freigabe gestartet wird.
- Wenn jemand beginnt mit der Aufzeichnung der Sitzung.
- Wenn jemand während der Sitzung Remotebildschirmsteuerung aufruft.

    Achtung: Nachdem die Sitzung zu RDP gewechselt hat, wechselt sie nicht wieder zu VbSS zurück. Auch hier ist ein nahtloser Übergang von VbSS vorgesehen, und der Wechsel wird voraussichtlich in den meisten Situationen nicht bemerkt werden.
  
- Besprechungen mit mehr als 250 Teilnehmern (bei denen VbSS derzeit nicht unterstützt wird).
    
> [!NOTE]
> Es wurde auf Block nicht unterstützt, oder versucht wird, zu blockieren, Übergang von VbSS zu RDP in Skype für Business Bildschirmfreigabe. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, Deaktivieren und Konfigurieren von VbSS

Der große Vorteil ist, nachdem Sie die Skype für Business Server 2015 kumulierten Update 3 (CU3) installiert haben oder höher, alle Benutzer werden für 1: 1 und mit mehreren Teilnehmern VbSS standardmäßig aktiviert. Das kann für Sie problematisch sein, wenn Sie aus irgend einem Grund diese Funktion nicht für alle Benutzer aktivieren möchten. In diesem Fall können Sie mit den folgenden Schritten Benutzer deaktivieren (im Anschluss folgen die Schritte zum Aktivieren von Benutzern):
  
### <a name="how-to-disable-users-from-using-vbss"></a>So deaktivieren Sie die Verwendung von VbSS für Benutzer

- Sie können eine Benutzerrichtlinie zuweisen, die keine VbSS Benutzern, die nutzen sollte nicht VbSS erlaubt durch Ausführen dieses Cmdlet in der Skype für Business-Verwaltungskonsole (ersetzen [PolicyName] durch die Richtlinie ein, die Sie dies tun):
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, von der alle Benutzer ohne zugewiesene Richtlinie betroffen sind:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS vollständig deaktivieren möchten, können Sie folgenden Befehl ausführen:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer mit mehreren Teilnehmern Skype für Business Besprechung werden die Einstellung für den Organisator der Besprechung von alle Clientendpunkte berücksichtigt. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>So aktivieren Sie die Verwendung von VbSS für Benutzer

- Sie können eine bestimmte Benutzerrichtlinie zuweisen, die VbSS Benutzern, die VbSS ermöglicht durch Ausführen dieses Cmdlet in der Skype für Business-Verwaltungskonsole (ersetzen [PolicyName] durch die Richtlinie ein, die Sie dies tun) verwenden werden müssen:
    
  ```
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, von der alle Benutzer ohne zugewiesene Richtlinie betroffen sind:
    
  ```
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS nach dem Deaktivieren wieder aktivieren möchten (die Funktion ist standardmäßig aktiviert), können Sie folgenden Befehl ausführen:
    
  ```
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer mit mehreren Teilnehmern Skype für Business Besprechung werden die Einstellung für den Organisator der Besprechung von alle Clientendpunkte berücksichtigt. 
  
## <a name="see-also"></a>Siehe auch

[Skype für Business Server 2015 kumulative Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[Video-basierte Bildschirmfreigabe-(VBSS) steht in Skype für Business Server 2015](https://support.microsoft.com/en-us/kb/3170163)
