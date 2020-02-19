---
title: 'Lync Server 2013: Grundlegendes zu Firewall-Anforderungen für SQL Server'
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
ms.openlocfilehash: 38a6fba264edb7659ba9324ce663de9de38a575b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-firewall-requirements-for-sql-server-with-lync-server-2013"></a><span data-ttu-id="4c819-102">Grundlegendes zu Firewall-Anforderungen für SQL Server mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c819-102">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c819-103">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4c819-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4c819-104">Bei einer Standard Edition-Bereitstellung werden während lync Server 2013 Setups automatisch Firewall-Ausnahmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4c819-104">For a Standard Edition deployment, firewall exceptions are created automatically during Lync Server 2013 Setup.</span></span> <span data-ttu-id="4c819-105">Für Enterprise Edition-Bereitstellungen müssen Sie die Firewall-Ausnahmen jedoch manuell auf dem SQL Server Back-End-Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4c819-105">However, for Enterprise Edition deployments, you must configure the firewall exceptions manually on the SQL Server Back End Server.</span></span> <span data-ttu-id="4c819-106">Beim TCP/IP-Protokoll kann ein Port nur für eine bestimmte IP-Adresse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c819-106">The TCP/IP protocol allows for a given port to be used once for a given IP address.</span></span> <span data-ttu-id="4c819-107">Dies bedeutet, dass Sie der Standarddatenbankinstanz für den SQL Server-basierten Server den standardmäßigen TCP-Port 1433 zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="4c819-107">This means that for the SQL Server-based server you can assign the default database instance the default TCP port 1433.</span></span> <span data-ttu-id="4c819-108">Für alle weiteren Instanzen müssen Sie mit dem SQL Server-Konfigurations-Manager eindeutige, nicht verwendete Ports zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4c819-108">For any other instances you will need to use the SQL Server Configuration Manager to assign unique and unused ports.</span></span> <span data-ttu-id="4c819-109">In diesem Abschnitt werden folgende Themen behandelt:</span><span class="sxs-lookup"><span data-stu-id="4c819-109">This topic covers:</span></span>

  - <span data-ttu-id="4c819-110">Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="4c819-110">Requirements for a firewall exception when using the default instance</span></span>

  - <span data-ttu-id="4c819-111">Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="4c819-111">Requirements for a firewall exception for the SQL Server Browser service</span></span>

  - <span data-ttu-id="4c819-112">Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="4c819-112">Requirements for static listening ports when using named instances</span></span>

<div>

## <a name="requirements-for-a-firewall-exception-when-using-the-default-instance"></a><span data-ttu-id="4c819-113">Anforderungen für eine Firewallausnahme bei Verwendung der Standardinstanz</span><span class="sxs-lookup"><span data-stu-id="4c819-113">Requirements for a Firewall Exception When Using the Default Instance</span></span>

<span data-ttu-id="4c819-114">Wenn Sie bei der Bereitstellung von lync Server 2013 die SQL Server Standardinstanz für eine Datenbank verwenden, werden die folgenden Firewall-Regel Anforderungen verwendet, um die Kommunikation zwischen der Front-End-Pool und der SQL Server Standardinstanz sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c819-114">If you are using the SQL Server default instance for any database when deploying Lync Server 2013, the following firewall rule requirements are used to help ensure communication from the Front End pool to the SQL Server default instance.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c819-115">Protokoll</span><span class="sxs-lookup"><span data-stu-id="4c819-115">Protocol</span></span></th>
<th><span data-ttu-id="4c819-116">Port</span><span class="sxs-lookup"><span data-stu-id="4c819-116">Port</span></span></th>
<th><span data-ttu-id="4c819-117">Direction</span><span class="sxs-lookup"><span data-stu-id="4c819-117">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c819-118">TCP</span><span class="sxs-lookup"><span data-stu-id="4c819-118">TCP</span></span></p></td>
<td><p><span data-ttu-id="4c819-119">1433</span><span class="sxs-lookup"><span data-stu-id="4c819-119">1433</span></span></p></td>
<td><p><span data-ttu-id="4c819-120">Eingehend zu SQL Server</span><span class="sxs-lookup"><span data-stu-id="4c819-120">Inbound to SQL Server</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-a-firewall-exception-for-the-sql-server-browser-service"></a><span data-ttu-id="4c819-121">Anforderungen für eine Firewallausnahme für den SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="4c819-121">Requirements for a Firewall Exception for the SQL Server Browser Service</span></span>

<span data-ttu-id="4c819-122">Der SQL Server-Browserdienst ermittelt die Datenbankinstanzen und kommuniziert den Port, für dessen Verwendung die Instanz (benannte Instanz oder Standardinstanz) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="4c819-122">The SQL Server Browser service will locate database instances and communicate the port that the instance (named or default) is configured to use.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c819-123">Protokoll</span><span class="sxs-lookup"><span data-stu-id="4c819-123">Protocol</span></span></th>
<th><span data-ttu-id="4c819-124">Port</span><span class="sxs-lookup"><span data-stu-id="4c819-124">Port</span></span></th>
<th><span data-ttu-id="4c819-125">Direction</span><span class="sxs-lookup"><span data-stu-id="4c819-125">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c819-126">UDP</span><span class="sxs-lookup"><span data-stu-id="4c819-126">UDP</span></span></p></td>
<td><p><span data-ttu-id="4c819-127">1434</span><span class="sxs-lookup"><span data-stu-id="4c819-127">1434</span></span></p></td>
<td><p><span data-ttu-id="4c819-128">Eingehend</span><span class="sxs-lookup"><span data-stu-id="4c819-128">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="requirements-for-static-listening-ports-when-using-named-instances"></a><span data-ttu-id="4c819-129">Anforderungen für statische Überwachungsports bei Verwendung benannter Instanzen</span><span class="sxs-lookup"><span data-stu-id="4c819-129">Requirements for Static Listening Ports When Using Named Instances</span></span>

<span data-ttu-id="4c819-130">Bei der Verwendung benannter Instanzen in der SQL Server-Konfiguration für Datenbanken, die lync Server 2013 unterstützen, konfigurieren Sie statische Ports mithilfe von SQL Server Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="4c819-130">When using named instances in the SQL Server configuration for databases supporting Lync Server 2013, you configure static ports by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="4c819-131">Nachdem die statischen Ports für jede benannte Instanz zugewiesen wurden, erstellen Sie Ausnahmen für jeden statischen Port in der Firewall.</span><span class="sxs-lookup"><span data-stu-id="4c819-131">After the static ports have been assigned to each named instance, you create exceptions for each static port in the firewall.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c819-132">Protokoll</span><span class="sxs-lookup"><span data-stu-id="4c819-132">Protocol</span></span></th>
<th><span data-ttu-id="4c819-133">Port</span><span class="sxs-lookup"><span data-stu-id="4c819-133">Port</span></span></th>
<th><span data-ttu-id="4c819-134">Direction</span><span class="sxs-lookup"><span data-stu-id="4c819-134">Direction</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c819-135">TCP</span><span class="sxs-lookup"><span data-stu-id="4c819-135">TCP</span></span></p></td>
<td><p><span data-ttu-id="4c819-136">Als statisch definiert</span><span class="sxs-lookup"><span data-stu-id="4c819-136">Statically defined</span></span></p></td>
<td><p><span data-ttu-id="4c819-137">Eingehend</span><span class="sxs-lookup"><span data-stu-id="4c819-137">Inbound</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="sql-server-documentation"></a><span data-ttu-id="4c819-138">SQL Server Dokumentation</span><span class="sxs-lookup"><span data-stu-id="4c819-138">SQL Server Documentation</span></span>

<span data-ttu-id="4c819-139">In Microsoft SQL Server 2012-Dokumentation finden Sie detaillierte Anleitungen zum Konfigurieren des Firewall-Zugriffs für Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="4c819-139">Microsoft SQL Server 2012 documentation provides detailed guidance on how to configure firewall access for databases.</span></span> <span data-ttu-id="4c819-140">Ausführliche Informationen zu Microsoft SQL Server 2012 finden Sie unter "Konfigurieren der Windows-Firewall, um SQL Server Zugriff [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031)zu ermöglichen" unter.</span><span class="sxs-lookup"><span data-stu-id="4c819-140">For details about Microsoft SQL Server 2012, see “Configuring the Windows Firewall to Allow SQL Server Access” at [https://go.microsoft.com/fwlink/p/?linkId=218031](https://go.microsoft.com/fwlink/p/?linkid=218031).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

