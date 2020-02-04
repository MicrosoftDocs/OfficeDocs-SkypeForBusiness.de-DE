---
title: 'Lync Server 2013: Unterstützte Hybridkonfigurationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported hybrid configurations
ms:assetid: 5d456d6c-ad71-420c-b6d8-4d9cd0324f86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945633(v=OCS.15)
ms:contentKeyID: 51541482
ms.date: 05/10/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dea28ecfcd5e6a881c1d3d1ee63f16cd4821410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Unterstützte lync Server 2013-Hybridkonfigurationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-05-10_

Sie können die lync Server 2013-Bereitstellungen für die Integration mit Microsoft Exchange Server 2010 und Microsoft Exchange Server 2013 und SharePoint Server sowohl lokal als auch Online konfigurieren. Falls nicht anders angegeben, werden die in der folgenden Tabelle aufgeführten Funktionen von allen Clients unterstützt. Weitere Informationen zum Client Support finden Sie unter [Client Vergleichstabellen für lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) und Skype for Business Online-Vergleichstabellen für [Clients für Skype for Business Online](http://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In der folgenden Tabelle sind die in einer hybridbereitstellung unterstützten Features aufgeführt, wenn Sie in Microsoft Exchange Server integriert sind.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Lokales Exchange</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 lokal</strong></p></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-im-and-presence.md">Chat und Anwesenheit in lync Server 2013</a></p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</a></p></li>
<li><p>Chat/Anwesenheit in Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung</a> .</p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-mobility.md">Bereitstellen von Mobilität in lync Server 2013</a></p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</a> .</p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.<BR>Ein lync 2013-Desktop Client ist erforderlich.


</div></li>
<li><p>Kontakt Foto mit hoher Auflösung in lync 2013-Client und lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013</a></p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Das Protokoll von „Verpasste Unterhaltungen“ und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Bereitstellungscheckliste für die Archivierung in lync Server 2013</a></p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Durchsuchen von archivierten Inhalten</p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Voicemail</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Bereitstellen von lokalen Exchange um für die Bereitstellung von lync Server 2013-Voicemail</a> .</p></li>
</ul></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online</a> .</p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in OWA</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online</a> .</p></li>
<li><p>Planen und teilnehmen an einer Onlinebesprechung in Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online</a> .</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnehmen an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher). Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</a> .</p>
<div>

> [!NOTE]  
> Nur lync Server 2013 Ein lync 2013-Desktop Client ist erforderlich.


</div></li>
<li><p>Kontakt Foto mit hoher Auflösung in lync 2013-Client und lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von Fotos mit hoher Auflösung in Microsoft lync Server 2013</a>.</p></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Das Protokoll von „Verpasste Unterhaltungen“ und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Bereitstellungscheckliste für die Archivierung in lync Server 2013</a></p></li>
<li><p>Durchsuchen von archiviertem Inhalt. Weitere Informationen finden Sie unter <a href="http://go.microsoft.com/fwlink/p/?linkid=285448">Konfigurieren von Exchange für SharePoint eDiscovery Center</a> .</p></li>
<li><p>Voicemail. Weitere Informationen finden Sie unter <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">Bereitstellen von lync Server 2013-Benutzern für Voicemail in gehosteten Exchange um</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Chat und Anwesenheit in Outlook</p></li>
<li><p>Planen von und Teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Das Protokoll von „Verpasste Unterhaltungen“ und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Kontakt Foto mit hoher Auflösung in lync 2013-Client.</p>
<div>

> [!NOTE]  
> Erfordert Microsoft Exchange Server 2013. Dies wird in lync Web App nicht unterstützt, wenn Benutzer in Skype for Business Online verwaltet werden.


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
<li><p>Planen und teilnehmen an einer Onlinebesprechung in Outlook Web App</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnehmen an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen im Outlook-Kalender</p></li>
<li><p>Das Protokoll von „Verpasste Unterhaltungen“ und Anruflisten werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<div>

> [!NOTE]  
> Lync Server 2013-Client erforderlich


</div></li>
<li><p>Kontakt Foto mit hoher Auflösung in lync 2013-Client und lync Web App</p></li>
<li><p>Besprechungsdelegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur oder wenn beide Benutzer lokal gehostet werden.</p></li>
<li><p>Inhalt wird in Exchange archiviert (Chat und Besprechung).</p></li>
<li><p>Durchsuchen von archivierten Inhalten</p></li>
<li><p>Voicemail</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die in einer lync Server 2013-hybridbereitstellung unterstützten Features aufgeführt, wenn Sie in SharePoint integriert sind.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Lokales SharePoint</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 lokal</strong></p></td>
<td><ul>
<li><p>Qualifikationssuche</p></li>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

