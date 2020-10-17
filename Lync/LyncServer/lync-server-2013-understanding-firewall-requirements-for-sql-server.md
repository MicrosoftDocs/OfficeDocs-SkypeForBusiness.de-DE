---
title: 'Lync Server 2013: Grundlegendes zu Firewall-Anforderungen für SQL Server'
description: 'Lync Server 2013: Grundlegendes zu Firewall-Anforderungen für SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Understanding firewall requirements for SQL Server
ms:assetid: 31d7df2c-589f-465e-be74-cf6767db190d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425818(v=OCS.15)
ms:contentKeyID: 48183781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434474b36ced0fe64b9398f7d0e6136ff523a93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542381"
---
# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="d165e-103">Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d165e-103">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d165e-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d165e-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d165e-105">Bei einer Standard Edition-Bereitstellung werden während lync Server 2013 Setups automatisch Firewall-Ausnahmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d165e-105">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="d165e-106">Für Enterprise Edition-Bereitstellungen müssen Sie die Firewall-Ausnahmen jedoch manuell auf dem SQL Server Back-End-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d165e-106">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="d165e-107">Beim TCP/IP-Protokoll kann ein Port nur für eine bestimmte IP-Adresse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d165e-107">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="d165e-108">Dies bedeutet, dass Sie der Standarddatenbankinstanz für den SQL Server-basierten Server den standardmäßigen TCP-Port 1433 zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="d165e-108">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="d165e-109">Für alle weiteren Instanzen müssen Sie mit dem SQL Server-Konfigurations-Manager eindeutige, nicht verwendete Ports zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d165e-109">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="d165e-110">In diesem Abschnitt werden folgende Themen behandelt:</span><span class="sxs-lookup"><span data-stu-id="d165e-110">This topic covers:</span></span>

  - <span data-ttu-id="d165e-111">Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="d165e-111">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="d165e-112">Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="d165e-112">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="d165e-113">Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="d165e-113">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="d165e-114">Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="d165e-114">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="d165e-115">Wenn Sie bei der Bereitstellung von lync Server 2013 die SQL Server Standardinstanz für eine Datenbank verwenden, werden die folgenden Firewall-Regel Anforderungen verwendet, um die Kommunikation zwischen der Front-End-Pool und der SQL Server Standardinstanz sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d165e-115">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d165e-116">Protokoll</span><span class="sxs-lookup"><span data-stu-id="d165e-116">Protocol</span></span></th>
<th><span data-ttu-id="d165e-117">Port</span><span class="sxs-lookup"><span data-stu-id="d165e-117">Port</span></span></th>
<th><span data-ttu-id="d165e-118">Direction</span><span class="sxs-lookup"><span data-stu-id="d165e-118">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d165e-119">TCP</span><span class="sxs-lookup"><span data-stu-id="d165e-119">TCP</span></span></p></td>
<td><p><span data-ttu-id="d165e-120">1433</span><span class="sxs-lookup"><span data-stu-id="d165e-120">1433</span></span></p></td>
<td><p><span data-ttu-id="d165e-121">Eingehend zu SQL Server</span><span class="sxs-lookup"><span data-stu-id="d165e-121">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="d165e-122">Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="d165e-122">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="d165e-123">Der SQL Server-Browserdienst ermittelt die Datenbankinstanzen und kommuniziert den Port, für dessen Verwendung die Instanz (benannte Instanz oder Standardinstanz) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="d165e-123">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d165e-124">Protokoll</span><span class="sxs-lookup"><span data-stu-id="d165e-124">Protocol</span></span></th>
<th><span data-ttu-id="d165e-125">Port</span><span class="sxs-lookup"><span data-stu-id="d165e-125">Port</span></span></th>
<th><span data-ttu-id="d165e-126">Direction</span><span class="sxs-lookup"><span data-stu-id="d165e-126">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d165e-127">UDP</span><span class="sxs-lookup"><span data-stu-id="d165e-127">UDP</span></span></p></td>
<td><p><span data-ttu-id="d165e-128">1434</span><span class="sxs-lookup"><span data-stu-id="d165e-128">1434</span></span></p></td>
<td><p><span data-ttu-id="d165e-129">Eingehend</span><span class="sxs-lookup"><span data-stu-id="d165e-129">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="d165e-130">Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="d165e-130">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="d165e-131">Bei der Verwendung benannter Instanzen in der SQL Server-Konfiguration für Datenbanken, die lync Server 2013 unterstützen, konfigurieren Sie statische Ports mithilfe von SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="d165e-131">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="d165e-132">Nachdem die statischen Ports für jede benannte Instanz zugewiesen wurden, erstellen Sie Ausnahmen für jeden statischen Port in der Firewall.</span><span class="sxs-lookup"><span data-stu-id="d165e-132">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d165e-133">Protokoll</span><span class="sxs-lookup"><span data-stu-id="d165e-133">Protocol</span></span></th>
<th><span data-ttu-id="d165e-134">Port</span><span class="sxs-lookup"><span data-stu-id="d165e-134">Port</span></span></th>
<th><span data-ttu-id="d165e-135">Direction</span><span class="sxs-lookup"><span data-stu-id="d165e-135">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d165e-136">TCP</span><span class="sxs-lookup"><span data-stu-id="d165e-136">TCP</span></span></p></td>
<td><p><span data-ttu-id="d165e-137">Als statisch definiert</span><span class="sxs-lookup"><span data-stu-id="d165e-137">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="d165e-138">Eingehend</span><span class="sxs-lookup"><span data-stu-id="d165e-138">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="d165e-139">SQL Server Dokumentation</span><span class="sxs-lookup"><span data-stu-id="d165e-139">SQL Server Documentation</span></span>

<span data-ttu-id="d165e-140">In Microsoft SQL Server 2012-Dokumentation finden Sie detaillierte Anleitungen zum Konfigurieren des Firewall-Zugriffs für Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="d165e-140">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="d165e-141">Ausführliche Informationen zu Microsoft SQL Server 2012 finden Sie unter "Konfigurieren der Windows-Firewall, um SQL Server Zugriff zu ermöglichen" unter [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031) .</span><span class="sxs-lookup"><span data-stu-id="d165e-141">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

