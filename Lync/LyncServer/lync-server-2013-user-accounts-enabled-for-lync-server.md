---
title: 'Lync Server 2013: für lync Server aktivierte Benutzerkonten'
description: 'Lync Server 2013: für lync Server aktivierte Benutzerkonten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User accounts enabled for Lync Server 2013
ms:assetid: 8021087e-5084-4a39-9fef-ab9376c6d371
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182543(v=OCS.15)
ms:contentKeyID: 48184651
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf87177c378ffe61715d5332d2fd23b1d8e6fce6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569871"
---
# <a name="user-accounts-enabled-for-lync-server-2013"></a>Für lync Server 2013 aktivierte Benutzerkonten

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-04-18_

Die Themen in diesem Abschnitt bieten schrittweise Anleitungen zum Konfigurieren von Benutzereinstellungen, die Sie mit der lync Server 2013-Systemsteuerung ausführen können.

<div>


> [!IMPORTANT]  
> Sie können lync Server-Systemsteuerung nicht zum Verwalten von Benutzern verwenden, die Mitglied der Gruppe "Active Directory Domänen-Admins" sind. Für Benutzer von Domänenadministratoren können Sie lync Server-Systemsteuerung nur zum Ausführen schreibgeschützter Suchvorgänge verwenden. Zum Ausführen von Schreibvorgängen für Benutzer von Domänenadministratoren (zum Beispiel aktivieren oder deaktivieren für lync Server-Systemsteuerung, Ändern von Pool-oder Richtlinienzuweisungen, Telefonieeinstellungen, SIP-Adresse) müssen Sie Windows PowerShell-Cmdlets verwenden, während Sie als Domänenadministrator Benutzer angemeldet sind. Ausführliche Informationen zur Verwendung von Windows PowerShell-Cmdlets zum Verwalten von Benutzern finden Sie unter <A href="lync-server-2013-lync-server-management-shell.md">lync Server 2013 Management Shell</A>.



</div>

Wenn Sie eine lync Server 2013 administrative Aufgabe ausführen, die die Suche nach einem Benutzer oder das Filtern von Benutzersuchergebnissen umfasst, gibt es einige Benutzereigenschaften, die als Attribute in Active Directory-Domänendienste vorhanden sind, aber erst nach der Bereitstellung von Exchange Server in den globalen Katalog repliziert werden. Microsoft Exchange, nicht lync Server, markiert bei der Installation die folgenden Attribute für die Replikation in den globalen Katalog:


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
<th>Organization (Organisation)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Initialen</p></td>
<td><p>Adresse</p>
<p>Land/Region</p>
<p>Pager</p>
<p>Fax</p>
<p>Mobile</p></td>
<td><p>Titel</p>
<p>Company</p>
<p>Abteilung</p>
<p>Büro</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Anzeigen von Informationen zu Benutzerkonten, die für lync Server 2013 aktiviert sind](lync-server-2013-viewing-information-about-user-accounts-enabled-for-lync-server.md)

  - [Aktivieren und Deaktivieren von Benutzern für lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)

  - [Verwalten von Enterprise-VoIP für Benutzer in lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)

  - [Ändern von Benutzerkontoeigenschaften in lync Server 2013](lync-server-2013-modifying-user-account-properties.md)

  - [Verwalten von Richtlinien für den externen Zugriff in lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Zuweisen von Richtlinien pro Benutzer in lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Cmdlets für die Benutzerverwaltung in lync Server 2013](lync-server-2013-user-management-cmdlets.md)  


[Verwalten von Benutzern in lync Server 2013](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

