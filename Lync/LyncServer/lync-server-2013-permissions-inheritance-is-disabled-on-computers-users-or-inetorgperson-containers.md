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
# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Die Vererbung von Berechtigungen ist für Computer-, Benutzer-oder inetOrgPerson-Container in lync Server 2013 deaktiviert.

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-19_

In einer gesperrten Active Directory-Domänendienste werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierten Berechtigungen vererbt, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (Group Policy Objects, GPOs) zum Erzwingen von Sicherheitsrichtlinien zu ermöglichen.

Domänenvorbereitung und Serveraktivierung legen Sie die für lync Server 2013 erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) fest. Wenn die Vererbung von Berechtigungen deaktiviert ist, können die lync Server Sicherheitsgruppen diese ACEs nicht erben. Wenn diese Berechtigungen nicht vererbt werden, können lync Server Sicherheitsgruppen nicht auf Einstellungen zugreifen, und es treten die folgenden beiden Probleme auf:

  - Um Benutzer, InetOrgPersons und Kontakte zu verwalten und Server zu betreiben, erfordern die lync Server Sicherheitsgruppen ACEs, die von der Domänen Vorbereitungs Prozedur auf den Eigenschaftensätzen der einzelnen Benutzer, RTC (Real-Time Communications), RTC-Benutzersuche und öffentlichen Informationen festgelegt sind. Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von den Sicherheitsgruppen nicht geerbt, sodass diese keine Server oder Benutzer verwalten können.

  - Zum Ermitteln von Servern und Pools beruhen Server mit lync Server auf ACEs, die durch Aktivierung für computerbezogene Objekte festgelegt wurden, einschließlich des Microsoft-Containers und des Server Objekts. Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von Sicherheitsgruppen, Servern und Pools nicht geerbt und können nicht verwendet werden.

Um diese Probleme zu beheben, stellt lync Server das **Grant-CsOuPermission-** Cmdlet bereit. Dieses Cmdlet legt fest, dass lync Server ACEs direkt für einen angegebenen Container und für Organisationseinheiten und die Objekte innerhalb des Containers oder der Organisationseinheit erforderlich sind.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Festlegen von Berechtigungen für Benutzer-, InetOrgPerson- und Kontaktobjekte nach dem Ausführen der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Benutzer- oder InetOrgPerson-Objekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt. In dieser Situation müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit mit Benutzer- oder InetOrgPerson-Objekten ausführen, für die die Vererbung von Berechtigungen deaktiviert ist. Wenn eine Topologie mit einer zentralen Gesamtstruktur bereitgestellt wurde, müssen Sie dieses Verfahren auch für die Container oder Organisationseinheiten mit Kontaktobjekten ausführen. Ausführliche Informationen zu Topologien mit zentraler Gesamtstruktur finden Sie unter [Supported Active Directory Topologies in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation. Der "ObjectType"-Parameter gibt den Objekttyp an. Der OU-Parameter gibt die Organisationseinheit an.

Mit diesem Cmdlet werden den angegebenen Containern oder Organisationseinheiten und den Benutzer- bzw. InetOrgPerson-Objekten innerhalb des Containers die erforderlichen Zugriffssteuerungseinträge direkt hinzugefügt. Wenn die Organisationseinheit, für die dieser Befehl ausgeführt wird, über untergeordnete OUs mit User-oder inetOrgPerson-Objekten verfügt, werden die Berechtigungen nicht auf diese angewendet. Sie müssen den Befehl für jede untergeordnete ou einzeln ausführen. Dies ist ein gängiges Szenario bei lync-Hosting-Bereitstellungen, beispielsweise übergeordnete OU = OCS-Mandanten, DC = contoso, DC = local und Child ou = Tenant1, ou = OCS-Mandanten, DC = contoso, DC = local.

Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren. Wenn die authentifizierten Benutzer-ACEs ebenfalls in der gesperrten Umgebung entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container oder OUs in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen werden in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Benutzer-, InetOrgPerson- und Kontaktobjekte fest**

1.  Melden Sie sich unter Verwendung eines Kontos, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt, bei einem Domänencomputer an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Suchen Sie in der Protokolldatei **\<Success\>** am Ende jeder Aufgabe nach dem Ausführungsergebnis, um sicherzustellen, dass die Berechtigungen festgelegt wurden, und schließen Sie dann das Protokollfenster. Sie können auch den folgenden Befehl ausführen, um zu bestimmen, ob die Berechtigungen festgelegt wurden:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Festlegen von Berechtigungen für Computerobjekte nach der Ausführung der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Computerobjekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt. In diesem Fall müssen Sie das **Grant-CsOuPermission-** Cmdlet für jeden Container oder jede OU ausführen, auf dem Computer ausgeführt werden, auf denen lync Server die Vererbung von Berechtigungen deaktiviert ist. Der ObjectType-Parameter gibt den Objekttyp an.

Bei diesem Verfahren werden die erforderlichen Zugriffssteuerungseinträge den angegebenen Containern direkt hinzugefügt.

Sie benötigen für die Ausführung dieses Cmdlets entsprechende Benutzerrechte für die Gruppenmitgliedschaft von Domänenadministratoren. Wenn die authentifizierten Benutzer-ACEs ebenfalls entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Computerobjekte fest**

1.  Melden Sie sich beim Domänencomputer mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Ausführen
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  In der Beispielprotokolldatei C: \\ Logs \\OUPermissions.xml würden Sie **\<Success\>** am Ende jeder Aufgabe nach dem Ausführungsergebnis suchen und sicherstellen, dass keine Fehler vorliegen, und dann das Protokoll schließen. Sie können das folgende Cmdlet ausführen, um Berechtigungen zu testen:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Domänenvorbereitung in der Gesamtstruktur-Stammdomäne in einer gesperrten Active Directory Umgebung ausführen, müssen Sie beachten, dass lync Server Zugriff auf das Active Directory-Schema und die Konfigurationscontainer benötigt.<BR>Wenn die standardmäßige Berechtigung "authentifizierter Benutzer" aus dem Schema oder den Konfigurationscontainern in AD DS entfernt wird &nbsp; , dürfen nur Mitglieder der Gruppe "Schema-Admins" (für den Schemacontainer) oder der Gruppe "Organisations-Admins" (für den Konfigurationscontainer) auf den angegebenen Container zugreifen. Da Setup.exe, lync Server-Verwaltungsshell-Cmdlets und lync Server-Systemsteuerung Zugriff auf diese Container erfordern, tritt beim Setup und bei der Installation der Verwaltungstools ein Fehler auf, es sei denn, der Benutzer, der die Installation ausführt, verfügt über Benutzerrechte, die den Schema-Admins und den Gruppenmitgliedschaften der Organisations-Admins entsprechen.<BR>Um dieses Problem zu beheben, müssen Sie der Gruppe "RTCUniversalGlobalWriteGroup" Lese- und Schreibberechtigungen für die Schema- und Konfigurationscontainer gewähren.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

