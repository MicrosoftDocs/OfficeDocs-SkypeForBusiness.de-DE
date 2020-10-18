---
title: 'Lync Server 2013: Bereitstellungsberechtigungen für SQL Server'
description: 'Lync Server 2013: Bereitstellungsberechtigungen für SQL Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment permissions for SQL Server
ms:assetid: 56ea0c02-bcf5-4d45-aa13-570531c29074
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398375(v=OCS.15)
ms:contentKeyID: 48184197
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be5985bc8f3173b03d8969d3dd58cfbf8daf85f8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575721"
---
# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="23a05-103">Bereitstellungsberechtigungen für SQL Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23a05-103">Deployment permissions for SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23a05-104">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="23a05-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="23a05-105">Microsoft SQL Server 2012 hat bestimmte Anforderungen beim Installieren und Bereitstellen von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="23a05-105">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="23a05-106">Da Windows und SQL Server Ihre Sicherheit anders definieren, gewährt die Anmeldung als Administrator in der Active Directory Domäne nicht implizit Berechtigungen für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="23a05-106">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="23a05-107">Sie müssen zudem ein Mitglied der sysadmin-Entität auf dem SQL Server-basierten Server sein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="23a05-107">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="23a05-108">Erforderliche Berechtigungen für die Installation von Datenbank und Lync Server</span><span class="sxs-lookup"><span data-stu-id="23a05-108">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="23a05-109">Die folgenden Optionen beschreiben drei Berechtigungen und Gruppen Mitgliedschafts Zuordnungen für die Installation von lync Server 2013 Dateien und SQL Server Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="23a05-109">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="23a05-110">Wählen Sie das Szenario, das den Anforderungen Ihrer Organisation am ehesten entspricht.</span><span class="sxs-lookup"><span data-stu-id="23a05-110">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="23a05-111">Berechtigungen und Gruppenmitgliedschaftszuordnungen</span><span class="sxs-lookup"><span data-stu-id="23a05-111">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23a05-112">SQL Server oder lync Server 2013 Rolle</span><span class="sxs-lookup"><span data-stu-id="23a05-112">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="23a05-113">Für die Rolle typische SQL Server-Berechtigungen und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="23a05-113">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="23a05-114">Rollen typische lync Server 2013 Berechtigungen und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="23a05-114">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="23a05-115">Resultierende Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="23a05-115">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23a05-116">Lync Server 2013 Administrator</span><span class="sxs-lookup"><span data-stu-id="23a05-116">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="23a05-117">Mitgliedschaft in der SQL Server-Sicherheitsgruppe "sysadmins" und lokalen Administratorgruppe in SQL Server erforderlich</span><span class="sxs-lookup"><span data-stu-id="23a05-117">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="23a05-118">Mitgliedschaft in der Gruppe "RTCUniversalServerAdmins" erforderlich</span><span class="sxs-lookup"><span data-stu-id="23a05-118">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="23a05-119">Lync Server 2013 Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="23a05-119">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23a05-120">SQL Server-Administrator</span><span class="sxs-lookup"><span data-stu-id="23a05-120">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="23a05-121">Mitgliedschaft in der SQL Server-Gruppe "sysadmin" (oder äquivalente Berechtigungen) und Mitgliedschaft in der lokalen Administratorgruppe von SQL Server erforderlich</span><span class="sxs-lookup"><span data-stu-id="23a05-121">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="23a05-122">Mitgliedschaft in der Gruppe "RTCUniversalServerReadOnly" erforderlich</span><span class="sxs-lookup"><span data-stu-id="23a05-122">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="23a05-123">SQL Server Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="23a05-123">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23a05-124">Beide Administratoren sind für Installationsaufgaben verantwortlich</span><span class="sxs-lookup"><span data-stu-id="23a05-124">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="23a05-125">Der SQL Server-Administrator ist Mitglied der Gruppe "sysadmin" (oder verfügt über äquivalente Berechtigungen) und Mitglied der lokalen Administratorgruppe von SQL Server</span><span class="sxs-lookup"><span data-stu-id="23a05-125">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="23a05-126">Lync Server 2013 Administrator ist Mitglied von RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="23a05-126">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="23a05-127">Der lync Server 2013 Administrator kann lync Server 2013 installieren, aber die Datenbanken nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="23a05-127">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="23a05-128">Der SQL Server Administrator verwendet die vom lync Server 2013-Administrator bereitgestellten lync Server-Verwaltungsshell-und Windows PowerShell-Cmdlets zum Installieren der Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="23a05-128">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="23a05-129">Die lync Server 2013 Verwaltungsshell, die vom SQL Server-Administrator verwendet wird, wird auf der Front-End-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="23a05-129">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="23a05-130">Dadurch entfällt die Notwendigkeit, die lync Server 2013 Verwaltungstools auf dem SQL Server basierten Server zu installieren.</span><span class="sxs-lookup"><span data-stu-id="23a05-130">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

