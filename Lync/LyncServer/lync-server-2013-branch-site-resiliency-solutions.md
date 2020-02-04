---
title: 'Lync Server 2013: Ausfallsicherheitslösungen für Zweigstellenstandorte'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Ausfallsicherheitslösungen für Zweigstellenstandorte in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-10_

Es gibt offensichtliche Vorteile für die Bereitstellung von Ausfallsicherheit für Zweigstellen in Ihrer Organisation. Insbesondere wenn Sie die Verbindung mit dem zentralen Standort verlieren, verfügen die Benutzer von Zweigstellenbenutzern weiterhin über Enterprise-VoIP-Dienst und Voicemail (wenn Sie die Einstellungen für die Neukonfiguration von Voicemail konfigurieren; Einzelheiten finden Sie unter Anforderungen an die [Standort Stabilität von lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Bei Websites mit weniger als 25 Benutzern bietet eine Lösung für Ausfallsicherheit möglicherweise keine ausreichende Rentabilität.

Wenn Sie sich für die Bereitstellung von Ausfallsicherheit für Zweigstellen entscheiden, stehen Ihnen drei Optionen zur Verfügung. In der folgenden Tabelle können Sie die beste Option für Ihre Organisation ermitteln.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Wenn Sie...</th>
<th>Wir empfehlen die Verwendung einer...</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hosten Sie zwischen 25 und 1000 Benutzern an ihrer Zweigstelle, und wenn die Kapitalrendite keine vollständige Bereitstellung unterstützt oder wenn die lokale administrative Unterstützung nicht verfügbar ist</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Die Survivable Branch-Appliance ist ein branchenüblicher Blade-Server mit einer lync Server-Registrierungsstelle und einem Vermittlungsserver, die unter Windows Server 2008 R2 ausgeführt werden. Die Survivable Branch-Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network). Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im SBA-Qualifizierungs-/-Zertifizierungsprogramm) bieten eine durchgehende PSTN-Verbindung im Fall eines WAN-Fehlers, doch dieser Ansatz bietet keine belastbaren Anwesenheits-und Konferenzfunktionen, da diese Features von Front-End-Servern am zentralen Standort abhängen.</p>
<p>Details zu Überlebenden Branch-Appliances finden &quot;Sie&quot; weiter unten in diesem Thema unter Survivable Branch Appliance Details.</p>
<p><strong>Hinweis:</strong> Wenn Sie sich entscheiden, auch einen SIP-Trunk für Ihre Survivable Branch-Appliance zu verwenden, wenden Sie sich an den Anbieter von Survivable Branch Appliance, um zu erfahren, welcher Dienstanbieter für Ihre Organisation am besten geeignet ist.</p></td>
</tr>
<tr class="even">
<td><p>Hosten zwischen 1000-und 2000-Benutzern an ihrer Zweigstelle, keine robuste WAN-Verbindung und geschulte lync Server-Administratoren verfügbar</p></td>
<td><p>Überlebensfähiger Branch-Server oder zwei überlebensfähige Branch-Appliances.</p>
<p>Bei dem Überlebenden Verzweigungs Server handelt es sich um eine Windows Server-Besprechung, die die Hardwareanforderungen enthält, auf denen die lync Server Registrar-und Mediation Server-Software installiert ist. Sie muss mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen werden.</p>
<p>Details zu Überlebenden Verzweigungs Servern finden Sie &quot;&quot; weiter unten in diesem Thema unter Informationen zu Überlebenden Verzweigungs Servern.</p></td>
</tr>
<tr class="odd">
<td><p>Wenn Sie zusätzlich zu den Sprachfeatures für bis zu 5000-Benutzer Anwesenheits-und Konferenzfeatures benötigen und die lync Server-Administratoren verfügbar sind</p></td>
<td><p>Bereitstellen als zentrale Website mit einem Standard Edition-Server und nicht als Verzweigungs Website</p>
<p>Eine umfassende lync Server-Bereitstellung bietet eine durchgehende PSTN-Verbindung sowie eine zuverlässige Anwesenheits-und Konferenzfunktion bei einem WAN-Fehler.</p>
<p>Details zum Vorbereiten dieser Lösung finden Sie unter <a href="lync-server-2013-planning-for-your-organization.md">Organisationsplanung für lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln der Systemanforderungen für lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Ermitteln der Infrastrukturanforderungen für lync Server 2013</a>und anderer relevanter Abschnitte der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Stabilitäts Topologien

Die folgende Abbildung zeigt die empfohlenen Topologien für die Ausfallsicherheit von Zweigstellen.

**Stabilitäts Optionen für Zweigstellenstandorte**

![Optionen für die Widerstandsfähigkeit der sprach Verzweigung](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Optionen für die Widerstandsfähigkeit der sprach Verzweigung")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Details zu Survivable Branch Appliances

Die lync Server Survivable Branch-Appliance umfasst die folgenden Komponenten:

  - Eine Registrierungsstelle für Benutzerauthentifizierung, Registrierung und Anrufweiterleitung

  - Ein Vermittlungs Server für die Verarbeitung der Signalübertragung zwischen der Registrierungsstelle und einem PSTN-Gateway

  - Ein PSTN-Gateway zum Weiterleiten von Anrufen an das PSTN als Fall Back Transport bei einem WAN-Ausfall

  - SQL Server Express für den lokalen Benutzerdatenspeicher

Die Survivable Branch-Appliance umfasst außerdem PSTN-Stämme, analoge Anschlüsse und einen Ethernet-Adapter.

Wenn die WAN-Verbindung der Zweigstelle zu einem zentralen Standort nicht mehr zur Verfügung steht, werden Benutzer der internen Verzweigung weiterhin bei der überlebensfähigen Branch Appliance-Registrierungsstelle registriert und erhalten unterbrechungsfreien Sprachdienst mithilfe der Survivable Branch Appliance-Verbindung. ins Festnetz. Zweigstellenbenutzer, die eine Verbindung von zu Hause aus oder aus anderen Remotestandorten herstellen, können sich bei einem Registrierungsstellen Server an einem zentralen Standort registrieren, wenn die WAN-Verbindung zur Zweigstelle nicht verfügbar ist. Diese Benutzer verfügen über eine vollständige Unified Communications-Funktion, mit der Ausnahme, dass eingehende Anrufe an die Zweigstelle an die Voicemail weitergesendet werden. Wenn die WAN-Verbindung verfügbar wird, sollte die vollständige Funktionalität für Benutzer der Verzweigungs Website wiederhergestellt werden. Weder das Failover auf die Survivable Branch-Appliance noch die Wiederherstellung des Diensts erfordert das vorhanden sein eines IT-Administrators.

Lync Server unterstützt bis zu zwei überlebensfähige Branch-Appliances an einer Zweigstelle.

<div>


> [!NOTE]  
> Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Übersicht über Survivable Branch Appliance-Bereitstellung

Die Survivable Branch Appliance wird von Herstellern von Originalgeräten in Partnerschaft mit Microsoft hergestellt und in deren Auftrag von Wert Schöpfungs Händlern bereitgestellt. Diese Bereitstellung sollte erst erfolgen, nachdem lync Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit der Zweigstelle vorhanden ist und die Benutzer von Zweigstellenbenutzern für Enterprise-VoIP aktiviert sind.

Ausführliche Informationen zu diesen Phasen finden Sie unter [Bereitstelleneiner Survivable Branch-Appliance oder eines Servers mit lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in der Bereitstellungsdokumentation.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Benutzerrechte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einrichten von Active Directory-Domänendiensten für die Survivable Branch Appliance</p></td>
<td><p><strong>Auf der zentralen Website:</strong></p>
<ol>
<li><p>Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch-Appliance auf der Zweigstelle installieren und aktivieren wird.</p></li>
<li><p>Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)) für Survivable Branch Appliance in den Active Directory-Domänendiensten.</p></li>
<li><p>Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch-Appliance.</p></li>
</ol></td>
<td><p>Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein. Die Survivable Branch-Appliance muss zur RTCSBAUniversalServices-Gruppe gehören, die automatisch erfolgt, wenn Sie den Topology Builder verwenden.</p></td>
</tr>
<tr class="even">
<td><p>Installieren Sie die Survivable Branch-Appliance, und aktivieren Sie Sie.</p></td>
<td><p><strong>Auf der Zweigstelle:</strong></p>
<ol>
<li><p>Verbinden Sie die Survivable Branch-Appliance mit einem Ethernet-Port und einem PSTN-Anschluss.</p></li>
<li><p>Starten Sie die Survivable Branch-Appliance.</p></li>
<li><p>Nehmen Sie an der Überlebenden Branch-Appliance mit dem Domänenbenutzerkonto Teil, das für die Survivable Branch-Appliance am zentralen Standort erstellt wurde. Legen Sie den FQDN und die IP-Adresse so ein, dass er dem FQDN entspricht, der im Computerkonto erstellt wurde.</p></li>
<li><p>Konfigurieren Sie die Survivable Branch-Appliance mithilfe der OEM-Benutzeroberfläche.</p></li>
<li><p>Testen Sie die PSTN-Konnektivität.</p></li>
</ol></td>
<td><p>Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Informationen zu Überlebenden Verzweigungs Servern

Erstellen Sie im Topologie-Generator die Verzweigungs Website, fügen Sie den Überlebenden Verzweigungs Server zu dieser Website hinzu, und führen Sie dann den lync Server-Bereitstellungs-Assistenten auf dem Computer aus, auf dem Sie die Rolle installieren möchten.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

