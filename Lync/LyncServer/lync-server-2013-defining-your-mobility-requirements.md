---
title: 'Lync Server 2013: Definieren Ihrer Mobilitätsanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0eeb3feda41a62472c79214681bc4b9ce0a22ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definieren der Mobilitätsanforderungen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Wenn Sie in der Planungsphase für das lync Server 2013 Mobilitätsfeature lync 2010 Mobile und lync 2013 Mobile Clients verwenden, treffen Sie Entscheidungen, die die Bereitstellungsschritte bestimmen.

Hier sind die Entscheidungen, die Sie berücksichtigen müssen:

  - **Möchten Sie die automatische Ermittlung für Mobile lync-Clients verwenden?**
    
    Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue interne und externe Domain Name System (DNS) Einträge erstellen, Zertifikate auf den Front-End-Servern, Directors und Reverseproxy hinzufügen und die vorhandenen Veröffentlichungsregeln ändern. auf dem Reverse-Proxy. Ausführliche Informationen finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Mit der automatischen Ermittlung können Benutzer automatisch lync Server 2013 Webdienste von einer beliebigen Stelle innerhalb oder außerhalb des Unternehmensnetzwerks Auffinden, ohne URLs in Ihre Einstellungen für mobile Geräte einzugeben.
    
    Wenn Sie anstelle der automatischen Ermittlung manuelle Einstellungen verwenden, müssen Mobile Benutzer die folgenden URLs manuell in ihren mobilen Geräten eingeben:
    
      - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root für externen Zugriff
    
      - https://\<IntPoolFQDN\>/autodiscover/autodiscoverservice. svc/Stammverzeichnis für internen Zugriff
    
    Es wird dringend empfohlen, die automatische Ermittlung zu verwenden. Die primäre Verwendung von manuellen Einstellungen ist für die Problembehandlung.

  - **Wenn Sie sich dafür entscheiden, die automatische Ermittlung zu unterstützen, sind Sie bereit, Zertifikate auf dem Reverseproxy mit alternativen Antragstellernamen für jede SIP-Domäne zu aktualisieren?**
    
    Wenn Sie über zahlreiche SIP-Domänen verfügen, kann das Aktualisieren öffentlicher Zertifikate auf dem Reverseproxy sehr kostspielig werden. Wenn dies der Fall ist, können Sie die automatische Ermittlung so implementieren, dass die anfängliche AutoErmittlungsdienst Anforderung http an Port 80 verwendet, anstatt HTTPS an Port 443 zu verwenden. Dies ist jedoch nicht die empfohlene Vorgehensweise. Wenn Sie sich für diese Alternative entscheiden, müssen Sie die Zertifikate auf dem Reverseproxy nicht aktualisieren, aber Sie müssen eine Webveröffentlichungsregel für http auf Port 80 erstellen. Weitere Informationen finden Sie unter [Technical Requirements for Mobility in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Möchten Sie lync Mobile-Clients sowohl intern als auch extern für das Unternehmensnetzwerk unterstützen oder Clients nur innerhalb des Unternehmensnetzwerks unterstützen?**
    
    Wenn Sie Mobile Clients innerhalb und außerhalb Ihres Netzwerks unterstützen möchten, können mobile Geräte von jedem Standort aus auf Mobilitätsfunktionen zugreifen. Die Standardkonfiguration besteht darin, sowohl interne als auch externe Clients für das Unternehmensnetzwerk zu unterstützen.
    
    Die Standardkonfiguration ermöglicht zwar den mobilen Client Datenverkehr, um den externen Standort zu durchlaufen, aber Sie können den Datenverkehr für mobile Clients auf das interne Unternehmensnetzwerk einschränken. Wenn Sie den Datenverkehr auf das interne Netzwerk beschränken, können Benutzer lync Mobile-Anwendungen nur auf Ihren mobilen Geräten verwenden, wenn Sie sich innerhalb des Netzwerks befinden.
    
    Für Bereitstellungen, die die Mobilität mit dem MCX-Mobilitätsdienst und lync 2010 Mobile unterstützen, führen Sie das Cmdlet " **CsMcxConfiguration** " aus. Um die Mobilität nur für die interne Verwendung festzulegen, verwenden Sie einen Befehl wie den folgenden:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Für UCWA sind keine zusätzlichen Konfigurationen erforderlich. UCWA hat keine äquivalente interne Konfiguration.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie eine lync Server 2013&nbsp;-Front-End-Server-oder Front-End-Pools verwenden und keine lync Server 2010&nbsp;-Front-End-Server oder Front-End-Pools <STRONG>haben</STRONG> , <STRONG>ist keine Notwendigkeit für die Cookie-basierte Persistenz</STRONG>. Wenn Sie lync Server 2010&nbsp;Front-End-Server oder Front-End-Pools beibehalten müssen, gelten dieselben Regeln wie in lync Server 2010 für die Cookie-basierte Persistenz.

    
    </div>

  - **Möchten Sie Push-Benachrichtigungen für Apple IOS-Geräte und Windows phones unterstützen?**
    
    Wenn Sie Push-Benachrichtigungen unterstützen, erhalten unterstützte Apple IOS-Geräte und Windows Phone eine Benachrichtigung über Ereignisse, die auftreten, wenn die Mobile Anwendung inaktiv ist. Sie müssen ihre Edgeserver so konfigurieren, dass Sie über eine Verbundbeziehung mit dem cloudbasierten lync Server Push-Benachrichtigungsdienst verfügt, der sich im lync Online Datencenter befindet, und führen Sie ein Cmdlet aus, um Push-Benachrichtigungen zu aktivieren.
    
    Wenn Sie Push-Benachrichtigungen über Ihr WLAN-Netzwerk unterstützen möchten, müssen Sie zusätzlich zur Unterstützung von Push-Benachrichtigungen über die 3G-oder Datennetzwerke der Mobilgeräte Anbieter den Port 5223 Outbound in Ihrem WLAN-Netzwerk in Ihrem Unternehmen öffnen. Unterstützen von Push-Benachrichtigungen über das WLAN-Netzwerk unterstützt mobile Geräte, die nur WLAN und mobile Geräte verwenden, die einen schlechten innen Empfang haben.
    
    <div>
    

    > [!IMPORTANT]  
    > Das Öffnen von Port TCP 5223 ist nur erforderlich, wenn Apple-Geräte unterstützt werden, auf denen der lync 2010 Mobile-Client installiert ist.

    
    </div>
    
    Wenn Sie keine Push-Benachrichtigungen unterstützen, werden Benutzer von mobilen Apple-Geräten und Windows-Telefonen nicht über Ereignisse erfahren, beispielsweise über sofortnachrichteneinladungen oder verpasste Nachrichten, die auftreten, wenn die Mobile Anwendung inaktiv ist.
    
    <div>
    

    > [!NOTE]  
    > Für lync 2013 Mobile Clients auf Apple-Geräten ist keine Push-Benachrichtigung erforderlich. Die lync 2013 Mobile Clients in Windows Phone verwenden eine Push-Benachrichtigung. Die Planung für die Push-Benachrichtigung und das Push Notification Clearing House bleiben für lync Mobile auf Windows Phone und Apple-Geräten unverändert, die den lync 2013 mobilen Client nicht ausführen können.

    
    </div>

  - **Möchten Sie, dass alle Benutzer Zugriff auf Mobilitätsfunktionen haben, oder möchten Sie angeben können, welche Benutzer Zugriff auf diese Features haben?**
    
    In der Tabelle werden die Features beschrieben, die Benutzern in lync Server 2013 zur Verfügung stehen. Die Standardeinstellungen erlauben den Anruf über Arbeit, ermöglichen VoIP (Voice over IP) und ermöglichen Mobilität. Hier finden Sie die vollständige Palette der verfügbaren Optionen:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parameter Name/Bereich (die Richtlinien Parameter Namen sind möglicherweise nicht identisch)</th>
    <th>Beschreibung</th>
    <th>Eingeführt</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Aktivieren der Mobilität</p>
    <p>Parameter Name:<code>EnableMobility</code></p>
    <p>Bereich: Global/Site/User</p></td>
    <td><p>Administrative Einstellung zum Steuern von Benutzern in einem bestimmten Bereich, auf dem lync Mobile installiert ist, wenn die Richtlinie auf "false" festgelegt ist, kann der Benutzer sich nicht beim Client anmelden.</p>
    <p>Die Standardeinstellung ist true.</p></td>
    <td><p>Kumulatives Update für lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Aktivieren von externer Sprachausgabe</p>
    <p>Parameter Name:<code>EnableOutsideVoice</code></p>
    <p>Bereich: Global/Site/User</p></td>
    <td><p>Steuert die Fähigkeit eines Benutzers, die Funktion "Anruf über Arbeit" zu verwenden, ein Feature, mit dem Benutzer Anrufe über Ihre Arbeitsnummer anstelle Ihrer Mobiltelefonnummer tätigen und empfangen können. Bei Festlegung auf "false" kann der Benutzer keine Anrufe tätigen oder empfangen, indem er seine Arbeitsnummer auf seinem mobilen Gerät verwendet.</p>
    <p>Die Standardeinstellung ist true.</p></td>
    <td><p>Kumulatives Update für lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Aktivieren von IP-Audio und-Video</p>
    <p>Parameter Name:<code>EnableIPAudioVideo</code></p>
    <p>Bereich: Global/Site/User</p></td>
    <td><p>Steuert, ob ein Benutzer VoIP-oder Videoanrufe auf seinem mobilen Gerät tätigen oder empfangen kann. Wenn dieser Wert auf "false" festgelegt ist, kann der Benutzer keine VoIP-oder Videoanrufe auf seinem Gerät tätigen oder empfangen.</p>
    <p>Die Standardeinstellung ist true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>WiFi für IP-Audio erforderlich</p>
    <p>Parameter Name:<code>RequireWiFiForIPAudio</code></p>
    <p>Bereich: Global/Site/User</p></td>
    <td><p>Mit dieser Einstellung wird festgelegt, ob der Client Anrufe über VoIP auf WLAN anstelle des Mobil Datennetzwerks tätigen und empfangen muss. Wenn dieser Wert auf true festgelegt ist, kann der Benutzer nur dann VoIP-Anrufe tätigen und empfangen, wenn er mit einem WLAN-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Erfordern von WLAN für IP-Video</p>
    <p>Parameter Name:<code>RequireWiFiForIPVideo</code></p>
    <p>Bereich: Global/Site/User</p></td>
    <td><p>Mit dieser Einstellung wird festgelegt, ob der Client Videoanrufe über WLAN statt im Mobilfunk-Datennetzwerk tätigen und empfangen muss. Wenn dieser Wert auf "true" festgelegt ist, kann der Benutzer Videoanrufe nur dann tätigen und empfangen, wenn er mit einem Wi-Fi-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Eine Beschreibung der Richtlinieneinstellungen, die Sie konfigurieren können, und wie Sie die Richtlinien verwalten, finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) und [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Möchten Sie, dass Benutzer, die nicht für Enterprise-VoIP aktiviert sind, mit der Option zum beitreten an Konferenzen teilnehmen können?**
    
    Damit Benutzer Zugriff auf Mobilitätsfunktionen haben und über Arbeit anrufen können, müssen Sie für Enterprise-VoIP aktiviert sein. Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können jedoch an Konferenzen teilnehmen, indem Sie auf Ihrem mobilen Gerät auf den Link klicken, wenn Ihnen eine entsprechende VoIP-Richtlinie zugewiesen ist. Sie können diesen Benutzern entweder eine bestimmte VoIP-Richtlinie zuweisen oder sicherstellen, dass eine globale Richtlinie oder Richtlinie auf Websiteebene vorhanden ist, die für diese Benutzer gilt. Für die VoIP-Richtlinie, die Sie zuweisen, müssen PSTN-Verwendungsdaten Sätze (Public Switched Telephone Network) und-Routen verwendet werden, in denen die Bereiche definiert sind, an die Benutzer für die Teilnahme an einer Konferenz wählen können. Ausführliche Informationen zum Festlegen von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und Routen finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Mobile Benutzer, die Click to Join verwenden möchten, benötigen eine VoIP-Richtlinie zusammen mit den zugehörigen PSTN-Verwendungsdatensätzen und VoIP-Routen, da durch Klicken auf den Link auf dem mobilen Gerät ein ausgehender Anruf von lync Server 2013 entsteht.

    
    </div>

<div>

## <a name="see-also"></a>Siehe auch


[Technische Anforderungen für die Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

