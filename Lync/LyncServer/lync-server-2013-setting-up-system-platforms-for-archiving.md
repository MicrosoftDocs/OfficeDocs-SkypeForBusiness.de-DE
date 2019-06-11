---
title: 'Lync Server 2013: Einrichten von Systemplattformen für die Archivierung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d8d9499d68bcca3848e1e069b4962bb7526091d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Einrichten von Systemplattformen für die Archivierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Bevor Sie die Bereitstellung der Archivierung starten, müssen Sie das erforderliche Betriebssystem und alle anderen erforderlichen Software auf Hardware installieren, die den Systemanforderungen entspricht:

  - **Lync Server 2013 Platform**   lync Server 2013-Bereitstellungen verfügen nicht über Archivierungsserver. Stattdessen werden Unified Data Collection-Agents auf Front-End-Servern und Standard Edition-Servern ausgeführt, um Daten für die Archivierung zu erfassen, sodass keine separate Systemplattform zum Hosten der Archivierung erforderlich ist.

  - **Datenspeicherplattform**   in lync Server 2013 können Sie Daten mithilfe einer der folgenden Optionen speichern:
    
      - **Microsoft Exchange-Integration**   Wenn Sie lync Server 2013-Archivierungsdaten mithilfe Ihrer Exchange 2013-Bereitstellung speichern möchten, anstatt eine separate Datenbank für die Speicherung von Archivierungsdaten einzurichten, muss Ihre Exchange-Bereitstellung Exchange 2013 wird ausgeführt. Details zum Einrichten von Systemplattformen für Exchange 2013 finden Sie in der Exchange-Produktdokumentation.
    
      - **SQL Server**   Wenn Sie eine separate SQL Server-Datenbank für die Speicherung von Archivierungsdaten verwenden möchten, müssen Sie die Systemplattform für die Datenbank vor der Bereitstellung der Archivierung einrichten, anstatt die Microsoft Exchange-Integration zu verwenden. Die spezifischen Anforderungen an die Systemplattform hängen davon ab, ob Sie Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für die Archivierungsdatenbank verwenden. Details zum Einrichten von Systemplattformen für diese Datenbanken finden Sie in der Produktdokumentation zu Microsoft SQL Server 2008 R2 und Microsoft SQL Server 2012.

  - **Die Dateiserver Plattform**   lync Server 2013 speichert lync Server-Archivierungsdateien an dem Speicherort, den Sie für die Dateispeicherung angeben, wenn Sie Ihre Front-End-Server oder Standard Edition-Server einrichten. Sie können keinen separaten Speicherort für das Archivieren von Dateispeicher angeben, daher ist keine separate Systemplattform für die Archivierung von Dateispeicher erforderlich. Wenn Sie die Microsoft Exchange-Integration verwenden, werden die Dateien für archivierte lync-Kommunikationen auf Exchange 2013 2013-Servern für Benutzer gespeichert, die auf diesen Exchange-Servern verwaltet werden.

</div>

<span> </span>

</div>

</div>

</div>

