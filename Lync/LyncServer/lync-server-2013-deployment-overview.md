---
title: 'Lync Server 2013: Übersicht über die Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment overview
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205305(v=OCS.15)
ms:contentKeyID: 48185555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b21d6c6a977fbb94a54114753f32c022aa5e713
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-overview-for-lync-server-2013"></a>Übersicht über die Bereitstellung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-12_

Der Hauptunterschied zwischen lync Server 2013 Enterprise Edition und lync Server 2013 Standard Edition besteht darin, dass die Standard Edition die in Enterprise Edition enthaltenen Features für hohe Verfügbarkeit nicht unterstützt. Für hohe Verfügbarkeit müssen Sie mehrere Front-End-Server in einem Pool bereitstellen und dann den Server mit SQL Server spiegeln. Mit Enterprise Edition können Sie eine eigenständige Vermittlungsserver festlegen oder collocate. Die Monitoring Server und Archivierungsserver können einen eigenständigen Server mit SQL Server verwenden. Sie können auch Instanzen von SQL Server haben, die auf dem Daten Bank Server für die Front-End-Server und-Pools aktiv sind.

Server, auf denen lync Server 2013 Standard Edition betrieben wird, sind für kleinere Organisationen und Remotestandorte gedacht, die geografisch aus der Haupt Bereitstellungs Organisation entfernt werden. Zwei Standard Edition-Server-Server, die bei einem Notfall für ein Failover zusammengefügt wurden, können bis zu 5.000 Benutzer unterstützen. Sie können keine Standard Edition-Server wie die Front-End-Server in Enterprise Edition Pool. Außerdem ist die SQL Server-Datenbank, die von Standard Edition verwendet wird, ein zusammengefasster Server mit SQL Server Express, der Standard Edition-Server Arbeitslasten verarbeiten soll. Dies bedeutet nicht, dass sich alle Rollen auf einem Standard Edition-Server befinden müssen. Sie können eigenständige Vermittlungsserver und Edgeserver haben. Die SQL Server Datenbank für den zentralen Verwaltungsspeicher und für die Zwecke von lync Server 2013 muss sich in der Standard Edition-Server befinden, die mit dem Server mit SQL Server verbunden ist. Die Monitoring Server und Archivierungsserver verwenden einen eigenständigen Server mit der SQL Server Datenbank.

</div>

<span> </span>

</div>

</div>

</div>

