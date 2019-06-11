---
title: 'Lync Server 2013: IIS-Anforderungen (Internetinformationsdienste)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcb0350178a19a75ac821a452ef90e10da297677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831958"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="c448b-102">IIS-Anforderungen (Internetinformationsdienste) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c448b-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c448b-103">_**Letztes Änderungsdatum des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="c448b-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="c448b-104">Mehrere lync Server 2013-Komponenten erfordern Internet Informationsdienste (IIS).</span><span class="sxs-lookup"><span data-stu-id="c448b-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="c448b-105">In diesem Thema werden die speziellen IIS-Features beschrieben, die für die Unterstützung von lync Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c448b-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="c448b-106">In den Themen in diesem Abschnitt werden die Anforderungen bestimmter Komponenten für IIS beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c448b-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="c448b-107">Wenn die Rolle des Webservers (IIS) unter Windows Server 2008 aktiviert ist, werden standardmäßig verschiedene Rollendienste installiert.</span><span class="sxs-lookup"><span data-stu-id="c448b-107">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default.</span></span> <span data-ttu-id="c448b-108">In der folgenden Tabelle werden die zusätzlichen Rollendienste beschrieben, die installiert werden müssen, wenn die Webserver (IIS)-Rolle unter Windows Server 2008 aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c448b-108">The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c448b-109">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="c448b-109">Role service</span></span></th>
<th><span data-ttu-id="c448b-110">Feature</span><span class="sxs-lookup"><span data-stu-id="c448b-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c448b-111">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="c448b-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="c448b-112">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="c448b-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c448b-113">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="c448b-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c448b-114">ASP.net</span><span class="sxs-lookup"><span data-stu-id="c448b-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c448b-115">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="c448b-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c448b-116">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="c448b-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c448b-117">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="c448b-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c448b-118">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="c448b-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c448b-119">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="c448b-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="c448b-120">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="c448b-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c448b-121">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c448b-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c448b-122">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="c448b-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c448b-123">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="c448b-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="c448b-124">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="c448b-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c448b-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c448b-125">Security</span></span></p></td>
<td><p><span data-ttu-id="c448b-126">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="c448b-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c448b-127">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c448b-127">Security</span></span></p></td>
<td><p><span data-ttu-id="c448b-128">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c448b-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c448b-129">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="c448b-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c448b-130">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="c448b-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c448b-131">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="c448b-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="c448b-132">IIS 6-Verwaltungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="c448b-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="c448b-134">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="c448b-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c448b-135">Wenn Sie IIS 7,0 unter einem Windows Server 2008-Betriebssystem verwenden, deaktiviert das lync Server-Setup die Kernelmodus-Authentifizierung in IIS.</span><span class="sxs-lookup"><span data-stu-id="c448b-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c448b-136">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="c448b-136">In This Section</span></span>

  - [<span data-ttu-id="c448b-137">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c448b-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

