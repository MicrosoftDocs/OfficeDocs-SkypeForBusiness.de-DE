---
title: 'Lync Server 2013: Planen von Lync Server-Hybridbereitstellungen'
TOCTitle: Planen von Lync Server-Hybridbereitstellungen
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205403(v=OCS.15)
ms:contentKeyID: 49295960
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von Lync Server 2013-Hybridbereitstellungen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bei der Planung einer Hybridbereitstellung sollten Sie die Anforderungen im Hinblick auf die Benutzer und Netzwerkinfrastruktur berücksichtigen.

## Infrastrukturanforderungen

Zum Implementieren und Konfigurieren einer Lync Server 2013-Hybridbereitstellung muss in der Umgebung Folgendes verfügbar sein:

  - Ein Office 365-Mandant, auf dem Lync Online aktiviert ist.

  - Ein Server für Active Directory-Verbunddienste (AD FS), der entweder lokal oder über Microsoft Azure bereitgestellt wird. Weitere Informationen zu AD FS finden Sie unter [Active Directory-Verbunddienste (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=393795) oder [Konfigurieren von Active Directory-Verbunddiensten für das Windows Azure Pack](http://go.microsoft.com/fwlink/p/?linkid=522475).

  - Eine lokale Bereitstellung von Lync Server 2013 oder Lync Server 2010 mit kumulativen Updates für Lync Server 2010: März 2013 oder höher.

  - Lync Server 2013 Verwaltungstools.

  - Verzeichnissynchronisierung. Details zur Verzeichnissynchronisierung finden Sie unter [Hybrid-Identitätsverwaltung](http://go.microsoft.com/fwlink/p/?linkid=231010).

## Unterstützung des Lync-Clients

Es gibt einige Unterschiede in Bezug auf die Features, die von Lync-Clients unterstützt werden, und die Features, die in lokalen und Onlineumgebungen verfügbar sind. Bevor Sie entscheiden, wo die Benutzer in Ihrer Organisation verwaltet werden sollen, können Sie sich über die Clientunterstützung für die verschiedenen Konfigurationen von Lync Server informieren. Die folgenden Clients werden mit Skype for Business Online in einer Lync-Hybridbereitstellung unterstützt:

  - Lync 2010

  - Lync 2013

  - Windows Store-App für Lync

  - Lync Web App

  - Lync Mobile

  - Lync für Mac 2011

  - Lync Room System

  - Lync Basic 2013

Ausführliche Informationen zur Clientunterstützung finden Sie in den folgenden Themen:

  - [Clients für Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Vergleichstabellen für mobile Clients für Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

## Anforderungen im Hinblick auf die Topologie

Zum Konfigurieren einer Hybridbereitstellung aus Lync Server 2013 und Skype for Business Online müssen Sie über eine der folgenden unterstützten Topologien verfügen:

  - Microsoft Office Communications Server 2007 R2 mit lokaler Lync Server 2013-Bereitstellung. Auf dem Partnerverbund- Edgeserver in Lync Server 2013 und auf dem nächsten Hopserver aus dem Partnerverbund- Edgeserver muss Lync Server 2013 ausgeführt werden. Zudem muss ein zentraler Verwaltungsspeicher bereitgestellt werden. Der Edgeserver und der Pool müssen lokal bereitgestellt werden.
    

    > [!IMPORTANT]
    > Obwohl diese Topologie unterstützt wird, sind einige Funktionen möglicherweise eingeschränkt. Beispielsweise funktionieren Präsenzinformationen zwischen Microsoft Lync Online-Benutzern und lokalen Office Communications Server 2007 R2-Benutzern möglicherweise nicht wie erwartet.



  - Microsoft Lync Server 2010 mit angewendeten kumulativen Updates für Lync Server 2010: März 2013 (oder späteres Update) und lokal installierten Lync Server 2013-Verwaltungstools. Auf dem Partnerverbund-Edgeserver und dem nächsten Hopserver aus dem Partnerverbund-Edgeserver muss Microsoft Lync Server 2010 mit angewendeten kumulativen Updates von März 2013 (oder später) oder Lync Server 2013 ausgeführt werden.
    

    > [!IMPORTANT]
    > Die Lync Server 2013-Verwaltungstools sollten auf einem separaten Server installiert sein, der Verbindungszugriff auf die vorhandene Lync Server 2010-Bereitstellung hat. Das Move-CsUser-cmdlet zum Verschieben von Benutzern aus Ihrer lokalen Bereitstellung nach Lync Online muss von den Lync Server 2013-Verwaltungstools, die mit Ihrer lokalen Bereitstellung verbunden sind, aus ausgeführt werden.



  - Eine Lync Server 2013-Bereitstellung mit allen Servern, auf denen Lync Server 2013 ausgeführt wird.

Weitere Informationen zu den unterstützten Topologien finden Sie unter [Unterstützte Topologien in Lync Server 2013](lync-server-2013-supported-topologies.md) und [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).

Informationen zur Problembehandlung in Hybridbereitstellungen und zum Herstellen von Verbindungen der PowerShell mit Lync Online finden Sie unter [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).

## Anforderungen in Bezug auf die Listen der zugelassenen und blockierten Domänen für den Partnerverbund

Die Liste der zugelassenen Domänen enthält Domänen, für die ein Partner-Edge-FQDN (vollqualifizierter Domänenname) konfiguriert ist. Diese werden mitunter als *zulässige Partnerserver* oder *direkte Verbundpartner* bezeichnet. Sie sollten mit dem Unterschied zwischen einem öffentlichen Partnerverbund und einem geschlossenen Partnerverbund vertraut sein, der in lokalen Bereitstellungen als *Partnerermittlung* bzw. *Liste der zulässigen Partnerdomänen* bezeichnet wird.

Die folgenden Anforderungen müssen erfüllt sein, um eine Hybridbereitstellung erfolgreich zu konfigurieren:

  - Der Domänenabgleich muss für die lokale Bereitstellung und den Office 365-Mandanten identisch konfiguriert sein. Wenn die Partnerermittlung für die lokale Bereitstellung aktiviert ist, muss der öffentliche Partnerverbund für den Onlinemandaten konfiguriert sein. Wenn die Partnerermittlung nicht aktiviert ist, muss für den Onlinemandanten der geschlossene Partnerverbund konfiguriert sein.

  - Die Liste der blockierten Domänen in der lokalen Bereitstellung muss genau mit der Liste der blockierten Domänen für den Onlinemandanten übereinstimmen.

  - Die Liste der zugelassenen Domänen in der lokalen Bereitstellung muss genau mit der Liste der zugelassenen Domänen für den Onlinemandanten übereinstimmen.

  - Der Partnerverbund muss für die externe Kommunikation für den Onlinemandanten aktiviert sein, der mithilfe der Lync Online-Systemsteuerung konfiguriert wird.

## DNS-Einstellungen

Beim Erstellen von DNS-SRV-Einträgen für Hybridbereitstellungen sollten die Einträge "\_sipfederationtls.\_tcp.\<domäne\>" und "\_sip.\_tls.\<domäne\>" auf den lokalen Zugriffsproxy zeigen.

## Überlegungen zu Firewalls

Die Computer in Ihrem Netzwerk müssen Standard-Internet-DNS-Lookups ausführen können. Wenn diese Computer Standard-Internetwebsites erreichen können, erfüllt Ihr Netzwerk diese Anforderung.

Abhängig vom Standort des Microsoft Online Services-Rechenzentrums müssen Sie auch Ihre Netzwerkfirewallgeräte so konfigurieren, dass Verbindungen basierend auf Platzhalterdomänennamen akzeptiert werden (z. B. der gesamte Datenverkehr von "\*.outlook.com"). Wenn die Firewalls Ihrer Organisation Konfigurationen mit Platzhalternamen nicht unterstützen, müssen Sie die IP-Adressbereiche, die Sie zulassen möchten, und die angegebenen Ports manuell festlegen.

Informationen finden Sie im Hilfethema [URLs und IP-Adressbereiche für Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

## Port- und Firewallanforderungen

Sie müssen nicht nur die Portanforderungen für die interne Lync Server 2013-Kommunikation berücksichtigen, sondern auch die folgenden Ports konfigurieren.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll/Port</th>
<th>Anwendungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Active Directory-Verbunddienste (Active Directory Federation Services, AD&amp;nbsp;FS) (Verbundserverrolle)</p>
<p>Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Grundlegendes zu AD FS-Rollendiensten</a>.</p></li>
<li><p>Active Directory-Verbunddienste (Proxyserverrolle)</p></li>
<li><p>Microsoft Online Services-Portal</p></li>
<li><p>Unternehmensportal</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync-Client (Kommunikation mit Lync Online vom lokalen Lync Server aus)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 und 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Microsoft Online Services-Verzeichnissynchronisierungstool</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports auf dem Edgeserver</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Datenfreigabesitzungen</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Audio-, Video- und Anwendungsfreigabesitzungen</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Audio- und Videositzungen</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Geöffnete ausgehende Ports für Audio- und Videositzungen</p></td>
</tr>
<tr class="even">
<td><p>TCP 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Active Directory-Verbunddienste (Active Directory Federation Services, AD&amp;nbsp;FS) (Verbundserverrolle)</p>
<p>Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Grundlegendes zu AD FS-Rollendiensten</a>.</p></li>
<li><p>Active Directory-Verbunddienste (Proxyserverrolle)</p></li>
<li><p>Microsoft Online Services-Portal</p></li>
<li><p>Unternehmensportal</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync-Client (Kommunikation mit Lync Online vom lokalen Lync Server aus)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 80 und 443</p></td>
<td><p>Geöffnet, eingehend</p>
<ul>
<li><p>Microsoft Online Services-Verzeichnissynchronisierungstool</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 5061</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports auf dem Edgeserver</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/TLS 443</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Datenfreigabesitzungen</p></td>
</tr>
<tr class="even">
<td><p>STUN/TCP 443</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Audio-, Video- und Anwendungsfreigabesitzungen</p></td>
</tr>
<tr class="odd">
<td><p>STUN/UDP 3478</p></td>
<td><p>Geöffnete eingehende/ausgehende Ports für Audio- und Videositzungen</p></td>
</tr>
<tr class="even">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Geöffnete ausgehende Ports für Audio- und Videositzungen</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Wenn Sie einen Verbund mit Partnern benötigen, die Office Communications Server 2007 ausführen, müssen Sie die eingehenden/ausgehenden RTP/UDP- und RTP/TCP-Ports 50000-59999 öffnen. Weitere Informationen zu A/V-Firewallanforderungen finden Sie unter <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013</A>. Weitere Informationen zu Ports und Protokollen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013</A>.



## Benutzerkonten und -daten

In einer Lync Server 2013-Hybridbereitstellung muss jeder Benutzer, den Sie in Lync Online verwalten möchten, zuerst in der lokalen Bereitstellung erstellt werden, damit das Benutzerkonto in Active Directory-Domänendienste erstellt wird. Sie können den Benutzer dann zu Skype for Business Online verschieben, wodurch auch die Kontaktliste des Benutzers verschoben wird.

Wenn Sie Benutzerkonten zwischen Ihrer standortgebundenen und der Lync Online-Bereitstellung mit AD FS und Dirsync synchronisieren, müssen Sie die AD-Konten für alle Lync-Benutzer in Ihrer Organisation zwischen der standortgebundenen und der Onlinebereitstellung von Lync synchronisieren, selbst wenn die Benutzer nicht nach Lync Online migriert werden. Wenn Sie nicht alle Benutzer synchronisieren, funktioniert die Kommunikation zwischen lokalen und Onlinebenutzern in Ihrem Unternehmen möglicherweise nicht erwartungsgemäß.


> [!IMPORTANT]
> Wenn der Benutzer mit dem Onlineportal für Office 365 erstellt wird, wird der Benutzer nicht mit der lokalen Active Directory-Bereitstellung synchronisiert und ist dort nicht vorhanden. Wenn Sie bereits Benutzer in Lync Online erstellt haben und eine Hybridkonfiguration mit einem lokalen Lync Server erstellen möchten, finden Sie entsprechende Informationen unter <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Verschieben von Lync Online-Benutzern zur lokalen Lync-Bereitstellung in Lync Server 2013</A>.



Sie sollten bei der Planung einer Hybridbereitstellung auch die folgenden benutzerbezogenen Aspekte berücksichtigen.

  - **Benutzerkontakte**   Lync Online-Benutzer können maximal 250 Kontakte besitzen. Alle darüber hinausgehenden Kontakte werden aus der Kontraktliste des Benutzers entfernt, wenn das Konto nach Lync Online verschoben wird.

  - **Chat und Anwesenheit**   Benutzerkontaktlisten, Benutzergruppen und Zugriffssteuerungslisten (ACLs) werden mit dem Benutzerkonto migriert.

  - **Konferenzdaten, Besprechungsinhalte und geplante Besprechungen**   Dieser Inhalt wird nicht mit dem Benutzerkonto migriert. Benutzer müssen Besprechungen neu planen, nachdem ihre Konten zu Lync Online migriert wurden.

## Benutzerrichtlinien und Features

  - In einer Lync Server 2013-Hybridumgebung können Benutzer entweder lokal oder online für Chat, VoIP und Besprechungen aktiviert werden. Eine gleichzeitige Aktivierung in einer lokalen Bereitstellung und einer Onlinebereitstellung ist nicht möglich.

  - **Lync Client**    Einige Benutzer benötigen vor der Migration zu Lync Online möglicherweise eine neue Clientversion. Für Office Communications Server 2007 R2 müssen Benutzer vor der Migration zu Lync Online in einen Lync Server 2013-Pool verschoben werden.
    
    Weitere Informationen zum Clientsupport finden Sie unter [Clients für Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) und [Unterstützte Lync-Clients und Netzwerkportkonfigurationen](http://go.microsoft.com/fwlink/p/?linkid=281901) .

  - **Lokale Richtlinien und Konfiguration (nicht benutzerbezogen)**   Für Onlinerichtlinien und lokale Richtlinien ist eine separate Konfiguration erforderlich. Sie können keine globalen Richtlinien festlegen, die für beides gelten.

