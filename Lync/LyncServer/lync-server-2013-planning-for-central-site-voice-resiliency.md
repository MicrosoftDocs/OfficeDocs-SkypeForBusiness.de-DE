---
title: 'Lync Server 2013: Planen von VoIP-Ausfallsicherheit für den zentralen Standort'
TOCTitle: Planen von VoIP-Ausfallsicherheit für den zentralen Standort
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398347(v=OCS.15)
ms:contentKeyID: 49294009
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von VoIP-Ausfallsicherheit für den zentralen Standort in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Immer mehr Unternehmen verfügen über mehrere Standorte, die weltweit verteilt sind. Die Bereitstellung von Notrufdiensten, Zugang zum Helpdesk und die Möglichkeit, wichtige geschäftliche Aufgaben weiterhin ausführen zu können, wenn ein zentraler Standort nicht verfügbar ist, ist für eine Enterprise-VoIP-Ausfallsicherheitslösung entscheidend. Wenn ein zentraler Standort nicht länger verfügbar ist, muss Folgendes sichergestellt werden:

  - Bereitstellung von VoIP-Failover.

  - Benutzer, die sich üblicherweise für den Front-End-Pool am zentralen Standort registrieren, müssen sich für einen alternativen Front-End-Pool registrieren können. Zu diesem Zweck können Sie mehrere DNS-SRV-Einträge erstellen, die jeweils in einen Directorpool oder Front-End-Pool an jedem Ihrer zentralen Standorte aufgelöst werden. Sie können die Priorität und Gewichtung der SRV-Einträge so anpassen, dass die Benutzer des zentralen Standorts die Ressourcen von Director und Front-End-Pool vor den Benutzern in anderen SRV-Einträgen erhalten.

  - Eingehende und ausgehende Anrufe von Benutzern an anderen Standorten müssen an das Telefonfestnetz umgeleitet werden.

In diesem Thema wird die empfohlene Lösung zum Sicherstellen der VoIP-Ausfallsicherheit für einen zentralen Standort beschrieben.

## Architektur und Topologie

Für die Planung von VoIP-Ausfallsicherheit an einem zentralen Standort benötigen Sie grundlegende Kenntnisse der zentralen Rolle der Lync Server 2013-Registrierung für das VoIP-Failover. Die Lync Server-Registrierung ist eine neue Serverrolle für Clientregistrierung, Authentifizierung und Routingdienste. Diese Rolle wird gemeinsam mit anderen Komponenten in einem Standard Edition-Server, Front-End-Server, Director oder einer Survivable Branch-Anwendung bereitgestellt. Ein Registrierungspool umfasst Registrierungsdienste, die im Front-End-Pool ausgeführt werden und sich am selben Standort befinden. Für den Front-End-Pool muss ein Lastenausgleich implementiert sein. Empfohlen wird der DNS-Lastenausgleich, der Einsatz eines Hardwaregeräts zum Lastenausgleich ist jedoch ebenfalls möglich. Ein Lync ermittelt den Front-End-Pool anhand des folgenden Erkennungsmechanismus:

1.  DNS-SRV-Eintrag

2.  AutoErmittlungsdienst (neu in Lync Server 2013)

3.  DHCP-Option 120

Nachdem der Lync-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Lastenausgleich an einen Front-End-Server im Pool weitergeleitet. Dieser Front-End-Server wiederum leitet den Client an eine bevorzugte Registrierung innerhalb des Pools um.

Jeder für Enterprise-VoIP aktivierte Benutzer wird einem bestimmten Registrierungspool zugewiesen, der zum primären Registrierungspool für diesen Benutzer wird. Typischerweise verwenden Hunderte oder Tausende Benutzer an einem Standort einen einzigen primären Registrierungspool gemeinsam. Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer als Benutzer betrachten, der für den zentralen Standort registriert ist. Für die Anzahl von Zweigstellenbenutzern (einschließlich der für eine Survivable Branch-Anwendung registrierten Benutzer) gelten gegenwärtig keine Einschränkungen.

Zum Gewährleisten von VoIP-Ausfallsicherheit beim Ausfall eines zentralen Standorts muss der primäre Registrierungspool über einen einzelnen designierten Sicherungsregistrierungspool verfügen, der sich an einem anderen Standort befindet. Die Sicherung kann über die Ausfallsicherheitseinstellungen im Topologie-Generator konfiguriert werden. Vorausgesetzt, dass eine ausfallsichere WAN-Leitung zwischen den beiden Standorten besteht, werden Benutzer des nicht mehr verfügbaren primären Registrierungspools automatisch an den Sicherungsregistrierungspool geleitet.

Der Such- und Registrierungsprozess des Clients umfasst die folgenden Schritte:

1.  Ein Client ermittelt Lync Server anhand von DNS-SRV-Einträgen. DNS-SRV-Einträge können in Lync Server 2013 so konfiguriert werden, dass für die DNS-SRV-Abfrage mehrere vollqualifizierte Domänennamen zurückgegeben werden. Beispiel: Wenn das Unternehmen Contoso über drei zentrale Standorte (in Nordamerika, Europa und im asiatisch-pazifischen Raum) sowie einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die vollqualifizierten Domänennamen der Director-Pools an jedem dieser drei Standorte verweisen. Wenn der Director-Pool an einem der Standorte verfügbar ist, kann sich der Client mit dem ersten Lync Server-Hop verbinden.
    

    > [!NOTE]
    > Die Verwendung eines Directorpool ist optional. Stattdessen kann ein Front-End-Pool verwendet werden.



2.  Der Directorpool informiert den Lync-Client über den primären Registrierungspool und den Sicherungsregistrierungspool des Benutzers.

3.  Der Lync-Client versucht zunächst, sich mit dem primären Registrierungspool des Benutzers zu verbinden. Wenn der primäre Registrierungspool verfügbar ist, wird die Registrierung akzeptiert. Wenn der primäre Registrierungspool nicht verfügbar ist, versucht der Lync-Client, sich mit dem Sicherungsregistrierungspool zu verbinden. Wenn der Sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (kein Empfang des Heartbeatsignals innerhalb eines festgelegten Failoverintervalls), akzeptiert der Sicherungsregistrierungspool die Registrierung des Benutzers. Wenn die Sicherungsregistrierung feststellt, dass die primäre Registrierung erneut verfügbar ist, leitet der Sicherungsregistrierungspool Lync-Failoverclients an ihren primären Pool um.

Die folgende Abbildung zeigt die empfohlene Topologie zum Gewährleisten von Ausfallsicherheit für einen zentralen Standort. Die zwei Standorte sind über eine ausfallsichere WAN-Leitung verbunden. Wenn der zentrale Standort ausfällt, werden Benutzer, die diesem Pool zugewiesen sind, zur Registrierung an den Sicherungsstandort umgeleitet.

**Empfohlene Topologie für VoIP-Ausfallsicherheit an einem zentralen Standort**

![Topologie für VoIP-Ausfallsicherheit für den zentralen Standort](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topologie für VoIP-Ausfallsicherheit für den zentralen Standort")

## Anforderungen und Empfehlungen

Die folgenden Anforderungen und Empfehlungen für die Implementierung von VoIP-Ausfallsicherheit an einem zentralen Standort gelten für die meisten Organisationen:

  - Die Standorte, an denen sich der primäre und der Sicherungsregistrierungspool befinden, sollten über eine ausfallsichere WAN-Leitung verbunden sein.

  - Jeder zentrale Standort muss über einen Registrierungspool mit mindestens einer Registrierung verfügen.

  - Für jeden Registrierungspool muss ein Lastenausgleich (DNS-Lastenausgleich, Hardwaregerät zum Lastenausgleich oder beides) implementiert sein. Ausführliche Informationen zum Planen Ihrer Lastenausgleichskonfiguration finden Sie unter [Anforderungen an den Lastenausgleich für Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

  - Jedem Benutzer muss mit dem Cmdlet **set-CsUser** in der Lync Server-Verwaltungsshell oder über die Lync Server-Systemsteuerung einem primären Registrierungspool zugewiesen werden.

  - Der primäre Registrierungspool muss über einen einzelnen Sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.

  - Für den primären Registrierungspool muss ein Failover auf den Sicherungsregistrierungspool konfiguriert sein. In der Standardeinstellung ist für die primäre Registrierung ein Failover auf den Sicherungsregistrierungspool nach 300 Sekunden festgelegt. Dieses Intervall kann über den Topologie-Generator in Lync Server 2013 geändert werden.

  - Konfigurieren Sie eine Failoverroute wie im Thema [Konfigurieren einer Failoverroute in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md) in der Planungsdokumentation beschrieben. Geben Sie beim Konfigurieren der Route ein Gateway an, das sich an einem anderen Standort befindet als das in der primären Route angegebene Gateway.

  - Wenn sich Ihr primärer Verwaltungsserver am zentralen Standort befindet und dieser Standort wahrscheinlich für einen längeren Zeitraum ausfällt, müssen Sie Ihre Verwaltungstools am Sicherungsstandort erneut installieren. Andernfalls können keine Verwaltungseinstellungen geändert werden.

## Abhängigkeiten

Lync Server hängt von den folgenden Infrastruktur- und Softwarekomponenten ab, um VoIP-Ausfallsicherheit zu gewährleisten:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Komponente</strong></p></td>
<td><p><strong>Funktion</strong></p></td>
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
<td><p>Wenn DNS-SRV nicht verfügbar ist, versucht der Client, DHCP Option 120 für die Suche nach der Registrierung zu verwenden. Zu diesem Zweck muss entweder ein DHCP-Server konfiguriert oder Lync Server 2013-DHCP aktiviert sein. Ausführliche Informationen finden Sie im Abschnitt &quot;Hardware- und Softwareanforderungen für die Ausfallsicherheit am Zweigstellenstandort&quot; unter <a href="lync-server-2013-branch-site-resiliency-requirements.md">Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>


## VoIP-Funktionen mit Ausfallsicherheit

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
    
      - Konfigurieren Sie die Exchange UM-Wähleinstellungen der einzelnen Benutzer so, dass sie sowohl am zentralen Standort als auch am Sicherungsstandort Exchange UM-Server enthalten, die Exchange UM-Sicherungsserver jedoch als deaktiviert festgelegt werden. Beim Ausfall des primären Standorts muss der Exchange-Administrator die Exchange UM-Server am Sicherungsstandort als aktiviert kennzeichnen.
    
    Wenn keine der oben genannten Lösungen möglich ist, ist Exchange UM beim Ausfall des zentralen Standorts nicht verfügbar.

  - Alle Konferenztypen
    
    Ein Benutzer, für den ein Failover auf einen Sicherungsstandort durchgeführt wurde, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist. In seinem eigenen primären Pool, der nicht länger verfügbar ist, kann der Benutzer jedoch keine Konferenz erstellen oder hosten. Gleichermaßen können auch keine anderen Benutzer an Konferenzen teilnehmen, die im betroffenen primären Pool des Benutzers gehostet werden.

Die folgenden VoIP-Funktionen können nicht verwendet werden, wenn ein primärer zentraler Standort ausfällt:

  - Automatische Konferenzzentrale

  - Anwesenheits- und DNS-basiertes Routing

  - Aktualisieren der Einstellungen für die Anrufweiterleitung

  - Reaktionsgruppendienst und Parken von Anrufen

  - Bereitstellen neuer Telefone und Clients

  - Adressbuchwebsuche

## Siehe auch

#### Weitere Ressourcen

[Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md)

