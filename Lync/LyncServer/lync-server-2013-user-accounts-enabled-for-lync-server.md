---
title: 'Lync Server 2013: Benutzerkonten, die für lync Server aktiviert sind'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b7a8935e83b79cfac1c4d3283fe0011a72aa3ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-accounts-enabled-for-lync-server-2013"></a>Für lync Server 2013 aktivierte Benutzerkonten

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-04-18_

Die Themen in diesem Abschnitt enthalten Schritt-für-Schritt-Verfahren zum Konfigurieren von Benutzereinstellungen, die Sie mit der lync Server 2013-Systemsteuerung durchführen können.

<div>


> [!IMPORTANT]  
> Sie können die lync Server-Systemsteuerung nicht zum Verwalten von Benutzern verwenden, die Mitglieder der Gruppe "Active Directory-Domänenadministratoren" sind. Für Benutzer von Domänenadministratoren können Sie die lync Server-Systemsteuerung nur zum Durchführen von schreibgeschützten Suchvorgängen verwenden. Wenn Sie Schreibvorgänge für Benutzer von Domänenadministratoren durchführen möchten (beispielsweise für die lync Server-Systemsteuerung aktivieren oder deaktivieren, Pool-oder Richtlinienzuweisungen ändern, Telefoneinstellungen, SIP-Adresse), müssen Sie Windows PowerShell-Cmdlets verwenden, während Sie als Domänenadministrator angemeldet sind. Details zur Verwendung von Windows PowerShell-Cmdlets zum Verwalten von Benutzern finden Sie unter <A href="lync-server-2013-lync-server-management-shell.md">lync Server 2013-Verwaltungsshell</A>.



</div>

Wenn Sie eine beliebige lync Server 2013-Verwaltungsaufgabe ausführen, die die Suche nach einem Benutzer oder das Filtern von Benutzersuchergebnissen umfasst, gibt es einige Benutzereigenschaften, die als Attribute in den Active Directory-Domänendiensten vorhanden sind, aber nicht in den globalen Katalog repliziert werden. bis Microsoft Exchange Server bereitgestellt wird. Microsoft Exchange, nicht lync Server, kennzeichnet die folgenden Attribute für die Replikation beim globalen Katalog, wenn die Installation erfolgt:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzerinformationen</th>
<th>Adresse und Telefon</th>
<th>Organisation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initialen</p></td>
<td><p>Straßenanschrift</p>
<p>Land/Region</p>
<p>Pager</p>
<p>Fax</p>
<p>Mobil</p></td>
<td><p>Titel</p>
<p>Unternehmen</p>
<p>Abteilung</p>
<p>Office</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anzeigen von Informationen zu Benutzerkonten, die für lync Server 2013 aktiviert sind](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Verwalten von Enterprise-VoIP für Benutzer in lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Ändern von Benutzerkontoeigenschaften in lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Cmdlets für die Benutzerverwaltung in lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Verwalten von Benutzern in Lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

