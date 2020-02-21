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
ms.openlocfilehash: 34a73d343375f53acf7f1b7383efb05dd63b9a64
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-lync-server-2013-hybrid-configurations"></a>Unterstützte lync Server 2013 Hybridkonfigurationen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-05-10_

Sie können lync Server 2013-Bereitstellungen für die Integration in Microsoft Exchange Server 2010 und Microsoft Exchange Server 2013 und SharePoint Server sowohl lokal als auch Online konfigurieren. Sofern nicht anders angegeben, werden die in der folgenden Tabelle aufgeführten Features mit allen Clients unterstützt. Weitere Informationen zur Clientunterstützung finden Sie unter [Client Vergleichstabellen für lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md) -und Skype for Business Online-Client Vergleichstabellen auf [Clients für Skype for Business Online](https://go.microsoft.com/fwlink/p/?linkid=281902).

<div>

## <a name="integration-with-exchange-server"></a>Integration in Exchange Server

In der folgenden Tabelle sind die Features aufgeführt, die in einer hybridbereitstellung unterstützt werden, wenn Sie in Exchange Server integriert sind.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Exchange lokal</th>
<th>Exchange Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 lokal</strong></p></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-im-and-presence.md">Chat und Anwesenheit in lync Server 2013</a></p></li>
<li><p>Planen und teilnehmen an Onlinebesprechungen über Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-integrating-with-microsoft-exchange-server-2013.md">integrieren von Microsoft lync Server 2013 und Microsoft Exchange Server 2013</a></p></li>
<li><p>Chat/Anwesenheit in Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-in-a-cross-premises-environment.md">Konfigurieren von Microsoft lync Server 2013 in einer standortübergreifenden Umgebung</a> .</p></li>
<li><p>Planen und teilnehmen an Onlinebesprechungen über Outlook Web App</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-mobility.md">Deploying Mobility in lync Server 2013</a></p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen des Outlook-Kalenders</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</a> .</p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.<BR>Ein lync 2013-Desktop Client ist erforderlich.


</div></li>
<li><p>Hochauflösendes Kontakt Foto in lync 2013 Client und lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013</a></p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Besprechungs Delegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden.</p></li>
<li><p>Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Archivieren von Inhalt (Chat und Besprechung) in Exchange</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Checkliste für die Bereitstellung für die Archivierung in lync Server 2013</a></p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Durchsuchen archivierter Inhalte</p>
<div>

> [!NOTE]  
> Erfordert Exchange 2013.


</div></li>
<li><p>Voicemail</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md">Deploying on-premises Exchange um to bereitstellen lync Server 2013 Voice Mail</a></p></li>
</ul></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises lync Server 2013 Integration in Exchange Online</a></p></li>
<li><p>Planen und teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in OWA</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises lync Server 2013 Integration in Exchange Online</a></p></li>
<li><p>Planen und an einer Onlinebesprechung teilnehmen Outlook Web App</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md">Configuring on-premises lync Server 2013 Integration in Exchange Online</a></p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen des Outlook-Kalenders</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher). Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md">Konfigurieren von Microsoft lync Server 2013 für die Verwendung des einheitlichen Kontaktspeichers</a> .</p>
<div>

> [!NOTE]  
> Nur lync Server 2013. Ein lync 2013-Desktop Client ist erforderlich.


</div></li>
<li><p>Hochauflösendes Kontakt Foto in lync 2013 Client und lync Web App.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-configuring-the-use-of-high-resolution-photos.md">Konfigurieren der Verwendung von hochauflösenden Fotos in Microsoft lync Server 2013</a>.</p></li>
<li><p>Besprechungs Delegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden.</p></li>
<li><p>Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Archivieren von Inhalt (Chat und Besprechung) in Exchange.</p>
<p>Weitere Informationen finden Sie unter <a href="lync-server-2013-deployment-checklist-for-archiving.md">Checkliste für die Bereitstellung für die Archivierung in lync Server 2013</a></p></li>
<li><p>Durchsuchen archivierter Inhalte. Weitere Informationen finden Sie unter <a href="https://go.microsoft.com/fwlink/p/?linkid=285448">Konfigurieren von Exchange für SharePoint eDiscovery Center</a></p></li>
<li><p>Voicemail. Weitere Informationen finden Sie unter <a href="lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md">providing lync Server 2013 users Voice Mail on Hosted Exchange um</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Lync Online</strong></p></td>
<td><ul>
<li><p>Chat und Anwesenheit in Outlook</p></li>
<li><p>Planen und teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Hochauflösendes Kontakt Foto in lync 2013 Client.</p>
<div>

> [!NOTE]  
> Erfordert Microsoft Exchange Server 2013. Dies wird in lync Web App nicht unterstützt, wenn Benutzer in Skype for Business Online verwaltet werden.


</div></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen des Outlook-Kalenders</p></li>
<li><p>Besprechungs Delegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden.</p></li>
</ul></td>
<td><ul>
<li><p>Chat/Anwesenheit in Outlook</p></li>
<li><p>Planen und teilnehmen an Onlinebesprechungen über Outlook</p></li>
<li><p>Chat/Anwesenheit in Outlook Web App</p></li>
<li><p>Planen und an einer Onlinebesprechung teilnehmen Outlook Web App</p></li>
<li><p>Chat/Anwesenheit in mobilen Clients</p></li>
<li><p>Teilnahme an Onlinebesprechungen in mobilen Clients</p></li>
<li><p>Veröffentlichen des Status basierend auf den Frei/Gebucht-Informationen des Outlook-Kalenders</p></li>
<li><p>Verlauf von verpassten Unterhaltungen und Anrufprotokolle werden in das Exchange-Postfach des Benutzers geschrieben.</p></li>
<li><p>Kontaktliste (über den einheitlichen Kontaktspeicher)</p>
<div>

> [!NOTE]  
> Lync Server 2013-Client erforderlich


</div></li>
<li><p>Hochauflösendes Kontakt Foto in lync 2013 Client und lync Web App</p></li>
<li><p>Besprechungs Delegation</p>
<p>Wird nur unterstützt, wenn beide Benutzer online in derselben Gesamtstruktur verwaltet werden oder beide lokal verwaltet werden.</p></li>
<li><p>Archivieren von Inhalt (Chat und Besprechung) in Exchange</p></li>
<li><p>Durchsuchen archivierter Inhalte</p></li>
<li><p>Voicemail</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="integration-with-sharepoint"></a>Integration in SharePoint

In der folgenden Tabelle sind die Features aufgeführt, die in einer lync Server 2013-hybridbereitstellung bei Integration in SharePoint unterstützt werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Lokale Version von SharePoint</th>
<th>SharePoint Online</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Lync Server 2013 lokal</strong></p></td>
<td><ul>
<li><p>Skills-Suche</p></li>
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

