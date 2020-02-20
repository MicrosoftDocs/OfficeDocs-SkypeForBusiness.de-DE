---
title: 'Lync Server 2013: Einrichten des lync-Verbund'
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
ms.openlocfilehash: ce06c67e3c7e90f8e1170edb82e515f66be7a2ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-lync-federation-in-lync-server-2013"></a>Einrichten von lync Federation in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-03-27_

Wenn Sie bereits einen oder mehrere Edgeserver bereitgestellt haben, ist das Hinzufügen der Features für Partnerverbundszenarien ganz einfach. Wenn Sie noch keine Edgeserver eingerichtet haben, müssen Sie diese Einrichtung zuerst durchführen. Ausführliche Informationen finden Sie unter: [Planen des Zugriffs durch externe Benutzer in lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> Wenn Sie eine beliebige Kombination von XMPP-Partnerverbund, Lync-Partnerverbund oder Konnektivität mit öffentlichen Chatdiensten einrichten möchten, können Sie diese Partnerverbundtypen gleichzeitig oder nacheinander bereitstellen. Wenn Sie die Optionen über den Topologie-Generator und die Lync Server-Verwaltungsshell konfigurieren und dann den Bereitstellungs-Assistenten auf den Edgeserver ausführen, nachdem Sie die Optionen für einen, zwei oder drei Partnerverbundtypen konfiguriert haben, können Sie die Anzahl der erforderlichen Schritte reduzieren.



</div>

<div>

## <a name="setting-up-lync-federation-in-topology-builder-and-the-deployment-wizard"></a>Einrichten des Lync-Partnerverbunds im Topologie-Generator und im Bereitstellungs-Assistenten

1.  Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie die Edgepools, und klicken Sie dann mit der rechten Maustaste auf Ihren Edgeserver oder Edgeserverpool. Wählen Sie Eigenschaften bearbeiten aus.

2.  Klicken Sie in "Eigenschaften bearbeiten" unter "Allgemein" auf "Partnerverbund für diesen Edgepool aktivieren" (Port 5061). Klicken Sie auf "OK".

3.  Klicken Sie auf "Aktion", wählen Sie "Topologie", und wählen Sie "Veröffentlichen" aus. Wenn Sie unter "Topologie veröffentlichen" dazu aufgefordert werden, klicken Sie auf "Weiter". Wenn die Veröffentlichung abgeschlossen ist, klicken Sie auf "Fertig stellen".

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf "Lync Server-System installieren oder aktualisieren", und klicken Sie anschließend auf "Lync Server-Komponenten einrichten oder entfernen". Klicken Sie auf "Erneut ausführen".

5.  Klicken Sie unter Lync Server-Komponenten einrichten auf Weiter. Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf Protokoll anzeigen, um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf Fertig stellen, um die Bereitstellung abzuschließen.
    
    <div>
    

    > [!IMPORTANT]  
    > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzer öffentlicher Sofortnachrichtendienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.

    
    </div>

</div>

<div>

## <a name="configuring-federation-with-partners"></a>Konfigurieren des Verbunds mit Partnern

1.  Zum Einrichten eines erfolgreichen Verbunds mit einem anderen Microsoft lync Server 2013, lync Server 2010, Office Communications Server 2007 R2 oder Office Communicator 2007 wählen Sie den Typ des Verbunds in der folgenden Tabelle aus und definieren DNS-SRV-Einträge, DNS-Host (a oder AAAA für IPv6) und Konfigurieren von Richtlinien für den Typ des Verbunds:
    
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Partnerverbundtyp</th>
    <th>DNS-Einträge</th>
    <th>Richtliniendefinition</th>
    <th>Hinweise</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Ermittelte Partnerdomäne</p></td>
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, bei dem der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist. &lt;externer Domänenname&gt; – der FQDN ihrer Zugriffs-Edgedienst. Weitere Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</a></p></li>
    </ul></td>
    <td><p>In vorherigen Versionen wurde dieser Partnerverbundtyp als <strong>Offener erweiterter Partnerverbund</strong> definiert. Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp erforderlich und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können.</p></td>
    </tr>
    <tr class="even">
    <td><p>Zulässige Partnerdomäne</p></td>
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format _sipfederationtls. _tcp. &lt;externer Domänenname&gt;, bei dem der Portwert für den SRV-Eintrag TCP 5061 ist und der Host, der <strong>diesen Dienst anbietet</strong> , als SIP definiert ist. &lt;externer Domänenname&gt; – der FQDN ihrer Zugriffs-Edgedienst. Weitere Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</a> .</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></li>
    </ul></td>
    <td><p>In früheren Versionen wurde dieser Typ von Verbund als <strong>Erweiterter Verbund</strong>bezeichnet. Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp optional und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können. In diesem Fall handelt es sich natürlich um einen <strong>Offenen erweiterten Partnerverbund</strong> oder eine <strong>Ermittelte Partnerdomäne</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Zulässiger Partnerserver</p></td>
    <td><p>Konfigurieren Sie den SIP-Domänennamen und den Partner Edgeserver FQDN als Verbundpartner in Richtlinien</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Konfigurieren der Unterstützung für blockierte externe Domänen in lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Dieser Partnerverbundtyp ist die Definition einer 1:1-Beziehung und lässt die Ermittlung anderer Verbundpartner nicht zu. Jeder Verbundpartner wird explizit konfiguriert. In vorherigen Versionen wurde dies als <strong>Direkter Partnerverbund</strong> bezeichnet.</p></td>
    </tr>
    <tr class="even">
    <td><p>Hostinganbieter und öffentlicher Chatanbieter</p></td>
    <td><p>Für diesen Partnerverbundtyp sind keine besonderen DNS-Anforderungen definiert.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Dieser Partnerverbundtyp definiert Dienste und Hostinganbieter, die Sie für Ihre Benutzer konfigurieren möchten. Zu den typischen Verwendungen gehört die Konfiguration für öffentliche Chatanbieter wie Windows Live Messenger, Yahoo! und AOL sowie Hosting-Anbieter wie lync Online und Office 365</p>
    <div>

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definieren und Konfigurieren von erforderlichen DNS-Hosteinträgen (A oder AAAA für IPv6) und DNS-SRV-Einträgen

3.  Definieren und konfigurieren Sie alle Richtlinien mithilfe der lync Server-Systemsteuerung oder mithilfe der lync Server-Verwaltungsshell und der entsprechenden Cmdlets. Ausführliche Informationen zu den lync Server-Verwaltungsshell-Cmdlets finden Sie unter [Verbund-und externer Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/)
    
    <div>
    

    > [!NOTE]  
    > Lync Room System (LRS) zeigt keine Verknüpfungsschaltfläche für Besprechungen an, die von Organisatoren in Partner-lync-Partnern gesendet werden. Damit ein Link zum besprechungsbeitritt auf dem LRS angezeigt wird, muss die sendende Organisation TNEF mithilfe des folgenden Cmdlets aktivieren:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Beachten Sie, dass dies nicht LRS-spezifisch ist. Outlook und lync würden auch in diesem Fall keine Verknüpfungs Verknüpfungen anzeigen, da MAPI-Eigenschaften nicht transportiert werden, aber im Fall von Outlook kann der Benutzer die Besprechungseinladung öffnen und auf die Besprechungs-URL klicken. Wenn TNEFEnabled auf true festgelegt ist Exchange 2013 keine MAPI-Eigenschaften einschließlich OnlineMeetingExternalLink, und die Schaltfläche beitreten wird in der Erinnerung angezeigt.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

