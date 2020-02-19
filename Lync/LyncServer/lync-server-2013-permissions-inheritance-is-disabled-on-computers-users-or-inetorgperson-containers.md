---
title: 'Lync Server 2013: Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container deaktiviert'
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
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="4788f-102">Die Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container in lync Server 2013 deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4788f-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4788f-103">_**Letztes Änderungsstand des Themas:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="4788f-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="4788f-104">In einer gesperrten Active Directory-Domänendienste werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierten Berechtigungen vererbt, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zu ermöglichen. zum Erzwingen von Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="4788f-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="4788f-105">Domänenvorbereitung und Serveraktivierung legen Sie die für lync Server 2013 erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) fest.</span><span class="sxs-lookup"><span data-stu-id="4788f-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="4788f-106">Wenn die Vererbung von Berechtigungen deaktiviert ist, können die lync Server Sicherheitsgruppen diese ACEs nicht erben.</span><span class="sxs-lookup"><span data-stu-id="4788f-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="4788f-107">Wenn diese Berechtigungen nicht vererbt werden, können lync Server Sicherheitsgruppen nicht auf Einstellungen zugreifen, und es treten die folgenden beiden Probleme auf:</span><span class="sxs-lookup"><span data-stu-id="4788f-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="4788f-108">Um Benutzer, InetOrgPersons und Kontakte zu verwalten und Server zu betreiben, erfordern die lync Server Sicherheitsgruppen ACEs, die von der Domänen Vorbereitungs Prozedur für die Eigenschaftensätze der einzelnen Benutzer, Echtzeitkommunikation (RTC), RTC-Benutzersuche und öffentliche Informationen festgelegt sind. .</span><span class="sxs-lookup"><span data-stu-id="4788f-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="4788f-109">Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von den Sicherheitsgruppen nicht geerbt, sodass diese keine Server oder Benutzer verwalten können.</span><span class="sxs-lookup"><span data-stu-id="4788f-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="4788f-110">Zum Ermitteln von Servern und Pools beruhen Server mit lync Server auf ACEs, die durch Aktivierung für computerbezogene Objekte festgelegt wurden, einschließlich des Microsoft-Containers und des Server Objekts.</span><span class="sxs-lookup"><span data-stu-id="4788f-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="4788f-111">Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von Sicherheitsgruppen, Servern und Pools nicht geerbt und können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4788f-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="4788f-112">Um diese Probleme zu beheben, stellt lync Server das **Grant-CsOuPermission-** Cmdlet bereit.</span><span class="sxs-lookup"><span data-stu-id="4788f-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="4788f-113">Dieses Cmdlet legt fest, dass lync Server ACEs direkt für einen angegebenen Container und für Organisationseinheiten und die Objekte innerhalb des Containers oder der Organisationseinheit erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4788f-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="4788f-114">Festlegen von Berechtigungen für Benutzer-, InetOrgPerson- und Kontaktobjekte nach dem Ausführen der Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="4788f-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="4788f-115">In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Benutzer- oder InetOrgPerson-Objekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4788f-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="4788f-116">In dieser Situation müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit mit Benutzer- oder InetOrgPerson-Objekten ausführen, für die die Vererbung von Berechtigungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4788f-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="4788f-117">Wenn eine Topologie mit einer zentralen Gesamtstruktur bereitgestellt wurde, müssen Sie dieses Verfahren auch für die Container oder Organisationseinheiten mit Kontaktobjekten ausführen.</span><span class="sxs-lookup"><span data-stu-id="4788f-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="4788f-118">Ausführliche Informationen zu Topologien mit zentraler Gesamtstruktur finden Sie unter [Supported Active Directory Topologies in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4788f-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="4788f-119">Der "ObjectType"-Parameter gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="4788f-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="4788f-120">Der OU-Parameter gibt die Organisationseinheit an.</span><span class="sxs-lookup"><span data-stu-id="4788f-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="4788f-121">Mit diesem Cmdlet werden den angegebenen Containern oder Organisationseinheiten und den Benutzer- bzw. InetOrgPerson-Objekten innerhalb des Containers die erforderlichen Zugriffssteuerungseinträge direkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4788f-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="4788f-122">Wenn die Organisationseinheit, für die dieser Befehl ausgeführt wird, über untergeordnete OUs mit User-oder inetOrgPerson-Objekten verfügt, werden die Berechtigungen nicht auf diese angewendet.</span><span class="sxs-lookup"><span data-stu-id="4788f-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="4788f-123">Sie müssen den Befehl für jede untergeordnete ou einzeln ausführen.</span><span class="sxs-lookup"><span data-stu-id="4788f-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="4788f-124">Dies ist ein gängiges Szenario bei lync-Hosting-Bereitstellungen, beispielsweise übergeordnete OU = OCS-Mandanten, DC = contoso, DC = local und Child ou = Tenant1, ou = OCS-Mandanten, DC = contoso, DC = local.</span><span class="sxs-lookup"><span data-stu-id="4788f-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="4788f-125">Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren.</span><span class="sxs-lookup"><span data-stu-id="4788f-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="4788f-126">Wenn die authentifizierten Benutzer-ACEs ebenfalls in der gesperrten Umgebung entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container oder OUs in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen werden in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.</span><span class="sxs-lookup"><span data-stu-id="4788f-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="4788f-127">**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Benutzer-, InetOrgPerson- und Kontaktobjekte fest**</span><span class="sxs-lookup"><span data-stu-id="4788f-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="4788f-128">Melden Sie sich unter Verwendung eines Kontos, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt, bei einem Domänencomputer an.</span><span class="sxs-lookup"><span data-stu-id="4788f-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="4788f-129">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4788f-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4788f-130">Ausführen</span><span class="sxs-lookup"><span data-stu-id="4788f-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4788f-131">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="4788f-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="4788f-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4788f-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="4788f-133">Suchen Sie in der Protokolldatei nach \*\* \<dem\> \*\* Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um sicherzustellen, dass die Berechtigungen festgelegt wurden, und schließen Sie dann das Protokollfenster.</span><span class="sxs-lookup"><span data-stu-id="4788f-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="4788f-134">Sie können auch den folgenden Befehl ausführen, um zu bestimmen, ob die Berechtigungen festgelegt wurden:</span><span class="sxs-lookup"><span data-stu-id="4788f-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="4788f-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4788f-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="4788f-136">Festlegen von Berechtigungen für Computerobjekte nach der Ausführung der Domänenvorbereitung</span><span class="sxs-lookup"><span data-stu-id="4788f-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="4788f-137">In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Computerobjekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4788f-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="4788f-138">In diesem Fall müssen Sie das **Grant-CsOuPermission-** Cmdlet für jeden Container oder jede OU ausführen, auf dem Computer ausgeführt werden, auf denen lync Server die Vererbung von Berechtigungen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="4788f-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="4788f-139">Der ObjectType-Parameter gibt den Objekttyp an.</span><span class="sxs-lookup"><span data-stu-id="4788f-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="4788f-140">Bei diesem Verfahren werden die erforderlichen Zugriffssteuerungseinträge den angegebenen Containern direkt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4788f-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="4788f-141">Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren.</span><span class="sxs-lookup"><span data-stu-id="4788f-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="4788f-142">Wenn die authentifizierten Benutzer-ACEs ebenfalls entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.</span><span class="sxs-lookup"><span data-stu-id="4788f-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="4788f-143">**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Computerobjekte fest**</span><span class="sxs-lookup"><span data-stu-id="4788f-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="4788f-144">Melden Sie sich beim Domänencomputer mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="4788f-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="4788f-145">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="4788f-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4788f-146">Ausführen</span><span class="sxs-lookup"><span data-stu-id="4788f-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="4788f-147">Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.</span><span class="sxs-lookup"><span data-stu-id="4788f-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="4788f-148">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4788f-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="4788f-149">In der Beispielprotokolldatei C:\\Logs\\OUPermissions. XML würden Sie nach \*\* \<\> \*\* dem Ergebnis der Erfolgs Ausführung am Ende jeder Aufgabe suchen und sicherstellen, dass keine Fehler vorliegen, und dann das Protokoll schließen.</span><span class="sxs-lookup"><span data-stu-id="4788f-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="4788f-150">Sie können das folgende Cmdlet ausführen, um Berechtigungen zu testen:</span><span class="sxs-lookup"><span data-stu-id="4788f-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4788f-151">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4788f-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4788f-152">Wenn Sie die Domänenvorbereitung in der Gesamtstruktur-Stammdomäne in einer gesperrten Active Directory Umgebung ausführen, müssen Sie beachten, dass lync Server Zugriff auf das Active Directory-Schema und die Konfigurationscontainer benötigt.</span><span class="sxs-lookup"><span data-stu-id="4788f-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="4788f-153">Wenn die standardmäßige Berechtigung "authentifizierter Benutzer" aus dem Schema oder den Konfigurations&nbsp;Containern in AD DS entfernt wird, dürfen nur Mitglieder der Gruppe "Schema-Admins" (für den Schemacontainer) oder der Gruppe "Organisations-Admins" (für den Konfigurationscontainer) auf den angegebenen Container zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4788f-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="4788f-154">Da Setup. exe, lync Server-Verwaltungsshell-Cmdlets und lync Server-Systemsteuerung Zugriff auf diese Container benötigen, tritt beim Setup und bei der Installation der Verwaltungstools ein Fehler auf, es sei denn, der Benutzer, der die Installation ausführt, verfügt über Benutzerrechte, die dem Schema entsprechen. Gruppenmitgliedschaft von Administratoren und Organisations-Admins.</span><span class="sxs-lookup"><span data-stu-id="4788f-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="4788f-155">Um dieses Problem zu beheben, müssen Sie der Gruppe "RTCUniversalGlobalWriteGroup" Lese- und Schreibberechtigungen für die Schema- und Konfigurationscontainer gewähren.</span><span class="sxs-lookup"><span data-stu-id="4788f-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

