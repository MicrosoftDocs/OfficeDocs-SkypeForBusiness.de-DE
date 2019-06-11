---
title: 'Lync Server 2013: Definieren der Mobilitätsanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 604812d96f58a53ee008bfe42603243571138d1e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Definieren der Mobilitätsanforderungen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Während der Planungsphase für das lync Server 2013 Mobility-Feature treffen Sie bei der Verwendung von lync 2010 Mobile-und lync 2013-mobilen Clients Entscheidungen, die ihre Bereitstellungsschritte bestimmen.

Hier sind die Entscheidungen, die Sie beachten müssen:

  - **Möchten Sie die automatische Ermittlung für Mobile lync-Clients verwenden?**
    
    Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue interne und externe DNS-Einträge (Domain Name System) erstellen, Zertifikate auf den Front-End-Servern, Directors und Reverse-Proxys mit alternativen Subjektnamen versehen und die vorhandenen Veröffentlichungsregeln ändern. auf dem Reverse-Proxy. Ausführliche Informationen finden Sie unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Mit der automatischen Ermittlung können Benutzer die lync Server 2013-Webdienste automatisch von einer beliebigen Stelle innerhalb oder außerhalb des Unternehmensnetzwerks finden, ohne die URLs in die Einstellungen Ihres mobilen Geräts einzugeben.
    
    Wenn Sie anstelle der automatischen Ermittlung manuelle Einstellungen verwenden, müssen Mobile Benutzer die folgenden URLs manuell auf Ihren mobilen Geräten eingeben:
    
      - https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root für externen Zugriff
    
      - https://\<IntPoolFQDN\>/autodiscover/autodiscoverservice. svc/root für internen Zugriff
    
    Wir empfehlen dringend die Verwendung der automatischen Erkennung. Die primäre Verwendung von manuellen Einstellungen dient zur Problembehandlung.

  - **Wenn Sie sich entschließen, die automatische Ermittlung zu unterstützen, sind Sie bereit, Zertifikate auf dem Reverse-Proxy mit alternativen Subjektnamen für die einzelnen SIP-Domänen zu aktualisieren?**
    
    Wenn Sie über viele SIP-Domänen verfügen, kann das Aktualisieren öffentlicher Zertifikate auf dem Reverse-Proxy sehr teuer werden. Wenn dies der Fall ist, können Sie die automatische Ermittlung so implementieren, dass die anfängliche AutoErmittlungsdienst Anforderung http auf Port 80 verwendet, anstatt HTTPS auf Port 443 zu verwenden. Dies ist jedoch nicht die empfohlene Vorgehensweise. Wenn Sie sich entscheiden, diese Alternative zu wählen, müssen Sie die Zertifikate auf dem Reverseproxy nicht aktualisieren, Sie müssen jedoch eine Webveröffentlichungsregel für http auf Port 80 erstellen. Weitere Informationen finden Sie unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Möchten Sie lync Mobile-Clients sowohl intern als auch extern für das Unternehmensnetzwerk unterstützen oder Clients nur innerhalb des Unternehmensnetzwerks unterstützen?**
    
    Wenn Sie Mobile Clients innerhalb und außerhalb Ihres Netzwerks unterstützen möchten, können mobile Geräte von jedem beliebigen Standort aus auf Mobilitätsfeatures zugreifen. Die Standardkonfiguration ist die Unterstützung von internen und externen Clients im Unternehmensnetzwerk.
    
    Zwar kann die Standardkonfiguration den mobilen Client Datenverkehr auf der externen Website durchlaufen, doch können Sie den mobilen Client Datenverkehr auf das interne Unternehmensnetzwerk einschränken. Wenn Sie den Datenverkehr auf das interne Netzwerk einschränken, können Benutzer lync Mobile-Anwendungen nur auf Ihren mobilen Geräten verwenden, wenn Sie sich im Netzwerk befinden.
    
    Für Bereitstellungen, die Mobilität mithilfe des MCX **-** mobilitätsdiensts und lync 2010 Mobile unterstützen, führen Sie das Cmdlet "setCsMcxConfiguration" aus. Wenn Sie die Mobilität nur für die interne Verwendung einstellen möchten, verwenden Sie einen Befehl ähnlich der folgenden:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Für UCWA sind keine zusätzlichen Konfigurationen erforderlich. UCWA hat keine äquivalente interne Konfiguration.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie einen lync Server 2013&nbsp;-Front-End-Server oder Front-End <STRONG></STRONG> -Pools verwenden und keine lync Server 2010&nbsp;-Front-End-Server oder Front-End-Pools vorhanden sind, <STRONG>gibt es keine Anforderung für die Cookie-basierte Persistenz</STRONG>. Wenn Sie alle lync Server 2010&nbsp;-Front-End-Server oder Front-End-Pools beibehalten müssen, gelten die gleichen Regeln wie in lync Server 2010 für Cookie-basierte Persistenz.

    
    </div>

  - **Möchten Sie Push-Benachrichtigungen für Apple IOS-Geräte und Windows phones unterstützen?**
    
    Wenn Sie Push-Benachrichtigungen unterstützen, erhalten unterstützte Apple IOS-Geräte und Windows phones eine Benachrichtigung über Ereignisse, die auftreten, wenn die Mobile Anwendung inaktiv ist. Sie müssen den Edgeserver so konfigurieren, dass er über eine Verbundbeziehung mit dem cloudbasierten lync Server-Push-Benachrichtigungsdienst verfügt, der sich im lync Online-Rechenzentrum befindet, und ein Cmdlet ausführen, um Push-Benachrichtigungen zu aktivieren.
    
    Wenn Sie Push-Benachrichtigungen über Ihr WLAN-Netzwerk unterstützen möchten, müssen Sie zusätzlich zur Unterstützung von Push-Benachrichtigungen über die 3G-oder Datennetzwerke des Mobilfunkanbieters Port 5223 in Ihrem WLAN-Netzwerk für Unternehmen öffnen. Das unterstützen von Push-Benachrichtigungen über das WLAN-Netzwerk unterstützt mobile Geräte, die nur WLAN-und mobile Geräte verwenden, die einen schlechten Empfang im Innenbereich aufweisen.
    
    <div>
    

    > [!IMPORTANT]  
    > Das Öffnen von Port TCP 5223 ist nur erforderlich, wenn Apple-Geräte unterstützt werden, auf denen der Mobile lync 2010-Client ausgeführt wird.

    
    </div>
    
    Wenn Sie keine Push-Benachrichtigungen unterstützen, finden Benutzer von mobilen Apple-Geräten und Windows-Smartphones keine Informationen zu Ereignissen wie Sofortnachrichten-Einladungen oder verpassten Nachrichten, die auftreten, wenn die Mobile Anwendung inaktiv ist.
    
    <div>
    

    > [!NOTE]  
    > Für lync 2013 Mobile-Clients auf Apple-Geräten ist keine Push-Benachrichtigung erforderlich. Die mobilen lync 2013-Clients auf Windows Phone verwenden eine Push-Benachrichtigung. Die Planung für die Push-Benachrichtigung und das Clearing House für die Push-Benachrichtigung bleiben für lync Mobile auf Windows Phone-und Apple-Geräten gleich, die nicht in der Lage sind, den mobilen lync 2013-Client auszuführen.

    
    </div>

  - **Möchten Sie, dass alle Benutzer Zugriff auf Mobilitätsfeatures haben, oder möchten Sie in der Lage sein, anzugeben, welche Benutzer Zugriff auf diese Features haben?**
    
    In der Tabelle werden die Features beschrieben, die Benutzern in lync Server 2013 zur Verfügung stehen. Die Standardeinstellungen ermöglichen Anruf über Arbeit, VoIP (Voice over IP) und ermöglichen Mobilität. Hier finden Sie die vollständige Auswahl der verfügbaren Optionen:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parameter Name/Bereich (Richtlinien Parameter Namen sind möglicherweise nicht identisch)</th>
    <th>Beschreibung</th>
    <th>Eingeführt</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Mobilität aktivieren</p>
    <p>Parameter Name:<code>EnableMobility</code></p>
    <p>Bereich: Global/Website/Benutzer</p></td>
    <td><p>Administrative Einstellung Wenn die Richtlinie auf "false" festgelegt ist, kann der Benutzer sich nicht beim Client anmelden, um die Benutzer in einem bestimmten Bereich zu steuern, auf dem die lync Mobile-Anwendung installiert ist.</p>
    <p>Die Standardeinstellung ist wahr.</p></td>
    <td><p>Kumulatives Update für lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Aktivieren von Fremdsprache</p>
    <p>Parameter Name:<code>EnableOutsideVoice</code></p>
    <p>Bereich: Global/Website/Benutzer</p></td>
    <td><p>Steuert die Möglichkeit des Benutzers, Anrufe über Arbeit zu verwenden, eine Funktion, mit der Benutzer Anrufe tätigen und entgegennehmen können, indem Sie Ihre geschäftliche Nummer anstelle Ihrer Mobiltelefonnummer verwenden. Wenn Sie auf "false" festgelegt ist, kann der Benutzer keine Anrufe tätigen oder entgegennehmen, indem er seine geschäftliche Nummer auf seinem mobilen Gerät verwendet.</p>
    <p>Die Standardeinstellung ist wahr.</p></td>
    <td><p>Kumulatives Update für lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP-Audio und -Video aktivieren</p>
    <p>Parameter Name:<code>EnableIPAudioVideo</code></p>
    <p>Bereich: Global/Website/Benutzer</p></td>
    <td><p>Steuert, ob ein Benutzer VoIP verwenden kann, um Sprach-oder Videoanrufe auf seinem mobilen Gerät zu tätigen oder zu empfangen. Wenn Sie auf "false" festgelegt ist, kann der Benutzer keine VoIP-oder Videoanrufe auf seinem Gerät tätigen oder empfangen.</p>
    <p>Die Standardeinstellung ist wahr.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Wi-Fi für IP-Audio erforderlich</p>
    <p>Parameter Name:<code>RequireWiFiForIPAudio</code></p>
    <p>Bereich: Global/Website/Benutzer</p></td>
    <td><p>Mit dieser Einstellung wird festgelegt, ob der Client Anrufe über VoIP über WLAN statt über das Mobilfunknetz führen und empfangen muss. Wenn der Benutzer auf "true" festgelegt ist, kann er nur dann VoIP-Anrufe tätigen und empfangen, wenn er mit einem WLAN-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist "false".</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Wi-Fi für IP-Video erforderlich</p>
    <p>Parameter Name:<code>RequireWiFiForIPVideo</code></p>
    <p>Bereich: Global/Website/Benutzer</p></td>
    <td><p>Mit dieser Einstellung wird festgelegt, ob der Client Videoanrufe über WLAN tätigen und empfangen muss, anstatt im Mobilfunk-Datennetzwerk. Wenn der Benutzer auf "true" festgelegt ist, kann er nur dann Videoanrufe tätigen und empfangen, wenn er mit einem WLAN-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist "false".</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Eine Beschreibung der Richtlinieneinstellungen, die Sie konfigurieren können, und wie Sie die Richtlinien verwalten, finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) und [ Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Möchten Sie, dass Benutzer, die nicht für Enterprise-VoIP aktiviert sind, in der Lage sein, Click-to-Join zu verwenden, um an Konferenzen teilzunehmen?**
    
    Damit Benutzer Zugriff auf Mobilitätsfunktionen haben und über die Arbeit anrufen können, müssen Sie für Enterprise-VoIP aktiviert sein. Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können jedoch an Konferenzen teilnehmen, indem Sie auf dem mobilen Gerät auf den Link klicken, wenn Ihnen eine entsprechende VoIP-Richtlinie zugewiesen ist. Sie können diesen Benutzern entweder eine bestimmte VoIP-Richtlinie zuweisen oder sicherstellen, dass eine globale Richtlinie oder eine Richtlinie auf Websiteebene vorhanden ist, die für diese Benutzer gilt. Die VoIP-Richtlinie, die Sie zuweisen, muss über öffentliche PSTN-Nutzungsdatensätze und-Routen verfügen, die die Bereiche definieren, in die die Benutzer zum teilnehmen an einer Konferenz wählen können. Details zum Festlegen von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und Routen finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Für mobile Benutzer, die Click-to-Join verwenden möchten, ist eine VoIP-Richtlinie zusammen mit den zugehörigen PSTN-Nutzungsdaten Sätzen und VoIP-Routen erforderlich, da durch Klicken auf den Link auf dem mobilen Gerät ein ausgehender Anruf von lync Server 2013 entsteht.

    
    </div>

<div>

## <a name="see-also"></a>Siehe auch


[Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

