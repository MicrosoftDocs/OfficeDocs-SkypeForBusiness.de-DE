---
title: 'Lync Server 2013: von der Gesamtstrukturvorbereitung vorgenommene Änderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef94ea82f31871cf90939aa25a130903f15ef756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a>Änderungen, die von der Gesamtstrukturvorbereitung in lync Server 2013 vorgenommen wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-30_

In diesem Abschnitt werden die globalen Einstellungen und Objekte sowie die Gruppen "Universeller Dienst" und "Verwaltung" beschrieben, die vom Gesamtstrukturvorbereitungsschritt erstellt werden.

<div>

## <a name="active-directory-global-settings-and-objects"></a>Globale Active Directory-Einstellungen und-Objekte

Wenn Sie globale Einstellungen im Konfigurationscontainer speichern (wie dies bei allen neuen lync Server 2013-Bereitstellungen der Fall ist), verwendet die Gesamtstrukturvorbereitung den vorhandenen Dienste- **** Container und fügt unter den Konfigurations\\Diensten ein RTC-Dienstobjekt hinzu. Objekt. Unter dem RTC-Dienstobjekt fügt die Gesamtstrukturvorbereitung ein **globales Einstellungs** Objekt vom Typ Attribut msRTCSIP-Global Container hinzu. Das Global Settings-Objekt enthält alle Einstellungen, die für die lync Server-Bereitstellung gelten. Wenn Sie globale Einstellungen im Systemcontainer speichern, verwendet die Gesamtstrukturvorbereitung einen Microsoft-Container unter dem Stammdomänen Systemcontainer und ein RTC-Dienstobjekt\\unter dem Microsoft-Systemobjekt.

Bei der Gesamtstrukturvorbereitung wird auch ein neues **Attribut msRTCSIP-Domänen** Objekt für die Stammdomäne hinzugefügt, in der die Prozedur ausgeführt wird.

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a>Active Directory-universelle Dienst-und Verwaltungsgruppen

Bei der Gesamtstrukturvorbereitung werden universelle Gruppen basierend auf der von Ihnen angegebenen Domäne erstellt und für diese Gruppen Zugriffssteuerungseinträge (ACEs) hinzugefügt. In diesem Schritt werden die universellen Gruppen in den Benutzer Containern der Domäne erstellt, die Sie angeben.

Universelle Gruppen ermöglichen Administratoren den Zugriff auf und die Verwaltung globaler Einstellungen und Dienste. Bei der Gesamtstrukturvorbereitung werden die folgenden Typen von universellen Gruppen hinzugefügt:

  - **Administrative Gruppen**   diese Gruppen definieren Administratorrollen für ein lync Server-Netzwerk.

  - **Infrastrukturgruppen**   diese Gruppen bieten die Berechtigung für den Zugriff auf bestimmte Bereiche der lync Server-Infrastruktur. Sie funktionieren als Komponenten administrativer Gruppen. Sie sollten diese Gruppen nicht ändern oder Benutzer direkt hinzufügen.

  - **Dienstgruppen**   diese Gruppen sind Dienstkonten, die für den Zugriff auf verschiedene lync Server-Dienste erforderlich sind.

In der folgenden Tabelle werden die administrativen Gruppen beschrieben.

### <a name="administrative-groups-created-during-forest-preparation"></a>Während der Gesamtstrukturvorbereitung erstellte administrative Gruppen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Administrative Gruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalServerAdmins</p></td>
<td><p>Ermöglicht Mitgliedern das Verwalten von Server-und Pooleinstellungen, einschließlich aller Serverrollen, globalen Einstellungen und Benutzer.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalUserAdmins</p></td>
<td><p>Ermöglicht Mitgliedern, Benutzereinstellungen zu verwalten und Benutzer von einem Server oder Pool in einen anderen zu verschieben.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalReadOnlyAdmins</p></td>
<td><p>Ermöglicht Mitgliedern, Server-, Pool-und Benutzereinstellungen zu lesen.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Infrastrukturgruppen beschrieben.

### <a name="infrastructure-groups-created-during-forest-preparation"></a>Während der Gesamtstrukturvorbereitung erstellte Infrastrukturgruppen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Infrastrukturgruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCUniversalGlobalWriteGroup</p></td>
<td><p>Gewährt Schreibzugriff auf globale Einstellungsobjekte für lync Server.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalGlobalReadOnlyGroup</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf globale Einstellungsobjekte für lync Server.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalUserReadOnlyGroup hinzugefügt</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf die lync Server-Benutzereinstellungen.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalServerReadOnlyGroup</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server-Einstellungen. Diese Gruppe hat keinen Zugriff auf Einstellungen auf Poolebene, sondern nur auf Einstellungen, die für einen einzelnen Server spezifisch sind.</p></td>
</tr>
<tr class="odd">
<td><p>RTCUniversalSBATechnicians</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf die lync Server-Konfiguration und wird während der Installation in der lokalen Gruppe Administratoren der Überlebenden Branch-Appliances gespeichert.</p></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle werden die Dienstgruppen beschrieben.

### <a name="service-groups-created-during-forest-preparation"></a>Während der Gesamtstrukturvorbereitung erstellte Dienstgruppen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dienstgruppe</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTCHSUniversalServices</p></td>
<td><p>Enthält Dienstkonten, mit denen Front-End-Server und Standard Edition-Server ausgeführt werden. Mit dieser Gruppe können Server Lese-und Schreibzugriff auf globale lync Server-Einstellungen und Active Directory-Benutzerobjekte erhalten.</p></td>
</tr>
<tr class="even">
<td><p>RTCComponentUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die für die Ausführung von A/V-Konferenzservern, Webdiensten, Mediations Servern, Archivierungsservern und Überwachungs Servern verwendet werden.</p></td>
</tr>
<tr class="odd">
<td><p>RTCProxyUniversalServices</p></td>
<td><p>Enthält Dienstkonten, die zum Ausführen von lync Server Edge-Servern verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>RTCUniversalConfigReplicator</p></td>
<td><p>Umfasst Server, die an der Replikation des lync Server Central-Verwaltungsspeichers teilnehmen können.</p></td>
</tr>
<tr class="odd">
<td><p>RTCSBAUniversalServices</p></td>
<td><p>Gewährt schreibgeschützten Zugriff auf lync Server-Einstellungen, ermöglicht aber die Konfiguration für die Installation eines überlebensfähigen Verzweigungs Servers und die Bereitstellung von Survivable Branch Appliances.</p></td>
</tr>
</tbody>
</table>


Die Gesamtstrukturvorbereitung fügt dann den entsprechenden Infrastrukturgruppen Dienst-und Verwaltungsgruppen wie folgt hinzu:

  - RTCUniversalServerAdmins wird zu RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

  - RTCUniversalUserAdmins wird als Mitglied von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

  - RTCHSUniversalServices, RTCComponentUniversalServices und RTCUniversalReadOnlyAdmins werden als Mitglieder von RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup und RTCUniversalUserReadOnlyGroup hinzugefügt hinzugefügt.

Bei der Gesamtstrukturvorbereitung werden auch die folgenden rollenbasierten Zugriffssteuerungsgruppen erstellt:

  - CSAdministrator

  - CSArchivingAdministrator

  - CSHelpDesk

  - CSLocationAdministrator

  - CSResponseGroupAdministrator

  - CSServerAdministrator

  - CSUserAdministrator

  - CSViewOnlyAdministrator

  - CSVoiceAdministrator

  - CsPersistentChatAdministator

  - CsResponseGroupManager

Details zu den Rollen und den jeweils zulässigen Aufgaben finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in der Planungsdokumentation.

Bei der Gesamtstrukturvorbereitung werden sowohl private als auch öffentliche ACEs erstellt. Es werden private ACEs im Container für globale Einstellungen erstellt, der von lync Server verwendet wird. Dieser Container wird nur von lync Server verwendet und befindet sich entweder im Konfigurationscontainer oder im System Container in der Stammdomäne, je nachdem, wo Sie die globalen Einstellungen speichern. Die von der Gesamtstrukturvorbereitung erstellten öffentlichen ACEs sind in der folgenden Tabelle aufgelistet.

### <a name="public-aces-created-by-forest-preparation"></a>Von der Gesamtstrukturvorbereitung erstellte öffentliche ACEs

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ACE</th>
<th>RTCUniversalGlobalReadOnlyGroup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Root Domain System Container (nicht geerbt)<strong>*</strong></p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>Lesen des DisplaySpecifiers-Containers der Konfiguration (nicht geerbt)</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>*</STRONG>Nicht geerbte ACEs gewähren unter diesen Containern keinen Zugriff auf untergeordnete Objekte. ACEs, die geerbt werden, gewähren Zugriff auf untergeordnete Objekte unter diesen Containern.



</div>

Im Konfigurationscontainer führt die Gesamtstrukturvorbereitung unter dem Konfigurationsnamenskontext die folgenden Aufgaben aus:

  - Fügt einen Eintrag **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** für die **RTC-Eigenschaften** Seite unter den Attributen adminContextMenu und adminPropertyPages des Sprachanzeige Bezeichners für Benutzer, Kontakte und inetOrgPerson hinzu (beispielsweise CN = Benutzeranzeige, CN = 409, CN = DisplaySpecifiers).

  - Fügt unter **Erweiterte Rechte** , die für die Benutzer-und Kontaktklassen gelten, ein **RTCPropertySet** -Objekt vom Typ **controlAccessRight** hinzu.

  - Fügt unter **Erweiterte Rechte** , die für Benutzer-, Kontakt-, ou-und domainDNS-Klassen gelten, ein **RTCUserSearchPropertySet** -Objekt vom Typ **controlAccessRight** hinzu.

  - Fügt **Attribut msRTCSIP-PrimaryUserAddress** unter dem **extraColumns** -Attribut des jeweiligen Anzeigebezeichners der sprach Organisationseinheit (z. b. CN = organizationalUnit-Display, CN = 409, CN = DisplaySpecifiers) hinzu und kopiert die Werte der **extraColumns** -Attribut der Standardanzeige (beispielsweise CN = default-Display, CN = 409, CN = DisplaySpecifiers).

  - Fügt **Attribut msRTCSIP-PrimaryUserAddress**-, **Attribut msRTCSIP-PrimaryHomeServer**-und **Attribut msRTCSIP-UserEnabled-** Filterattribute unter dem **attributeDisplayNames** -Attribut jedes Sprachanzeige Bezeichners für Benutzer, Kontakte, und InetOrgPerson-Objekte (beispielsweise in Englisch: CN = User-Display, CN = 409, CN = DisplaySpecifiers).

</div>

</div>

<span> </span>

</div>

</div>

</div>

