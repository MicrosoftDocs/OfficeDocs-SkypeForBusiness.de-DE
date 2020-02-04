---
title: 'Lync Server 2013: von Grant-CsOUPermission vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9056753e57f57b131a05d13eb2862611ba34f966
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a>Von Grant-CsOUPermission in lync Server 2013 vorgenommene Änderungen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-20_

Wenn Sie die Verwaltung von lync Server 2013 delegieren möchten, können Sie den angegebenen Organisationseinheiten Berechtigungen hinzufügen, sodass Mitglieder der von der Gesamtstrukturvorbereitung erstellten RTC universelle Gruppen auf die OUs zugreifen können, ohne Mitglieder der Gruppe der Domänenadministratoren zu sein.

Das Cmdlet **Grant-CsOuPermission** gewährt den Objekten in der angegebenen OU Berechtigungen, wie in den folgenden Tabellen angegeben.

<div>

## <a name="granting-permission-for-user-objects"></a>Erteilen der Berechtigung für Benutzerobjekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Benutzerobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.

### <a name="permissions-granted-for-user-objects"></a>Für Benutzerobjekte gewährte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigungs</th>
<th>Gilt für</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replizieren von Verzeichnisänderungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Lesen von RTCUserSearchPropertySet</p>
<p>Lesen von RTCUserProvisioningPropertySet</p>
<p>Lesen von RTCPropertySet</p>
<p>Lesen öffentlicher Informationen</p>
<p>Allgemeine Informationen lesen</p>
<p>Lesen von Benutzerkonto Einschränkungen</p></td>
<td><p>Nachfolger Benutzerobjekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Schreiben von RTCUserSearchPropertySet</p>
<p>Schreiben von msExchUCVoiceMailSettings</p>
<p>Schreiben von RTCUserProvisioningPropertySet</p>
<p>Schreiben von RTCPropertySet</p>
<p>Schreiben von proxyAddresses</p></td>
<td><p>Nachfolger Benutzerobjekte</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a>Erteilen der Berechtigung für Computer Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Computer Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.

### <a name="permissions-granted-for-computer-objects"></a>Für Computer Objekte gewährte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigungs</th>
<th>Gilt für</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replizieren von Verzeichnisänderungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Lesen öffentlicher Informationen</p>
<p>Read validiert-DNS-Host-Name</p></td>
<td><p>Nachfolger Computer Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Lesen öffentlicher Informationen</p>
<p>Read validiert-DNS-Host-Name</p></td>
<td><p>Nachfolger Computer Objekte</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a>Erteilen der Berechtigung für Kontakt-oder AppContact-Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Contact-Objekte oder AppContact-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a>Für Contact-oder AppContact-Objekte gewährte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigungs</th>
<th>Gilt für</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replizieren von Verzeichnisänderungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Lesen von RTCUserSearchPropertySet</p>
<p>Lesen von RTCUserProvisioningPropertySet</p>
<p>Lesen von RTCPropertySet</p>
<p>Lesen öffentlicher Informationen</p>
<p>Allgemeine Informationen lesen</p>
<p>Lesen persönlicher Informationen</p>
<p>Lesen von Benutzerkonto Einschränkungen</p></td>
<td><p>Nachfolger-Kontaktobjekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Schreiben von RTCUserSearchPropertySet</p>
<p>Schreiben von otherIpPhone</p>
<p>Schreiben von DisplayName</p>
<p>Beschreibung schreiben</p>
<p>Schreiben von telephoneNumber</p>
<p>Schreiben von msExchUCVoiceMailSettings</p>
<p>Schreiben von RTCUserProvisioningPropertySet</p>
<p>Schreiben von RTCPropertySet</p>
<p>Schreiben von proxyAddresses</p></td>
<td><p>Nachfolger-Kontaktobjekte</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a>Erteilen der Berechtigung für Geräteobjekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für Geräteobjekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.

### <a name="permissions-granted-for-device-objects"></a>Für Geräteobjekte gewährte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigungs</th>
<th>Gilt für</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replizieren von Verzeichnisänderungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Lesen von RTCUserSearchPropertySet</p>
<p>Lesen von RTCUserProvisioningPropertySet</p>
<p>Lesen von RTCPropertySet</p>
<p>Lesen öffentlicher Informationen</p>
<p>Lesen persönlicher Informationen</p>
<p>Allgemeine Informationen lesen</p>
<p>Lesen von Benutzerkonto Einschränkungen</p></td>
<td><p>Nachfolger-Kontaktobjekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Erstellen eines untergeordneten Elements</p>
<p>Untergeordnetes Element löschen</p>
<p>Struktur löschen</p></td>
<td><p>Kontakt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Schreiben von DisplayName</p>
<p>Beschreibung schreiben</p>
<p>Schreiben von telephoneNumber</p></td>
<td><p>Nachfolger Benutzerobjekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Schreiben von RTCUserSearchPropertySet</p>
<p>Schreiben von otherIpPhone</p>
<p>Schreiben von DisplayName</p>
<p>Beschreibung schreiben</p>
<p>Schreiben von telephoneNumber</p>
<p>Schreiben von msExchUCVoiceMailSettings</p>
<p>Schreiben von RTCUserProvisioningPropertySet</p>
<p>Schreiben von RTCPropertySet</p>
<p>Schreiben von proxyAddresses</p></td>
<td><p>Nachfolger-Kontaktobjekte</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a>Erteilen der Berechtigung für InetOrgPerson-Objekte

Wenn Sie das **Grant-CsOuPermission-** Cmdlet für InetOrgPerson-Objekte in einer OU ausführen, werden Gruppen Berechtigungen gewährt, wie in der folgenden Tabelle dargestellt.

### <a name="permissions-granted-for-inetorgperson-objects"></a>Für InetOrgPerson-Objekte gewährte Berechtigungen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Gruppe</th>
<th>Berechtigungs</th>
<th>Gilt für</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Replizieren von Verzeichnisänderungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Listeninhalt</p>
<p>Alle Eigenschaften lesen</p>
<p>Leseberechtigungen</p></td>
<td><p>Nur dieses Objekt</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Lesen von RTCUserSearchPropertySet</p>
<p>Lesen von RTCUserProvisioningPropertySet</p>
<p>Lesen von RTCPropertySet</p>
<p>Lesen persönlicher Informationen</p>
<p>Lesen öffentlicher Informationen</p>
<p>Allgemeine Informationen lesen</p>
<p>Lesen von Benutzerkonto Einschränkungen</p></td>
<td><p>Nachgeordnete InetOrgPerson-Objekte</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Schreiben von RTCUserSearchPropertySet</p>
<p>Schreiben von RTCUserProvisioningPropertySet</p>
<p>Schreiben von RTCPropertySet</p>
<p>Schreiben von proxyAddresses</p></td>
<td><p>Nachgeordnete InetOrgPerson-Objekte</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

