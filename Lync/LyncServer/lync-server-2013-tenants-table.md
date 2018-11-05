---
title: 'Lync Server 2013: Tenants-Tabelle'
TOCTitle: Tenants-Tabelle
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412950(v=OCS.15)
ms:contentKeyID: 49295300
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Tenants-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Tenants** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste verschiedener Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.


> [!NOTE]
> Bei der lokalen Bereitstellung wird die integrierte Mandanten-ID von der Aufzeichnung von Kommunikationsdatensätzen (KDS) zur Angabe verschiedener Authentifizierungstypen verwendet, wie z.&nbsp;B. Verbindung mit öffentlichen Chatdiensten, Partner und Anonym.




<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diese Mandanten-ID identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>Zulässige Werte:</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 - Enterprise</p></li>
<li><p>00000000-0000-0000-0000-000000000001 - Verbund</p></li>
<li><p>00000000-0000-0000-0000-000000000002 - Anonym</p></li>
<li><p>00000000-0000-0000-0000-000000000003 - Verbindung mit öffentlichen Chatdiensten</p></li>
</ul></td>
</tr>
</tbody>
</table>

