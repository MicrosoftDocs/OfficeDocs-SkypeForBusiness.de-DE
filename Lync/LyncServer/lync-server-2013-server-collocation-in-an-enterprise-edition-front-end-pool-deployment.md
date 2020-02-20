---
title: Lync Server 2013 Server-Zusammenstellungen in einer Enterprise Edition-Front-End-Pool Bereitstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44b6c298d6c0d2116be92d5e267ef9b7418ea480
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144013"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Server Zusammenstellungen in einer Enterprise Edition-Front-End-Pool Bereitstellung für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-11_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013 Front-End-Pool-Bereitstellung collocate können.

<div>

## <a name="server-roles"></a>Serverrollen

In lync Server 2013 werden A/V-Konferenzdienst, Vermittlungsdienst, Überwachung und Archivierung auf dem Front-End-Server zusammengefasst, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren. Falls Sie den Vermittlungsserver nicht mit dem Front-End-Server verbinden möchten, können Sie ihn als eigenständigen Vermittlungsserver auf einem separaten Computer bereitstellen.

Sie können einen vertrauenswürdigen Anwendungsserver mit dem Front-End-Server verbinden.

Die folgenden Serverrollen müssen auf jeweils einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (sofern nicht gemeinsam mit dem Front-End-Server ausgeführt)

  - Office Web Apps-Server

Sie können die Serverrolle "persistent Chat" nicht mit dem Front-End-Server collocate.

</div>

<div>

## <a name="databases"></a>Datenbanken

Sie können jede der folgenden Datenbanken auf demselben Datenbankserver ausführen:

  - Back-End-Datenbank

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Sie können eine oder alle diese Datenbanken in einer einzigen SQL Server Instanz collocate oder eine separate Instanz von SQL Server für jede verwenden, mit den folgenden Einschränkungen:

  - Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne Datenbank für beständigen Chat und eine einzelne Datenbank für beständigen Chat enthalten.

  - Der Datenbankserver kann nicht mehr als eine Front-End-Pool, eine Archivierungs Bereitstellung und eine Überwachungs Bereitstellung unterstützen, kann jedoch eines der beiden unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

Die gemeinsame Ausführung einer Dateifreigabe mit den Datenbanken ist möglich, wie weiter unten in diesem Abschnitt beschrieben.

<div>


> [!NOTE]  
> In lync Server 2013 haben Sie die Möglichkeit, den Archivierungsspeicher mit Exchange 2013 Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren. Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie der Exchange-Speicher bereitstellen.



</div>

<div>


> [!IMPORTANT]  
> Die gemeinsame Ausführung von Datenbanken wird zwar unterstützt, die Datenbanken können jedoch schnell wachsen. Wenn Sie beispielsweise in Erwägung ziehen, die Archivierungsdatenbank mit anderen Datenbanken zu verbinden, müssen Sie beachten, dass beim Archivieren der Nachrichten von mehreren Benutzern der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß sein kann. Aus diesem Grund wird nicht empfohlen, mehrere Datenbanken abstimmen, insbesondere die Archivierungsdatenbank, die Datenbank für beständigen Chat oder die Kompatibilitätsdatenbank für beständigen Chat mit der Back-End-Datenbank.



</div>

</div>

<div>

## <a name="file-share"></a>Dateifreigabe

Die Dateifreigabe kann auf einem separaten Server oder auf demselben Server wie folgende Server ausgeführt werden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Eine einzige Dateifreigabe kann für mehrere Front-End-Pools und Standard Edition-Server (alle am gleichen Standort) verwendet werden.

<div>


> [!NOTE]  
> In lync Server 2013 verwenden Überwachung und Archivierung die lync Server Dateifreigabe als Front-End-Server.



</div>

</div>

<div>

## <a name="other-components"></a>Weitere Komponenten

Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013 Komponente handelt, aber in Ihrer Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten. Sie können jedoch Reverse-Proxy Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverseproxy in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.

Sie können keine Exchange Unified Messaging (um) Komponente oder SharePoint-Komponente mit einer SharePoint Server Rolle collocate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

