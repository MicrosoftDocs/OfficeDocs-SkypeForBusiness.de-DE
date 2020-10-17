---
title: 'Lync Server 2013: Internet Information Services (IIS) Anforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0c1c9966945554af6d1d9cec02a17dd884a857
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498482"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="dc003-102">Internet Information Services (IIS) Anforderungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc003-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc003-103">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="dc003-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="dc003-104">Mehrere lync Server 2013 Komponenten erfordern Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dc003-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="dc003-105">In diesem Thema werden die spezifischen IIS-Features beschrieben, die zur Unterstützung von lync Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dc003-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="dc003-106">In den Abschnitten dieses Themas werden die Anforderungen spezifischer Komponenten in Bezug auf IIS erläutert.</span><span class="sxs-lookup"><span data-stu-id="dc003-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="dc003-p102">Wenn die Webserverrolle (IIS) auf Windows Server 2008 aktiviert wird, werden standardmäßig verschiedene Rollendienste installiert. In der folgenden Tabelle werden die zusätzlichen Rollendienste beschrieben, die bei Aktivierung der Webserverrolle (IIS) auf Windows Server 2008 installiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="dc003-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc003-109">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="dc003-109">Role service</span></span></th>
<th><span data-ttu-id="dc003-110">Feature</span><span class="sxs-lookup"><span data-stu-id="dc003-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc003-111">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="dc003-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="dc003-112">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="dc003-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc003-113">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="dc003-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="dc003-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dc003-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc003-115">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="dc003-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="dc003-116">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="dc003-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc003-117">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="dc003-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="dc003-118">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="dc003-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc003-119">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="dc003-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="dc003-120">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="dc003-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc003-121">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="dc003-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="dc003-122">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="dc003-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc003-123">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="dc003-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="dc003-124">Tracing</span><span class="sxs-lookup"><span data-stu-id="dc003-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc003-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dc003-125">Security</span></span></p></td>
<td><p><span data-ttu-id="dc003-126">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="dc003-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc003-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="dc003-127">Security</span></span></p></td>
<td><p><span data-ttu-id="dc003-128">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dc003-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc003-129">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="dc003-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="dc003-130">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="dc003-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc003-131">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="dc003-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="dc003-132">IIS 6-Verwaltungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="dc003-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="dc003-134">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="dc003-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="dc003-135">Wenn Sie IIS 7,0 auf einem Windows Server 2008 Betriebssystem verwenden, deaktiviert lync Server Setup die Kernelmodus-Authentifizierung in IIS.</span><span class="sxs-lookup"><span data-stu-id="dc003-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc003-136">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dc003-136">In This Section</span></span>

  - [<span data-ttu-id="dc003-137">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dc003-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

