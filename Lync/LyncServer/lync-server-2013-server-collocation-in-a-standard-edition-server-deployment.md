---
title: 'Lync Server 2013: Gemeinsames Ausführen von Servern in einer Standard Edition-Serverbereitstellung'
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
ms.openlocfilehash: 6fa25655fd9bdd2551e10d1fbbf0de617b89be64
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a>Gemeinsames Ausführen von Servern in einer Standard Edition-Serverbereitstellung für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-20_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013 Standard Edition-Server Bereitstellung collocate können.

<div>

## <a name="server-roles"></a>Server Rollen

In lync Server 2013 sind A/V-Konferenzdienst, Mediationsdienst, Überwachung und Archivierung auf dem Standard Edition-Server verfügbar, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren. Sie können den Vermittlungsdienst auf separaten Servern bereitstellen.

Sie können einen vertrauenswürdigen Anwendungsserver mit einem Standard Edition-Server collocate.

Die folgenden Serverrollen müssen jeweils auf einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (wenn Sie nicht mit dem Standard Edition-Server ausgestattet sind)

  - Office Web Apps-Server

</div>

<div>

## <a name="databases"></a>Datenbanken

Standardmäßig befindet sich die SQL Server Express-Back-End-Datenbank auf dem Standard Edition-Server. Sie können Sie nicht auf einen anderen Computer verschieben. Mit einer Ausnahme können Sie keine anderen Datenbanken auf dem Standard Edition-Server collocate. Wenn Sie den Server für beständigen Chat auf einem Standard Edition-Server bereitstellen möchten, können Sie die Datenbank für beständigen Chat und die Compliance-Datenbank für beständigen Chat auf demselben Standard Edition-Server collocate.

Sie können jede der folgenden Datenbanken auf einem einzelnen Datenbankserver collocate:

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Eine Back-End-Datenbank für einen Enterprise Edition-Front-End-Pool

Sie können eine beliebige oder eine beliebige oder alle dieser Datenbanken in einer einzelnen SQL-Instanz collocate oder für jede einzelne SQL-Instanzen verwenden, wobei die folgenden Einschränkungen gelten:

  - Jede SQL-Instanz kann nur eine einzige Back-End-Datenbank (für einen Enterprise Edition-Front-End-Pool), eine einzige Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne persistent Chat-Datenbank und eine einzelne beständige Chat-Kompatibilitätsdatenbank enthalten.

  - Der Datenbankserver kann nicht mehr als einen Enterprise Edition-Front-End-Pool, einen Server mit Archivierungsfunktion, einen Server mit Überwachung, eine einzige persistente Chat-Datenbank und eine einzelne beständige Chat-Compliance-Datenbank unterstützen, aber er kann jeweils eine davon unterstützen. unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

Sie können eine Dateifreigabe für die Datenbanken collocate, wie weiter unten in diesem Abschnitt beschrieben.

<div>


> [!NOTE]  
> In lync Server 2013 haben Sie die Möglichkeit, den Überwachungs-und Archivierungsspeicher mit Exchange 2013-Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren. Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie dem Exchange-Speicher bereitstellen.



</div>

<div>


> [!IMPORTANT]  
> Obwohl die Daten Bank Zusammenstellung unterstützt wird, kann die Größe der Datenbanken schnell zunehmen. Wenn Sie beispielsweise die Archivierungsdatenbank mit anderen Datenbanken abstimmen, beachten Sie Folgendes: Wenn Sie die Nachrichten von mehr als wenigen Benutzern archivieren, kann der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß werden. Aus diesem Grund raten wir davon ab, abstimmen mehrere Datenbanken, insbesondere die Archivierungsdatenbank, die persistente Chat-Datenbank und die beständige Chat-Kompatibilitätsdatenbank, mit der Back-End-Datenbank eines Enterprise-Pools zu verwenden.



</div>

</div>

<div>

## <a name="file-shares"></a>Dateifreigaben

Die Dateifreigabe kann ein separater Server sein oder sich auf dem gleichen Server wie die folgenden befinden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Eine einzelne Dateifreigabe kann für mehrere Front-End-Pools, Standard Edition-Server (alle auf der gleichen Website), verwendet werden.

<div>


> [!NOTE]  
> In lync Server 2013 verwenden die Überwachung und Archivierung die lync Server-Dateifreigabe als Standard Edition-Server.



</div>

</div>

<div>

## <a name="other-components"></a>Andere Komponenten

Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013-Komponente handelt, aber für Ihre Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten. Sie können jedoch eine Reverse-Proxy-Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverse-Proxy Server in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.

Sie können keine Exchange um-Komponente oder SharePoint-Komponente mit einer lync Server 2013-Rolle collocate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

