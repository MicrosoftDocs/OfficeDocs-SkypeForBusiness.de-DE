---
title: 'Lync Server 2013: Grundlegendes zu den Firewallanforderungen für SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 586985c3059e12d358249a71dc2435c3be9254f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a>Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Bei einer Standard Edition-Bereitstellung werden Firewall-Ausnahmen beim Einrichten von lync Server 2013 automatisch erstellt. Bei Enterprise Edition-Bereitstellungen müssen Sie die Firewall-Ausnahmen jedoch manuell auf dem SQL Server-Back-End-Server konfigurieren. Das TCP/IP-Protokoll ermöglicht es, einen bestimmten Port einmal für eine bestimmte IP-Adresse zu verwenden. Das bedeutet, dass Sie für den SQL Server-basierten Server die standardmäßige Datenbankinstanz den standardmäßigen TCP-Port 1433 zuweisen können. Für alle anderen Instanzen müssen Sie den SQL Server-Konfigurations-Manager verwenden, um eindeutige und nicht verwendete Ports zuzuweisen. In diesem Thema wird Folgendes behandelt:

  - Voraussetzungen für eine Firewall-Ausnahme bei Verwendung der Standardinstanz

  - Voraussetzungen für eine Firewall-Ausnahme für den SQL Server-Browser Dienst

  - Voraussetzungen für statische Abhör Anschlüsse bei Verwendung benannter Instanzen

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a>Voraussetzungen für eine Firewall-Ausnahme bei Verwendung der Standardinstanz

Wenn Sie bei der Bereitstellung von lync Server 2013 die SQL Server-Standardinstanz für eine Datenbank verwenden, werden die folgenden Firewall-Regel Anforderungen verwendet, um die Kommunikation zwischen dem Front-End-Pool und der SQL Server-Standardinstanz zu gewährleisten.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>1433</p></td>
<td><p>Eingehend zu SQL Server</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a>Voraussetzungen für eine Firewall-Ausnahme für den SQL Server-Browser Dienst

Der SQL Server-Browser Dienst findet Datenbankinstanzen und kommuniziert den Port, der für die Verwendung der Instanz (benannt oder Standard) konfiguriert ist.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>1434</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a>Voraussetzungen für statische Abhör Anschlüsse bei Verwendung benannter Instanzen

Wenn Sie benannte Instanzen in der SQL Server-Konfiguration für Datenbanken verwenden, die lync Server 2013 unterstützen, konfigurieren Sie statische Ports mithilfe des SQL Server-Konfigurations-Managers. Nachdem die statischen Ports jeder benannten Instanz zugewiesen wurden, erstellen Sie Ausnahmen für jeden statischen Port in der Firewall.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Protokoll</th>
<th>Port</th>
<th>Richtung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP</p></td>
<td><p>Statisch definiert</p></td>
<td><p>Inbound</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a>SQL Server-Dokumentation

In der Microsoft SQL Server 2012-Dokumentation finden Sie detaillierte Anleitungen zum Konfigurieren des Firewall-Zugriffs für Datenbanken. Details zu Microsoft SQL Server 2012 finden Sie unter "Konfigurieren der Windows-Firewall, um SQL Server-Zugriff [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)zu ermöglichen".

</div>

</div>

<span> </span>

</div>

</div>

</div>

