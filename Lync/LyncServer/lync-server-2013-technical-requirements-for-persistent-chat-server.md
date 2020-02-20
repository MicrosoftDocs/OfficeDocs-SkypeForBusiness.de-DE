---
title: 'Lync Server 2013: technische Anforderungen für den Server für beständigen Chat'
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
ms.openlocfilehash: c99493a2d6921214f91c36fb62e7a75a7279f646
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-persistent-chat-server-in-lync-server-2013"></a>Technische Anforderungen für den Server für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-06_

Jeder Computer, der den Server für beständigen Chat hostet, muss Zugriff auf eine vorhandene lync Server 2013 Topologie mit den folgenden Komponenten haben:

  - **Lync Server 2013, Front-End-Server.**  Das Front-End-Server ist die Grundlage für das SIP-Routing (Session Initiation Protocol), das die Kommunikation zwischen Computern mit persistent Chat Server und der Funktion für beständigen Chat ermöglicht. Bevor Sie mit der Bereitstellung des Servers für beständigen Chat beginnen, überprüfen Sie die Bereitstellung von lync Server 2013, Standard Edition oder einer lync Server Front-End-Pool sowie alle anderen internen Computer, die lync Server entsprechend Ihrer Organisation ausführen.

In den folgenden Abschnitten werden die spezifischen Anforderungen für den Server für beständigen Chat und die Datenbank beschrieben, in der die Daten des beständigen Chats gespeichert sind.

<div>

## <a name="persistent-chat-server-requirements"></a>Server Anforderungen für beständigen Chat

Ausführliche Informationen zur empfohlenen Hardware für die Bereitstellung von lync Server und die neueste Version des Servers für beständigen Chat finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zur Betriebssystemunterstützung für Server und Tools für lync Server und beständigen Chat Server finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Ausführliche Informationen zu zusätzlicher Software, die für die Bereitstellung von persistent Chat Server erforderlich ist, finden Sie in der folgenden Tabelle.

### <a name="persistent-chat-server-software-prerequisites"></a>Software Voraussetzungen für persistent Chat Server

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
<td><p>Wird vom beständigen Chat Server und dem Kompatibilitätsdienst für beständigen Chat verwendet, sofern bereitgestellt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-database-requirements"></a>Datenbankanforderungen für beständigen Chat Server

Der Server für beständigen Chat verwendet die Datenbank für beständigen Chat, um Chat Verlaufs-, Konfigurations-und Benutzerdaten zu speichern. Optional wird die Compliance-Datenbank für beständigen Chat zum Speichern von Kompatibilitätsdaten verwendet.

<div>


> [!IMPORTANT]  
> Die Datenbank für beständigen Chat (MGC) und die Kompatibilitätsdatenbank (mgccomp) können sich in derselben Instanz von SQL Server oder auf verschiedenen SQL-Servern befinden.



</div>

Um eine Datenbankserverplattform vorzubereiten, stellen Sie sicher, dass jeder Computer die Hardwareanforderungen erfüllt, und installieren Sie dann die erforderliche Software.

Die Server Plattform für die Datenbankserver für beständigen Chat erfordert die gleiche Hardware wie der lync Server Back-End-Datenbankserver. Ausführliche Informationen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

Stellen Sie sicher, dass eine der folgenden Softwareanwendungen auf dem Datenbankserver installiert ist:

  - Microsoft SQL Server 2012. Ausführliche Informationen zur Installation von Microsoft SQL Server 2012 finden Sie unter "Install SQL Server 2012" unter [https://go.microsoft.com/fwlink/p/?LinkID=248559](https://go.microsoft.com/fwlink/p/?linkid=248559).

  - Microsoft SQL Server 2008 R2. Ausführliche Informationen zum Installieren von Microsoft SQL Server 2008 R2 finden Sie unter "SQL Server Installation (SQL Server 2008 R2)" unter [https://go.microsoft.com/fwlink/?LinkId=275702](https://go.microsoft.com/fwlink/?linkid=275702).

</div>

<div>

## <a name="persistent-chat-server-certificate-requirements"></a>Zertifikatanforderungen für den Server für beständigen Chat

Ausführliche Informationen zum Erwerb von Zertifikaten, zum Erstellen der SQL Server Datenbank und zum Erstellen von Datei speichern finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.

</div>

</div>

<span> </span>

</div>

</div>

</div>

