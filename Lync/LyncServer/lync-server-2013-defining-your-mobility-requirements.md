---
title: 'Lync Server 2013: Definieren der Mobilitätsanforderungen'
TOCTitle: Definieren der Mobilitätsanforderungen
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690039(v=OCS.15)
ms:contentKeyID: 49295178
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren der Mobilitätsanforderungen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Wenn Sie mobile Lync 2010 Mobile- und Lync 2013-Clients verwenden, müssen Sie in der Planungsphase für das Lync Server 2013-Mobilitätsfeature einige Entscheidungen treffen, die sich auf Ihre Bereitstellungsschritte auswirken.

Folgende Entscheidungen sind zu berücksichtigen:

  - **Soll die automatische Ermittlung für mobile Lync-Clients verwendet werden?**
    
    Wenn Sie die automatische Ermittlung unterstützen möchten, müssen Sie neue interne und externe DNS-Einträge (Domain Name System) erstellen, den Zertifikaten auf den Front-End-Servern, Directorsn und dem Reverseproxy alternative Antragstellernamen hinzufügen und die vorhandenen Webveröffentlichungsregeln für den Reverseproxy ändern. Ausführliche Informationen finden Sie unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Wenn die automatische Ermittlung aktiviert ist, können Benutzer automatisch Lync Server 2013-Webdienste von überall innerhalb oder außerhalb des Firmennetzwerks ermitteln, ohne in den Einstellungen des mobilen Geräts URLs eingeben zu müssen.
    
    Wenn Sie anstelle der automatischen Ermittlung manuelle Einstellungen verwenden, müssen mobile Benutzer manuell die folgenden URLs in ihre mobile Geräte eingeben:
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for external access
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root for internal access
    
    Es wird dringend empfohlen, die automatische Ermittlung zu verwenden. Manuelle Einstellungen werden in erster Linie zur Problembehandlung verwendet.

  - **Wenn Sie sich für die Unterstützung der automatischen Ermittlung entscheiden, sind Sie dann auch bereit, die Zertifikate auf dem Reverseproxy für jede SIP-Domäne mit alternativen Antragstellernamen zu aktualisieren?**
    
    Wenn Sie viele SIP-Domänen verwenden, kann die Aktualisierung öffentlicher Zertifikate auf dem Reverseproxy sehr aufwendig sein. Wenn dies zutrifft, können Sie die die automatische Ermittlung so konfigurieren, dass die anfängliche AutoErmittlungsdienst-Anforderung HTTP an Port 80 und nicht HTTPS an Port 443 verwendet. Dies ist aber nicht der empfohlene Ansatz. Wenn Sie sich für diese Alternative entscheiden, müssen Sie zwar die Zertifikate auf dem Reverseproxy nicht aktualisieren, aber eine Webveröffentlichungsregel für HTTP an Port 80 erstellen. Weitere Informationen finden Sie unter [Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Möchten Sie mobile Lync-Clients sowohl innerhalb als auch außerhalb des Firmennetzwerks oder nur innerhalb des Firmennetzwerks unterstützen?**
    
    Wenn Sie mobile Clients sowohl innerhalb als auch außerhalb des Netzwerks unterstützen möchten, können mobile Geräte von einem beliebigen Ort aus auf die Mobilitätsfeatures zugreifen. Gemäß Standardkonfiguration werden Clients sowohl innerhalb als auch außerhalb des Firmennetzwerks unterstützt.
    
    Obwohl die Standardkonfiguration ermöglicht, dass der Datenverkehr des mobilen Clients über die externe Website erfolgt, können Sie den Datenverkehr mobiler Clients auf das interne Firmennetzwerk beschränken. Wenn Sie den Datenverkehr auf das interne Netzwerk beschränken, können Benutzer mobile Lync-Anwendungen auf ihren mobilen Geräten nur verwenden, wenn sie sich innerhalb des Netzwerks befinden.
    
    Für Bereitstellungen, die die Mobilität mit dem Mcx-Mobilitätsdienst und Lync 2010 Mobile unterstützen, führen Sie das **Set-CsMcxConfiguration**-Cmdlet aus. Um die Mobilität nur für die interne Verwendung festzulegen, können Sie einen Befehl ähnlich wie den folgenden verwenden:
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    

    > [!NOTE]
    > Für UCWA (Unified Communications Web API) sind keine zusätzlichen Konfigurationen erforderlich. UCWA hat keine entsprechende Konfiguration, die nur intern verwendet wird.

    

    > [!IMPORTANT]
    > Wenn Sie Lync Server 2013- Front-End-Server oder - Front-End-Pools verwenden <STRONG>und nicht über</STRONG>Lync Server 2010- Front-End-Server oder - Front-End-Pools verfügen, <STRONG>ist cookiegestützte Persistenz nicht erforderlich</STRONG>. Wenn Sie Lync Server 2010- Front-End-Server oder - Front-End-Pools beibehalten müssen, gelten die gleichen Regeln wie in Lync Server 2010 für cookiegestützte Persistenz.



  - **Möchten Sie Pushbenachrichtigungen für Apple iOS-Geräte und Windows Phones unterstützen?**
    
    Wenn Sie Pushbenachrichtigungen unterstützen, erhalten die unterstützten Apple iOS-Geräte und Windows Phones eine Benachrichtigung über Ereignisse, die auftreten, wenn die mobile Anwendung inaktiv ist. Sie müssen den Edgeserver so konfigurieren, dass eine Partnerverbundbeziehung mit dem cloudbasierten Lync Server-Pushbenachrichtigungsdienst besteht, der sich im Lync Online-Rechenzentrum befindet, und ein Cmdlet zum Aktivieren von Pushbenachrichtigungen ausführen.
    
    Wenn Sie Pushbenachrichtigungen nicht nur über das 3G-Netzwerk der Anbieter mobiler Geräte oder über Datenwerke unterstützen möchten, sondern auch über das WLAN-Netzwerk, müssen Sie den ausgehenden Port 5223 im WLAN-Netzwerk Ihres Unternehmens öffnen. Durch das Ermöglichen von Pushbenachrichtigungen über das WLAN-Netzwerk werden mobile Geräte unterstützt, die über WLAN eine Verbindung herstellen, sowie mobile Geräte, die in Gebäuden einen schlechten Empfang haben.
    

    > [!IMPORTANT]
    > Das Öffnen von Port TCP 5223 ist für die Unterstützung von Apple-Geräten erforderlich, auf denen der Lync 2010 Mobile-Client ausgeführt wird.

    
    Wenn Sie Pushbenachrichtigungen nicht unterstützen, werden Benutzer von mobilen Apple-Geräten und Windows Phones nicht über Ereignisse (z. B. Chateinladungen oder entgangene Nachrichten) informiert, die auftreten, wenn die mobile Anwendung inaktiv ist.
    

    > [!NOTE]
    > Für mobile Lync 2013-Clients auf Apple-Geräten ist keine Pushbenachrichtigung erforderlich. Die mobilen Lync 2013-Clients auf dem Windows Phone verwenden die Pushbenachrichtigung. Die Planung für Pushbenachrichtigungen und das Push Notification Clearing House (PNCH) bleiben für Lync Mobile auf dem Windows Phone und auf Apple-Geräten gleich, auf denen der mobile Lync 2013-Client nicht ausgeführt werden kann.



  - **Sollen alle Benutzer Zugriff auf Mobilitätsfeatures haben, oder möchten Sie angeben können, welche Benutzer Zugriff auf diese Features haben?**
    
    In der Tabelle werden die Features beschrieben, die für Benutzer in Lync Server 2013 verfügbar sind. Die Standardwerte ermöglichen Folgendes: Geschäftlich anrufen, Voice over IP (VoIP) und Mobilität. Im Folgenden sind alle verfügbaren Optionen aufgelistet:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Feature/Parametername/Gültigkeitsbereich (Namen der Richtlinienparameter können abweichen)</th>
    <th>Beschreibung</th>
    <th>Eingeführt</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Mobilität aktivieren</p>
    <p>Parametername: <code>EnableMobility</code></p>
    <p>Gültigkeitsbereich: Global/Website/Benutzer</p></td>
    <td><p>Verwaltungseinstellung, um Benutzer, die Lync Mobile installiert haben, in einem bestimmten Gültigkeitsbereich zu steuern. Wenn diese Richtlinie auf &quot;False&quot; gesetzt ist, kann der Benutzer sich nicht am Client anmelden.</p>
    <p>Die Standardeinstellung ist &quot;True&quot;.</p></td>
    <td><p>Kumulatives Update für Lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Externe Anrufe ermöglichen</p>
    <p>Parametername: <code>EnableOutsideVoice</code></p>
    <p>Gültigkeitsbereich: Global/Website/Benutzer</p></td>
    <td><p>Hiermit wird die Fähigkeit eines Benutzers gesteuert, das Feature &quot;Geschäftlich anrufen&quot; zu verwenden. Mit diesem Feature können Benutzer unter Verwendung der geschäftlichen Telefonnummer anstelle der Mobiltelefonnummer Anrufe tätigen und entgegennehmen. Wenn dieses Feature auf &quot;False&quot; gesetzt ist, kann der Benutzer auf seinem Mobiltelefon nicht die geschäftliche Telefonnummer verwenden, um Anrufe zu tätigen oder entgegenzunehmen.</p>
    <p>Die Standardeinstellung ist &quot;True&quot;.</p></td>
    <td><p>Kumulatives Update für Lync Server 2010: November 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>IP-Audio und -Video aktivieren</p>
    <p>Parametername: <code>EnableIPAudioVideo</code></p>
    <p>Gültigkeitsbereich: Global/Website/Benutzer</p></td>
    <td><p>Hiermit wird gesteuert, ob ein Benutzer VoIP verwenden kann, um von seinem mobilen Gerät aus Sprach- oder Videoanrufe zu tätigen oder zu empfangen. Wenn dieser Parameter auf &quot;False&quot; gesetzt ist, kann der Benutzer keine VoIP- oder Videoanrufe auf seinem mobilen Gerät tätigen oder entgegennehmen.</p>
    <p>Die Standardeinstellung ist &quot;True&quot;.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Wi-Fi für IP-Audio erforderlich</p>
    <p>Parametername : <code>RequireWiFiForIPAudio</code></p>
    <p>Gültigkeitsbereich: Global/Website/Benutzer</p></td>
    <td><p>Mit dieser Einstellung wird definiert, ob der Client VoIP-Anrufe über das WLAN-Netzwerk anstatt über das Mobilfunknetzwerk tätigen oder entgegennehmen muss. Wenn diese Einstellung auf &quot;True&quot; gesetzt ist, kann der Benutzer VoIP-Anrufe nur tätigen und empfangen, wenn wenn er mit einem WLAN-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist &quot;False&quot;.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Wi-Fi für IP-Video erforderlich</p>
    <p>Parametername: <code>RequireWiFiForIPVideo</code></p>
    <p>Gültigkeitsbereich: Global/Website/Benutzer</p></td>
    <td><p>Mit dieser Einstellung wird definiert, ob der Client Videoanrufe über das WLAN-Netzwerk anstatt über das Mobilfunknetzwerk tätigen oder entgegennehmen muss. Wenn diese Einstellung auf &quot;True&quot; gesetzt ist, kann der Benutzer Videoanrufe nur tätigen und empfangen, wenn wenn er mit einem WLAN-Netzwerk verbunden ist.</p>
    <p>Die Standardeinstellung ist &quot;False&quot;.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Eine Beschreibung der Richtlinieneinstellungen, die Sie konfigurieren können, und Informationen zur Verwaltung dieser Richtlinien finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy) und [Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Sollen Benutzer, die nicht für Enterprise-VoID aktiviert sind, an Konferenzen teilnehmen können, indem Sie auf den entsprechenden Teilnahmelink klicken?**
    
    Damit Benutzer auf die Mobilitätsfeatures und das Feature "Geschäftlich anrufen" zugreifen können, müssen Sie für Enterprise-VoIP aktiviert sein. Benutzer, die nicht für Enterprise-VoIP aktiviert sind, können jedoch an Konferenzen teilnehmen, indem Sie auf ihrem mobilen Gerät auf den entsprechenden Link klicken, sofern Sie diesen Benutzern eine entsprechende VoIP-Richtlinie zugewiesen haben. Sie können diesen Benutzern entweder eine bestimmte VoIP-Richtlinie zuweisen oder sicherstellen, dass eine globale Richtlinie oder eine Richtlinie auf Standortebene vorhanden ist, die für diese Benutzer gültig ist. Die zugewiesene VoIP-Richtlinie muss über PSTN-Verwendungseinträge und -Routen verfügen, die die Bereiche definieren, in die Benutzer hinauswählen können, um an einer Konferenz teilzunehmen. Ausführliche Informationen zum Festlegen der VoIP-Richtlinie, PSTN-Verwendungseinträge und -Routen finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    

    > [!NOTE]
    > Mobile Benutzer, die den Teilnahmelink verwenden möchten, benötigen eine VoIP-Richtlinie sowie die dazugehörigen PSTN-Verwendungseinträge und VoIP-Routen, da durch das Klicken auf diesen Link ein ausgehender Anruf von Lync Server 2013 initiiert wird.



## Siehe auch

#### Konzepte

[Technische Anforderungen für die Mobilität in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  

#### Weitere Ressourcen

[Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

