---
title: 'Lync Server 2013: Technische Anforderungen für den Server für beständigen Chat'
TOCTitle: Technische Anforderungen für den Server für beständigen Chat
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398495(v=OCS.15)
ms:contentKeyID: 49294281
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Jeder Computer, auf dem der Server für beständigen Chat gehostet wird, muss auf eine vorhandene Lync Server 2013-Topologie mit den folgenden Komponenten zugreifen können:

  - **Lync Server 2013, Front-End-Server.** Der Front-End-Server bildet die Grundlage für SIP-Routing (Session Initiation Protocol), das die Kommunikation zwischen Computern mit dem Server für beständigen Chat und den Beständiger Chat-Funktionen möglich macht. Vor Beginn der Bereitstellung des Server für beständigen Chat müssen Sie die Bereitstellung von Lync Server 2013, Standard Edition, oder eines Lync ServerFront-End-Pool und jeden anderen internen Computer in Ihrer Organisation, auf dem Lync Server ausgeführt wird, entsprechend überprüfen.

In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die Daten des Features Beständiger Chat gespeichert werden.

## Server für beständigen Chat-Anforderungen

Ausführliche Informationen zur empfohlenen Hardware für die Bereitstellung von Lync Server und der aktuellen Version von Server für beständigen Chat finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zu den unterstützten Betriebssystemen für Server und Tools für Lync Server und den Server für beständigen Chat finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zu zusätzlicher Software, die für die Bereitstellung des Server für beständigen Chat benötigt wird, finden Sie in der folgenden Tabelle.

### Erforderliche Software für den Server für beständigen Chat

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Software</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Message Queuing</p></td>
<td><p>Wird vom Kompatibilitätsdienst des Server für beständigen Chat und Beständiger Chat verwendet (wenn bereitgestellt).</p></td>
</tr>
</tbody>
</table>


## Anforderungen des Server für beständigen Chat an die Datenbank

Der Server für beständigen Chat verwendet die Beständiger Chat-Datenbank, um Daten zum Chatverlauf, zur Konfiguration und zu Benutzerbereitstellungen zu speichern. Optional verwendet er die Beständiger Chat-Kompatibilitätsdatenbank, um Kompatibilitätsdaten zu speichern.


> [!IMPORTANT]
> Die Beständiger Chat-Datenbank (mgc) und die Kompatibilitätsdatenbank (mgccomp) können sich in der gleichen Instanz von SQL Server oder auf unterschiedlichen SQL-Server befinden.



Beim Vorbereiten einer Datenbankserverplattform müssen Sie sich vergewissern, dass jeder Computer die Hardwareanforderungen erfüllt, bevor Sie die erforderliche Software installieren.

Die Serverplattform für den Beständiger Chat-Datenbankserver erfordert die gleiche Hardware wie der Lync Server-Back-End-Datenbankserver. Ausführliche Informationen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:

  - Microsoft SQL Server 2012. Einzelheiten zur Vorgehensweise bei der Installation von Microsoft SQL Server 2012 finden Sie in "Installieren von SQL Server 2012" unter [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Einzelheiten zur Vorgehensweise bei der Installation von Microsoft SQL Server 2008 R2 finden Sie in "SQL Server-Installation (SQL Server 2008 R2)" unter [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).

## Anforderungen des Server für beständigen Chat in Bezug auf Zertifikate

Ausführliche Informationen zum Beziehen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Dateispeichern finden Sie unter [Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

