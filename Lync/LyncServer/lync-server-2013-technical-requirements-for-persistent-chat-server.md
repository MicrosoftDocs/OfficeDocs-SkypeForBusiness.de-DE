---
title: 'Lync Server 2013: Technische Voraussetzungen für beständigen Chat Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Persistent Chat Server
ms:assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398495(v=OCS.15)
ms:contentKeyID: 48184383
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0437f56c5eb5564eb4f85809aefd181c2cbd2eaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Technische Anforderungen für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-06_

Jeder Computer, der den Server für beständigen Chat hostet, muss Zugriff auf eine vorhandene lync Server 2013-Topologie mit den folgenden Komponenten haben:

  - **Lync Server 2013, Front-End-Server.**  Der Front-End-Server ist die Grundlage für das SIP-Routing (Session Initiation Protocol), mit dem die Kommunikation zwischen Computern, auf denen der beständige Chat Server ausgeführt wird, und der Funktion für beständigen Chat ermöglicht wird. Bevor Sie mit der Bereitstellung des beständigen Chat Servers beginnen, überprüfen Sie die Bereitstellung von lync Server 2013, Standard Edition oder einem lync Server-Front-End-Pool und allen anderen internen Computern, auf denen lync Server ausgeführt wird, je nach Bedarf für Ihre Organisation.

In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die persistenten Chat-Daten gespeichert sind.

<div>

## <a name="persistent-chat-server-requirements"></a>Server Anforderungen für beständigen Chat

Details zur empfohlenen Hardware für die Bereitstellung von lync Server und die neueste Version des beständigen Chat Servers finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.

Details zur Unterstützung des Betriebssystems Server und Tools für lync Server und beständiger Chat Server finden Sie unter Unterstützung von [Server-und Tools-Betriebssystem in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

Details zu zusätzlicher Software, die für die Bereitstellung von persistent Chat Server erforderlich ist, finden Sie in der folgenden Tabelle.

### <a name="persistent-chat-server-software-prerequisites"></a>Voraussetzungen für beständige Chat Server Software

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
<td><p>Wird vom beständigen Chat Server und dem beständigen Chat-Kompatibilitätsdienst verwendet, falls bereitgestellt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für beständigen Chat Server

Der Server für beständigen Chat verwendet die Datenbank für beständigen Chat, um Chat Verlaufs-, Konfigurations-und Benutzer Bereitstellungsdaten zu speichern. Optional wird die Compliance-Datenbank für beständigen Chat verwendet, um Kompatibilitätsdaten zu speichern.

<div>


> [!IMPORTANT]  
> Die persistent Chat-Datenbank (MGC) und die Compliance-Datenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL-Servern befinden.



</div>

Beim Vorbereiten einer Datenbankserverplattform müssen Sie sich vergewissern, dass jeder Computer die Hardwareanforderungen erfüllt, bevor Sie die erforderliche Software installieren.

Die Server Plattform für die persistenten Chat-Datenbankserver erfordert dieselbe Hardware wie der lync Server-Back-End-Datenbankserver. Ausführliche Informationen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.

Stellen Sie sicher, dass auf dem Datenbankserver eine der folgenden Softwareanwendungen installiert ist:

  - Microsoft SQL Server 2012 Informationen zum Installieren von Microsoft SQL Server 2012 finden Sie unter "Installieren von SQL Server 2012" unter [http://go.microsoft.com/fwlink/p/?LinkID=248559](http://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2 Informationen zum Installieren von Microsoft SQL Server 2008 R2 finden Sie unter "SQL Server-Installation (SQL Server 2008 R2)" unter [http://go.microsoft.com/fwlink/?LinkId=275702](http://go.microsoft.com/fwlink/?linkid=275702).

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für beständigen Chat Server

Details zum Abrufen von Zertifikaten, zum Erstellen der SQL Server-Datenbank und zum Erstellen von Datei speichern finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

