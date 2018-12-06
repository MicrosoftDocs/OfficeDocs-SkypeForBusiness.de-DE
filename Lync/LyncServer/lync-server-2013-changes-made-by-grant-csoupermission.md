---
title: Änderungen, die durch Grant-CsOUPermission durchgeführt werden in Lync Server 2013
TOCTitle: Änderungen, die durch Grant-CsOUPermission durchgeführt werden in Lync Server 2013
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205310(v=OCS.15)
ms:contentKeyID: 49295558
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Änderungen, die durch Grant-CsOUPermission durchgeführt werden in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum Delegieren der Lync Server 2013-Verwaltung können Sie bestimmten Organisationseinheiten (Organizational Units, OUs) Berechtigungen gewähren, sodass Mitglieder der während der Gesamtstrukturvorbereitung erstellten universellen RTC-Gruppen auf die Organisationseinheiten zugreifen können, ohne Mitglieder der Gruppe Domänen-Admins zu sein.

Mit dem **Grant-CsOuPermission**-Cmdlet werden Objekten in der angegebenen Organisationseinheit Berechtigungen gemäß der folgenden Tabellen erteilt.

## Erteilen von Berechtigungen für User-Objekte

Wenn Sie das **Grant-CsOuPermission**-Cmdlet für User-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen gemäß der folgenden Tabelle erteilt.

### Für User-Objekte erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigung</th>
<th>Geltungsbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Verzeichnisänderungen replizieren</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Read RTCUserSearchPropertySet</p>
<p>Read RTCUserProvisioningPropertySet</p>
<p>Read RTCPropertySet</p>
<p>Read Public-Information</p>
<p>Read General-Information</p>
<p>Read User-Account-Restrictions</p></td>
<td><p>Untergeordnete User-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Write RTCUserSearchPropertySet</p>
<p>Write msExchUCVoiceMailSettings</p>
<p>Write RTCUserProvisioningPropertySet</p>
<p>Write RTCPropertySet</p>
<p>Write proxyAddresses</p></td>
<td><p>Untergeordnete User-Objekte</p></td>
</tr>
</tbody>
</table>


## Erteilen von Berechtigungen für Computer-Objekte

Wenn Sie das **Grant-CsOuPermission**-Cmdlet für Computer-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen gemäß der folgenden Tabelle erteilt.

### Für Computer-Objekte erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigung</th>
<th>Geltungsbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Verzeichnisänderungen replizieren</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Read Public-Information</p>
<p>Read Validated-DNS-Host-Name</p></td>
<td><p>Untergeordnete Computer-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Read Public-Information</p>
<p>Read Validated-DNS-Host-Name</p></td>
<td><p>Untergeordnete Computer-Objekte</p></td>
</tr>
</tbody>
</table>


## Erteilen von Berechtigungen für Contact oder AppContact-Objekte

Wenn Sie das **Grant-CsOuPermission**-Cmdlet für Contact- oder AppContact-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen gemäß der folgenden Tabelle erteilt.

### Für Contact- oder AppContact-Objekte erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigung</th>
<th>Geltungsbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Verzeichnisänderungen replizieren</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Read RTCUserSearchPropertySet</p>
<p>Read RTCUserProvisioningPropertySet</p>
<p>Read RTCPropertySet</p>
<p>Read Public-Information</p>
<p>Read General-Information</p>
<p>Read Personal-Information</p>
<p>Read User-Account-Restrictions</p></td>
<td><p>Untergeordnete Contact-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Write RTCUserSearchPropertySet</p>
<p>Write otherIpPhone</p>
<p>Write displayName</p>
<p>Write description</p>
<p>Write telephoneNumber</p>
<p>Write msExchUCVoiceMailSettings</p>
<p>Write RTCUserProvisioningPropertySet</p>
<p>Write RTCPropertySet</p>
<p>Write proxyAddresses</p></td>
<td><p>Untergeordnete Contact-Objekte</p></td>
</tr>
</tbody>
</table>


## Erteilen von Berechtigungen für Device-Objekte

Wenn Sie das **Grant-CsOuPermission**-Cmdlet für Device-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen gemäß der folgenden Tabelle erteilt.

### Für Device-Objekte erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigung</th>
<th>Geltungsbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Verzeichnisänderungen replizieren</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Read RTCUserSearchPropertySet</p>
<p>Read RTCUserProvisioningPropertySet</p>
<p>Read RTCPropertySet</p>
<p>Read Public-Information</p>
<p>Read Personal-Information</p>
<p>Read General-Information</p>
<p>Read User-Account-Restrictions</p></td>
<td><p>Untergeordnete Contact-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Untergeordnetes Element erstellen</p>
<p>Untergeordnetes Element löschen</p>
<p>Struktur löschen</p></td>
<td><p>Contact</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Write displayName</p>
<p>Write description</p>
<p>Write telephoneNumber</p></td>
<td><p>Untergeordnete User-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Write RTCUserSearchPropertySet</p>
<p>Write otherIpPhone</p>
<p>Write displayName</p>
<p>Write description</p>
<p>Write telephoneNumber</p>
<p>Write msExchUCVoiceMailSettings</p>
<p>Write RTCUserProvisioningPropertySet</p>
<p>Write RTCPropertySet</p>
<p>Write proxyAddresses</p></td>
<td><p>Untergeordnete Contact-Objekte</p></td>
</tr>
</tbody>
</table>


## Erteilen von Berechtigungen für InetOrgPerson-Objekte

Wenn Sie das **Grant-CsOuPermission**-Cmdlet für InetOrgPerson-Objekte in einer Organisationseinheit ausführen, werden Gruppen Berechtigungen gemäß der folgenden Tabelle erteilt.

### Für InetOrgPerson-Objekte erteilte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigung</th>
<th>Geltungsbereich</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Verzeichnisänderungen replizieren</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Inhalt auflisten</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup</p></td>
<td><p>Read RTCUserSearchPropertySet</p>
<p>Read RTCUserProvisioningPropertySet</p>
<p>Read RTCPropertySet</p>
<p>Read Personal-Information</p>
<p>Read Public-Information</p>
<p>Read General-Information</p>
<p>Read User-Account-Restrictions</p></td>
<td><p>Untergeordnete inetOrgPerson-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Write RTCUserSearchPropertySet</p>
<p>Write RTCUserProvisioningPropertySet</p>
<p>Write RTCPropertySet</p>
<p>Write proxyAddresses</p></td>
<td><p>Untergeordnete inetOrgPerson-Objekte</p></td>
</tr>
</tbody>
</table>

