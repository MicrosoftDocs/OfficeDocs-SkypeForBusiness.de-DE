---
title: 'Lync Server 2013: Unterstützte Hybridkonfigurationen'
TOCTitle: Unterstützte Hybridkonfigurationen
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945633(v=OCS.15)
ms:contentKeyID: 52056368
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Lync Server 2013-Hybridkonfigurationen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Sie können Lync Server 2013-Bereitstellungen sowohl lokal als auch online für die Integration von Microsoft Exchange Server 2010, Microsoft Exchange Server 2013 und SharePoint Server konfigurieren. Falls nicht anders angegeben, werden die in der folgenden Tabelle aufgeführten Features mit allen Clients unterstützt. Weitere Informationen zur Clientunterstützung finden Sie unter [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) und in den Lync Online-Client-Vergleichstabellen unter [Clients für Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

## Integration in Exchange Server

In der folgenden Tabelle werden die Features aufgeführt, die in einer Hybridbereitstellung unterstützt werden, wenn diese in Microsoft Exchange Server integriert ist.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange (lokal)</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 (lokal)</strong></p></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-im-and-presence.md">Chat und Anwesenheit in Lync Server 2013</a></p></li>
<li><p>Verwenden von Outlook zum Planen von und Teilnehmen an Onlinebesprechungen</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrieren von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013</a></p></li>
<li><p>Chat/Anwesenheit in Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Konfigurieren von Microsoft Lync Server 2013 in einer standortübergreifenden Umgebung</a></p></li>
<li><p>Verwenden von Outlook Web App zum Planen von und Teilnehmen an Onlinebesprechungen</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-mobility.md">Bereitstellen von Mobilität in Lync Server 2013</a></p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers</a></p>
<div>

> [!NOTE]
> Setzt Exchange 2013 voraus.<BR>Ein Lync 2013-Desktopclient ist erforderlich.


</div></li>
<li><p>Kontaktfoto in hoher Auflösung in Lync 2013-Client und Lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013</a></p>
<div>

> [!NOTE]
> Setzt Exchange 2013 voraus.


</div></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Das Protokoll von &quot;Verpasste Unterhaltungen&quot; und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013</a></p>
<div>

> [!NOTE]
> Setzt Exchange 2013 voraus.


</div></li>
<li><p>Durchsuchen von archivierten Inhalten</p>
<div>

> [!NOTE]
> Setzt Exchange 2013 voraus.


</div></li>
<li><p>Voicemail</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Bereitstellen lokaler Exchange Unified Messaging-Dienste zur Unterstützung von Lync Server 2013-Voicemail</a></p></li>
</ul></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online</a></p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in OWA</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online</a></p></li>
<li><p>Planen von und Teilönehmen an Onlinebesprechungen in der Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen Lync Server 2013-Integration in Exchange Online</a></p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnehmen an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher). Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers</a></p>
<div>

> [!NOTE]
> Nur Lync Server 2013. Ein Lync 2013-Desktopclient ist erforderlich.


</div></li>
<li><p>Kontaktfoto in hoher Auflösung in Lync 2013-Client und Lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013</a>.</p></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Das Protokoll von &quot;Verpasste Unterhaltungen&quot; und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Prüfliste zur Bereitstellung für die Archivierung in Lync Server 2013</a></p></li>
<li><p>Durchsuchen von archiviertem Inhalt. Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Konfigurieren von Exchange für SharePoint eDiscovery Center</a></p></li>
<li><p>Voicemail. Weitere Informationen finden Sie unter <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Chat und Anwesenheit in Outlook</p></li>
<li><p>Verwenden von Outlook zum Planen von und Teilnehmen an Onlinebesprechungen</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Das Protokoll von &quot;Verpasste Unterhaltungen&quot; und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Kontaktfoto in hoher Auflösung in Lync 2013-Client.</p>
<div>

> [!NOTE]
> Setzt Microsoft Exchange Server 2013 voraus. Wird in Lync Web App nicht unterstützt, wenn Benutzer auf Skype for Business Online gehostet werden.


</div></li>
<li><p>Teilnehmen an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
</ul></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in Outlook Web App</p></li>
<li><p>Planen von und Teilönehmen an Onlinebesprechungen in der Outlook Web App</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnehmen an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Das Protokoll von &quot;Verpasste Unterhaltungen&quot; und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<div>

> [!NOTE]
> Lync Server 2013-Client erforderlich


</div></li>
<li><p>Kontaktfoto in hoher Auflösung in Lync 2013-Client und Lync Web App.</p></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p></li>
<li><p>Durchsuchen von archivierten Inhalten</p></li>
<li><p>Voicemail</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Integration in SharePoint

In der folgenden Tabelle werden die Features aufgeführt, die in einer Lync Server 2013-Hybridbereitstellung bei einer Integration mit SharePoint unterstützt werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>SharePoint (lokal)</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 (lokal)</strong></p></td>
<td><ul>
<li><p>Fertigkeitensuche</p></li>
<li><p>Anwesenheit in SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Anwesenheit in SharePoint</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Anwesenheit in SharePoint</p></li>
</ul></td>
<td><ul>
<li><p>Anwesenheit in SharePoint</p></li>
</ul></td>
</tr>
</tbody>
</table>

