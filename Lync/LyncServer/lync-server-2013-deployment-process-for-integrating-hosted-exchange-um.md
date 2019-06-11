---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6269efd85261c702c77568fac67c96034ba01a71
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-25_

Bei der effektiven Planung für die Integration von lync Server 2013 in gehostete Exchange Unified Messaging (um) müssen Sie Folgendes berücksichtigen:

  - Voraussetzungen für die Integration von lync Server 2013 in Hosted Exchange um

  - Erforderliche Schritte während des Integrationsprozesses

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Voraussetzungen für die Bereitstellung für die Integration in Hosted Exchange um

Bevor Sie mit dem Integrationsprozess beginnen können, müssen Sie bereits lync Server 2013 (mindestens einen Front-End-Pool oder einen Standard Edition-Server), einen Edgeserver und lync 2013-oder lync 2010-Clients bereitgestellt haben.

</div>

<div>

## <a name="integration-process"></a>Integrationsprozess

Die folgende Tabelle enthält eine Übersicht über den gehosteten Exchange um-Integrationsprozess. Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [Bereitstellen von lync Server 2013-Benutzern für Voicemail](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation für gehostete Exchange um.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Rechte und Berechtigungen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfigurieren Sie den Edgeserver.</p></td>
<td><ol>
<li><p>Konfigurieren Sie den Edgeserver für einen Partnerverbund.</p></li>
<li><p>Manuelles Replizieren von Daten auf den Edgeserver</p></li>
<li><p>Konfigurieren Sie den Hostinganbieter auf dem Edgeserver.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren der Richtlinie für gehostete Voicemail</p></td>
<td><ol>
<li><p>Ändern Sie entweder die Global Hosted Voicemail-Richtlinie, oder erstellen Sie eine neue gehostete Voicemail-Richtlinie mit Website-oder pro-Benutzer-Bereich.</p></li>
<li><p>Weisen Sie für Richtlinien mit benutzerspezifischem Bereich die Richtlinie Benutzern oder Gruppen zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzern für gehostete Voicemails</p></td>
<td><ul>
<li><p>Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von gehosteten Kontaktobjekten</p></td>
<td><ol>
<li><p>Erstellen Sie Kontaktobjekte für die automatische Telefonzentrale für gehostete Exchange um.</p></li>
<li><p>Erstellen von Kontaktobjekten für den Abonnenten Zugriff für gehostete Exchange um.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Zum Erstellen, ändern oder Entfernen von Kontaktobjekten muss der Benutzer, der das Cmdlet New-CsExUmContact, CsExUmContact oder Remove-CsExUmContact ausführt, über die richtige Berechtigung für die Active Directory-Organisationseinheit verfügen, in der die neuen Kontaktobjekte gespeichert sind. Diese Berechtigungen können gewährt werden, indem das Cmdlet Grant-CsOUPermission ausgeführt wird. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

