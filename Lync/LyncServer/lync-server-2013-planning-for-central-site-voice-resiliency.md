---
title: 'Lync Server 2013: Planen der VoIP-Ausfallsicherheit für den zentralen Standort'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16a61a07ae14f004b406aa38ef783a1c873f2128
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a>Planen der VoIP-Ausfallsicherheit für den zentralen Standort in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-30_

Immer mehr Unternehmen verfügen über mehrere Standorte, die weltweit verteilt sind. Die Verwaltung von Notfalldiensten, der Zugriff auf das Helpdesk und die Möglichkeit, wichtige geschäftliche Aufgaben auszuführen, wenn ein zentraler Standort außer Betrieb ist, sind für alle Lösungen für die Ausfallsicherheit von Enterprise-VoIP unerlässlich. Wenn ein zentraler Standort nicht länger verfügbar ist, muss Folgendes sichergestellt werden:

  - Bereitstellung von VoIP-Failover.

  - Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich mit einem alternativen Front-End-Pool registrieren können. Dies kann durch Erstellen mehrerer DNS-SRV-Einträge geschehen, die jeweils in eine Directorpool oder Front-End-Pool an jedem zentralen Standort aufgelöst werden. Sie können die Priorität und die Gewichtung der SRV-Einträge anpassen, sodass Benutzer, die von diesem zentralen Standort bedient werden, den entsprechenden Director und Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.

  - Eingehende und ausgehende Anrufe von Benutzern an anderen Standorten müssen an das Telefonfestnetz umgeleitet werden.

In diesem Thema wird die empfohlene Lösung zum Sicherstellen der VoIP-Ausfallsicherheit für einen zentralen Standort beschrieben.

<div>

## <a name="architecture-and-topology"></a>Architektur und Topologie

Für die Planung der VoIP-Ausfallsicherheit an einem zentralen Standort ist ein grundlegendes Verständnis der zentralen Rolle erforderlich, die die lync Server 2013 Registrierungsstelle beim Aktivieren des VoIP-Failovers spielt. Die lync Server Registrierungsstelle ist eine Server Rolle, die die Clientregistrierung und-Authentifizierung ermöglicht und Routingdienste bereitstellt. Sie befindet sich zusammen mit anderen Komponenten auf einem Standard Edition-Server, Front-End-Server, Director oder Survivable Branch Appliance. Ein registrierungsstellenpool besteht aus Registrierungsdiensten, die auf der Front-End-Pool und an derselben Website installiert sind. Die Front-End-Pool muss Lastenausgleich aufweisen. Empfohlen wird der DNS-Lastenausgleich, der Einsatz eines Hardwaregeräts zum Lastenausgleich ist jedoch ebenfalls möglich. Ein lync-Client ermittelt die Front-End-Pool über den folgenden Erkennungsmechanismus:

1.  DNS-SRV-Eintrag

2.  AutoErmittlungsdienst (neu in lync Server 2013)

3.  DHCP-Option 120

Nachdem der lync-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Lastenausgleich an einen der Front-End-Server im Pool geleitet. Durch diese Front-End-Server wird der Client wiederum an eine bevorzugte Registrierungsstelle im Pool umgeleitet.

Jeder für Enterprise-VoIP aktivierte Benutzer wird einem bestimmten registrierungsstellenpool zugewiesen, der zum primären registrierungsstellenpool des Benutzers wird. Typischerweise verwenden Hunderte oder Tausende Benutzer an einem Standort einen einzigen primären Registrierungspool gemeinsam. Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer als Benutzer betrachten, der für den zentralen Standort registriert ist. Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die mit einem Survivable Branch Appliance registriert sind.

Zum Gewährleisten von VoIP-Ausfallsicherheit beim Ausfall eines zentralen Standorts muss der primäre Registrierungspool über einen einzelnen designierten Sicherungsregistrierungspool verfügen, der sich an einem anderen Standort befindet. Die Sicherung kann mithilfe von Ausfall Sicherheitseinstellungen für den Topologie-Generator konfiguriert werden. Vorausgesetzt, dass eine ausfallsichere WAN-Leitung zwischen den beiden Standorten besteht, werden Benutzer des nicht mehr verfügbaren primären Registrierungspools automatisch an den Sicherungsregistrierungspool geleitet.

Der Such- und Registrierungsprozess des Clients umfasst die folgenden Schritte:

1.  Ein Client erkennt lync Server über DNS-SRV-Einträge. In lync Server 2013 können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird. Beispiel: Wenn das Unternehmen Contoso über drei zentrale Standorte (in Nordamerika, Europa und im asiatisch-pazifischen Raum) sowie einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die vollqualifizierten Domänennamen der Director-Pools an jedem dieser drei Standorte verweisen. Solange die Directorpool an einem der Standorte verfügbar ist, kann der Client eine Verbindung mit dem ersten Hop-lync Server herstellen.
    
    <div>
    

    > [!NOTE]  
    > Die Verwendung eines Directorpool ist optional. Stattdessen kann ein Front-End-Pool verwendet werden.

    
    </div>

2.  Das Directorpool informiert den lync-Client über den primären Registrierungspool des Benutzers und den sicherungsregistrierungspool.

3.  Der lync-Client versucht zuerst, eine Verbindung mit dem primären Registrierungspool des Benutzers herzustellen. Wenn der primäre Registrierungspool verfügbar ist, wird die Registrierung akzeptiert. Wenn der primäre registrierungsstellenpool nicht verfügbar ist, versucht der lync-Client, eine Verbindung mit dem Sicherungs registrierungsstellenpool herzustellen. Wenn der Sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (kein Empfang des Heartbeatsignals innerhalb eines festgelegten Failoverintervalls), akzeptiert der Sicherungsregistrierungspool die Registrierung des Benutzers. Nachdem die Sicherungs Registrierungsstelle festgestellt hat, dass die primäre Registrierungsstelle wieder verfügbar ist, leitet der Sicherungs Registrierungsstellen-Pool Failover-lync-Clients an Ihren primären Pool weiter.

Die folgende Abbildung zeigt die empfohlene Topologie zum Gewährleisten von Ausfallsicherheit für einen zentralen Standort. Die zwei Standorte sind über eine ausfallsichere WAN-Leitung verbunden. Wenn der zentrale Standort ausfällt, werden Benutzer, die diesem Pool zugewiesen sind, zur Registrierung an den Sicherungsstandort umgeleitet.

**Empfohlene Topologie für VoIP-Ausfallsicherheit an einem zentralen Standort**

![Topologie für VoIP-resliency für den zentralen Standort](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie für VoIP-resliency für den zentralen Standort")

</div>

<div>

## <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Die folgenden Anforderungen und Empfehlungen für die Implementierung von VoIP-Ausfallsicherheit an einem zentralen Standort gelten für die meisten Organisationen:

  - Die Standorte, an denen sich der primäre und der Sicherungsregistrierungspool befinden, sollten über eine ausfallsichere WAN-Leitung verbunden sein.

  - Jeder zentrale Standort muss über einen Registrierungspool mit mindestens einer Registrierung verfügen.

  - Jeder registrierungsstellenpool muss mithilfe des DNS-Lastenausgleichs, des Hardwarelastenausgleichs oder beider Lastenausgleich erfolgen. Ausführliche Informationen zum Planen der Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Jeder Benutzer muss einem primären registrierungsstellenpool zugewiesen werden, indem er entweder das lync Server-Verwaltungsshell-Cmdlet " **CsUser** " oder den lync Server-Systemsteuerung verwendet.

  - Der primäre Registrierungspool muss über einen einzelnen Sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.

  - Für den primären Registrierungspool muss ein Failover auf den Sicherungsregistrierungspool konfiguriert sein. In der Standardeinstellung ist für die primäre Registrierung ein Failover auf den Sicherungsregistrierungspool nach 300 Sekunden festgelegt. Sie können dieses Intervall mithilfe des lync Server 2013 Topologie-Generators ändern.

  - Konfigurieren Sie eine Failover-Route, wie im Thema "[Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md)" in der Planungsdokumentation beschrieben. Geben Sie beim Konfigurieren der Route ein Gateway an, das sich an einem anderen Standort befindet als das in der primären Route angegebene Gateway.

  - Wenn sich Ihr primärer Verwaltungsserver am zentralen Standort befindet und dieser Standort wahrscheinlich für einen längeren Zeitraum ausfällt, müssen Sie Ihre Verwaltungstools am Sicherungsstandort erneut installieren. Andernfalls können keine Verwaltungseinstellungen geändert werden.

</div>

<div>

## <a name="dependencies"></a>Abhängigkeiten

Lync Server hängt von den folgenden Infrastruktur-und Softwarekomponenten ab, um die VoIP-Ausfallsicherheit zu gewährleisten:


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
<td><p>Auflösen von SRV- und A-Einträgen für Konnektivität zwischen Servern bzw. zwischen Servern und Clients</p></td>
</tr>
<tr class="odd">
<td><p>Exchange und Exchange-Webdienste</p></td>
<td><p>Speicherung von Kontakten, Kalenderdaten</p></td>
</tr>
<tr class="even">
<td><p>Exchange Unified Messaging und Exchange-Webdienste</p></td>
<td><p>Anrufprotokolle, Voicemailliste, Voicemail</p></td>
</tr>
<tr class="odd">
<td><p>DHCP Options 120</p></td>
<td><p>Wenn DNS-SRV nicht verfügbar ist, versucht der Client, DHCP Option 120 für die Suche nach der Registrierung zu verwenden. Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert sein, oder lync Server 2013 DHCP muss aktiviert sein. Ausführliche Informationen finden Sie unter Hardware-und Software Anforderungen für Ausfallsicherheit für Zweigstellenstandorte in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für lync Server 2013</a> Abschnitt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a>VoIP-Funktionen mit Ausfallsicherheit

Wenn die vorstehenden Anforderungen und Empfehlungen implementiert wurden, werden die folgenden VoIP-Funktionen vom Sicherungsregistrierungspool bereitgestellt:

  - Ausgehende PSTN-Anrufe

  - Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter das Failover auf einen Sicherungsstandort unterstützt

  - Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden

  - Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe

  - Instant Messaging mit zwei Teilnehmern sowie Freigabe von Audio- und Videoinhalten zwischen Benutzern am selben Standort

  - Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste (jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung oder alle Teammitglieder am selben Standort konfiguriert sind).

  - Vorhandene Telefone und Clients sind weiterhin funktionsfähig.

  - Aufzeichnung von Kommunikationsdatensätzen (KDS)

  - Authentifizierung und Autorisierung

Abhängig von ihrer Konfiguration können die folgenden VoIP-Funktionen beim Ausfall eines primären zentralen Standorts verwendet werden oder nicht:

  - Hinterlassen und Abrufen von Voicemail
    
    Wenn Exchange UM beim Ausfall des primären zentralen Standorts verfügbar sein soll, führen Sie einen der folgenden Schritte aus:
    
      - Ändern Sie DNS-SRV-Einträge so, dass die Exchange UM-Server am zentralen Standort auf Exchange UM-Sicherungsserver an einem anderen Standort verweisen.
    
      - Konfigurieren Sie die Exchange UM Wähleinstellungen für die einzelnen Benutzer so, dass Sie Exchange um Server am zentralen Standort und am Sicherungsstandort einschließen, jedoch die Sicherung Exchange um Server als deaktiviert festlegen. Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange um Server am Sicherungsstandort als aktiviert kennzeichnen.
    
    Wenn keine der oben genannten Lösungen möglich ist, sind Exchange um nicht verfügbar, falls der zentrale Standort nicht mehr verfügbar ist.

  - Alle Konferenztypen
    
    Ein Benutzer, für den ein Failover auf einen Sicherungsstandort durchgeführt wurde, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist. In seinem eigenen primären Pool, der nicht länger verfügbar ist, kann der Benutzer jedoch keine Konferenz erstellen oder hosten. Gleichermaßen können auch keine anderen Benutzer an Konferenzen teilnehmen, die im betroffenen primären Pool des Benutzers gehostet werden.

Die folgenden VoIP-Funktionen können nicht verwendet werden, wenn ein primärer zentraler Standort ausfällt:

  - Automatische Konferenzzentrale

  - Anwesenheits- und DNS-basiertes Routing

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Reaktionsgruppendienst und Parken von Anrufen

  - Bereitstellen neuer Telefone und Clients

  - Adressbuchwebsuche

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von VoIP-Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

