---
title: 'Lync Server 2013: tblADCookie'
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg558610(v=OCS.15)
ms:contentKeyID: 49293124
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# tblADCookie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

"tblADCookie" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol).

### Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Prinzipal-GUID der überwachten Domäne.</p></td>
</tr>
<tr class="even">
<td><p>prinDCHost</p></td>
<td><p>nvarchar (255)</p></td>
<td><p>Vollqualifizierter Domänenname (Fully Qualified Domain Name, FQDN) des aktuellen Domänencontrollers für die Active Directory-Domänendienste-Synchronisierung (Active Directory Domain Services, Active-Directory-Domänendienste). Hat informativen Wert.</p></td>
</tr>
<tr class="odd">
<td><p>adcContent</p></td>
<td><p>image (binary)</p></td>
<td><p>Cookie für die Active Directory-Synchronisierung.</p></td>
</tr>
<tr class="even">
<td><p>lastUpdated</p></td>
<td><p>datetime</p></td>
<td><p>Zeitstempel der Aktualisierungszeit der Zeile.</p></td>
</tr>
<tr class="odd">
<td><p>lockedUntil</p></td>
<td><p>datetime</p></td>
<td><p>Zeitpunkt bis zu dem die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Sperrmechanismus der Software, durch den sichergestellt ist, dass nur jeweils ein Chatdienst die Active Directory-Synchronisierung durchführt.</p></td>
</tr>
</tbody>
</table>


### Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte(n)</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinGuid</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>Fremdschlüssel mit Abfrage der <strong>Principal.prinGuid</strong> -Tabelle.</p></td>
</tr>
</tbody>
</table>

