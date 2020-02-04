---
title: 'Lync Server 2013: Erforderliche Gruppenmitgliedschaft'
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
ms.openlocfilehash: 44ad8c7f6eab93f3bdcd7b73d4ae05bd3b2e25ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-membership-requirements-for-lync-server-2013"></a><span data-ttu-id="6d599-102">Erforderliche Gruppenmitgliedschaft für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d599-102">Group membership requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d599-103">_**Letztes Änderungsdatum des Themas:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="6d599-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="6d599-104">In der folgenden Tabelle sind die Gruppen oder Gruppen zusammengefasst, zu denen eine Person gehören soll, um lync Server 2013 erfolgreich zu installieren, zu verwalten und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6d599-104">The following table summarizes the group or groups that a person should belong to in order to successfully install, manage, and troubleshoot Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d599-105">Lync Server 2013, ausführbare Datei</span><span class="sxs-lookup"><span data-stu-id="6d599-105">Lync Server 2013 Executable</span></span></th>
<th><span data-ttu-id="6d599-106">Gruppenmitgliedschaft erforderlich</span><span class="sxs-lookup"><span data-stu-id="6d599-106">Group Membership Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d599-107"><strong>Setup. exe</strong> – ausführbare Datei, mit der die Installation der lync Server 2013-Verwaltungstools gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="6d599-107"><strong>Setup.exe</strong> – Executable that starts the installation of the Lync Server 2013 administrative tools.</span></span></p></td>
<td><p><span data-ttu-id="6d599-108">Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d599-108">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6d599-109">Mitglied der Gruppe "Domänenbenutzer", um Informationen in den Active Directory-Domänendiensten zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6d599-109">Member of Domain Users group to read information in Active Directory Domain Services.</span></span> <span data-ttu-id="6d599-110">Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="6d599-110">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p>
<div>

> [!TIP]  
> <span data-ttu-id="6d599-111">Sie können auch Setup Berechtigungen an Benutzer oder Gruppen delegieren, denen Sie nicht die Mitgliedschaft in der Gruppe Domänenadministratoren gewähren möchten.</span><span class="sxs-lookup"><span data-stu-id="6d599-111">You can also delegate setup permissions to users or groups to whom you do not want to grant membership in the Domain Admins group.</span></span> <span data-ttu-id="6d599-112">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d599-112">For details, see <A href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</A> in the Deployment documentation.</span></span>


</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d599-113"><strong>Deploy</strong> . exe – von Setup. exe aufgerufen, ist "Deploy. exe" für die Bereitstellung der Softwarekomponenten für die Serverrollen verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="6d599-113"><strong>Deploy.exe</strong> – Called by setup.exe, deploy.exe is responsible for the deployment of the software components for the server roles.</span></span></p></td>
<td><p><span data-ttu-id="6d599-114">Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d599-114">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6d599-115">Mitglied der Gruppe "Domänenbenutzer", um Informationen in AD DS zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6d599-115">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="6d599-116">Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="6d599-116">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span> <span data-ttu-id="6d599-117">Die Mitgliedschaft in der RtcUniversalReadOnlyAdmins-Gruppe ist erforderlich, um den zentralen Verwaltungsspeicher lesen zu können.</span><span class="sxs-lookup"><span data-stu-id="6d599-117">Membership in RtcUniversalReadOnlyAdmins group is necessary to read the Central Management store.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="6d599-118">Wenn Sie das BetriebssystemWindows Vista oder Windows 7 ausführen, werden Sie von der Benutzerkontensteuerung (User Account Control, UAC) aufgefordert, die Installation fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6d599-118">If you are running the Windows Vista operating system or Windows 7 operating system, you will be prompted by User Account Control (UAC) to proceed with installation.</span></span> <span data-ttu-id="6d599-119">Wenn Sie mit einem Standardbenutzerkonto angemeldet sind, benötigen Sie eine Person, die ein Mitglied der lokalen Gruppe Administratoren ist, um Anmeldeinformationen einzugeben, wenn Sie aufgefordert werden, ein Konto mit den Berechtigungen zum Installieren der Software einzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d599-119">If you are logged on with a standard user account, you will need someone who is a member of the Local Administrators group to provide credentials when prompted for an account with permissions to install the software.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d599-120"><strong>Bootstrapper. exe</strong> – von Setup. exe aufgerufen, ist Bootstrapper. exe verantwortlich für die Bereitstellung und Konfiguration von Serverrollen.</span><span class="sxs-lookup"><span data-stu-id="6d599-120"><strong>Bootstrapper.exe</strong> – Called by setup.exe, bootstrapper.exe is responsible for deployment and configuration of server roles.</span></span></p></td>
<td><p><span data-ttu-id="6d599-121">Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d599-121">Member of the Local Administrators group on the computer from which the executable is run.</span></span> <span data-ttu-id="6d599-122">Mitglied der RTCUniversalServerAdmins-Gruppe, um Bootstrapper. exe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6d599-122">Member of the RTCUniversalServerAdmins group to run Bootstrapper.exe.</span></span> <span data-ttu-id="6d599-123">Mitglied der Gruppe "Domänenbenutzer", um Informationen in AD DS zu lesen.</span><span class="sxs-lookup"><span data-stu-id="6d599-123">Member of Domain Users group to read information in AD DS.</span></span> <span data-ttu-id="6d599-124">Diese Berechtigungsstufe ist erforderlich, da für die automatische Installation erforderlicher MSI-Pakete auf dem lokalen Computer Berechtigungen erforderlich sind, die das Lesen und Schreiben von geschützten lokalen Computerressourcen wie Programmdatei Verzeichnissen und geschützten Registrierung wie die Hive des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="6d599-124">This level of permission is required because the automatic installation of required MSI packages on the local computer requires privileges that allow reading from and writing to protected local computer resources such as Program Files directories, and protected registry such as the Local Machine hive.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d599-125"><strong>TopologyBuilder</strong> – Assistenten gesteuerte Benutzeroberfläche zum Erstellen, anzeigen, anpassen und Validieren von lync Server 2013-Topologien.</span><span class="sxs-lookup"><span data-stu-id="6d599-125"><strong>TopologyBuilder</strong> – Wizard-driven user interface to create, view, adjust, and validate Lync Server 2013 topologies.</span></span></p></td>
<td><p><span data-ttu-id="6d599-126">Mitglied der lokalen Gruppe Administratoren auf dem Computer, auf dem die ausführbare Datei ausgeführt wird, um die Topologie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d599-126">Member of the Local Administrators group on the computer from which the executable is run to view the topology.</span></span> <span data-ttu-id="6d599-127">Mitglied der RTCUniversalServerAdmins-Gruppe, um die Konfigurationseinstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6d599-127">Member of the RTCUniversalServerAdmins group to change configuration settings.</span></span> <span data-ttu-id="6d599-128">Mitglied der Gruppe "RTCUniversalServerAdmins", Gruppe "Domänen-Admins" oder Mitglied der RTCUniversalServerAdmins-Gruppe (nur, wenn der Gruppe Berechtigungen für die Stellvertretung erteilt wurden), um die Topologie zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="6d599-128">Member of the RTCUniversalServerAdmins group and Domain Admins group, or member of the RTCUniversalServerAdmins group (only if the group has been granted delegate setup permissions), to publish the topology.</span></span> <span data-ttu-id="6d599-129">Details zum Delegieren von Setup Berechtigungen, damit Mitglieder der RTCUniversalServerAdmins-Gruppe die Topologie veröffentlichen können, ohne Mitglieder der Gruppe "Domänen-Admins" zu sein, finden Sie unter <a href="lync-server-2013-granting-setup-permissions.md">Gewähren von Setup Berechtigungen in lync Server 2013</a> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d599-129">For details about delegating setup permissions to allow members of the RTCUniversalServerAdmins group to publish the topology without being members of the Domain Admins group, see <a href="lync-server-2013-granting-setup-permissions.md">Granting setup permissions in Lync Server 2013</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d599-130"><strong>AdminUIHost</strong> – webbasierte grafische Benutzeroberfläche für die Verwaltung von lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6d599-130"><strong>AdminUIHost</strong> – Web-based graphical user interface for managing Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="6d599-131">Mitglied der CsAdministrator-Gruppe oder Mitglied einer anderen rollenbasierten zugriffssteuerungsrolle (Role-Based Access Control, RBAC), der die bestimmte administrative Aufgabe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="6d599-131">Member of CsAdministrator group or member of another role-based access control (RBAC) role to which the specific administrative task is assigned.</span></span> <span data-ttu-id="6d599-132">Die lync Server 2013-Systemsteuerung implementiert Konfigurationsänderungen, indem Sie die lync Server 2013-Verwaltungsshell-Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d599-132">Lync Server 2013 Control Panel implements configuration changes by running Lync Server 2013 Management Shell cmdlets.</span></span> <span data-ttu-id="6d599-133">Eine Liste der vordefinierten Rollen und die Cmdlets, die Mitglieder ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d599-133">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d599-134"><strong>PowerShell. exe mit dem lync Server 2013-Modul geladen</strong> – Befehlszeilen-Verwaltungstool mit Cmdlets, die für die Verwaltung von lync Server 2013 spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="6d599-134"><strong>PowerShell.exe with the Lync Server 2013 module loaded</strong> – Command-line administrative tool with cmdlets specific to management of Lync Server 2013.</span></span></p></td>
<td><p><span data-ttu-id="6d599-135">Mitglied der CsAdministrator-Gruppe oder Mitglied einer anderen RBAC-Rolle, der das jeweilige Cmdlet zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="6d599-135">Member of CsAdministrator group or member of another RBAC role to which the specific cmdlet has been assigned.</span></span> <span data-ttu-id="6d599-136">Eine Liste der vordefinierten Rollen und die Cmdlets, die Mitglieder ausführen dürfen, finden Sie unter <a href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</a> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6d599-136">For a list of predefined roles and the cmdlets members are permitted to run, see <a href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="6d599-137">Oder, abhängig vom Cmdlet, Mitglied einer oder mehrerer der folgenden Gruppen:</span><span class="sxs-lookup"><span data-stu-id="6d599-137">Or, member of one or more of the following groups, depending on the cmdlet:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d599-138">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="6d599-138">RTCUniversalServerAdmins</span></span></p></li>
<li><p><span data-ttu-id="6d599-139">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="6d599-139">RTCUniversalUserAdmins</span></span></p></li>
<li><p><span data-ttu-id="6d599-140">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="6d599-140">RTCUniversalReadOnlyAdmins</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

