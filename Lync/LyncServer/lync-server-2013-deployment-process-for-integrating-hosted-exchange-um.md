---
title: 'Lync Server 2013: Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste'
TOCTitle: Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste in Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398968(v=OCS.15)
ms:contentKeyID: 49295614
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für die Integration gehosteter Exchange UM-Dienste in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Für eine effektive Planung der Integration von Lync Server 2013 in gehostete Exchange Unified Messaging-Dienste (UM) müssen Sie Folgendes berücksichtigen:

  - Voraussetzungen für die Integration von Lync Server 2013 in gehostete Exchange Unified Messaging-Dienste

  - Erforderliche Schritte während des Integrationsprozesses

## Bereitstellungsvoraussetzungen für die Integration in gehostete Exchange UM-Dienste

Bevor Sie mit der Integration beginnen, müssen Sie bereits Lync Server 2013 (Mindestvoraussetzung sind ein Front-End-Pool oder ein Standard Edition-Server), einen Edgeserver und Lync 2013- oder Lync 2010-Clients bereitgestellt haben.

## Integrationsprozess

Die folgende Tabelle zeigt eine Übersicht über den Integrationsprozess der gehosteten Exchange Unified Messaging-Dienste. Ausführliche Informationen zu den Bereitstellungsschritten finden Sie unter [Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in der Bereitstellungsdokumentation.


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
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Konfigurieren des Edgeservers für die Integration in gehostete Exchange UM-Dienste</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren der Richtlinie für gehostete Voicemail</p></td>
<td><ol>
<li><p>Ändern Sie entweder die globale Richtlinie für gehostete Voicemail, oder erstellen Sie eine neue Richtlinie für gehostete Voicemail auf Standort- oder Benutzerebene.</p></li>
<li><p>Weisen Sie auf Benutzerebene erstellte Richtlinien den geeigneten Benutzern oder Gruppen zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Verwalten von Richtlinien für gehostete Voicemail in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Aktivieren von Benutzerkonten für gehostete Voicemail</p></td>
<td><ul>
<li><p>Konfigurieren Sie Benutzerkonten für Benutzer, deren Postfächer sich in einem gehosteten Exchange-Dienst befinden.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Aktivieren von Benutzern für gehostete Voicemail in Lync Server 2013</a></p></td>
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
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Erstellen von Kontaktobjekten für gehostete Exchange UM-Dienste in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

