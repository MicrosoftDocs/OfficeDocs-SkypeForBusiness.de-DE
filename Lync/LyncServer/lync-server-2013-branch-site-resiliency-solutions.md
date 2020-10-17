---
title: 'Lync Server 2013: Ausfall Sicherheitslösungen für Zweigstellenstandorte'
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
ms.openlocfilehash: 25541f7681ece7b299d6e4c8076fb190382650ba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512982"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Ausfall Sicherheitslösungen für Zweigstellenstandorte in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-10_

Das Bereitstellen von Ausfallsicherheit für Zweigstellenstandorte bietet offensichtliche Vorteile. Insbesondere wenn Sie die Verbindung mit dem zentralen Standort verlieren, verfügen die Zweigstellenbenutzer weiterhin über Enterprise-VoIP-Dienst und Voicemail (wenn Sie Einstellungen für die Umleitung von Voicemail konfigurieren; Weitere Informationen finden Sie unter Anforderungen an die [Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Für Standorte mit weniger als 25 Benutzern ist die Implementierung einer Ausfallsicherheitslösung jedoch möglicherweise nicht ausreichend rentabel.

Wenn Sie sich zur Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte entschließen, haben Sie drei Möglichkeiten. Entscheiden Sie mithilfe der folgenden Tabelle, welche Option für Sie geeignet ist.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Situation</th>
<th>Empfehlung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Host mit 25 bis 1.000 Benutzern am Zweigstellenstandort, wobei eine vollständige Bereitstellung nicht rentabel ist oder kein administrativer Support zur Verfügung steht</p></td>
<td><p>Survivable Branch Appliance</p>
<p>Das Survivable Branch Appliance ist ein Industriestandard-Blade-Server mit einer lync Server Registrierungsstelle und Vermittlungsserver, die auf Windows Server 2008 R2 läuft. Das Survivable Branch Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network). Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im Programm zur SBA-Qualifizierung/-Zertifizierung) bieten bei einem WAN-Ausfall eine dauerhafte PSTN-Verbindung (Public Switched Telephone Network, Telefonfestnetz), es werden jedoch keine ausfallsicheren Anwesenheits- und Konferenzfeatures bereitgestellt, da diese Features von den Front-End-Servern am zentralen Standort abhängen.</p>
<p>Ausführliche Informationen zu Survivable Branch Appliances finden Sie unter &quot; Survivable Branch Appliance Details &quot; weiter unten in diesem Thema.</p>
<p><strong>Hinweis:</strong> Wenn Sie sich entscheiden, auch einen SIP-Trunk mit Ihrem Survivable Branch Appliance zu verwenden, wenden Sie sich an Ihren Survivable Branch Appliance-Anbieter, um zu erfahren, welcher Dienstanbieter am besten für Ihre Organisation geeignet ist.</p></td>
</tr>
<tr class="even">
<td><p>Host zwischen 1000 und 2000 Benutzern an Ihrem Zweigstellenstandort, keine ausfallsichere WAN-Verbindung, und Sie haben lync Server Administratoren zur Verfügung gestellt</p></td>
<td><p>Survivable Branch Server oder zwei Survivable Branch Appliances.</p>
<p>Bei der Survivable Branch Server handelt es sich um eine Windows Server-Sitzung, für die die Hardwareanforderungen festgelegt sind, auf denen lync Server Registrierungsstelle und Vermittlungsserver Software installiert ist. Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein.</p>
<p>Ausführliche Informationen zu Survivable Branch-Servern finden Sie unter &quot; Survivable Branch Server Details &quot; weiter unten in diesem Thema.</p></td>
</tr>
<tr class="odd">
<td><p>Wenn Sie zusätzlich zu den VoIP-Funktionen für bis zu 5000 Benutzer Anwesenheits-und Konferenzfunktionen benötigen und lync Server Administratoren verfügbar gemacht haben</p></td>
<td><p>Führen Sie statt einer Zweigstellenbereitstellung eine Bereitstellung als zentraler Standort mit einem Standard Edition-Server durch.</p>
<p>Eine umfassende lync Server-Bereitstellung bietet eine durchgehende PSTN-Verbindung und eine belastbare Anwesenheits-und Konferenzfunktion bei einem WAN-Ausfall.</p>
<p>Ausführliche Informationen zur Vorbereitung dieser Lösung finden Sie unter <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">bestimmen der Systemanforderungen für lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">bestimmen der Infrastrukturanforderungen für lync Server 2013</a>und anderer relevanter Abschnitte der Planungsdokumentation.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologien zur Bereitstellung von Ausfallsicherheit

Die folgende Abbildung zeigt die empfohlenen Topologien zum Gewährleisten von Ausfallsicherheit für einen Zweigstellenstandort.

**Optionen für die Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte**

![Optionen für die Ausfallsicherheit von VoIP-Zweigstellen](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Optionen für die Ausfallsicherheit von VoIP-Zweigstellen")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Details zur Survivable Branch Appliance

Die lync Server Survivable Branch Appliance umfasst die folgenden Komponenten:

  - Einen Registrierungsserver für Benutzerauthentifizierung, Registrierung und Anrufrouting

  - Einen Vermittlungsserver für die Signalverarbeitung zwischen der Registrierung und einem PSTN-Gateway

  - Ein PSTN-Gateway zum Routen von Anrufen an das Telefonfestnetz als Fallback bei WAN-Ausfällen

  - SQL Server Express zur Speicherung lokaler Benutzerdaten

Das Survivable Branch Appliance enthält auch PSTN-Trunks, analoge Ports und einen Ethernet-Adapter.

Wenn die WAN-Verbindung der Zweigstelle zu einem zentralen Standort nicht mehr verfügbar ist, werden interne Zweigstellenbenutzer weiterhin bei der Survivable Branch Appliance Registrierungsstelle registriert und erhalten unterbrechungsfreie Sprachdienste über die Survivable Branch Appliance-Verbindung mit dem PSTN. Zweigstellenbenutzer, die von zu Hause oder von Remotestandorten aus eine Verbindung herstellen, können sich beim Registrierungsserver am zentralen Standort registrieren, wenn die WAN-Leitung zum Zweigstellenstandort nicht verfügbar ist. Diese Benutzer haben Zugriff auf die vollständige Unified Communications-Funktionalität (UM), mit der Ausnahme, dass eingehende Anrufe am Zweigstellenstandort an das Voicemailsystem übermittelt werden. Wenn die WAN-Verbindung wieder verfügbar ist, sollte für Benutzer am Zweigstellenstandort automatisch die vollständige Funktionalität wiederhergestellt werden. Weder das Failover auf die Survivable Branch Appliance noch die Wiederherstellung des Diensts erfordert das vorhanden sein eines IT-Administrators.

Lync Server unterstützt bis zu zwei Survivable Branch Appliance an einem Zweigstellenstandort.

<div>


> [!NOTE]  
> Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Übersicht über die Bereitstellung einer Survivable Branch Appliance

Das Survivable Branch Appliance wird von Herstellern von Originalgeräten in Partnerschaft mit Microsoft hergestellt und in Ihrem Auftrag von Wert Schöpfungs Händlern bereitgestellt. Diese Bereitstellung sollte nur erfolgen, nachdem lync Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit dem Zweigstellenstandort vorhanden ist und Zweigstellenbenutzer für Enterprise-VoIP aktiviert sind.

Ausführliche Informationen zu diesen Phasen finden Sie unter [Deploying a Survivable Branch Appliance or Server with lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in der Bereitstellungsdokumentation.


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
<td><p>Einrichten Active Directory-Domänendienste für die Survivable Branch Appliance</p></td>
<td><p><strong>Am zentralen Standort:</strong></p>
<ol>
<li><p>Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch Appliance am Zweigstellenstandort installieren und aktivieren wird.</p></li>
<li><p>Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)) für Survivable Branch Appliance in Active Directory-Domänendienste.</p></li>
<li><p>Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch Appliance.</p></li>
</ol></td>
<td><p>Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein. Die Survivable Branch Appliance müssen zur Gruppe RTCSBAUniversalServices gehören, die automatisch bei Verwendung des Topologie-Generators erfolgt.</p></td>
</tr>
<tr class="even">
<td><p>Installieren und aktivieren Sie die Survivable Branch Appliance.</p></td>
<td><p><strong>Am Zweigstellenstandort:</strong></p>
<ol>
<li><p>Verbinden Sie die Survivable Branch Appliance mit einem Ethernet-Port und einem PSTN-Port.</p></li>
<li><p>Starten Sie die Survivable Branch Appliance.</p></li>
<li><p>Fügen Sie die Survivable Branch Appliance der Domäne mithilfe des Domänenbenutzerkontos hinzu, das für die Survivable Branch Appliance am zentralen Standort erstellt wurde. Legen Sie FQDN und IP-Adresse auf den FQDN fest, den Sie im Computerkonto erstellt haben.</p></li>
<li><p>Konfigurieren Sie die Survivable Branch Appliance mithilfe der OEM-Benutzeroberfläche.</p></li>
<li><p>Testen Sie die PSTN-Anbindung.</p></li>
</ol></td>
<td><p>Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Details zum Survivable Branch Server

Erstellen Sie im Topologie-Generator den Zweigstellenstandort, fügen Sie den Survivable Branch Server zu diesem Standort hinzu, und führen Sie dann den Assistenten für die lync Server-Bereitstellung auf dem Computer aus, auf dem Sie die Rolle installieren möchten.

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

