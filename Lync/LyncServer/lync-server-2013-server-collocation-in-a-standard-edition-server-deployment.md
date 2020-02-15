---
title: Lync Server 2013 Server-nebeneinander in einer Standard Edition-Server-Bereitstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 428f666ade00d2f809f25cb7eb9ef1525d7f835c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Server Zusammenstellung in einer Standard Edition-Server-Bereitstellung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-20_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013 Standard Edition-Server-Bereitstellung collocate können.

<div>

## <a name="server-roles"></a>Serverrollen

In lync Server 2013 werden A/V-Konferenzdienst, Vermittlungsdienst, Überwachung und Archivierung auf dem Standard Edition-Server zusammengefasst, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren. Sie können den Vermittlungsdienst auf verschiedenen Servern bereitstellen.

Sie können einen vertrauenswürdigen Andwendungsserver mit einem Standard Edition-Server verbinden.

Die folgenden Serverrollen müssen jede auf einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (sofern nicht gemeinsam mit dem Standard Edition-Server ausgeführt)

  - Office Web Apps-Server

</div>

<div>

## <a name="databases"></a>Datenbanken

Die SQL Server Express-Back-End-Datenbank wird standardmäßig mit dem Standard Edition-Server verbunden. Sie kann nicht auf einen separaten Computer verschoben werden. Mit einer Ausnahme können Sie andere Datenbanken im Standard Edition-Server nicht collocate. Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen, können Sie die Datenbank für beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat auf demselben Standard Edition-Server collocate.

Sie können jede der folgenden Datenbanken mit einem einzigen Datenbankserver verbinden:

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Eine Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool

Sie können diese Datenbanken einzeln oder alle in einer einzigen SQL-Instanz verbinden oder für jede eine separate SQL-Instanz verwenden, wobei folgende Beschränkungen gelten:

  - Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank (für einen Enterprise Edition-Front-End-Pool), eine einzige Überwachungsdatenbank, eine einzige Archivierungsdatenbank, eine einzige Datenbank für beständigen Chat und eine einzige Kompatibilitätsdatenbank für beständigen Chat enthalten.

  - Der Datenbankserver kann nicht mehrere Enterprise Edition-Front-End-Pool, einen Server, auf dem die Archivierung durchführen wird, eine Überwachung, eine einzelne Datenbank für beständigen Chat und eine einzelne Datenbank für beständigen Chat, aber eine der beiden unterstützen. unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

Die gemeinsame Ausführung einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.

<div>


> [!NOTE]  
> In lync Server 2013 haben Sie die Möglichkeit, Überwachungs-und Archivierungsspeicher mit Exchange 2013 Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren. Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie der Exchange-Speicher bereitstellen.



</div>

<div>


> [!IMPORTANT]  
> Die gemeinsame Ausführung von Datenbanken wird zwar unterstützt, die Datenbanken können jedoch schnell wachsen. Wenn Sie beispielsweise in Erwägung ziehen, die Archivierungsdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann. Aus diesem Grund wird nicht empfohlen, mehrere Datenbanken abstimmen, insbesondere die Datenbank für Archivierungsdatenbank, beständigen Chat und die Kompatibilitätsdatenbank für beständigen Chat mit der Back-End-Datenbank eines Enterprise-Pool.



</div>

</div>

<div>

## <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann ein separater Server sein oder mit dem gleichen Server wie die folgenden Komponenten (einzeln oder alle) verbunden werden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Eine einzige Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (alle am gleichen Standort) verwendet werden.

<div>


> [!NOTE]  
> In lync Server 2013 verwenden Überwachung und Archivierung die lync Server Dateifreigabe als Standard Edition-Server.



</div>

</div>

<div>

## <a name="other-components"></a>Weitere Komponenten

Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber in Ihrer Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten. Sie können jedoch Reverse-Proxy Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.

Sie können keine Exchange um Komponente oder SharePoint-Komponente mit einer lync Server 2013 Rolle collocate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

