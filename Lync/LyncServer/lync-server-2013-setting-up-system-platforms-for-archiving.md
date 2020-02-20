---
title: 'Lync Server 2013: Einrichten von Systemplattformen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec73e1af0b1fb86cbd31cb8f23ddb7633a3970ce
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Einrichten von Systemplattformen für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-09_

Bevor Sie mit der Bereitstellung der Archivierung beginnen, müssen Sie das erforderliche Betriebssystem und alle anderen erforderlichen Softwarekomponenten auf Hardware installieren, die die Systemanforderungen erfüllt:

  - **Lync Server 2013 Plattform**   lync Server 2013-Bereitstellungen verfügen nicht über Archivierungsserver. Stattdessen werden einheitliche Datenerfassungs-Agents auf Front-End-Servern und Standard Edition-Servern ausgeführt, um Daten für die Archivierung zu erfassen, sodass keine separate Systemplattform zum Hosten der Archivierung benötigt wird.

  - **Datenspeicherplattform**   in lync Server 2013 können Sie Daten mithilfe einer der folgenden Optionen speichern:
    
      - **Microsoft Exchange Integration**   Wenn Sie lync Server 2013 Archivierungsdaten mithilfe der Exchange 2013-Bereitstellung speichern möchten, statt oder zusätzlich zum Einrichten einer separaten Datenbank für die Speicherung von Archivierungsdaten, muss Ihre Exchange-Bereitstellung Exchange 2013 ausführen. Ausführliche Informationen zum Einrichten von Systemplattformen für Exchange 2013 finden Sie in der Exchange-Produktdokumentation.
    
      - **SQL Server**   Wenn Sie eine separate SQL Server Datenbank für die Speicherung von Archivierungsdaten anstelle von oder zusätzlich zur Verwendung Microsoft Exchange Integration verwenden möchten, müssen Sie vor der Bereitstellung der Archivierung die Systemplattform für die Datenbank einrichten. Die spezifischen Anforderungen an die Systemplattform hängen davon ab, ob Sie Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für den Archivierungsdatenbank verwenden. Ausführliche Informationen zum Einrichten von Systemplattformen für diese Datenbanken finden Sie in der Produktdokumentation zu Microsoft SQL Server 2008 R2 und Microsoft SQL Server 2012.

  - **Dateiserver Plattform**   lync Server 2013 speichert lync Server Archivierungsdateien an demselben Speicherort, den Sie für die Dateispeicherung angegeben haben, wenn Sie Ihre Front-End-Server oder Standard Edition-Server einrichten. Sie können keinen separaten Speicherort für die Archivierung von Dateispeicher angeben, daher ist für die Archivierung von Datei speichern keine separate Systemplattform erforderlich. Wenn Sie Microsoft Exchange Integration verwenden, werden Exchange 2013 die Dateien für archivierte lync-Kommunikation auf Exchange 2013 Servern für Benutzer gespeichert, die auf diesen Exchange-Servern verwaltet werden.

</div>

<span> </span>

</div>

</div>

</div>

