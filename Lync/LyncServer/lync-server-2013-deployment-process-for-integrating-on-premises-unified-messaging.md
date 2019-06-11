---
title: Bereitstellungsprozess für die Integration von lokalen Unified Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7147a83bad1ed8b5cacc369d8d64e71fcaac32b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-12-17_

Wenn Sie Exchange Unified Messaging (um) in lync Server 2013 integrieren möchten, müssen Sie die in diesem Thema beschriebenen Aufgaben ausführen. Stellen Sie außerdem sicher, dass Sie die bewährten Methoden für die Planung und Bereitstellung überprüfen, die unter [Richtlinien für die Integration von lokalen Unified Messaging und lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)beschrieben sind. In diesem Thema wird davon ausgegangen, dass Sie lync Server 2013 mit einem zusammengefassten Vermittlungsserver bereitgestellt haben und dass Sie Benutzer für lync Server 2013 aktiviert haben, aber nicht unbedingt, dass Sie alle Bereitstellungs-und Konfigurationsschritte ausgeführt haben, um Enterprise-VoIP zu aktivieren, wie beschrieben unter [Bereitstellen von Enterprise-VoIP in lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in der Bereitstellungsdokumentation.

<div>

## <a name="unified-messaging-integration-process"></a>Integrationsprozess für Unified Messaging (UM)

<div>


> [!IMPORTANT]
> Es ist wichtig, dass Sie sich bezüglich der durchzuführenden Aufgaben mit den Exchange-Administratoren in Ihrer Organisation absprechen, um eine nahtlose und erfolgreiche Integration sicherzustellen.



</div>


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
<th>Erforderliche Gruppen und Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Stellen Sie eine der folgenden Exchange-Versionen bereit:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) oder neuestes Service Pack</p></li>
<li><p>Microsoft Exchange Server 2010 oder neuestes Service Pack</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Wenn Sie Microsoft Exchange Server 2013 verwenden, installieren Sie die folgenden Exchange-Serverrollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</p>
<ul>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn Microsoft Exchange Server 2013 und Exchange Unified Messaging (um) in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur vertraut.</p>
<p>Wenn Sie Exchange 2010 verwenden, installieren Sie die folgenden Exchange-Serverrollen entweder in der gleichen Gesamtstruktur oder in einer anderen Gesamtstruktur wie lync Server 2013:</p>
<ul>
<li><p>Unified Messaging</p></li>
<li><p>Hub-Transport</p></li>
<li><p>Clientzugriff</p></li>
<li><p>Postfach</p></li>
</ul>
<p>Wenn lync Server 2013 und Exchange Unified Messaging (um) in verschiedenen Gesamtstrukturen installiert sind, konfigurieren Sie jede Exchange-Gesamtstruktur so, dass Sie der lync Server 2013-Gesamtstruktur vertraut.</p></td>
<td><p>Organisations-Admins (wenn es sich um den ersten Exchange Server in der Organisation handelt)</p>
<p>- oder -</p>
<p>Exchange-Organisationsadministrator (wenn es sich nicht um den ersten Exchange Server in der Organisation handelt)</p></td>
<td><p>Weitere Informationen finden Sie in der Dokumentation zur jeweiligen Version von Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Exchange Server 2007-Bereitstellungs <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>Dokumentation unter.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 oder neueste Service Pack-Bereitstellungs <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Dokumentation unter.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013-Planung und- <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>Bereitstellung bei.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Installieren Sie Zertifikate.</p></td>
<td><p>Laden Sie Zertifikate für jeden Exchange um-Server von einer vertrauenswürdigen Stammzertifizierungsstelle herunter, und installieren Sie Sie. Die Zertifikate sind für MTLS (Mutual Transport Level Security) zwischen den Servern mit Exchange um und lync Server 2013 erforderlich.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird</a></p></td>
</tr>
<tr class="odd">
<td><p>Erstellen und Konfigurieren eines neuen Exchange um-SIP-Wählplans</p></td>
<td><p>Erstellen Sie auf dem Exchange um-Server einen SIP-Wählplan, der auf den spezifischen Bereitstellungsanforderungen Ihrer Organisation basiert.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p>Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Erstellen eines Unified Messaging-SIP-&quot; URI <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>-Wähl Plans unter.</p>
<p>Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Erstellen eines&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>-Wählplans unter.</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie die Sicherheitseinstellungen für den Exchange um-SIP-Wählplan.</p></td>
<td><p>Um Enterprise-VoIP-Datenverkehr zu verschlüsseln, konfigurieren Sie die Sicherheitseinstellungen für den Exchange um-SIP-Wählplan als <strong>SIP-gesichert</strong> oder <strong>gesichert</strong>. Dies ist ein besonders wichtiger Schritt, wenn Sie lync Phone Edition-Geräte in Ihrer Umgebung bereitgestellt oder geplant haben. Damit lync Phone Edition-Geräte in einer Umgebung mit Exchange um-Integration funktionieren, müssen die lync Server-Verschlüsselungseinstellungen mit den Sicherheitseinstellungen für den Exchange um-Wählplan ausgerichtet werden. Ausführliche Informationen zu diesem Thema finden Sie in der Bereitstellungsdokumentation.</p></td>
<td><p>Exchange-Organisationsadministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</a></p>
<p>Für Exchange 2007 SP1 oder das neueste Service Pack siehe auch:</p>
<p>&quot;Informationen zum Konfigurieren der Sicherheit für einen Unified Messaging-&quot; Wählplan <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>finden Sie unter.</p>
<p>Informationen zu Exchange&#160;2010 oder neuestes Service Pack finden Sie auch hier:</p>
<p>&quot;Konfigurieren der VoIP&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>-Sicherheit für einen um-Wählplan</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</p></td>
</tr>
<tr class="odd">
<td><p>Fügen Sie dem Exchange um-SIP-Wählplan Unified Messaging-Server hinzu.</p></td>
<td><p>Wenn Sie einen neu installierten Unified Messaging-Server zur Entgegennahme und Verarbeitung eingehender Anrufe aktivieren möchten, müssen Sie den Unified Messaging-Server einem UM-Wählplan hinzufügen. Fügen Sie in diesem Fall den Server dem Exchange um-SIP-Wählplan hinzu.</p></td>
<td><p>Administratoren</p>
<p>Exchange-Serveradministratoren</p></td>
<td><p>Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Hinzufügen eines Unified Messaging-Servers&quot; zu <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>einem Wählplan unter.</p>
<p>Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Anzeigen oder Konfigurieren der Eigenschaften eines&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>-Servers.</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren Sie Postfächer mit SIP-Adressen.</p></td>
<td><p>Weisen Sie den Postfächern von Enterprise-VoIP-Benutzern, die Exchange um-Features verwenden werden, SIP-Adressen zu.</p></td>
<td><p>Lync Server 2013-Administrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter Hinzufügen, entfernen oder Ändern einer SIP-Adresse für einen um-&quot; aktivierten <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a>Benutzer unter.</p>
<p>Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Ändern einer SIP-Adresse für einen&quot; um <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>-aktivierten Benutzer unter.</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Skript "exchucutil.ps1" aus.</p></td>
<td><p>Öffnen Sie auf dem Server, auf dem Exchange um-Dienste ausgeführt wird, die Exchange-Verwaltungsshell, und führen Sie das exchucutil. ps1-Skript aus, das Folgendes ausführt:</p>
<ul>
<li><p>Erteilt lync Server 2013 die Berechtigung zum Lesen von Exchange um-Active Directory-Domänendienst Objekten, insbesondere den SIP-Wählplänen, die in der vorherigen Aufgabe erstellt wurden.</p></li>
<li><p>Erstellt ein Unified Messaging-IP-Gateway-Objekt in Active Directory für jeden lync Server 2013 Enterprise Edition-Pool oder Standard Edition-Server, der Benutzer hostet, die für Enterprise-VoIP aktiviert sind.</p></li>
<li><p>Erstellt einen Exchange um-Sammelanschluss für jedes Gateway. Die Pilot-ID des Sammelanschlusses ist der Name des Wählplans, der dem entsprechenden Gateway zugeordnet ist. Es muss sich um eine 1:1-Zuordnung handeln, wenn mehrere Wählpläne verwendet werden.</p></li>
</ul></td>
<td><p>Exchange-Organisationsadministrator</p>
<p>Exchange-Empfängeradministrator</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Konfigurieren von Unified Messaging in Microsoft Exchange für lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von lync Server 2013-Wählplänen</p></td>
<td><p>Wenn Sie in Exchange 2007 SP1 oder in das neueste Service Pack oder Exchange 2010 integriert sind, erstellen Sie einen neuen Enterprise-VoIP-Wählplan mit einem Namen, der dem vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange um-Wählplans entspricht.</p>



> [!NOTE]
> Sie müssen dies für jeden UM-Wählplan durchführen.


<p>Wenn Sie die Integration in Exchange 2010 SP1 durchführen, stellen Sie sicher, dass geeignete Einstellungen für Enterprise-sprach Wählpläne auf globaler/Websiteebene oder auf Poolebene konfiguriert wurden.</p>



> [!NOTE]
> Wenn Sie in Exchange 2010 SP1 integriert sind, müssen die Namen für den lync Server-Wählplan und die Exchange um-SIP-Wähleinstellungen nicht übereinstimmen.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Konfigurieren von Wählplänen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Führen Sie das Exchange um-integrationstool aus.</p></td>
<td><p>Führen Sie auf dem lync Server 2013 die <strong>OCSUMUtil. exe</strong>aus, die:</p>
<ul>
<li><p>Erstellen von Kontaktobjekten für Teilnehmerzugriff und automatische Telefonzentrale.</p></li>
<li><p>Überprüft, ob ein Enterprise-VoIP-Wählplan mit einem Namen vorhanden ist, der dem FQDN des Exchange um-Wählplans entspricht. Wenn Sie Exchange 2010 SP1 oder höher ausführen, müssen die Namen des Wählplans nicht übereinstimmen, und Sie können die Warnung des Tools dazu ignorieren.</p></li>
</ul>
<p>Dieses Tool scannt die Active Directory für Exchange um-Einstellungen und ermöglicht es dem lync Server 2013-Administrator, Kontaktobjekte anzuzeigen, zu erstellen und zu bearbeiten.</p></td>
<td><p>RTCUniversalServerAdmins  <em>und </em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Zur erfolgreichen Ausführung von "ocsumutil.exe" muss der Benutzer beiden dieser Gruppe angehören.





> [!NOTE]
> Zum Erstellen von Kontaktobjekten muss der Benutzer, der ocsumutil.exe ausführt, über geeignete Berechtigungen für die Active Directory-Organisationseinheit (Organizational Unit, OU) verfügen, in der die neuen Kontaktobjekte gespeichert werden. Diese Berechtigungen können gewährt werden, indem das Cmdlet <STRONG>Grant-CsOUPermission</STRONG> ausgeführt wird. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Konfigurieren von Lync Server 2013 für die Zusammenarbeit mit Unified Messaging auf Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Führen Sie bei Bedarf andere Enterprise-VoIP-Konfigurationsschritte aus.</p></td>
<td><p>Wenn Sie die Enterprise-VoIP-Einstellungen für Ihre Server oder Benutzer noch nicht konfiguriert haben, führen Sie eine oder mehrere der folgenden Aktionen aus:</p>
<ul>
<li><p>Bereitstellen und Konfigurieren</p>
<p>PSTN-Gateways und Vermittlungsservern</p></li>
<li><p>Definieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und ausgehenden Anrufrouten</p></li>
<li><p>Aktivieren von Benutzern für Enterprise-VoIP</p></li>
<li><p>(Optional) Konfigurieren von Wähleinstellungen für bestimmte Benutzer</p></li>
</ul>
<p>Je nach den von Ihnen aktivierten Enterprise-VoIP-Features sind möglicherweise andere Konfigurationsschritte erforderlich.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Siehe die Themen in den folgenden Abschnitten:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Konfigurieren von VoIP-Richtlinien, PSTN-Verwendungsdatensätzen und VoIP-Routen in lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Bereitstellen von Enterprise-VoIP in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Aktivieren Sie Enterprise-VoIP-Benutzer für Exchange um.</p></td>
<td><p>Stellen Sie auf dem Exchange um-Server sicher, dass eine Unified Messaging-Postfachrichtlinie erstellt wurde und dass jeder Benutzer eine eindeutige Durchwahlnummern Zuweisung hat, und aktivieren Sie dann den Benutzer für Unified Messaging.</p></td>
<td><p>Exchange-Empfängeradministrator</p></td>
<td><p>Informationen zu Exchange 2007 SP1 oder neuestem Service Pack &quot;finden Sie unter so wird es gemacht:&quot; aktivieren <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>eines Benutzers für Unified Messaging unter.</p>
<p>Informationen zu Exchange 2010 oder dem neuesten Service Pack &quot;finden Sie unter Aktivieren eines Benutzers&quot; für <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>Unified Messaging unter.</p>
<p>Informationen zu Exchange 2013 finden Sie unter Unified <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>Messaging unter.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

