---
title: 'Lync Server 2013: Einrichten eines Lync-Partnerverbunds'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Lync federation
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204800(v=OCS.15)
ms:contentKeyID: 48183822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7df0dd85bac0aa3053fb6a3496d6a13fa1f4a85e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764601"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Einrichten eines Lync-Partnerverbunds in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-03-27_

Wenn Sie bereits Edgeserver oder Server bereitgestellt haben, ist das Hinzufügen der Features für Verbundszenarien direkt. Wenn Sie keine Edgeserver eingerichtet haben, müssen Sie dies zunächst tun. Ausführliche Informationen finden Sie unter: [Planen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs externer Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie beabsichtigen, eine beliebige Kombination aus XMPP-Föderation, lync-Föderation oder öffentlicher Instant Messaging-Konnektivität einzurichten, können Sie Sie gleichzeitig oder einzeln bereitstellen. Wenn Sie die Optionen über den Topologie-Generator und die lync Server-Verwaltungsshell konfigurieren und dann den Bereitstellungs-Assistenten auf dem Edgeserver ausführen, nachdem Sie die Optionen für einen, zwei oder alle drei Föderations Typen konfiguriert haben, können Sie die Anzahl der erforderlichen Schritte reduzieren.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Einrichten von lync Federation im Topologie-Generator und im Bereitstellungs-Assistenten

1.  Öffnen Sie auf einem Front-End-Server den Topologie-Generator. Erweitern Sie Edge-Pools, und klicken Sie dann mit der rechten Maustaste auf den Edgeserver oder den Edge-Serverpool. Wählen Sie Eigenschaften bearbeiten aus.

2.  Wählen Sie in Eigenschaften bearbeiten unter Allgemein die Option Föderation für diesen Edge-Pool aktivieren (Port 5061) aus. Klicken Sie auf OK.

3.  Klicken Sie auf Aktion, wählen Sie Topologie aus, und wählen Sie veröffentlichen aus. Wenn Sie dazu aufgefordert werden, die Topologie zu veröffentlichen, klicken Sie auf Weiter. Wenn der Veröffentlichungsvorgang abgeschlossen ist, klicken Sie auf Fertig stellen.

4.  Öffnen Sie auf dem Edgeserver den lync Server-Bereitstellungs-Assistenten. Klicken Sie auf lync Server System installieren oder aktualisieren und dann auf lync Server-Komponenten einrichten oder entfernen. Klicken Sie erneut auf ausführen.

5.  Klicken Sie bei der Installation von lync Server-Komponenten auf Weiter. Auf dem Zusammenfassungsbildschirm werden die Aktionen während der Ausführung angezeigt. Nachdem die Bereitstellung abgeschlossen ist, klicken Sie auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können diese Option auswählen, aber nur ein Edge-Pool oder Edgeserver in Ihrer Organisation kann extern für den Verbund veröffentlicht werden. Der gesamte Zugriff von Verbundbenutzern, einschließlich öffentlicher Chat-Benutzer, durchlaufen denselben Edge-Pool oder Single Edge-Server. Wenn Ihre Bereitstellung beispielsweise einen Edge-Pool oder einen einzelnen Edgeserver umfasst, der in New York bereitgestellt und in London bereitgestellt wurde, und Sie die Unterstützung der Föderation auf dem New York Edge-Pool oder einem Single Edge-Server aktivieren, wird der Signal Verkehr für verbundene Benutzer durch das New York durchlaufen. Edge-Pool oder Single Edge-Server. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Konfigurieren des Verbunds mit Partnern

1.  Wenn Sie einen erfolgreichen Verbund mit einem anderen Microsoft lync Server 2013, lync Server 2010, Office Communications Server 2007 R2 oder Office Communicator 2007 einrichten möchten, wählen Sie den Typ des Verbandes aus der folgenden Tabelle aus, und definieren Sie DNS-SRV-Einträge, DNS-Host (a oder AAAA für IPv6) und Konfigurieren von Richtlinien, die für den Typ des Verbandes gelten:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Föderations</th>
    <th>DNS-Einträge</th>
    <th>Richtlinien Definition</th>
    <th>Hinweise</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Erkannte Partner Domäne</p></td>
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, wobei der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist. &lt;externer Domänenname&gt; – der FQDN Ihres Access Edge-Diensts. Details zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Frühere Versionen verweisen auf diesen Typ von Federation als <strong>Open Enhanced Federation</strong>. Die Erstellung des SRV-Eintrags ist für diesen Föderations erforderlich und ermöglicht es anderen Partnern, ihre Föderation zu entdecken.</p></td>
    </tr>
    <tr class="even">
    <td><p>Zulässige Partner Domäne</p></td>
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, wobei der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist. &lt;externer Domänenname&gt; – der FQDN Ihres Access Edge-Diensts. Details zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>In früheren Versionen wurde dieser Typ von Federation als <strong>Enhanced Federation</strong>bezeichnet. Die Erstellung des SRV-Eintrags ist für diesen Föderations optional und ermöglicht es anderen Partnern, ihre Föderation zu entdecken. Selbstverständlich handelt es sich hierbei um eine <strong>offene erweiterte Föderation</strong>oder um eine <strong>erkannte Partner Domäne</strong> .</p></td>
    </tr>
    <tr class="odd">
    <td><p>Zulässiger Partner Server</p></td>
    <td><p>Konfigurieren des SIP-Domänennamens und des Partner-Edgeserver-FQDN als Verbundpartner in Richtlinien</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Bei diesem Verbundtyp handelt es sich um die Definition einer 1:1-Beziehung, die keine Ermittlung anderer Verbundpartner ermöglicht. Jeder Föderationspartner wird explizit konfiguriert. In früheren Versionen wurde dies als <strong>direkte Föderation</strong> bezeichnet.</p></td>
    </tr>
    <tr class="even">
    <td><p>Hostinganbieter und Anbieter von öffentlichen Chats</p></td>
    <td><p>Für diese Art von Föderation sind keine spezifischen DNS-Anforderungen definiert.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Dieser Verbundtyp definiert Dienste und Hosting-Anbieter, die Sie für Ihre Benutzer konfigurieren möchten. Typische Verwendungen sind die Konfiguration für öffentliche Chat-Anbieter wie Windows Live Messenger, Yahoo! und AOL sowie Hosting-Anbieter wie lync Online und Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definieren und Konfigurieren aller erforderlichen DNS-Hosts (A oder AAAA für IPv6) und DNS-SRV-Einträge

3.  Definieren und konfigurieren Sie alle Richtlinien mithilfe der lync Server-Systemsteuerung oder mithilfe der lync Server-Verwaltungsshell und der entsprechenden Cmdlets. Ausführliche Informationen zu den Cmdlets der lync Server-Verwaltungsshell finden Sie unter [Föderations-und externe Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) zeigt die Schaltfläche "Verknüpfung" nicht für Besprechungen an, die von Organisatoren in verbundenen lync-Partnern gesendet werden. Damit ein Besprechungs Verknüpfungs Link auf LRS angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Cmdlets aktivieren:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Beachten Sie, dass dies nicht LRS-spezifisch ist. Outlook und lync würden in diesem Fall auch keine Verknüpfungs Verknüpfungen anzeigen, da MAPI-Eigenschaften nicht transportiert werden, aber im Fall von Outlook kann der Benutzer die Besprechungseinladung öffnen und auf die Besprechungs-URL klicken. Wenn TNEFEnabled auf true festgelegt ist, werden in Exchange 2013 keine MAPI-Eigenschaften wie OnlineMeetingExternalLink und die Schaltfläche "beitreten" auf der Erinnerung angezeigt.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

