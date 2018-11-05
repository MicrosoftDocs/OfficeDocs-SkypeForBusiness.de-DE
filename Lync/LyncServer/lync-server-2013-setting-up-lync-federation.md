---
title: 'Lync Server 2013: Einrichten eines Lync-Partnerverbunds'
TOCTitle: Einrichten eines Lync-Partnerverbunds
ms:assetid: 374ddc43-26f9-499d-be68-a5158adfa49c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204800(v=OCS.15)
ms:contentKeyID: 49293666
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten eines Lync-Partnerverbunds in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wenn Sie bereits einen oder mehrere Edgeserver bereitgestellt haben, ist das Hinzufügen der Features für Partnerverbundszenarien ganz einfach. Wenn Sie noch keine Edgeserver eingerichtet haben, müssen Sie diese Einrichtung zuerst durchführen. Ausführliche Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation und [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.


> [!NOTE]
> Wenn Sie eine beliebige Kombination von XMPP-Partnerverbund, Lync-Partnerverbund oder Konnektivität mit öffentlichen Chatdiensten einrichten möchten, können Sie diese Partnerverbundtypen gleichzeitig oder nacheinander bereitstellen. Wenn Sie die Optionen über den Topologie-Generator und die Lync Server-Verwaltungsshell konfigurieren und dann den Bereitstellungs-Assistenten auf den Edgeserver ausführen, nachdem Sie die Optionen für einen, zwei oder drei Partnerverbundtypen konfiguriert haben, können Sie die Anzahl der erforderlichen Schritte reduzieren.



## Einrichten des Lync-Partnerverbunds im Topologie-Generator und im Bereitstellungs-Assistenten

1.  Öffnen Sie den Topologie-Generator auf einem Front-End-Server. Erweitern Sie die Edgepools, und klicken Sie dann mit der rechten Maustaste auf Ihren Edgeserver oder Edgeserverpool. Wählen Sie **Eigenschaften bearbeiten** aus.

2.  Wählen Sie im Dialogfeld **Eigenschaften bearbeiten** unter **Allgemein** die Option **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus. Klicken Sie auf **OK** .

3.  Klicken Sie auf **Aktion** , und wählen Sie **Topologie** und dann **Veröffentlichen** aus. Wenn Sie gefragt werden, ob Sie die Topologie veröffentlichen möchten, klicken Sie auf **Weiter** . Klicken Sie nach Abschluss der Veröffentlichung auf **Fertig stellen** .

4.  Öffnen Sie auf dem Edgeserver den Lync Server-Bereitstellungs-Assistenten. Klicken Sie auf **Lync Server-System installieren oder aktualisieren** , und klicken Sie dann auf **Lync Server-Komponenten einrichten oder entfernen** . Klicken Sie auf **Erneut ausführen** .

5.  Klicken Sie unter **Lync Server-Komponenten einrichten** auf **Weiter** . Auf dem Zusammenfassungsbild werden die ausgeführten Aktionen angezeigt. Klicken Sie nach Abschluss der Bereitstellung auf **Protokoll anzeigen** , um die verfügbaren Protokolldateien anzuzeigen. Klicken Sie auf **Fertig stellen** , um die Bereitstellung abzuschließen.
    

    > [!IMPORTANT]
    > Sie können diese Option auswählen, es kann jedoch nur ein Edgepool oder Edgeserver in Ihrer Organisation extern für den Partnerverbund veröffentlicht werden. Der Zugriff durch Partnerbenutzer, einschließlich Benutzer öffentlicher Chatdienste, erfolgt stets über denselben Edgepool oder einzelnen Edgeserver. Wenn Ihre Bereitstellung beispielsweise je einen Edgepool oder einzelnen Edgeserver in New York und in London umfasst und Sie die Unterstützung des Partnerverbunds für den Edgepool oder einzelnen Edgeserver in New York aktivieren, erfolgt der Signaldatenverkehr für Partnerbenutzer über den Edgepool oder einzelnen Edgeserver in New York. Dies gilt auch für die Kommunikation mit Benutzern in London, wenngleich ein interner Benutzer in London, der einen Partnerbenutzer in London anruft, für den A/V-Datenverkehr den Pool oder Edgeserver in London verwendet.



## Konfigurieren des Verbunds mit Partnern

1.  Zum Einrichten eines erfolgreichen Verbunds mit einem anderen Microsoft Lync Server 2013-, Lync Server 2010-, Office Communications Server 2007 R2- oder Office Communicator 2007-Partner wählen Sie in der folgenden Tabelle den Typ des Partnerverbunds aus, und definieren Sie DNS-SRV-Einträge und DNS-Hosteinträge (A oder AAAA für IPv6). Konfigurieren Sie dann entsprechende Richtlinien für den Typ des Partnerverbunds:
    
    
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
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format &quot;_sipfederationtls._tcp.&lt;externer Domänenname&gt;&quot;. Dabei ist der Portwert für den SRV-Eintrag TCP 5061, und der <strong>Host, der diesen Dienst anbietet</strong> ist definiert als &quot;sip. &lt;externer Domänenname&gt;&quot; - der FQDN des Zugriffs-Edgediensts. Ausführliche Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013</a>.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>In vorherigen Versionen wurde dieser Partnerverbundtyp als <strong>Offener erweiterter Partnerverbund</strong> definiert. Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp erforderlich und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können.</p></td>
    </tr>
    <tr class="even">
    <td><p>Zulässige Partnerdomäne</p></td>
    <td><p>Konfigurieren Sie den SRV-Eintrag im Format &quot;_sipfederationtls._tcp.&lt;externer Domänenname&gt;&quot;. Dabei ist der Portwert für den SRV-Eintrag TCP 5061, und der <strong>Host, der diesen Dienst anbietet</strong> ist definiert als &quot;sip. &lt;externer Domänenname&gt;&quot; - der FQDN des Zugriffs-Edgediensts. Ausführliche Informationen zum Erstellen des SRV-Eintrags finden Sie unter <a href="lync-server-2013-configure-dns-for-edge-support.md">Konfigurieren von DNS für die Edgeunterstützung in Lync Server 2013</a>.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>In vorherigen Versionen wurde dieser Partnerverbundtyp als <strong>Erweiterter Partnerverbund</strong> bezeichnet. Das Erstellen des SRV-Eintrags ist für diesen Partnerverbundtyp optional und dient dazu, dass andere Partner Ihren Partnerverbund ermitteln können. In diesem Fall handelt es sich natürlich um einen <strong>Offenen erweiterten Partnerverbund</strong> oder eine <strong>Ermittelte Partnerdomäne</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p>Zulässiger Partnerserver</p></td>
    <td><p>Konfigurieren des SIP-Domänennamens und des Edgeserver-FQDN des Partners als Verbundpartner in Richtlinien</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-allowed-external-domains.md">Konfigurieren der Unterstützung für zulässige externe Domänen in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-configure-support-for-blocked-external-domains.md">Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Dieser Partnerverbundtyp ist die Definition einer 1:1-Beziehung und lässt die Ermittlung anderer Verbundpartner nicht zu. Jeder Verbundpartner wird explizit konfiguriert. In vorherigen Versionen wurde dies als <strong>Direkter Partnerverbund</strong> bezeichnet.</p></td>
    </tr>
    <tr class="even">
    <td><p>Hostinganbieter und öffentlicher Chatanbieter</p></td>
    <td><p>Für diesen Partnerverbundtyp sind keine besonderen DNS-Anforderungen definiert.</p></td>
    <td><ul>
    <li><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</a></p></li>
    <li><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013</a></p></li>
    </ul></td>
    <td><p>Dieser Partnerverbundtyp definiert Dienste und Hostinganbieter, die Sie für Ihre Benutzer konfigurieren möchten. Zu den typischen Verwendungen gehört die Konfiguration für öffentliche Chatanbieter wie Windows Live Messenger, Yahoo! und AOL sowie für Hostinganbieter, z. B. Lync Online und Office 365.</p>
    <div>

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
    > <LI>
    > <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
    > <LI>
    > <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>


    </div></td>
    </tr>
    </tbody>
    </table>


2.  Definieren und Konfigurieren von erforderlichen DNS-Hosteinträgen (A oder AAAA für IPv6) und DNS-SRV-Einträgen

3.  Definieren und konfigurieren Sie Richtlinien mithilfe der Lync Server-Systemsteuerung oder der Lync Server-Verwaltungsshell und den entsprechenden Cmdlets. Ausführliche Informationen zu den Lync Server-Verwaltungsshell-Cmdlets finden Sie unter [Cmdlets für Partnerverbund und externen Zugriff in Lync Server 2013](https://docs.microsoft.com/en-us/powershell/module/skype/).
    

    > [!NOTE]
    > In Lync Room System (LRS) wird die Schaltfläche "Teilnehmen" nicht für Besprechungen angezeigt, die von Organisatoren in Lync-Verbundpartnern gesendet werden. Damit ein Link für die Besprechungsteilnahme in LRS angezeigt wird, muss die sendende Organisation TNEF über das folgende Cmdlet aktivieren:<BR><BR><CODE>New-RemoteDomain -DomainName Contoso.com -Name Contoso</CODE><BR><CODE>Set-RemoteDomain -Identity Contoso -TNEFEnabled $true</CODE><BR>Beachten Sie, dass dies nicht LRS-spezifisch ist. In Outlook und Lync würden in diesem Fall ebenfalls keine Links zum Teilnehmen angezeigt werden, da MAPI-Eigenschaften nicht transportiert werden. Im Fall von Outlook kann der Benutzer aber die Besprechungseinladung öffnen und auf die Besprechungs-URL klicken. Wenn TNEFEnabled auf "True" gesetzt ist, entfernt Exchange 2013 MAPI-Eigenschaften einschließlich OnlineMeetingExternalLink nicht und die Schaltfläche "Teilnehmen" wird in der Erinnerung angezeigt.



## Siehe auch

#### Weitere Ressourcen

[Planen für SIP-, XMPP-Partnerverbund und öffentliche Chats in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)  
[Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)

