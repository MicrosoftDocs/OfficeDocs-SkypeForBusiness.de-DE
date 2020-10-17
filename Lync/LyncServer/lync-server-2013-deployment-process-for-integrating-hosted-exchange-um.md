---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration von gehosteten Exchange um'
description: 'Lync Server 2013: Bereitstellungsprozess für die Integration von gehosteten Exchange um.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542611"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a>Bereitstellungsprozess für die Integration gehosteter Exchange um mit lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-25_

Für eine effektive Planung für die Integration von lync Server 2013 mit gehosteten Exchange Unified Messaging (um) müssen Sie Folgendes berücksichtigen:

  - Voraussetzungen für die Integration von lync Server 2013 mit gehosteten Exchange um

  - Erforderliche Schritte während des Integrationsprozesses

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a>Bereitstellungsvoraussetzungen für die Integration in gehostete Exchange UM-Dienste

Bevor Sie mit dem Integrationsprozess beginnen können, müssen Sie bereits lync Server 2013 bereitgestellt haben (mindestens eine Front-End-Pool oder ein Standard Edition-Server), eine Edgeserver und lync 2013 oder lync 2010 Clients.

</div>

<div>

## <a name="integration-process"></a>Integrationsprozess

Die folgende Tabelle zeigt eine Übersicht über den Integrationsprozess der gehosteten Exchange Unified Messaging-Dienste. Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [providing lync Server 2013 users Voice Mail on Hosted Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation.


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
<td><p>Konfigurieren des Edgeservers</p></td>
<td><ol>
<li><p>Konfigurieren Sie den Edgeserver für einen Partnerverbund.</p></li>
<li><p>Replizieren Sie die Daten manuell auf den Edgeserver.</p></li>
<li><p>Konfigurieren Sie den Hostingprovider auf dem Edgeserver.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren der Edgeserver für die Integration in gehostete Exchange um</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren der Richtlinie für gehostete Voicemail</p></td>
<td><ol>
<li><p>Ändern Sie entweder die globale Richtlinie für gehostete Voicemail, oder erstellen Sie eine neue Richtlinie für gehostete Voicemail auf Standort- oder Benutzerebene.</p></li>
<li><p>Weisen Sie auf Benutzerebene erstellte Richtlinien den geeigneten Benutzern oder Gruppen zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzerkonten für gehostete Voicemail</p></td>
<td><ul>
<li><p>Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von gehosteten Kontaktobjekten</p></td>
<td><ol>
<li><p>Erstellen Sie Kontaktobjekte für automatische Telefonzentralen für gehostete Exchange UM-Dienste.</p></li>
<li><p>Erstellen Sie Kontaktobjekte für den Teilnehmerzugriff für gehostete Exchange UM-Dienste.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>
<div>

> [!NOTE]  
> Zum Erstellen, Ändern oder Entfernen von Kontaktobjekten muss der Benutzer, der das Cmdlet "New-CsExUmContact", "Set-CsExUmContact" oder "Remove-CsExUmContact" ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden. Diese Berechtigungen können mit dem Cmdlet "Grant-CsOUPermission" gewährt werden. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.


</div></td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Contact-Objekten für gehostete Exchange um in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

