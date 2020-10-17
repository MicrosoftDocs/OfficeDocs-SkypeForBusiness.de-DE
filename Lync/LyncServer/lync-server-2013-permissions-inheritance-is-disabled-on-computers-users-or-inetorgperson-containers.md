---
title: 'Lync Server 2013: Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container deaktiviert'
description: 'Lync Server 2013: Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container deaktiviert.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a619ccd00e328ccef2e3b9eef4d64b190bdbdfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545161"
---
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="47f3e-103">Die Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container in lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="47f3e-103">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47f3e-104">_**Letztes Änderungsstand des Themas:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="47f3e-104">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="47f3e-105">In einer gesperrten Active Directory-Domänendienste werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierten Berechtigungen vererbt, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zum Erzwingen von Sicherheitsrichtlinien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-105">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="47f3e-106">Domänenvorbereitung und Serveraktivierung legen Sie die für lync Server 2013 erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) fest.</span><span class="sxs-lookup"><span data-stu-id="47f3e-106">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="47f3e-107">Wenn die Vererbung von Berechtigungen deaktiviert ist, können die lync Server Sicherheitsgruppen diese ACEs nicht erben.</span><span class="sxs-lookup"><span data-stu-id="47f3e-107">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="47f3e-108">Wenn diese Berechtigungen nicht vererbt werden, können lync Server Sicherheitsgruppen nicht auf Einstellungen zugreifen, und es treten die folgenden beiden Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="47f3e-108">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="47f3e-109">Um Benutzer, InetOrgPersons und Kontakte zu verwalten und Server zu betreiben, erfordern die lync Server Sicherheitsgruppen ACEs, die von der Domänen Vorbereitungs Prozedur auf den Eigenschaftensätzen der einzelnen Benutzer, RTC (Real-Time Communications), RTC-Benutzersuche und öffentlichen Informationen festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="47f3e-109">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="47f3e-110">Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von den Sicherheitsgruppen nicht geerbt, sodass diese keine Server oder Benutzer verwalten können.</span><span class="sxs-lookup"><span data-stu-id="47f3e-110">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="47f3e-111">Zum Ermitteln von Servern und Pools beruhen Server mit lync Server auf ACEs, die durch Aktivierung für computerbezogene Objekte festgelegt wurden, einschließlich des Microsoft-Containers und des Server Objekts.</span><span class="sxs-lookup"><span data-stu-id="47f3e-111">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="47f3e-112">Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von Sicherheitsgruppen, Servern und Pools nicht geerbt und können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47f3e-112">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="47f3e-113">Um diese Probleme zu beheben, stellt lync Server das **Grant-CsOuPermission-** Cmdlet bereit.</span><span class="sxs-lookup"><span data-stu-id="47f3e-113">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="47f3e-114">Dieses Cmdlet legt fest, dass lync Server ACEs direkt für einen angegebenen Container und für Organisationseinheiten und die Objekte innerhalb des Containers oder der Organisationseinheit erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="47f3e-114">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="47f3e-115">Festlegen von Berechtigungen für Benutzer-, InetOrgPerson- und Kontaktobjekte nach dem Ausführen der Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="47f3e-115">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="47f3e-116">In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Benutzer- oder InetOrgPerson-Objekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-116">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="47f3e-117">In dieser Situation müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit mit Benutzer- oder InetOrgPerson-Objekten ausführen, für die die Vererbung von Berechtigungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="47f3e-117">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="47f3e-118">Wenn eine Topologie mit einer zentralen Gesamtstruktur bereitgestellt wurde, müssen Sie dieses Verfahren auch für die Container oder Organisationseinheiten mit Kontaktobjekten ausführen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-118">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="47f3e-119">Ausführliche Informationen zu Topologien mit zentraler Gesamtstruktur finden Sie unter [Supported Active Directory Topologies in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="47f3e-119">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="47f3e-120">Der "ObjectType"-Parameter gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="47f3e-120">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="47f3e-121">Der OU-Parameter gibt die Organisationseinheit an.</span><span class="sxs-lookup"><span data-stu-id="47f3e-121">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="47f3e-122">Mit diesem Cmdlet werden den angegebenen Containern oder Organisationseinheiten und den Benutzer- bzw. InetOrgPerson-Objekten innerhalb des Containers die erforderlichen Zugriffssteuerungseinträge direkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-122">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="47f3e-123">Wenn die Organisationseinheit, für die dieser Befehl ausgeführt wird, über untergeordnete OUs mit User-oder inetOrgPerson-Objekten verfügt, werden die Berechtigungen nicht auf diese angewendet.</span><span class="sxs-lookup"><span data-stu-id="47f3e-123">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="47f3e-124">Sie müssen den Befehl für jede untergeordnete ou einzeln ausführen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-124">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="47f3e-125">Dies ist ein gängiges Szenario bei lync-Hosting-Bereitstellungen, beispielsweise übergeordnete OU = OCS-Mandanten, DC = contoso, DC = local und Child ou = Tenant1, ou = OCS-Mandanten, DC = contoso, DC = local.</span><span class="sxs-lookup"><span data-stu-id="47f3e-125">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="47f3e-126">Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren.</span><span class="sxs-lookup"><span data-stu-id="47f3e-126">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="47f3e-127">Wenn die authentifizierten Benutzer-ACEs ebenfalls in der gesperrten Umgebung entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container oder OUs in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen werden in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.</span><span class="sxs-lookup"><span data-stu-id="47f3e-127">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="47f3e-128">**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Benutzer-, InetOrgPerson- und Kontaktobjekte fest**</span><span class="sxs-lookup"><span data-stu-id="47f3e-128">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="47f3e-129">Melden Sie sich unter Verwendung eines Kontos, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt, bei einem Domänencomputer an.</span><span class="sxs-lookup"><span data-stu-id="47f3e-129">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="47f3e-130">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="47f3e-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="47f3e-131">Ausführen</span><span class="sxs-lookup"><span data-stu-id="47f3e-131">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="47f3e-132">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="47f3e-132">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="47f3e-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47f3e-133">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="47f3e-134">Suchen Sie in der Protokolldatei **\<Success\>** am Ende jeder Aufgabe nach dem Ausführungsergebnis, um sicherzustellen, dass die Berechtigungen festgelegt wurden, und schließen Sie dann das Protokollfenster.</span><span class="sxs-lookup"><span data-stu-id="47f3e-134">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="47f3e-135">Sie können auch den folgenden Befehl ausführen, um zu bestimmen, ob die Berechtigungen festgelegt wurden:</span><span class="sxs-lookup"><span data-stu-id="47f3e-135">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="47f3e-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47f3e-136">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="47f3e-137">Festlegen von Berechtigungen für Computerobjekte nach der Ausführung der Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="47f3e-137">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="47f3e-138">In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Computerobjekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-138">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="47f3e-139">In diesem Fall müssen Sie das **Grant-CsOuPermission-** Cmdlet für jeden Container oder jede OU ausführen, auf dem Computer ausgeführt werden, auf denen lync Server die Vererbung von Berechtigungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="47f3e-139">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="47f3e-140">Der ObjectType-Parameter gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="47f3e-140">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="47f3e-141">Bei diesem Verfahren werden die erforderlichen Zugriffssteuerungseinträge den angegebenen Containern direkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-141">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="47f3e-142">Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren.</span><span class="sxs-lookup"><span data-stu-id="47f3e-142">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="47f3e-143">Wenn die authentifizierten Benutzer-ACEs ebenfalls entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.</span><span class="sxs-lookup"><span data-stu-id="47f3e-143">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="47f3e-144">**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Computerobjekte fest**</span><span class="sxs-lookup"><span data-stu-id="47f3e-144">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="47f3e-145">Melden Sie sich beim Domänencomputer mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-145">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="47f3e-146">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="47f3e-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="47f3e-147">Ausführen</span><span class="sxs-lookup"><span data-stu-id="47f3e-147">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="47f3e-148">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="47f3e-148">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="47f3e-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47f3e-149">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="47f3e-150">In der Beispielprotokolldatei C: \\ Logs \\OUPermissions.xml würden Sie **\<Success\>** am Ende jeder Aufgabe nach dem Ausführungsergebnis suchen und sicherstellen, dass keine Fehler vorliegen, und dann das Protokoll schließen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-150">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="47f3e-151">Sie können das folgende Cmdlet ausführen, um Berechtigungen zu testen:</span><span class="sxs-lookup"><span data-stu-id="47f3e-151">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="47f3e-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47f3e-152">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="47f3e-153">Wenn Sie die Domänenvorbereitung in der Gesamtstruktur-Stammdomäne in einer gesperrten Active Directory Umgebung ausführen, müssen Sie beachten, dass lync Server Zugriff auf das Active Directory-Schema und die Konfigurationscontainer benötigt.</span><span class="sxs-lookup"><span data-stu-id="47f3e-153">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="47f3e-154">Wenn die standardmäßige Berechtigung "authentifizierter Benutzer" aus dem Schema oder den Konfigurationscontainern in AD DS entfernt wird &nbsp; , dürfen nur Mitglieder der Gruppe "Schema-Admins" (für den Schemacontainer) oder der Gruppe "Organisations-Admins" (für den Konfigurationscontainer) auf den angegebenen Container zugreifen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-154">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="47f3e-155">Da Setup.exe, lync Server-Verwaltungsshell-Cmdlets und lync Server-Systemsteuerung Zugriff auf diese Container erfordern, tritt beim Setup und bei der Installation der Verwaltungstools ein Fehler auf, es sei denn, der Benutzer, der die Installation ausführt, verfügt über Benutzerrechte, die den Schema-Admins und den Gruppenmitgliedschaften der Organisations-Admins entsprechen.</span><span class="sxs-lookup"><span data-stu-id="47f3e-155">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="47f3e-156">Um dieses Problem zu beheben, müssen Sie der Gruppe "RTCUniversalGlobalWriteGroup" Lese- und Schreibberechtigungen für die Schema- und Konfigurationscontainer gewähren.</span><span class="sxs-lookup"><span data-stu-id="47f3e-156">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

