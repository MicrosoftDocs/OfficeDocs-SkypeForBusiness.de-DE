---
title: 'Lync Server 2013: Bereitstellungsberechtigungen für SQL Server'
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
ms.openlocfilehash: 393e293dfc7e20fa1e990d9f87c17c6e72776be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-permissions-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="9c29b-102">Bereitstellungsberechtigungen für SQL Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c29b-102">Deployment permissions for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c29b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9c29b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9c29b-104">Microsoft SQL Server 2012 hat bestimmte Anforderungen beim Installieren und Bereitstellen von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c29b-104">Microsoft SQL Server 2012 has specific requirements when installing and deploying Lync Server 2013.</span></span> <span data-ttu-id="9c29b-105">Da Windows und SQL Server Ihre Sicherheit anders definieren, gewährt die Anmeldung als Administrator in der Active Directory-Domäne implizit keine Berechtigungen für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9c29b-105">Because Windows and SQL Server define their security differently, logging in as an administrator in the Active Directory domain does not implicitly grant permissions for SQL Server.</span></span> <span data-ttu-id="9c29b-106">Sie müssen auch ein Mitglied der sysadmin-Entität auf dem SQL Server-basierten Server sein, den Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9c29b-106">You must also be a member of the sysadmin entity on the SQL Server-based server you are configuring.</span></span>

<div>

## <a name="permissions-required-for-database-and-lync-server-installation"></a><span data-ttu-id="9c29b-107">Für die Installation von Datenbank und lync Server erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9c29b-107">Permissions Required for Database and Lync Server Installation</span></span>

<span data-ttu-id="9c29b-108">Die folgenden Optionen erläutern drei Berechtigungen und Gruppen Mitgliedschafts Zuordnungen für die Installation von lync Server 2013-Dateien und SQL Server-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="9c29b-108">The following options detail three permissions and group membership associations for installation of Lync Server 2013 files and SQL Server databases.</span></span> <span data-ttu-id="9c29b-109">Wählen Sie das Szenario aus, das den Anforderungen Ihrer Organisation am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="9c29b-109">Choose the scenario that best meets the requirements of your organization.</span></span>

### <a name="permissions-and-group-membership-associations"></a><span data-ttu-id="9c29b-110">Berechtigungen und Gruppen Mitgliedschafts Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="9c29b-110">Permissions and Group Membership Associations</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9c29b-111">SQL Server-oder lync Server 2013-Rolle</span><span class="sxs-lookup"><span data-stu-id="9c29b-111">SQL Server or Lync Server 2013 role</span></span></th>
<th><span data-ttu-id="9c29b-112">Rollen typische SQL Server-Berechtigungen und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="9c29b-112">Role-Typical SQL Server permissions and group membership</span></span></th>
<th><span data-ttu-id="9c29b-113">Rollen typische lync Server 2013-Berechtigungen und Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="9c29b-113">Role-typical Lync Server 2013 permissions and group membership</span></span></th>
<th><span data-ttu-id="9c29b-114">Berechtigungs Ergebnis</span><span class="sxs-lookup"><span data-stu-id="9c29b-114">Permissions outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9c29b-115">Lync Server 2013-Administrator</span><span class="sxs-lookup"><span data-stu-id="9c29b-115">Lync Server 2013 administrator</span></span></p></td>
<td><p><span data-ttu-id="9c29b-116">Es muss eine Mitgliedschaft in der SQL Server-Sicherheitsgruppe SysAdmins und Mitglied der Gruppe der lokalen Administratoren von SQL Server gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="9c29b-116">Must be granted membership of sysadmins SQL Server security group and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="9c29b-117">Muss ein Mitglied der RTCUniversalServerAdmins-Gruppe sein</span><span class="sxs-lookup"><span data-stu-id="9c29b-117">Must be a member of the RTCUniversalServerAdmins group</span></span></p></td>
<td><p><span data-ttu-id="9c29b-118">Der lync Server 2013-Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="9c29b-118">Lync Server 2013 administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9c29b-119">SQL Server-Administrator</span><span class="sxs-lookup"><span data-stu-id="9c29b-119">SQL Server administrator</span></span></p></td>
<td><p><span data-ttu-id="9c29b-120">SQL Server sysadmin-Gruppenmitglied (oder Äquivalent) und Mitglied der Gruppe der lokalen SQL Server-Administratoren</span><span class="sxs-lookup"><span data-stu-id="9c29b-120">SQL Server sysadmin group member (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="9c29b-121">Muss ein Mitglied der RTCUniversalServerReadOnly-Gruppe sein</span><span class="sxs-lookup"><span data-stu-id="9c29b-121">Must be a member of the RTCUniversalServerReadOnly group</span></span></p></td>
<td><p><span data-ttu-id="9c29b-122">Der SQL Server-Administrator verfügt über die erforderlichen Berechtigungen zum Installieren von lync Server 2013-und SQL Server-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="9c29b-122">SQL Server administrator has the proper permissions to install both Lync Server 2013 and SQL Server databases.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9c29b-123">Beide Administratoren Teilen Installationsaufgaben</span><span class="sxs-lookup"><span data-stu-id="9c29b-123">Both administrators sharing installation duties</span></span></p></td>
<td><p><span data-ttu-id="9c29b-124">Der SQL Server-Administrator ist Mitglied der Gruppe Sysadmins (oder Äquivalent) und Mitglied der Gruppe der lokalen Administratoren von SQL Server.</span><span class="sxs-lookup"><span data-stu-id="9c29b-124">SQL Server administrator is member of sysadmins group (or equivalent) and member of the SQL Server local Administrators group</span></span></p></td>
<td><p><span data-ttu-id="9c29b-125">Lync Server 2013-Administrator ist Mitglied von RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9c29b-125">Lync Server 2013 administrator is member of RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="9c29b-126">Der lync Server 2013-Administrator kann lync Server 2013 installieren, die Datenbankenkönnen aber nicht installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9c29b-126">The Lync Server 2013 administrator can install Lync Server 2013, but cannot install the databases.</span></span> <span data-ttu-id="9c29b-127">Der SQL Server-Administrator verwendet die lync Server-Verwaltungsshell und die Windows PowerShell-Cmdlets, die vom lync Server 2013-Administrator bereitgestellt werden, um die Datenbanken zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9c29b-127">The SQL Server administrator uses the Lync Server Management Shell and Windows PowerShell cmdlets provided by the Lync Server 2013 administrator to install the databases.</span></span> <span data-ttu-id="9c29b-128">Die vom SQL Server-Administrator verwendete lync Server 2013-Verwaltungsshell ist auf dem Front-End-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="9c29b-128">The Lync Server 2013 Management Shell used by the SQL Server administrator is installed on the Front End Server.</span></span> <span data-ttu-id="9c29b-129">Dadurch entfällt die Notwendigkeit, die lync Server 2013-Verwaltungstools auf dem SQL Server-basierten Server zu installieren.</span><span class="sxs-lookup"><span data-stu-id="9c29b-129">This eliminates the need to install the Lync Server 2013 administrative tools on the SQL Server-based server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

