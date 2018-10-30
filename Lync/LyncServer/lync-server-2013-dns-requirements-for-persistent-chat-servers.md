---
title: DNS-Anforderungen für Persistent Chat-Server
TOCTitle: DNS-Anforderungen für Persistent Chat-Server
ms:assetid: f7531374-d7ed-4b63-ae81-02294cb4496a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205391(v=OCS.15)
ms:contentKeyID: 49295938
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für Persistent Chat-Server

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden die DNS-Einträge (Domain Name System) beschrieben, die für die Bereitstellung von Server für beständigen Chat erforderlich sind.

## DNS-Einträge für Persistent Chat Server

In der folgenden Tabelle werden die Anforderungen hinsichtlich DNS-Einträgen für eine Server für beständigen Chat-Bereitstellung aufgelistet.

### DNS-Anforderungen für Persistent Chat Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Bereitstellungsszenario</th>
<th>DNS-Anforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ein (1) Persistent Chat-Server</p></td>
<td><p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p></td>
</tr>
<tr class="even">
<td><p>Persistent Chat-Pool</p></td>
<td><p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p>
<p><strong>Beispiel</strong></p>
<p>PersistentChatServer01.contoso.com     10.10.10.1</p>
<p>PersistentChatServer02.contoso.com     10.10.10.2</p>
<p>Ein interner A-Eintrag, mit dem der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Servers in die zugehörige IP-Adresse aufgelöst wird.</p>
<p><strong>Beispiel</strong></p>
<p>PersistentChatPool.contoso.com    10.10.10.1</p>
<p>PersistentChatPool.contoso.com    10.10.10.2</p></td>
</tr>
</tbody>
</table>

