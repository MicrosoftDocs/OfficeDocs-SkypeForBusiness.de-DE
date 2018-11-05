---
title: Änderungen, die durch Grant-CsSetupPermission durchgeführt werden in Lync Server 2013
TOCTitle: Änderungen, die durch Grant-CsSetupPermission durchgeführt werden in Lync Server 2013
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205250(v=OCS.15)
ms:contentKeyID: 49295347
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Änderungen, die durch Grant-CsSetupPermission durchgeführt werden in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum Delegieren von Setup können Sie der universellen Gruppe RTCUniversalServerAdmins Berechtigungen für eine spezifische Active Directory-Organisationseinheit gewähren, sodass Mitglieder dieser Gruppe in dieser Organisationseinheit Lync Server 2013 in der angegebenen Domäne installieren können, ohne Mitglieder der Gruppe Domänen-Admins zu sein.

Mit dem **Grant-CsSetupPermission**-Cmdlet werden der Gruppe RTCUniversalServerAdmins Berechtigungen für eine Organisationseinheit gemäß der folgenden Tabelle erteilt:

### Objekten in der Organisationseinheit erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Gültigkeitsbereich der Berechtigungen:</th>
<th>Erteilte Berechtigungen:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>servicePrincipalName lesen</p></li>
<li><p>servicePrincipalName schreiben</p></li>
<li><p>Struktur löschen</p></li>
<li><p>Verzeichnisänderungen replizieren</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete serviceConnectionPoint-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Leseberechtigungen</p></li>
<li><p>Schreibberechtigungen</p></li>
<li><p>Untergeordnetes Element erstellen</p></li>
<li><p>Untergeordnetes Element löschen</p></li>
<li><p>Inhalt auflisten</p></li>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-Server-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-WebComponents-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-MCU-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-MediationServer-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete msRTCSIP-ApplicationServer-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Untergeordnete msRTCSIP-ConnectionPoint-Objekte</p></td>
<td><p>Beschränkter Zugriff:</p>
<ul>
<li><p>Eigenschaft schreiben</p></li>
<li><p>Eigenschaft lesen</p></li>
<li><p>Struktur löschen</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Untergeordnete Computer-Objekte</p></td>
<td><p>Beschränkter Zugriff für serviceConnectionPoint:</p>
<ul>
<li><p>Untergeordnete Objekte erstellen</p></li>
<li><p>Untergeordnete Objekte löschen</p></li>
<li><p>Struktur löschen</p></li>
</ul>
<p>Beschränkter Zugriff für öffentliche Informationen:</p>
<ul>
<li><p>Eigenschaft lesen</p></li>
</ul>
<p>Beschränkter Zugriff für DNS-Hostnamen:</p>
<ul>
<li><p>Eigenschaft lesen</p></li>
</ul></td>
</tr>
</tbody>
</table>

