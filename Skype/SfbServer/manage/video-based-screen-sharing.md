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
description: Skype for Business Server Planungs- und Konfigurationsinformationen für die videobasierte Bildschirmfreigabe (VbSS)
ms.openlocfilehash: 0dacf7372a0c72d8cdaf01c1e3b12564fb5580a4526738f401d2227983c25c01
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349277"
---
# <a name="video-based-screen-sharing-for-skype-for-business-server"></a>Videobasierte Bildschirmübertragung für Skype for Business Server 
 
Videobasierte Bildschirmübertragung (VbSS) in Skype For Business Server 2015 steht jetzt zum Download zur Verfügung: [Skype for Business Server kumulatives Update 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690). VbSS ist in Skype for Business Server 2019 enthalten.
  
Videobasierte Bildschirmfreigabe (VbSS) verhindert die Lync-Bildschirmfreigabe. Der Unterschied zwischen VbSS und der herkömmlichen Bildschirmfreigabe hängt mit den zugrunde liegenden Protokollen zusammen, die verwendet werden und wozu sie besonders gut sind. Für die Bildschirmfreigabe wird das Remotedesktopprotokoll (RDP) verwendet, das sich hervorragend eignet, um Tausende von 1:1-Sitzungen zwischen den Computern der Benutzer zu erstellen. Neuere Technologie, VbSS, verwendet das User Datagram-Protokoll (UDP).
  
Skype for Business Server wollten die 1:1-Unterhaltungen und Besprechungserfahrungen von 1:n (mehreren Teilnehmern) verbessern. VbSS nutzt die Medienplattform (die UDP als zugrunde liegendes Protokoll verwendet) mit dem Ziel, ihre Videostartzeiten zu verbessern, die Anzeigequalität ihrer Überwachung (insbesondere, wenn sich das, was Sie gerade beobachten, schnell bewegt) und die Zuverlässigkeit insgesamt zu verbessern.
  
Ein Teil des Ziels der Verbesserung der Bildschirmfreigabe besteht darin, dass Übergänge zwischen VbSS und RDP so nahtlos wie möglich sind, wenn sie auftreten. Da VbSS ein Update der zugrunde liegenden Technologie ist, die bei der Bildschirmfreigabe für Skype for Business Server verwendet wird, ist es möglicherweise schwierig zu erkennen, welche Technologie Sie nutzen, es sei denn, Sie sehen sich SIP-Details im Netzwerkdatenverkehr an oder teilen Inhalte, die sich schnell bewegen oder 3D- Wenn Ihr Arbeitsplatz beispielsweise über viele ältere Clients verfügt, ist RDP weiterhin als Failsafe für Ihre Besprechungen und Unterhaltungen verfügbar. Skype for Business Server verwendet interne Logik, um zu entscheiden, welche der beiden Methoden (VbSS oder herkömmliche Bildschirmfreigabe) angewendet werden soll, wenn Clients eine Verbindung herstellen. RDP kann und wird durch VbSS ersetzt, wenn die Situation dies aufruft, sodass die Anzeige nicht unterbrochen wird.
  
## <a name="planning"></a>Planung

### <a name="vbss-pros-and-cons"></a>VbSS-Vor- und Nachteile

Durch den Wechsel zu VbSS sollen drei wichtige Verbesserungen vorgenommen werden:
  
1. Bildschirmfreigabe (bis zu 5 %) zuverlässiger im Vergleich zu RDP allein.

2. Beschleunigen Sie die Einrichtung von Sitzungen und Videos im Vergleich zu RDP allein (Einrichtung in der Hälfte der Zeit mit einer 6:1-Verbesserung bei Frames pro Sekunde).

3. Funktioniert unter Bedingungen mit geringer Bandbreite wesentlich besser als RDP, auch wenn Inhalte mit hoher Bewegung freigegeben werden, z. B. 3D-Grafiken.
    
Bitte beachten Sie, dass diese Nummern von der Integrität und der richtigen Leistungsoptimierung Ihres Netzwerks abhängen und netzwerke außerhalb Ihres eigenen Netzwerks umfassen können, wenn sich Ihre Clients auf mobilen Geräten befinden.
  
Sie sollten auch beachten, dass einige Genauigkeit/Scharfheit Ihrer freigegebenen Inhalte um Zuverlässigkeit, Geschwindigkeit und Effizienz gehandelt wurde. In den meisten Fällen ist dies für Benutzer nicht leicht sichtbar.
  
### <a name="ports-and-protocols"></a>Ports und Protokolle

**Erforderliche Serverports**

|**Serverrolle**|**Dienstname**|**Port oder Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|:-----|
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabedienst  <br/> |5065  <br/> |TCP  <br/> |Wird für eingehende SIP-Überwachungsanforderungen für die Anwendungsfreigabe verwendet.  <br/> |
|Front-End-Server  <br/> |Skype for Business Server Anwendungsfreigabedienst  <br/> |49152-65535  <br/> |TCP/UDP  <br/> |Für die Anwendungsfreigabe verwendeter Medienportbereich.  <br/> |
   
**Erforderliche Clientports**

|**Komponente**|**Portbereich**|**Protocol**|**Notizen**|
|:-----|:-----|:-----|:-----|
|Clients  <br/> |1024-65535  <br/> |TCP/UDP  <br/> |Anwendungsfreigabe.  <br/> |
   
Wenn QoS für die folgenden Medienports aktiviert ist und VbSS auch aktiviert ist, verwendet die AS MCU während einer Konferenz, die die Desktopfreigabe umfasst, die unten fett dargestellten Videoporteinstellungen für den Datenverkehr der Bildschirmfreigabe. 
  
> [!IMPORTANT]
> Diese Einstellungen sind ein Sonderfall, und diese genauen Einstellungen müssen bei der Implementierung dieser beiden Features verwendet werden. Dadurch werden andere empfohlene Einstellungen in der [Dokumentation für QoS](/previous-versions/office/lync-server-2013/lync-server-2013-managing-quality-of-service-qos)überschrieben. Für die Anwendungsfreigabe müssen Sie zusätzlich zum Definieren dieser Portwerte auch ASMCUSVC.exe im QoS-Gruppenrichtlinienobjekt angeben. 
  
**Erforderliche Einstellungen für Application Server QoS/VbSS**

|**Eigenschaft**|**Portwert**|**Protocol**|
|:-----|:-----|:-----|
|AudioPortStart  <br/> |49152  <br/> |Udp  <br/> |
|AudioPortCount  <br/> |8348  <br/> |Udp  <br/> |
|**VideoPortStart** <br/> |**57501** <br/> |Udp  <br/> |
|**VideoPortCount** <br/> |**8034** <br/> |Udp  <br/> |
|AppSharingPortStart  <br/> |40803  <br/> |TCP  <br/> |
|AppSharingPortCount  <br/> |8348  <br/> |TCP  <br/> |
   
### <a name="capacity-planning"></a>Kapazitätsplanung

Jeder Front-End-Server mit Skype for Business Server kumulativen Update 2 (CU2) 2 (2015) oder höher unterstützt bis zu 375 Teilnehmer für die Bildschirmfreigabe mit RDP (jedoch nur 250 pro Besprechung). Diese Kapazität ändert sich nach CU3 nicht, wenn VbSS eingeführt und verwendet wird.
  
Trotzdem haben wir Leistungs- und Stresstests in unserem Labor durchgeführt, und die folgenden Messungen sollten auch im Hinblick auf Ihre eigene Bereitstellung berücksichtigt werden (natürlich abhängig von der Nutzung).
  
Vorausgesetzt:
  
- Sie verwenden Skype for Business Server 2015 CU2 oder höher in Ihrer Bereitstellung.
    
- Alle Benutzer in Ihrer Skype for Business Server Umgebung verfügen über Bildschirmauflösungen von mehr als 1920 x 1080.
    
Bei voller Kapazität (wie oben erwähnt: 375 Bildschirmfreigabeteilnehmer pro Front-End-Server insgesamt, aber nur 250 pro Besprechung), verwendet Ihr Front-End-Server möglicherweise ~89 % der 1 Ethernet-Netzwerkkarte. Dies liegt daran, dass die vorhandene Bildschirmfreigabetechnologie in Skype for Business Server CU2 (RDP) den Inhalt auf dem Bildschirm in der systemeigenen Auflösung des PCs des Referenten überträgt. Wenn höhere Bildschirmauflösungen mit eingerechnet werden, treten möglicherweise bereits Netzwerkengpässe bei der Bildschirmfreigabe mit Skype for Business Server 2015 CU2 auf.
  
Um dies zu vermeiden, kann eine oder mehrere der folgenden Optionen hilfreich sein:
  
- Aktualisieren Sie Ihren Front-End-Server von einer 1-Ethernet-Netzwerkkarte auf eine 10-Ethernet-Karte.

- Erhöhen Sie die Anzahl der Front-End-Server, um den Datenverkehr auszugleichen.

- Beschränken Sie die Bandbreite (Bitrate), die für VbSS und RDP verwendet wird, indem Sie die maximale Bandbreite, die von beiden Kanälen verwendet wird, begrenzen.
    
Die Zahlen in dieser Tabelle werden von einzelnen Netzwerken und den freigegebenen Inhalten beeinflusst. Testen Sie, um Basispläne für Ihr Netzwerk oder Ihre Netzwerke zu erstellen.
  
|**1080p-Inhalt**|**RDP-Durchschnitt**|**RDP Peak**|**VbSS-Durchschnitt**|**VbSS Peak**|
|:-----|:-----|:-----|:-----|:-----|
|Ppt  <br/> |200 KBit/s  <br/> |12mbps  <br/> |100 KBit/s  <br/> |3 MBit/s  <br/> |
|Cad  <br/> |3 MBit/s  <br/> |7 MBit/s  <br/> |1 MBit/s  <br/> |3 MBit/s  <br/> |
|Video  <br/> |5 MBit/s  <br/> |7 MBit/s  <br/> |1,3 MBit/s  <br/> |2,2 MBit/s  <br/> |
   
### <a name="network-bandwidth-requirements-for-media-traffic"></a>Netzwerkbandbreitenanforderungen für Mediendatenverkehr

Die VbSS-Bandbreite ist:
  
|**Videocodec**|**Auflösung und Seitenverhältnis**|**Maximale Bitrate der Videonutzlast (KBit/s)**|**Bitrate der mindesten Videonutzlast (KBit/s)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |1920 x 1080 (16:9)  <br/> (Das Seitenverhältnis hängt von der Bildschirmauflösung des Sharers ab und ist nicht immer 16:9.  <br/> |4000  <br/> |1500  <br/> |
   
## <a name="clients-and-servers-support"></a>Unterstützung für Clients und Server

Für die videobasierte Bildschirmübertragung sind Skype for Business Server 2015 CU3 oder höher sowie eine aktuelle Version der unterstützenden Clients erforderlich, die im Vergleich der [Mobilen Clientfeatures für die](../plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) Unterstützung von Skype for Business und [Besprechungen](../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md#BKMK_Conferencing)aufgeführt sind. 
  
Es gibt Situationen, in denen die Bildschirmfreigabe auf RDP umgestellt wird, z. B.:
  
- Wenn Ihr Konto in einer Umgebung gehostet wird, in der ASMCU nicht den Mindestbuild erfüllt, der VbSS unterstützt.
- Wenn eine Person, die eine ältere Version des Skype for Business-Clients verwendet, ihrer Sitzung beitritt, z. B. eine beliebige Windows Clientversion, die niedriger als 16.0.6330.1000 ist, Skype for Business Raumsystemgeräte oder Skype for Business Mobile Apps. 
- Wenn ein Benutzer die Freigabe von der Skype for Business-Web-App aus vorgibt.
- Wenn jemand Skype for Business auf einem Mac verwendet und nicht auf Skype for Business Online oder Skype for Business Server 2015 mit dem kumulativen Update vom Juli 2018 (oder höher) verwaltet wird.
- Wenn jemand eine Programm-/Windows-Freigabe startet.
- Wenn jemand beginnt, die Sitzung aufzuzeichnen.
- Wenn während der Sitzung jemand die Remotebildschirmsteuerung aufruft. 
- Besprechungen mit mehr als 250 Teilnehmern (wobei VbSS derzeit nicht unterstützt wird).

Beachten Sie, dass nach dem Übergang der Sitzung zu RDP kein Übergang zurück zu VbSS erfolgt. Auch hier soll der Übergang von VbSS nahtlos erfolgen und in den meisten Situationen nicht leicht zu erkennen sein.
    
> [!NOTE]
> Es wird nicht unterstützt, den Übergang von VbSS zu RDP in Skype for Business Bildschirmfreigabe zu blockieren oder zu blockieren. 
  
## <a name="enabling-disabling-and-configuring-vbss"></a>Aktivieren, Deaktivieren und Konfigurieren von VbSS

Das Tolle ist: Nachdem Sie das kumulative Update 3 (CU3) Skype for Business Server 2015 (CU3) oder höher installiert haben, werden alle Ihre Benutzer standardmäßig für VbSS mit 1:1 und mehreren Teilnehmern aktiviert. Dies kann für Sie problematisch sein, wenn Sie einen Grund haben, diese Funktion nicht für alle Ihre Benutzer aktiviert zu haben. In diesem Fall können Sie diese Schritte verwenden, um Benutzer zu deaktivieren (die Schritte zum Aktivieren von Benutzern folgen):
  
### <a name="how-to-disable-users-from-using-vbss"></a>So deaktivieren Sie die Verwendung von VbSS durch Benutzer

- Sie können eine Benutzerrichtlinie zuweisen, die VbSS keinem Benutzer zulässt, der vbSS nicht verwenden sollte, indem Sie dieses Cmdlet in der Skype for Business Verwaltungskonsole ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode RDP
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirkt:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode RDP
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsConferencingPolicy".](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- Wenn Sie VbSS vollständig deaktivieren müssen, können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $false
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsMediaConfiguration".](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> In einer Besprechung mit mehreren Teilnehmern Skype for Business berücksichtigen alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
### <a name="how-to-enable-users-to-use-vbss"></a>So ermöglichen Sie Benutzern die Verwendung von VbSS

- Sie können eine bestimmte Benutzerrichtlinie zuweisen, die VbSS allen Benutzern zulässt, die VbSS verwenden müssen, indem Sie dieses Cmdlet in der Skype for Business Management Console ausführen (ersetzen Sie [PolicyName] durch die Richtlinie, für die Sie dies tun):
    
  ```PowerShell
  Set-CsConferencingPolicy -Identity [PolicyName] -ApplicationSharingMode VideoWithFallback
  ```

- Sie können auch die globale Konferenzrichtlinie aktualisieren, die sich auf alle Benutzer ohne zugewiesene Richtlinie auswirkt:
    
  ```PowerShell
  Set-CsConferencingPolicy -ApplicationSharingMode VideoWithFallback
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsConferencingPolicy".](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)
    
- Wenn Sie VbSS nach dem Deaktivieren wieder aktivieren müssen (standardmäßig aktiviert), können Sie diesen Befehl ausführen:
    
  ```PowerShell
  Set-CsMediaConfiguration -EnableVideoBasedSharing $true
  ```

    Weitere Informationen zu diesem Befehl finden Sie unter ["Set-CsMediaConfiguration".](/powershell/module/skype/set-csmediaconfiguration?view=skype-ps)
    
> [!NOTE]
> In einer Besprechung mit mehreren Teilnehmern Skype for Business berücksichtigen alle Clientendpunkte die Richtlinieneinstellung für den Besprechungsorganisator. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server kumulatives Update 2015 KB3061064](https://www.microsoft.com/download/details.aspx?id=47690)
  
[Videobasierte Bildschirmfreigabe (VBSS) ist in Skype for Business Server 2015 verfügbar](https://support.microsoft.com/kb/3170163)