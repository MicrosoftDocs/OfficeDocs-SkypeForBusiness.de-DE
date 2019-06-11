---
title: 'Lync Server 2013: Planen von VoIP-Ausfallsicherheit für den zentralen Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13195c50e88c035b0775d2958cf62cf71f7924c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planen von VoIP-Ausfallsicherheit für den zentralen Standort in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-30_

In zunehmendem Maße haben Unternehmen mehrere Websites, die sich auf der ganzen Welt verteilen. Die Verwaltung von Notfalldiensten, der Zugriff auf den Helpdesk und die Möglichkeit, wichtige Geschäftsaufgaben auszuführen, wenn eine zentrale Website nicht mehr zur Verfügung steht, ist für die Lösung von Enterprise-VoIP-Resilienz unerlässlich. Wenn eine zentrale Website nicht mehr verfügbar ist, müssen die folgenden Bedingungen erfüllt sein:

  - Sprach-Failover muss bereitgestellt werden.

  - Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich mit einem alternativen Front-End-Pool registrieren können. Dies kann durch Erstellen mehrerer DNS-SRV-Einträge erfolgen, die jeweils zu einem Director-Pool oder einem Front-End-Pool in jeder ihrer zentralen Websites aufgelöst werden. Sie können die Priorität und die Gewichtung der SRV-Einträge anpassen, damit Benutzer, die von dieser zentralen Website bedient werden, den entsprechenden Director und den Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.

  - Anrufe an und von Benutzern, die sich an anderen Standorten befinden, müssen an das PSTN umgeleitet werden.

In diesem Thema wird die empfohlene Lösung zum Sichern der VoIP-Stabilität der zentralen Website beschrieben.

<div>

## <a name="architecture-and-topology"></a>Architektur und Topologie

Für die Planung der sprach Stabilität an einem zentralen Standort ist ein grundlegendes Verständnis der zentralen Rolle erforderlich, die von der lync Server 2013-Registrierungsstelle beim Aktivieren des sprach Failovers gespielt wird. Die lync Server-Registrierungsstelle ist eine Serverrolle, die die Clientregistrierung und-Authentifizierung ermöglicht und Routingdienste bereitstellt. Es befindet sich zusammen mit anderen Komponenten auf einem Standard Edition-Server, Front-End-Server, Director oder Survivable Branch-Appliance. Ein Registrierungspool besteht aus Registrierungsdiensten, die im Front-End-Pool ausgeführt werden und sich am gleichen Standort befinden. Der Front-End-Pool muss Lastenausgleich sein. DNS-Lastenausgleich wird empfohlen, der Hardwarelastenausgleich ist jedoch akzeptabel. Ein lync-Client ermittelt den Front-End-Pool mithilfe des folgenden Ermittlungsmechanismus:

1.  DNS-SRV-Eintrag

2.  AutoDiscovery Web Service (neu in lync Server 2013)

3.  DHCP-Option 120

Nachdem der lync-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Load Balancer an einen der Front-End-Server im Pool weitergeleitet. Dieser Front-End-Server leitet den Client wiederum an eine bevorzugte Registrierungsstelle im Pool um.

Jeder Benutzer, der für Enterprise-VoIP aktiviert ist, wird einem bestimmten Registrar-Pool zugewiesen, der zum primären Registrierungspool des Benutzers wird. An einer bestimmten Website teilen sich in der Regel Hunderte oder Tausende von Benutzern einen einzigen primären Registrierungspool. Zum berücksichtigen des Verbrauchs von Ressourcen für zentrale Websites durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie die einzelnen Verzweigungs Websitebenutzer als Benutzer berücksichtigen, die bei der zentralen Website registriert sind. Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.

Um die sprach Sicherheit bei einem zentralen Standortausfall zu gewährleisten, muss der primäre Registrierungspool über einen einzelnen dedizierten Sicherungs Registrierungs Registrierungspool an einer anderen Website verfügen. Die Sicherung kann mithilfe der Stabilitäts Einstellungen des Topologie-Generators konfiguriert werden. Unter der Voraussetzung, dass eine stabile WAN-Verbindung zwischen den beiden Websites besteht, werden Benutzer, deren primärer Registrierungspool nicht mehr verfügbar ist, automatisch an den sicherungsregistrierungspool weitergeleitet.

Die folgenden Schritte beschreiben den Client Ermittlungs-und Registrierungsprozess:

1.  Ein Client erkennt lync Server über DNS-SRV-Einträge. In lync Server 2013 können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird. Wenn Enterprise Contoso beispielsweise über drei zentrale Standorte (Nordamerika, Europa und Asien – Pazifik) und einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die FQDNs des Director-Pools in jedem der drei Speicherorte verweisen. Solange der Director-Pool an einem der Speicherorte verfügbar ist, kann der Client eine Verbindung mit dem lync-Server für den ersten Hop herstellen.
    
    <div>
    

    > [!NOTE]  
    > Die Verwendung eines Director-Pools ist optional. Stattdessen kann ein Front-End-Pool verwendet werden.

    
    </div>

2.  Der Director-Pool informiert den lync-Client über den primären Registrierungspool und den sicherungsregistrierungspool des Benutzers.

3.  Der lync-Client versucht zunächst, eine Verbindung mit dem primären Registrierungspool des Benutzers herzustellen. Wenn der primäre Registrierungspool verfügbar ist, akzeptiert die Registrierungsstelle die Registrierung. Wenn der primäre Registrierungspool nicht verfügbar ist, versucht der lync-Client, eine Verbindung mit dem sicherungsregistrierungspool herzustellen. Wenn der sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (durch Erkennen eines fehlenden Heartbeats für ein angegebenes Failover-Intervall), akzeptiert der sicherungsregistrierungspool die Registrierung des Benutzers. Nachdem die Sicherungs Registrierungsstelle festgestellt hat, dass die primäre Registrierungsstelle wieder verfügbar ist, leitet der sicherungsregistrierungspool Failover-lync-Clients an Ihren primären Pool um.

Die folgende Abbildung zeigt die empfohlene Topologie zur Gewährleistung der Stabilität des zentralen Standorts. Die beiden Standorte sind durch eine stabile WAN-Verbindung verbunden. Wenn die zentrale Website nicht mehr verfügbar ist, werden Benutzer, die diesem Pool zugewiesen sind, zur Registrierung an die Sicherungswebsite weitergeleitet.

**Empfohlene Topologie für die sprach Stabilität von Central Site**

![Topologie für Voice-resliency für zentrale Websites] (images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie für Voice-resliency für zentrale Websites")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Die folgenden Voraussetzungen und Empfehlungen für die Implementierung der VoIP-Flexibilität für die zentrale Website sind für die meisten Organisationen geeignet:

  - Die Websites, auf denen sich die primären und die Sicherungs registrierungspools befinden, sollten über eine stabile WAN-Verbindung verbunden sein.

  - Jede zentrale Website muss einen Registrierungspool enthalten, der aus einer oder mehreren Registrierungsstellen besteht.

  - Jeder Registrierungspool muss mithilfe des DNS-Lastenausgleichs, des Hardwarelastenausgleichs oder beider Lastenausgleich erfolgen. Detaillierte Informationen zum Planen Ihrer Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Jeder Benutzer muss einem primären registrierungsstellenpool mithilfe des lync Server-Verwaltungsshell-Cmdlets " **CsUser** " oder der lync Server-Systemsteuerung zugewiesen werden.

  - Der primäre Registrierungspool muss über einen einzelnen sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.

  - Der primäre Registrierungspool muss so konfiguriert sein, dass ein Failover zum sicherungsregistrierungspool durchführen kann. Standardmäßig ist die primäre Registrierungsstelle so eingestellt, dass Sie nach einem Intervall von 300 Sekunden ein Failover für den sicherungsregistrierungspool durchführen kann. Sie können dieses Intervall mithilfe des lync Server 2013-Topologie-Generators ändern.

  - Konfigurieren Sie eine Failover-Route, wie im Thema "[Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" in der Planning-Dokumentation beschrieben. Geben Sie bei der Konfiguration der Route ein Gateway an, das sich an einem anderen Standort als dem Gateway befindet, das auf der primären Route angegeben ist.

  - Wenn die zentrale Website Ihren primären Verwaltungsserver enthielt und die Website wahrscheinlich für einen längeren Zeitraum nicht mehr zur Verfügung steht, müssen Sie Ihre Verwaltungstools auf der Sicherungswebsite erneut installieren. Andernfalls können Sie keine Verwaltungseinstellungen ändern.

</div>

<div>

## <a name="dependencies"></a>Abhängigkeiten

Lync Server hängt von den folgenden Infrastruktur-und Softwarekomponenten ab, um die sprach Sicherheit zu gewährleisten:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Komponente</strong></p></td>
<td><p><strong>Funktions</strong></p></td>
</tr>
<tr class="even">
<td><p>DNS</p></td>
<td><p>Auflösen von SRV-Einträgen und Datensätzen für Server-Server-und Server-Client-Konnektivität</p></td>
</tr>
<tr class="odd">
<td><p>Exchange-und Exchange-Webdienste (EWS)</p></td>
<td><p>Kontaktspeicher; Kalenderdaten</p></td>
</tr>
<tr class="even">
<td><p>Exchange Unified Messaging und Exchange-Webdienste</p></td>
<td><p>Anrufprotokolle, voicemailliste, Voicemail</p></td>
</tr>
<tr class="odd">
<td><p>DHCP-Optionen 120</p></td>
<td><p>Wenn der DNS-SRV nicht zur Verfügung steht, versucht der Client, DHCP-Option 120 zu verwenden, um die Registrierungsstelle zu ermitteln. Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert sein, oder lync Server 2013 DHCP muss aktiviert sein. Ausführliche Informationen finden Sie unter Hardware-und Software Anforderungen für die Stabilität des Zweigstellen Standorts in den Anforderungen an die <a href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität des Zweigstellen Standorts für den lync Server 2013</a> -Abschnitt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>Überlebende sprach Features

Wenn die Voraussetzungen und Empfehlungen implementiert wurden, werden die folgenden Sprachfeatures vom sicherungsregistrierungspool bereitgestellt:

  - Ausgehende PSTN-Anrufe

  - Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter die Möglichkeit unterstützt, ein Failover zu einer Sicherungswebsite durchführen zu können

  - Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites

  - Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen

  - Instant Messaging mit zwei Teilnehmern und Freigeben von Audio und Video zwischen Benutzern am gleichen Standort

  - Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn beide Teilnehmer die Delegation oder alle Teammitglieder anrufen, auf der gleichen Website konfiguriert sind.

  - Vorhandene Telefone und Clients funktionieren weiterhin.

  - Aufzeichnung von Kommunikationsdatensätzen (KDS)

  - Authentifizierung und Autorisierung

Je nachdem, wie Sie konfiguriert sind, funktionieren die folgenden Sprachfeatures möglicherweise nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:

  - Voicemail-Einzahlung und-Abruf
    
    Wenn Sie Exchange um verfügbar machen möchten, wenn der primäre zentrale Standort außer Dienst ist, müssen Sie eine der folgenden Aktionen ausführen:
    
      - Ändern Sie die DNS-SRV-Einträge so, dass die Exchange um-Server am zentralen Standort auf Exchange-Exchange um-Server an einem anderen Standort verweisen.
    
      - Konfigurieren Sie die Exchange UM-Wähleinstellungen für jeden Benutzer so, dass Exchange um-Server sowohl am zentralen Standort als auch an der Sicherungswebsite eingeschlossen werden, die Exchange um-Server jedoch als deaktiviert festlegen. Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange um-Server auf der Sicherungswebsite als aktiviert kennzeichnen.
    
    Wenn keine der vorhergehenden Lösungen möglich ist, steht Exchange um nicht zur Verfügung, wenn die zentrale Website nicht mehr zur Verfügung steht.

  - Konferenzen aller Typen
    
    Ein Benutzer, der ein Failover auf eine Sicherungswebsite durchgeführt hat, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist, aber keine Konferenz im eigenen primären Pool erstellen oder hosten kann, die nicht mehr verfügbar ist. Ebenso können andere Benutzer nicht an Konferenzen teilnehmen, die im primären Pool des betroffenen Benutzers gehostet werden.

Die folgenden Sprachfeatures funktionieren nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:

  - Automatische Telefonzentrale

  - Anwesenheits-und auf den textbasierendes Routing

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Reaktionsgruppendienst und Anruf parken

  - Bereitstellungneuer Telefone und Clients

  - Adressbuch-Websuche

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

