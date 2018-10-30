---
title: 'Lync Server 2013: Unterstützung für Lync Client-Software'
TOCTitle: Unterstützung für Lync Client-Software
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412781(v=OCS.15)
ms:contentKeyID: 49294994
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützung für Lync Client-Software in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt wird die Softwareunterstützung für Lync 2013 und das Onlinebesprechungs-Add-In für Lync 2013 zusammengefasst.


> [!NOTE]
> Das Onlinebesprechungs-Add-In für Lync&nbsp;2013, das die Besprechungsverwaltung aus dem Outlook für Messaging und Zusammenarbeit unterstützt, wird automatisch mit Lync 2013 installiert.



### Softwareanforderungen für Lync 2013 und das Onlinebesprechungs-Add-In für Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Systemkomponente</th>
<th>Mindestanforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows-Betriebssystem</p></td>
<td><p>Windows 8,1</p>
<p>Windows 8</p>
<p>Windows 7-Betriebssystem</p>
<p>Windows Server 2008 R2 mit neuestem Service Pack</p>
<div>

> [!NOTE]
> Lync 2013 und das Onlinebesprechungs-Add-In für Lync&nbsp;2013 werden unter Windows Vista oder Windows XP (alle Versionen) nicht unterstützt.


</div></td>
</tr>
<tr class="even">
<td><p>Installation und Updates</p></td>
<td><p>Administratorrechte und -berechtigungen</p></td>
</tr>
<tr class="odd">
<td><p>Browser</p></td>
<td><p>Windows Internet Explorer 10-Internetbrowser</p>
<p>Internet Explorer 9-Internetbrowser</p>
<p>Internet Explorer 8-Internetbrowser</p>
<p>Internet Explorer 7-Internetbrowser</p>
<p>Webbrowser Mozilla Firefox</p>
<div>

> [!NOTE]
> Falls Sie Lync mit Microsoft Exchange Online verwenden und Ihre Organisation einen authentifizierenden HTTP-Proxy bereitgestellt hat, ist Internet Explorer&nbsp;9 oder Internet Explorer&nbsp;8 erforderlich.


</div></td>
</tr>
<tr class="even">
<td><p>Microsoft Office-Integration</p></td>
<td><p>Alle Integrationsfunktionen:</p>
<ul>
<li><p>Outlook 2013-Client für Messaging und Zusammenarbeit</p></li>
<li><p>Outlook 2010-Client für Messaging und Zusammenarbeit</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Microsoft Exchange-Integration</p></td>
<td><p>Alle Integrationsfunktionen:</p>
<ul>
<li><p>Microsoft Exchange Server 2013</p></li>
<li><p>Microsoft Exchange Server 2010</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Macintosh-Betriebssysteme

Lync 2013 ist nur für Windows verfügbar. Lync Server 2013 unterstützt jedoch die folgenden Clients auf Computern, auf denen Mac OS 10.5.8 oder das neueste Service Pack oder die neueste Version (Intel-basierter) Betriebssysteme ausgeführt wird (Mac OS 10.9 wird derzeit nicht unterstützt). Einzelheiten zu den unterstützten Funktionen finden Sie unter [Clientvergleichstabellen für Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync für Mac 2011 (siehe "Lync für Mac 2011 - Bereitstellungshandbuch" unter [http://go.microsoft.com/fwlink/?linkid=268786\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268786%26clcid=0x407))

  - Microsoft Communicator für Mac 2011 (siehe "Communicator für Mac 2011 - Bereitstellungshandbuch" unter [http://go.microsoft.com/fwlink/?linkid=268787\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268787%26clcid=0x407))

## Lync Web App-Browser

Lync Web App unterstützt bestimmte Kombinationen aus Betriebssystem und Browser. Ausführliche Informationen finden Sie unter [Unterstützte Lync Web App-Plattformen für Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) in der Planungsdokumentation.

## Microsoft Office-Unterstützbarkeit

Lync Server 2013-Clients unterstützen die Integration in verschiedene Versionen von Microsoft Office, wie in diesem Abschnitt zusammengefasst wird.

  - Lync 2013-Integrationsfunktionen werden in Outlook 2013 und Microsoft Outlook 2010 unterstützt.

  - Lync 2013-Integrationsfunktionen werden in Microsoft Exchange Server 2013 und Microsoft Exchange Server 2010 unterstützt.

  - Das Onlinebesprechungs-Add-In für Lync 2013 wird mit Office 2013 und Microsoft Office 2010 unterstützt.

## Verwenden von verbindlichen Profilen

Wenn Benutzer beabsichtigen, Lync 2013-Konferenzfunktionen zu verwenden, sollten sie keine verbindlichen Profile für Active Directory-Domänendienste verwenden, um sich beim Lync 2013-Client anzumelden. Da es sich bei den verbindlichen Profilen um schreibgeschützte Benutzerprofile handelt, können die PKI-Schlüssel (Public Key Infrastructure), die für Lync 2013-Konferenzen erforderlich sind, nicht unter dem Profil gespeichert werden. Ausführliche Informationen dazu finden Sie im Microsoft Knowledge Base-Artikel 2552221 "Lync 2010-Konferenzfunktion schlägt fehl, wenn der Benutzer mit einem verbindlichen Benutzerprofil angemeldet ist" unter [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x407).

## Siehe auch

#### Konzepte

[Unterstützung für Lync Client-Hardware in Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Videoanforderungen für den Lync-Client für Lync Server 2013](lync-server-2013-lync-client-video-requirements.md)  
[Unterstützte Clients aus vorherigen Bereitstellungen in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)

