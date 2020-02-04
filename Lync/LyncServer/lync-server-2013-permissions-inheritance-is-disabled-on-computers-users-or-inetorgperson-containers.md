---
title: 'Lync Server 2013: Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a>Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-19_

In einer gesperrten Active Directory-Domänendienste werden Benutzer und Computer Objekte häufig in bestimmten Organisationseinheiten (Organizational Units, OUs) mit deaktivierter Berechtigungsvererbung gespeichert, um eine sichere administrative Delegierung zu gewährleisten und die Verwendung von Gruppenrichtlinienobjekten (GPOs) zu ermöglichen. So erzwingen Sie Sicherheitsrichtlinien

Domänenvorbereitung und Serveraktivierung legen Sie die für lync Server 2013 erforderlichen Zugriffssteuerungseinträge (Access Control Entries, ACEs) an. Wenn die Berechtigungsvererbung deaktiviert ist, können die lync Server-Sicherheitsgruppen diese ACEs nicht erben. Wenn diese Berechtigungen nicht vererbt werden, können lync Server-Sicherheitsgruppen nicht auf Einstellungen zugreifen, und die beiden folgenden Probleme treten auf:

  - Um Benutzer, InetOrgPersons und Kontakte zu verwalten und Server zu betreiben, erfordern die lync Server-Sicherheitsgruppen ACEs, die durch das Verfahren zur Domänenvorbereitung auf die Eigenschaftensätze der einzelnen Benutzer festgelegt sind, die Echtzeitkommunikation (RTC), RTC-Benutzersuche und öffentliche Informationen . Wenn die Vererbung von Berechtigungen deaktiviert ist, erben Sicherheitsgruppen diese ACEs nicht und können keine Server oder Benutzer verwalten.

  - Um Server und Pools zu ermitteln, basieren Server mit lync Server auf ACEs, die durch Aktivierung für computerbezogene Objekte, einschließlich des Microsoft-Containers und des Server Objekts, festgesetzt werden. Wenn die Vererbung von Berechtigungen deaktiviert ist, erben Sicherheitsgruppen, Server und Pools diese ACEs nicht und können diese ACEs nicht nutzen.

Zur Behebung dieser Probleme stellt lync Server das Cmdlet **Grant-CsOuPermission** bereit. Mit diesem Cmdlet werden die erforderlichen lync Server-ACEs direkt für einen bestimmten Container und für die Organisationseinheiten und die Objekte im Container oder in der Organisationseinheit festgelegt.

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a>Einrichten von Berechtigungen für Benutzer-, InetOrgPerson-und Kontaktobjekte nach dem Ausführen der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Berechtigungsvererbung deaktiviert ist, werden bei der Domänenvorbereitung nicht die erforderlichen ACEs für die Container oder Organisationseinheiten festgelegt, die Benutzer oder InetOrgPerson-Objekte in der Domäne halten. In diesem Fall müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit ausführen, die über Benutzer-oder InetOrgPerson-Objekte verfügen, für die die Vererbung von Berechtigungen deaktiviert ist. Wenn Sie über eine zentrale Gesamtstrukturtopologie verfügen, müssen Sie dieses Verfahren auch für die Container oder OUs durchführen, in denen Kontaktobjekte enthalten sind. Details zu zentralen Gesamtstruktur Topologien finden Sie unter [unterstützte Active Directory-Topologien in lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Dokumentation zur Unterstützung. Der objectType-Parameter gibt den Objekttyp an. Der Parameter ou gibt die Organisationseinheit an.

Mit diesem Cmdlet werden die erforderlichen ACEs direkt für die angegebenen Container oder OUs sowie für die Objekte User oder inetOrgPerson innerhalb des Containers hinzugefügt. Wenn die Organisationseinheit, auf der dieser Befehl ausgeführt wird, über untergeordnete OUs mit Benutzer-oder inetOrgPerson-Objekten verfügt, werden die Berechtigungen nicht auf diese angewendet. Sie müssen den Befehl für jede untergeordnete ou einzeln ausführen. Hierbei handelt es sich um ein häufiges Szenario mit lync-Host Bereitstellungen, beispielsweise übergeordnete OU = OCS-Mandanten, DC = contoso, DC = local und Child ou = Mandanten 1, ou = OCS-Mandanten, DC = contoso, DC = local.

Zum Ausführen dieses Cmdlets benötigen Sie Benutzerrechte, die der Gruppenmitgliedschaft der Domänenadministratoren entsprechen. Wenn die ACEs für authentifizierte Benutzer auch in der gesperrten Umgebung entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container oder OUs in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet wird, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen ACEs für Benutzer-, InetOrgPerson-und Kontaktobjekte**

1.  Melden Sie sich bei einem Computer mit der Domäne mit einem Konto an, das ein Mitglied der Gruppe "Domänen-Admins" ist oder gleichwertige Benutzerrechte aufweist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Suchen Sie in der Protokolldatei nach ** \<dem\> ** Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, um zu überprüfen, ob die Berechtigungen festgelegt wurden, und schließen Sie dann das Protokollfenster. Sie können auch den folgenden Befehl ausführen, um zu ermitteln, ob die Berechtigungen festgelegt wurden:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a>Einrichten von Berechtigungen für Computer Objekte nach dem Ausführen der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Berechtigungsvererbung deaktiviert ist, werden für die Domänenvorbereitung nicht die erforderlichen ACEs für die Container oder OUs festgelegt, die Computer Objekte innerhalb der Domäne enthalten. In diesem Fall müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede OU ausführen, auf dem Computer mit lync Server ausgeführt werden, auf denen die Vererbung von Berechtigungen deaktiviert ist. Der objectType-Parameter gibt den Objekttyp an.

Mit diesem Verfahren werden die erforderlichen ACEs direkt in den angegebenen Containern hinzugefügt.

Zum Ausführen dieses Cmdlets benötigen Sie Benutzerrechte, die der Gruppenmitgliedschaft der Domänenadministratoren entsprechen. Wenn die ACEs für authentifizierte Benutzer ebenfalls entfernt wurden, müssen Sie diesem Konto Lesezugriffs-ACEs für die relevanten Container in der Gesamtstruktur-Stammdomäne erteilen, wie unter [authentifizierte Benutzerberechtigungen in lync Server 2013 entfernt](lync-server-2013-authenticated-user-permissions-are-removed.md) oder ein Konto verwendet wird, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen ACEs für Computerobjekte**

1.  Melden Sie sich bei dem Domänencomputer mit einem Konto an, das ein Mitglied der Gruppe "Domänen-Admins" ist oder gleichwertige Benutzerrechte aufweist.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Wenn Sie den Parameter Domain nicht angeben, ist der Standardwert die lokale Domäne.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  In der Beispielprotokolldatei C:\\Logs\\OUPermissions. XML suchen Sie nach ** \<\> ** dem Ergebnis der erfolgreichen Ausführung am Ende jeder Aufgabe, und stellen Sie sicher, dass keine Fehler vorhanden sind, und schließen Sie dann das Protokoll. Sie können das folgende Cmdlet ausführen, um Berechtigungen zu testen:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie die Domänenvorbereitung für die Gesamtstruktur-Stammdomäne in einer gesperrten Active Directory-Umgebung ausführen, beachten Sie, dass lync Server Zugriff auf das Active Directory-Schema und die Konfigurationscontainer benötigt.<BR>Wenn die Berechtigung für den Standard authentifizierten Benutzer aus dem Schema oder den Konfigurationscontainern&nbsp;in AD DS entfernt wird, dürfen nur Mitglieder der Gruppe Schemaadministratoren (für Schemacontainer) oder Gruppe Organisations-Admins (für Konfigurationscontainer) auf den angegebenen Container zugreifen. Da für Setup. exe, lync Server-Verwaltungsshell-Cmdlets und lync Server Control Panel Zugriff auf diese Container erforderlich ist, treten beim Einrichten und Installieren der Verwaltungstools Fehler auf, es sei denn, der Benutzer, der die Installation ausführt, verfügt über Benutzerrechte, die dem Schema entsprechen. Gruppenmitgliedschaft für Administratoren und Unternehmensadministratoren.<BR>Um dieses Problem zu beheben, müssen Sie RTCUniversalGlobalWriteGroup Group Read, Schreibzugriff auf die Schema-und Konfigurationscontainer erteilen.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

