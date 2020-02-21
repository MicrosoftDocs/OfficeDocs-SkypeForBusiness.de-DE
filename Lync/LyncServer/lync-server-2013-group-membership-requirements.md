---
title: 'Lync Server 2013: Anforderungen an die Gruppenmitgliedschaft'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group membership requirements
ms:assetid: 01876843-8717-4e72-baf5-866ac8cceee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204623(v=OCS.15)
ms:contentKeyID: 48183239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8726d471b1db95aa67cca58a77452d9faa43df4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="0d99f-102">Anforderungen an die Gruppenmitgliedschaft für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d99f-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d99f-103">_**Letztes Änderungsstand des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0d99f-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0d99f-104">In der folgenden Tabelle sind die Gruppen oder Gruppen zusammengefasst, denen eine Person angehören sollte, um lync Server 2013 erfolgreich zu installieren, zu verwalten und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="0d99f-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d99f-105">Lync Server 2013 ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="0d99f-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="0d99f-106">Gruppenmitgliedschaft erforderlich</span><span class="sxs-lookup"><span data-stu-id="0d99f-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d99f-107"><strong>Setup. exe</strong> – ausführbare Datei, mit der die Installation des lync Server 2013 Verwaltungstools gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0d99f-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-108">Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d99f-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="0d99f-109">Mitglied der Gruppe "Domänenbenutzer" zum Lesen von Informationen in Active Directory-Domänendienste.</span><span class="sxs-lookup"><span data-stu-id="0d99f-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="0d99f-110">Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0d99f-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="0d99f-111">Es ist möglich, Installationsberechtigungen an Benutzer oder Gruppen zu delegieren, die Sie nicht in die Gruppe "Domänen-Admins" aufnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="0d99f-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="0d99f-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d99f-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d99f-113"><strong>Deploy.exe</strong> – Wird von "setup.exe" aufgerufen und zur Bereitstellung der Softwarekomponenten für die Serverrollen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d99f-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-114">Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d99f-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="0d99f-115">Mitglied der Gruppe "Domänen-Benutzer" zum Lesen von Informationen in AD DS.</span><span class="sxs-lookup"><span data-stu-id="0d99f-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="0d99f-116">Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0d99f-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="0d99f-117">Zum Lesen des zentralen Verwaltungsspeichers ist die Mitgliedschaft in der RtcUniversalReadOnlyAdmins-Gruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0d99f-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="0d99f-118">Wenn Sie das Betriebssystem Windows Vista oder Windows 7 Betriebssystem ausführen, werden Sie von der Benutzerkontensteuerung (User Account Control, UAC) aufgefordert, die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="0d99f-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="0d99f-119">Wenn Sie über ein Standardbenutzerkonto angemeldet sind, muss ein Mitglied der lokalen Administratorgruppe die erforderlichen Anmeldeinformationen eingeben, wenn Sie zur Angabe eines Kontos mit Berechtigungen zum Installieren der Software aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0d99f-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d99f-120"><strong>Bootstrapper.exe</strong> – Wird von "setup.exe" aufgerufen und zur Bereitstellung und Konfiguration von Serverrollen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="0d99f-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-p105">Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei ausgeführt wird. Mitglied der Gruppe "RTCUniversalServerAdmins" zum Ausführen der Datei "Bootstrapper.exe". Mitglied der Gruppe "Domänen-Benutzer" zum Lesen von Informationen in AD DS. Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation der erforderlichen MSI-Pakete auf dem lokalen Computer Lese- und Schreibberechtigungen für geschützte Ressourcen des lokalen Computers – z. B. Verzeichnisse unter "Programme" oder geschützte Registrierungseinträge wie der Schlüssel "Local Machine" – benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="0d99f-p105">Member of the Local Administrators group on the computer from which the executable is run. Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe. Member of Domain Users group to read information in AD DS. This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d99f-125"><strong>TopologyBuilder</strong> – Assistenten gesteuerte Benutzeroberfläche zum Erstellen, anzeigen, anpassen und Validieren von lync Server 2013 Topologien.</span><span class="sxs-lookup"><span data-stu-id="0d99f-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-126">Mitglied der lokalen Administratorgruppe auf dem Computer, auf dem die ausführbare Datei zum Anzeigen der Topologie ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0d99f-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="0d99f-127">Mitglied der Gruppe "RTCUniversalServerAdmins" mit Berechtigung zum Ändern der Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="0d99f-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="0d99f-128">Mitglied der Gruppen "RTCUniversalServerAdmins" und "Domänen-Admins" oder Mitglied der Gruppe "RTCUniversalServerAdmins" (nur falls der Gruppe die Berechtigung zum Delegieren der Installationsberechtigungen erteilt wurde), um die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="0d99f-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="0d99f-129">Ausführliche Informationen zum Delegieren von Setup Berechtigungen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Veröffentlichen der Topologie zu ermöglichen, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein, finden Sie unter <a href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d99f-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d99f-130"><strong>AdminUIHost</strong> – webbasierte grafische Benutzeroberfläche für die Verwaltung von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d99f-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-131">Mitglied der Gruppe "CsAdministrator" oder einer anderen rollenbasierten Zugriffssteuerungsrolle (Role-Based Access Control, RBAC), der eine bestimmte Verwaltungsaufgabe zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0d99f-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="0d99f-132">In lync Server 2013 Systemsteuerung werden Konfigurationsänderungen durch Ausführen der Cmdlets der lync Server 2013 Verwaltungsshell implementiert.</span><span class="sxs-lookup"><span data-stu-id="0d99f-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="0d99f-133">Eine Liste mit vordefinierten Rollen und die Cmdlets, die von Mitgliedern ausgeführt werden dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d99f-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d99f-134"><strong>PowerShell. exe mit dem lync Server 2013 Modul Loaded</strong> – Befehlszeilen-Verwaltungstool mit Cmdlets für die Verwaltung von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d99f-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="0d99f-135">Mitglied der Gruppe "CsAdministrator" oder einer anderen rollenbasierten Zugriffssteuerungsrolle, der ein bestimmtes Cmdlet zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="0d99f-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="0d99f-136">Eine Liste mit vordefinierten Rollen und die Cmdlets, die von Mitgliedern ausgeführt werden dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0d99f-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="0d99f-137">Oder, abhängig vom Cmdlet, Mitglied einer oder mehrerer der folgenden Gruppen:</span><span class="sxs-lookup"><span data-stu-id="0d99f-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="0d99f-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0d99f-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="0d99f-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="0d99f-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="0d99f-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="0d99f-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

