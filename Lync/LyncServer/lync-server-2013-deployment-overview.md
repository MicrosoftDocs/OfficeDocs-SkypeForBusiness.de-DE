---
title: 'Lync Server 2013: Übersicht über die Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f71a61e2bd374f1dfe2863aead5bbadc23c8afe8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Übersicht über die Bereitstellung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-12_

Der Hauptunterschied zwischen lync Server 2013 Enterprise Edition und lync Server 2013 Standard Edition besteht darin, dass Standard Edition die in Enterprise Edition enthaltenen Features für die Verfügbarkeit von Funktionen nicht unterstützt. Für eine höhere Verfügbarkeit müssen Sie mehrere Front-End-Server in einem Pool bereitstellen, und Sie können den Server, auf dem SQL Server ausgeführt wird, spiegeln. Mit Enterprise Edition können Sie einen eigenständigen Vermittlungs Server collocate oder definieren. Der Überwachungsserver und der Archivierungsserver können einen eigenständigen Server verwenden, auf dem SQL Server ausgeführt wird. Oder es können Instanzen von SQL Server auf dem Datenbankserver für die Front-End-Server und-Pools ausgeführt werden.

Server mit lync Server 2013 Standard Edition sind für kleinere Organisationen und Remotestandorte vorgesehen, die geografisch aus der Haupt Bereitstellung des Unternehmens entfernt sind. Zwei Standard Edition-Server Server, die für Failover im Notfall kombiniert werden, können bis zu 5.000-Benutzer unterstützen. Sie können keine Standard Edition-Server wie Front-End-Server in Enterprise Edition Poolen. Darüber hinaus ist die SQL Server-Datenbank, die von der Standard Edition verwendet wird, ein Server mit SQL Server Express, der für die Verarbeitung von Arbeitsauslastungen auf Standard Edition ausgelegt ist. Damit soll nicht gesagt werden, dass sich alle Rollen auf einem Standard Edition-Server befinden müssen. Sie können eigenständige Vermittlungsserver und Edgeserver besitzen. Die SQL Server-Datenbank für den zentralen Verwaltungsspeicher und für die Zwecke von lync Server 2013 muss sich auf dem Standard Edition-Server befinden, der mit dem Server mit SQL Server ausgestattet ist. Der Überwachungsserver und der Archivierungsserver verwenden einen eigenständigen Server mit der SQL Server-Datenbank.

</div>

<span> </span>

</div>

</div>

</div>

