---
title: Videobasierte Bildschirmübertragung für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Informationen zur Planung und Konfiguration von Skype for Business Server für die Video basierte Bildschirmfreigabe (schlechte VBSS)
ms.openlocfilehash: 00c699f9a26d82506bd13fefe0e6f3e53f7b86bf
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992392"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Videobasierte Bildschirmübertragung für Skype for Business Server 
 
Video basierte Bildschirmübertragung (schlechte VBSS) in Skype for Business Server 2015 steht jetzt zum Download zur Verfügung: [Skype for Business Server 2015 Kumulatives Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690). Schlechte VBSS ist im Lieferumfang von Skype for Business Server 2019 enthalten.
  
Video basierte Bildschirm Freigaben oder schlechte VBSS sind aus der lync-Bildschirmfreigabe hervor gewachsen. Der Unterschied zwischen schlechte VBSS und herkömmlicher Bildschirmfreigabe liegt bei den zugrunde liegenden Protokollen, die verwendet werden, und dem, was Sie auszeichnen. Bei der Bildschirmfreigabe wird das Remotedesktopprotokoll (RDP) verwendet, mit dem Sie Tausende von 1-zu-1-Sitzungen zwischen den Computern der Personen erstellen können. Bei neueren Technologien, schlechte VBSS, wird das User Datagram Protocol (UDP) verwendet.
  
Skype for Business Server wollte die 1-zu-1-Unterhaltung von Personen und deren 1: n-(mehr Parteien-) Konversationen und Besprechungs Erlebnisse verbessern. VbSS nutzt die Medienplattform (die sich auf UDP als zugrunde liegendes Protokoll stützt) mit dem Ziel, die Videostartzeiten, die Anzeigequalität (vor allem bei der Anzeige schneller Bewegungen) und die Zuverlässigkeit insgesamt zu verbessern.
  
Zum Teil besteht das Verbesserungsziel bei der Bildschirmübertragung darin, die auftretenden Wechsel zwischen VbSS und RDP so nahtlos wie möglich zu gestalten. Da schlechte VBSS ein Update für die zugrunde liegende Technologie ist, die in der Bildschirmübertragung für Skype for Business Server verwendet wird, ist es möglicherweise schwierig zu erkennen, welche Technologie Sie nutzen, es sei denn, Sie suchen SIP-Details im Netzwerkdatenverkehr, oder Sie geben Inhalte frei, die ist schnell in Bewegung oder 3-D. Wenn beispielsweise Ihr Arbeitsplatz viele Legacy-Clients hat, ist RDP weiterhin als Failsafe für Ihre Besprechungen und Unterhaltungen verfügbar. Skype for Business Server verwendet interne Logik, um zu entscheiden, welche der beiden Methoden (schlechte VBSS oder herkömmliche Bildschirmfreigabe) angewendet werden soll, wenn Clients eine Verbindung herstellen. Wenn es die Situation erfordert, kann VbSS durch RDP ersetzt werden, sodass die Anzeigeerfahrung nicht unterbrochen wird.
  
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

|**Serverrolle**|**Name des Diensts**|**Port oder Portbereich**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabe Dienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server-Anwendungsfreigabe Dienst  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
   
**Erforderliche Client Anschlüsse**

|**Komponente**|**Portbereich**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden Medienanschlüsse aktiviert ist und schlechte VBSS ebenfalls aktiviert ist, wird während einer Konferenz, die die Desktopfreigabe umfasst, die als MCU verwendeten Video Porteinstellungen für den Bildschirmfreigabe Verkehr verwendet. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Sonderfall, und diese exakten Einstellungen müssen bei der Implementierung beider Features verwendet werden. Damit werden andere empfohlene Einstellungen in der [Dokumentation für QoS](https://technet.microsoft.com/en-us/library/gg405409%28v=ocs.15%29.aspx)außer Kraft gesetzt. Für die Anwendungsfreigabe müssen Sie zusätzlich zum Definieren dieser Portwerte auch ASMCUSVC. exe im QoS-GPO angeben. 
  
**Einstellungen für QoS/schlechte VBSS des Anwendungsservers**

|**Eigenschaft**|**Portwert**|**Protokoll**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jeder Front-End-Server, auf dem Skype for Business Server 2015 Kumulatives Update 2 (Cu2) oder höher ausgeführt wird, unterstützt bis zu 375 Teilnehmer für die Bildschirmübertragung mithilfe von RDP (allerdings nur 250 pro Besprechung). Diese Kapazität ändert sich nach CU3 mit der Einführung und Verwendung von VbSS nicht.
  
Dies vorausgeschickt, haben wir im Labor Leistungs- und Stresstests durchgeführt, und die folgenden Messungen sollten in Ihrer eigenen Bereitstellung (natürlich nutzungsabhängig) berücksichtigt werden.
  
Annahmen:
  
- Sie verwenden Skype for Business Server 2015 Cu2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype for Business Server-Umgebung haben Bildschirmauflösungen, die höher als 1920x1080 sind.
    
Bei voller Kapazität (wie bereits erwähnt, ist 375 Bildschirmfreigabe Teilnehmer pro Front-End-Server insgesamt, wenn auch nur 250 pro Besprechung), kann Ihr Front-End-Server ~ 89% der 1-Gigabit-Netzwerkkarte verwenden. Dies liegt daran, dass die vorhandene Bildschirmfreigabe Technologie in Skype for Business Server Cu2 (RDP) den Bildschirminhalt mit der systemeigenen Auflösung des PC des Referenten überträgt. Wenn Sie also höhere Bildschirmauflösungen berücksichtigen, treten möglicherweise bereits Netzwerkengpässe für die Bildschirmfreigabe mit Skype for Business Server 2015 Cu2 auf.
  
Um dieses Problem zu beheben, können die folgenden Optionen hilfreich sein:
  
- Aktualisieren Sie Ihren Front-End-Server von einer 1-Gigabit-Netzwerkkarte auf eine 10-Gigabit-Ethernet-Karte.

- Erhöhen Sie die Anzahl der Front-End-Server zum Lastenausgleich des Datenverkehrs.

- Beschränken Sie die Bandbreite (Bitrate), die für VbSS und RDP verwendet wird, indem Sie die maximal von den einzelnen Kanälen verwendete Bandbreite deckeln.
    
Die Zahlen in dieser Tabelle werden durch einzelne Netzwerke und den gemeinsam verwendeten Inhalten beeinflusst. Führen Sie Tests durch, um Baselines für Ihr Netzwerk bzw. Ihre Netzwerke zu erstellen.
  
|**1080p Inhalt **|**RDP-Mittelwert**|**RDP Spitzenauslastung**|**VbSS Durchschnittliche Auslastung**|**VbSS Spitzenauslastung**|
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

Für die Video basierte Bildschirmfreigabe ist Skype for Business Server 2015 CU3 oder höher erforderlich, und eine aktuelle Version der unterstützenden Clients, die im [Vergleich der mobilen Clientfunktionen für Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) und [Besprechungen unterstützt](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)werden. 
  
Es gibt Situationen, in denen die Bildschirmübertragung wie folgt auf RDP übertragen wird:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der das ASMCU nicht den Mindest-Build aufweist, der VbSS unterstützt.
- Wenn jemand, der eine ältere Version des Skype for Business-Clients verwendet, zu Ihrer Sitzung wechselt, beispielsweise jeder, der eine andere Windows-Client Version als 16.0.6330.1000, Skype for Business Room-System Geräte oder Skype for Business-Mobile-Apps verwendet. 
- Wenn ein Benutzer über die Skype for Business Web App freigegeben wird.
- Wenn jemand Skype for Business für Mac verwendet und nicht in Skype for Business Online oder Skype for Business Server 2015 mit dem kumulativen Update vom Juli, 2018 (oder höher).
- Wenn jemand eine Programm/Windows-Freigabe startet.
- Wenn jemand mit der Aufzeichnung der Sitzung beginnt.
- Wenn jemand während der Sitzung Remotebildschirmsteuerung aufruft. 
- Besprechungen mit mehr als 250 Teilnehmern (bei denen VbSS derzeit nicht unterstützt wird).

Achtung: Nachdem die Sitzung zu RDP gewechselt hat, wechselt sie nicht wieder zu VbSS zurück. Auch hier ist ein nahtloser Übergang von VbSS vorgesehen, und der Wechsel wird voraussichtlich in den meisten Situationen nicht bemerkt werden.
    
> [!NOTE]
> Es wird nicht unterstützt, den Übergang von schlechte VBSS zu RDP in Skype for Business-Bildschirmübertragung zu blockieren oder zu blockieren. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, Deaktivieren und Konfigurieren von VbSS

Das tolle ist, dass nach der Installation von Skype for Business Server 2015 Kumulatives Update 3 (CU3) oder höher alle Ihre Benutzer standardmäßig für 1-zu-1-und mehr Parteien-schlechte VBSS aktiviert werden. Das kann für Sie problematisch sein, wenn Sie aus irgend einem Grund diese Funktion nicht für alle Benutzer aktivieren möchten. In diesem Fall können Sie mit den folgenden Schritten Benutzer deaktivieren (im Anschluss folgen die Schritte zum Aktivieren von Benutzern):
  
### <a name="how-to-disable-users-from-using-vbss"></a>So deaktivieren Sie die Verwendung von VbSS für Benutzer

- Sie können einer Benutzerrichtlinie, die schlechte VBSS nicht zulässt, Benutzer zuweisen, die schlechte VBSS nicht verwenden dürfen, indem Sie dieses Cmdlet in der Skype for Business-Verwaltungskonsole ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, von der alle Benutzer ohne zugewiesene Richtlinie betroffen sind:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS vollständig deaktivieren möchten, können Sie folgenden Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business-Besprechung mit mehreren Teilnehmern berücksichtigen alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>So aktivieren Sie die Verwendung von VbSS für Benutzer

- Sie können eine bestimmte Benutzerrichtlinie zuweisen, die schlechte VBSS für alle Benutzer zulässt, die schlechte VBSS verwenden müssen, indem Sie dieses Cmdlet in der Skype for Business-Verwaltungskonsole ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, von der alle Benutzer ohne zugewiesene Richtlinie betroffen sind:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS nach dem Deaktivieren wieder aktivieren möchten (die Funktion ist standardmäßig aktiviert), können Sie folgenden Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Satz-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> Bei einer Skype for Business-Besprechung mit mehreren Teilnehmern berücksichtigen alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015-Kumulatives Update KB3061064](https://www.microsoft.com/en-us/download/details.aspx?id=47690)
  
[Video basierte Bildschirmübertragung (schlechte VBSS) ist in Skype for Business Server 2015 verfügbar](https://support.microsoft.com/en-us/kb/3170163)
