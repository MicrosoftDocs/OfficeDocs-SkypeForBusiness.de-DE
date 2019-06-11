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

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="28d1d-102">Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28d1d-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28d1d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="28d1d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="28d1d-104">Bei einer Standard Edition-Bereitstellung werden Firewall-Ausnahmen beim Einrichten von lync Server 2013 automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="28d1d-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="28d1d-105">Bei Enterprise Edition-Bereitstellungen müssen Sie die Firewall-Ausnahmen jedoch manuell auf dem SQL Server-Back-End-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="28d1d-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="28d1d-106">Das TCP/IP-Protokoll ermöglicht es, einen bestimmten Port einmal für eine bestimmte IP-Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="28d1d-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="28d1d-107">Das bedeutet, dass Sie für den SQL Server-basierten Server die standardmäßige Datenbankinstanz den standardmäßigen TCP-Port 1433 zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="28d1d-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="28d1d-108">Für alle anderen Instanzen müssen Sie den SQL Server-Konfigurations-Manager verwenden, um eindeutige und nicht verwendete Ports zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="28d1d-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="28d1d-109">In diesem Thema wird Folgendes behandelt:</span><span class="sxs-lookup"><span data-stu-id="28d1d-109">This topic covers:</span></span>

  - <span data-ttu-id="28d1d-110">Voraussetzungen für eine Firewall-Ausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="28d1d-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="28d1d-111">Voraussetzungen für eine Firewall-Ausnahme für den SQL Server-Browser Dienst</span><span class="sxs-lookup"><span data-stu-id="28d1d-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="28d1d-112">Voraussetzungen für statische Abhör Anschlüsse bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="28d1d-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="28d1d-113">Voraussetzungen für eine Firewall-Ausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="28d1d-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="28d1d-114">Wenn Sie bei der Bereitstellung von lync Server 2013 die SQL Server-Standardinstanz für eine Datenbank verwenden, werden die folgenden Firewall-Regel Anforderungen verwendet, um die Kommunikation zwischen dem Front-End-Pool und der SQL Server-Standardinstanz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="28d1d-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28d1d-115">Protokoll</span><span class="sxs-lookup"><span data-stu-id="28d1d-115">Protocol</span></span></th>
<th><span data-ttu-id="28d1d-116">Port</span><span class="sxs-lookup"><span data-stu-id="28d1d-116">Port</span></span></th>
<th><span data-ttu-id="28d1d-117">Richtung</span><span class="sxs-lookup"><span data-stu-id="28d1d-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28d1d-118">TCP</span><span class="sxs-lookup"><span data-stu-id="28d1d-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="28d1d-119">1433</span><span class="sxs-lookup"><span data-stu-id="28d1d-119">1433</span></span></p></td>
<td><p><span data-ttu-id="28d1d-120">Eingehend zu SQL Server</span><span class="sxs-lookup"><span data-stu-id="28d1d-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="28d1d-121">Voraussetzungen für eine Firewall-Ausnahme für den SQL Server-Browser Dienst</span><span class="sxs-lookup"><span data-stu-id="28d1d-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="28d1d-122">Der SQL Server-Browser Dienst findet Datenbankinstanzen und kommuniziert den Port, der für die Verwendung der Instanz (benannt oder Standard) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="28d1d-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28d1d-123">Protokoll</span><span class="sxs-lookup"><span data-stu-id="28d1d-123">Protocol</span></span></th>
<th><span data-ttu-id="28d1d-124">Port</span><span class="sxs-lookup"><span data-stu-id="28d1d-124">Port</span></span></th>
<th><span data-ttu-id="28d1d-125">Richtung</span><span class="sxs-lookup"><span data-stu-id="28d1d-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28d1d-126">UDP</span><span class="sxs-lookup"><span data-stu-id="28d1d-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="28d1d-127">1434</span><span class="sxs-lookup"><span data-stu-id="28d1d-127">1434</span></span></p></td>
<td><p><span data-ttu-id="28d1d-128">Inbound</span><span class="sxs-lookup"><span data-stu-id="28d1d-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="28d1d-129">Voraussetzungen für statische Abhör Anschlüsse bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="28d1d-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="28d1d-130">Wenn Sie benannte Instanzen in der SQL Server-Konfiguration für Datenbanken verwenden, die lync Server 2013 unterstützen, konfigurieren Sie statische Ports mithilfe des SQL Server-Konfigurations-Managers.</span><span class="sxs-lookup"><span data-stu-id="28d1d-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="28d1d-131">Nachdem die statischen Ports jeder benannten Instanz zugewiesen wurden, erstellen Sie Ausnahmen für jeden statischen Port in der Firewall.</span><span class="sxs-lookup"><span data-stu-id="28d1d-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="28d1d-132">Protokoll</span><span class="sxs-lookup"><span data-stu-id="28d1d-132">Protocol</span></span></th>
<th><span data-ttu-id="28d1d-133">Port</span><span class="sxs-lookup"><span data-stu-id="28d1d-133">Port</span></span></th>
<th><span data-ttu-id="28d1d-134">Richtung</span><span class="sxs-lookup"><span data-stu-id="28d1d-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28d1d-135">TCP</span><span class="sxs-lookup"><span data-stu-id="28d1d-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="28d1d-136">Statisch definiert</span><span class="sxs-lookup"><span data-stu-id="28d1d-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="28d1d-137">Inbound</span><span class="sxs-lookup"><span data-stu-id="28d1d-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="28d1d-138">SQL Server-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="28d1d-138">SQL Server Documentation</span></span>

<span data-ttu-id="28d1d-139">In der Microsoft SQL Server 2012-Dokumentation finden Sie detaillierte Anleitungen zum Konfigurieren des Firewall-Zugriffs für Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="28d1d-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="28d1d-140">Details zu Microsoft SQL Server 2012 finden Sie unter "Konfigurieren der Windows-Firewall, um SQL Server-Zugriff [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031)zu ermöglichen".</span><span class="sxs-lookup"><span data-stu-id="28d1d-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [http://go.microsoft.com/fwlink/p/?linkId=218031](http://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

