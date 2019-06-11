---
title: 'Lync Server 2013: Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947d732cf17cc053e48596ffd310f5df3b11636
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a>Gemeinsames Ausführen von Servern in einer Bereitstellung eines Front-End-Pools von Enterprise Edition für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-11_

In diesem Abschnitt werden die Serverrollen, Datenbanken und Dateifreigaben beschrieben, die Sie in einer lync Server 2013-collocate bereitstellen können.

<div>

## <a name="server-roles"></a>Server Rollen

In lync Server 2013 sind A/V-Konferenzdienst, Mediationsdienst, Überwachung und Archivierung auf dem Front-End-Server verfügbar, es ist jedoch eine zusätzliche Konfiguration erforderlich, um Sie zu aktivieren. Wenn Sie den Vermittlungsserver nicht mit dem Front-End-Server collocate möchten, können Sie ihn als eigenständigen Vermittlungsserver auf einem separaten Computer bereitstellen.

Sie können einen vertrauenswürdigen Anwendungsserver mit dem Front-End-Server collocate.

Die folgenden Serverrollen müssen jeweils auf einem separaten Computer bereitgestellt werden:

  - Director

  - Edgeserver

  - Vermittlungsserver (falls nicht mit dem Front-End-Server)

  - Office Web Apps-Server

Sie können die Serverfunktion "beständiger Chat" nicht mit dem Front-End-Server collocate.

</div>

<div>

## <a name="databases"></a>Datenbanken

Sie können jede der folgenden Datenbanken auf demselben Datenbankserver collocate:

  - Back-End-Datenbank

  - Überwachungsdatenbank

  - Archivierungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Sie können jede oder alle dieser Datenbanken in einer einzelnen Instanz von SQL Server collocate oder eine separate Instanz von SQL Server für jeden verwenden, wobei die folgenden Einschränkungen gelten:

  - Jede Instanz von SQL Server kann nur eine einzige Back-End-Datenbank, eine einzelne Überwachungsdatenbank, eine einzelne Archivierungsdatenbank, eine einzelne persistent Chat-Datenbank und eine einzelne Datenbank für beständigen Chat enthalten.

  - Der Datenbankserver kann nicht mehr als einen Front-End-Pool, eine Archivierungs Bereitstellung und eine Überwachungs Bereitstellung unterstützen, aber er kann jeweils eine davon unterstützen, unabhängig davon, ob die Datenbanken dieselbe Instanz von SQL Server oder separate Instanzen von SQL Server verwenden.

Sie können eine Dateifreigabe für die Datenbanken collocate, wie weiter unten in diesem Abschnitt beschrieben.

<div>


> [!NOTE]  
> In lync Server 2013 haben Sie die Möglichkeit, den Archivierungsspeicher mit Exchange 2013-Speicher für einige oder alle Benutzer in Ihrer Bereitstellung zu integrieren. Sie können keine Server mit lync Server oder Komponenten auf denselben Servern wie dem Exchange-Speicher bereitstellen.



</div>

<div>


> [!IMPORTANT]  
> Obwohl die Daten Bank Zusammenstellung unterstützt wird, kann die Größe der Datenbanken schnell zunehmen. Wenn Sie beispielsweise die Archivierungsdatenbank mit anderen Datenbanken abstimmen, beachten Sie Folgendes: Wenn Sie die Nachrichten von mehr als wenigen Benutzern archivieren, kann der von der Archivierungsdatenbank benötigte Speicherplatz sehr groß werden. Aus diesem Grund empfehlen wir nicht, abstimmen mehrere Datenbanken, insbesondere die Archivierungsdatenbank, die persistente Chat-Datenbank, oder die beständige Chat-Kompatibilitätsdatenbank mit der Back-End-Datenbank zu verwenden.



</div>

</div>

<div>

## <a name="file-share"></a>Dateifreigabe

Die Dateifreigabe kann ein separater Server sein oder sich auf dem gleichen Server wie die folgenden befinden:

  - Datenbankserver, einschließlich des Back-End-Servers eines Enterprise Edition-Front-End-Pools

  - Archivierungsdatenbank

  - Überwachungsdatenbank

  - Datenbank für beständigen Chat

  - Kompatibilitätsdatenbank für beständigen Chat

Eine einzelne Dateifreigabe kann für mehrere Front-End-Pools, Standard Edition-Server (alle auf der gleichen Website), verwendet werden.

<div>


> [!NOTE]  
> In lync Server 2013 verwenden die Überwachung und Archivierung die lync Server-Dateifreigabe als Front-End-Server.



</div>

</div>

<div>

## <a name="other-components"></a>Andere Komponenten

Sie können keinen Reverseproxy-Server collocate, bei dem es sich nicht um eine lync Server 2013-Komponente handelt, aber für Ihre Bereitstellung erforderlich ist, wenn Sie die Freigabe von Webinhalten für Verbundbenutzer mit einer beliebigen lync Server 2013-Serverrolle unterstützen möchten. Sie können jedoch eine Reverse-Proxy-Unterstützung für eine lync Server 2013-Bereitstellung implementieren, indem Sie die Unterstützung für einen vorhandenen Reverse-Proxy Server in Ihrer Organisation konfigurieren, der für andere Anwendungen verwendet wird.

Sie können keine Exchange Unified Messaging (um)-Komponente oder SharePoint-Komponente mit einer SharePoint Server-Rolle collocate.

</div>

</div>

<span> </span>

</div>

</div>

</div>

