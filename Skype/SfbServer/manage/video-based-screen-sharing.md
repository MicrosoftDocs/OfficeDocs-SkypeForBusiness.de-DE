---
title: Video basierte Bildschirmfreigabe für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/20/2018
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50755399-2228-4324-81db-c2bfc824c299
description: Skype for Business Server von Planungs-und Konfigurationsinformationen für Video basierte Bildschirm Freigaben (VbSS)
ms.openlocfilehash: d6b66da2994db892bc193103bca75e844c62197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42009568"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Video basierte Bildschirmfreigabe für Skype for Business Server 
 
Die Video basierte Bildschirmfreigabe (VbSS) in Skype for Business Server 2015 steht jetzt zum Download zur Verfügung: [Skype for Business Server 2015 Kumulatives Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS ist in Skype for Business Server 2019 enthalten.
  
Die Video basierte Bildschirmfreigabe oder VbSS wuchs von der lync-Bildschirmfreigabe. Der Unterschied zwischen VbSS und herkömmlicher Bildschirmfreigabe liegt bei den zugrunde liegenden Protokollen, die verwendet werden, und deren Excel. Die Bildschirmfreigabe verwendet das Remotedesktopprotokoll (RDP), mit dem Tausende von 1 bis 1 Sitzungen zwischen den Computern der Personen erstellt werden können. Die neuere Technologie, VbSS, verwendet das User Datagram Protocol (UDP).
  
Skype for Business Server wollte die Personen 1:1 und ihre 1: n (mehrteiligen) Unterhaltungen und Besprechungs Erlebnisse verbessern. VbSS nutzt die Medienplattform (die auf UDP als zugrunde liegendes Protokoll basiert), mit dem Ziel, Ihre Video Startzeiten zu verbessern, die Anzeigequalität von dem, was Sie beobachten (insbesondere, wenn das, was Sie gerade sehen, sich schnell bewegt) und die Zuverlässigkeit insgesamt.
  
Ein Teil des Ziels, die Bildschirmfreigabe zu verbessern, besteht darin, dass Übergänge zwischen VbSS und RDP so nahtlos wie möglich sein werden, wenn Sie auftreten. Da VbSS ein Update der zugrunde liegenden Technologie ist, die in der Bildschirmfreigabe für Skype for Business Server verwendet wird, ist es möglicherweise schwierig zu ermitteln, welche Technologie Sie nutzen, es sei denn, Sie sehen sich SIP-Details im Netzwerkdatenverkehr an, oder Sie teilen Inhalte, die ist schnell verschoben oder 3-D. Wenn Ihr Arbeitsplatz beispielsweise viele Legacyclients enthält, ist RDP weiterhin als Failsafe für Ihre Besprechungen und Unterhaltungen verfügbar. Skype for Business Server verwendet interne Logik, um zu entscheiden, welche der beiden Methoden (VbSS oder herkömmliche Bildschirmfreigabe) angewendet werden sollen, wenn Clients eine Verbindung herstellen. RDP kann und wird durch VbSS ersetzt, wenn es von der Situation gefordert wird, damit Ihre Anzeige Erfahrung nicht unterbrochen wird.
  
## <a name="planning"></a>Planung

### <a name="vbss-pros-and-cons"></a>VbSS pro und Cons

Das Wechseln zu VbSS zielt darauf ab, drei wichtige Verbesserungen vorzunehmen:
  
1. Bildschirmfreigabe vornehmen (bis zu 5%) zuverlässiger im Vergleich zu RDP allein.

2. Machen Sie das Sitzungs Setup und die Videowiedergabe schneller im Vergleich zu RDP allein (Setup in der Hälfte der Zeit, mit einer 6:1 Verbesserung in Frames pro Sekunde).

3. Funktioniert viel besser als RDP in niedrigen Bandbreitenbedingungen, auch wenn Sie hohe Bewegungs Inhalte wie 3D-Grafiken freigeben.
    
Beachten Sie, dass diese Zahlen von der Integrität und ordnungsgemäßen Leistungsoptimierung Ihres Netzwerks abhängen und möglicherweise auch externe Netzwerke umfassen, wenn sich Ihre Clients auf mobilen Geräten befinden.
  
Sie sollten auch beachten, dass einige treue/Knusprigkeit Ihrer freigegebenen Inhalte für Zuverlässigkeit, Geschwindigkeit und Effizienz gehandelt wurde. In den meisten Fällen ist dies für Benutzer nicht leicht sichtbar.
  
### <a name="ports-and-protocols"></a>Ports und Protokolle

**Erforderliche Serveranschlüsse**

|**Serverrolle**|**Dienstname**|**Port oder Portbereich**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabe Dienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabe Dienst  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Für die Anwendungsfreigabe verwendete Medienportbereich.  <br/> |
   
**Erforderliche Client-Ports**

|**Komponente**|**Port Bereich**|**Protokoll**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden Medienanschlüsse aktiviert ist und VbSS ebenfalls aktiviert ist, verwendet die AS MCU während einer Konferenz, die die Desktopfreigabe umfasst, die unten Fett gezeigten Video Porteinstellungen für den Bildschirmfreigabe Datenverkehr. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Sonderfall, und diese genauen Einstellungen müssen bei der Implementierung beider Funktionen verwendet werden. Dadurch werden andere empfohlene Einstellungen in der [Dokumentation für QoS](https://technet.microsoft.com/library/gg405409%28v=ocs.15%29.aspx)außer Kraft gesetzt. Für die Anwendungsfreigabe müssen Sie zusätzlich zur Definition dieser Port Werte auch ASMCUSVC. exe im QoS-GPO angeben. 
  
**Erforderliche Einstellungen für den Anwendungs Server für QoS/VbSS**

|**Eigenschaft**|**Port-Wert**|**Protokoll**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |UDP  <br/> |
|AudioPortCount  <br/> |8348  <br/> |UDP  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |UDP  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |UDP  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jede Front-End-Server, die Skype for Business Server 2015 Kumulatives Update 2 (Cu2) oder höher ausführt, unterstützt bis zu 375 Teilnehmer für die Bildschirmfreigabe mit RDP (allerdings nur 250 pro Besprechung). Diese Kapazität ändert sich nicht nach der CU3, wenn VbSS eingeführt und verwendet wird.
  
Dennoch haben wir Leistungs-und Belastungstests in unserem Labor durchgeführt, und die folgenden Messungen sollten auch im Hinblick auf Ihre eigene Bereitstellung berücksichtigt werden (natürlich abhängig von der Nutzung).
  
Annahme
  
- Sie verwenden Skype for Business Server 2015 Cu2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype for Business Server Umgebung verfügen über eine Bildschirmauflösung von mehr als 1920x1080.
    
Bei voller Kapazität (wie oben erwähnt, ist 375 Screen Sharing Teilnehmer pro Front-End-Server insgesamt, wenn auch nur 250 pro Besprechung), kann Ihr Front-End-Server ~ 89% der 1 Gigabit Netzwerkkarte nutzen. Dies liegt daran, dass die vorhandene Bildschirmfreigabe Technologie in Skype for Business Server Cu2 (RDP) die Bildschirminhalte an die systemeigene Auflösung des Referenten Computers überträgt. Wenn also höhere Bildschirmauflösungen berücksichtigt werden, sind möglicherweise bereits Netzwerkengpässe für die Bildschirmfreigabe mit Skype for Business Server 2015 Cu2 zu spüren.
  
Um dies zu vermeiden, können eine oder mehrere der folgenden Optionen hilfreich sein:
  
- Aktualisieren Sie Ihre Front-End-Server von einer 1-Gigabit-Netzwerkkarte auf eine 10-Gigabit-Ethernet-Karte.

- Verbessern Sie die Anzahl der Front-End-Server für den Lastenausgleich des Datenverkehrs.

- Begrenzen Sie die für VbSS und RDP verwendete Bandbreite (Bitrate), indem Sie eine Obergrenze für die maximale Bandbreite festlegen, die von beiden Kanälen verwendet wird.
    
Die Zahlen in dieser Tabelle werden durch einzelne Netzwerke und den Inhalt beeinflusst, der freigegeben wird. Testen Sie, um Basispläne für Ihr Netzwerk oder Ihre Netzwerke festzulegen.
  
|**1080p-Inhalt**|**RDP-Durchschnitt**|**RDP-Spitze**|**VbSS-Durchschnitt**|**VbSS-Spitze**|
|:-----|:-----|:-----|:-----|:-----|
|PPT  <br/> |200kbps  <br/> |12Mbps  <br/> |100Kbps  <br/> |3Mbps  <br/> |
|CAD  <br/> |3Mbps  <br/> |7mbps  <br/> |1Mbps  <br/> |3Mbps  <br/> |
|Video  <br/> |5mbps  <br/> |7mbps  <br/> |1,3 Mbit/s  <br/> |2,2 Mbit/s  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Anforderungen an die Netzwerkbandbreite für den Mediendatenverkehr

Die VbSS-Bandbreite lautet:
  
|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate für Video Nutzlast (Kbit/s)**|**Minimale Bitrate für Video Nutzlast (Kbit/s)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |1920x1080 (16:9)  <br/> (Das Seitenverhältnis hängt von der Bildschirmauflösung des Mitarbeiters ab und ist nicht immer 16:9)  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Unterstützung von Clients und Servern

Die Video basierte Bildschirmfreigabe erfordert Skype for Business Server 2015 CU3 oder höher sowie eine aktuelle Version der unterstützenden Clients, die unter [Mobile Client-Funktionsvergleich für Skype for Business](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) -und [Besprechungs Unterstützung](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)aufgeführt sind. 
  
Es gibt Situationen, in denen die Bildschirmfreigabe über einen Übergang zu RDP erfolgt, wie diese:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der ASMCU nicht den minimalen Build erfüllt, der VbSS unterstützt.
- Wenn eine Person, die eine ältere Version des Skype for Business-Clients verwendet, ihrer Sitzung Beitritt, beispielsweise jeder, der eine beliebige Windows-Client Version unter dem 16.0.6330.1000, Skype for Business Room-System Geräte oder Skype for Business Mobile Apps verwendet. 
- Wenn ein Benutzer über die Skype for Business-Webanwendung freigegeben wird.
- Wenn jemand Skype for Business auf dem Mac verwendet und nicht in Skype for Business Online oder Skype for Business Server 2015 mit dem kumulativen Update vom Juli 2018 (oder höher) verwaltet wird.
- Wenn jemand ein Programm/Windows-Freigabe startet.
- Wenn ein Benutzer mit der Aufzeichnung der Sitzung beginnt.
- Wenn ein Benutzer während der Sitzung die Remote Bildschirmsteuerung aufruft. 
- Besprechungen mit mehr als 250 Teilnehmern (wobei VbSS derzeit nicht unterstützt wird).

Beachten Sie, dass die Sitzung nach dem Übergang zu RDP nicht wieder zurück zu VbSS wird. Auch hier soll der Übergang von VbSS nahtlos sein und wird in den meisten Situationen mit Hoffnung nicht leicht zu erkennen sein.
    
> [!NOTE]
> Es wird nicht unterstützt, den Übergang von VbSS zu RDP in Skype for Business Bildschirmfreigabe zu blockieren oder zu blockieren. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, deaktivieren und Konfigurieren von VbSS

Das beste ist, dass nach der Installation des Skype for Business Server 2015 kumulativen Updates 3 (CU3) oder höher alle Ihre Benutzer standardmäßig für 1-zu-1-und mehr Parteien-VbSS aktiviert sind. Dies kann für Sie problematisch sein, wenn Sie einen Grund haben, diese Funktionalität nicht für alle Benutzer aktiviert zu haben. In diesem Fall können Sie die folgenden Schritte verwenden, um Benutzer zu deaktivieren (die Schritte enable users folgen):
  
### <a name="how-to-disable-users-from-using-vbss"></a>Vorgehensweise Deaktivieren von Benutzern für die Verwendung von VbSS

- Sie können eine Benutzerrichtlinie zuweisen, die VbSS nicht allen Benutzern zulässt, die VbSS nicht verwenden sollten, indem Sie dieses Cmdlet in der Skype for Business Verwaltungskonsole ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirkt:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Sets-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS vollständig deaktivieren müssen, können Sie den folgenden Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Sets-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer mehrteiligen Skype for Business Besprechung respektieren alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>Aktivieren von Benutzern für die Verwendung von VbSS

- Sie können eine bestimmte Benutzerrichtlinie zuweisen, die VbSS für alle Benutzer zulässt, die VbSS verwenden müssen, indem Sie dieses Cmdlet in der Skype for Business Verwaltungskonsole ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirkt:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Sets-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
    
- Wenn Sie VbSS nach dem Ausschalten wieder aktivieren müssen (standardmäßig aktiviert), können Sie den folgenden Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter [Sets-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps).
    
> [!NOTE]
> In einer Skype for Business Besprechung mit mehreren Teilnehmern respektieren alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015 Kumulatives Update KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Die Video basierte Bildschirmfreigabe (VBSS) steht in Skype for Business Server 2015 zur Verfügung.](https://support.microsoft.com/kb/3170163)
