---
title: 'Lync Server 2013: Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert'
TOCTitle: Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412970(v=OCS.15)
ms:contentKeyID: 49295334
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vererbung von Berechtigungen ist für Computer-, Benutzer- oder InetOrgPerson-Container deaktiviert in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-12-19_

Im gesperrten Modus von Active Directory-Domänendienste werden Benutzer- und Computerobjekte häufig in speziellen Organisationseinheiten (Organizational Units, OUs) angeordnet. Dabei ist die Vererbung von Berechtigungen deaktiviert, um zum Schutz der administrativen Delegierung beizutragen und um die Verwendung von Gruppenrichtlinienobjekten zur Durchsetzung von Sicherheitsrichtlinien zu aktivieren.

Die Domänenvorbereitung und die Serveraktivierung legen die Zugriffssteuerungseinträge (ACEs) fest, die Lync Server 2013 benötigt. Wenn die Vererbung von Berechtigungen deaktiviert ist, können die Lync Server-Sicherheitsgruppen diese Zugriffssteuerungseinträge nicht erben. Wenn diese Berechtigungen nicht vererbt werden, können die Lync Server-Sicherheitsgruppen nicht auf die Einstellungen zugreifen, was die beiden folgenden Probleme verursacht:

  - Um Benutzer, InetOrgPersons und Kontakte zu verwalten und Server zu betreiben, benötigen die Lync Server-Sicherheitsgruppen Zugriffssteuerungseinträge, die über das Verfahren zur Domänenvorbereitung für die Eigenschaftensätze der einzelnen Benutzer, für die Echtzeitkommunikation, für die Benutzersuche in Echtzeit und öffentliche Informationen festgelegt wurden. Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von den Sicherheitsgruppen nicht geerbt, sodass diese keine Server oder Benutzer verwalten können.

  - Zum Ermitteln von Servern und Pools verwenden Server mit Lync Server Zugriffssteuerungseinträge, die bei der Aktivierung für computerbezogene Objekte festgelegt wurden, einschließlich des Objekts für Microsoft-Container und -Server. Wenn die Vererbung von Berechtigungen deaktiviert ist, werden diese Zugriffssteuerungseinträge von Sicherheitsgruppen, Servern und Pools nicht geerbt und können nicht verwendet werden.

Um diese Probleme zu behandeln, bietet Lync Server das Cmdlet **Grant-CsOuPermission**. Dieses Cmdlet legt die erforderlichen Lync Server-Zugriffssteuerungseinträge direkt für einen angegebenen Container und Organisationseinheiten sowie die Objekte innerhalb des Containers bzw. der Organisationseinheit fest.

## Festlegen von Berechtigungen für Benutzer-, InetOrgPerson- und Kontaktobjekte nach dem Ausführen der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Benutzer- oder InetOrgPerson-Objekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt. In dieser Situation müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit mit Benutzer- oder InetOrgPerson-Objekten ausführen, für die die Vererbung von Berechtigungen deaktiviert ist. Wenn eine Topologie mit einer zentralen Gesamtstruktur bereitgestellt wurde, müssen Sie dieses Verfahren auch für die Container oder Organisationseinheiten mit Kontaktobjekten ausführen. Ausführliche Informationen zu Topologien mit zentralen Gesamtstrukturen finden Sie unter [Unterstützte Active Directory-Topologien in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in der Unterstützungsdokumentation. Der "ObjectType"-Parameter gibt den Objekttyp an. Der OU-Parameter gibt die Organisationseinheit an.

Mit diesem Cmdlet werden den angegebenen Containern oder Organisationseinheiten und den Benutzer- bzw. InetOrgPerson-Objekten innerhalb des Containers die erforderlichen Zugriffssteuerungseinträge direkt hinzugefügt.

Sie benötigen die Benutzerrechte der Gruppe "Domänen-Admins" oder gleichwertige Rechte, um dieses Cmdlet auszuführen. Wenn die Zugriffssteuerungseinträge für authentifizierte Benutzer auch in der gesperrten Umgebung entfernt wurden, müssen Sie diesem Konto Zugriffssteuerungseinträge für den Lesezugriff auf die entsprechenden Container oder Organisationseinheiten in der Gesamtstruktur-Stammdomäne hinzufügen. Dies ist unter [Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) beschrieben. Alternativ dazu können Sie ein Konto verwenden, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Benutzer-, InetOrgPerson- und Kontaktobjekte fest**

1.  Melden Sie sich unter Verwendung eines Kontos, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt, bei einem Domänencomputer an.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  Suchen Sie in der Protokolldatei am Ende jeder Aufgabe nach dem Ausführungsergebnis **\<Erfolg\>** , um sicherzustellen, dass die Berechtigungen festgelegt wurden. Schließen Sie anschließend das Protokollfenster. Sie können auch den folgenden Befehl ausführen, um zu ermitteln, ob die Berechtigungen festgelegt wurden:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

## Festlegen von Berechtigungen für Computerobjekte nach der Ausführung der Domänenvorbereitung

In einer gesperrten Active Directory-Umgebung, in der die Vererbung von Berechtigungen deaktiviert ist, werden die erforderlichen Zugriffssteuerungseinträge für Container oder Organisationseinheiten, in denen die Computerobjekte der Domäne enthalten sind, nicht über die Domänenvorbereitung festgelegt. In dieser Situation müssen Sie das Cmdlet **Grant-CsOuPermission** für jeden Container oder jede Organisationseinheit mit Lync Server-Computern ausführen, für die die Vererbung von Berechtigungen deaktiviert ist. Der ObjectType-Parameter gibt den Objekttyp an.

Bei diesem Verfahren werden die erforderlichen Zugriffssteuerungseinträge den angegebenen Containern direkt hinzugefügt.

Sie benötigen die Benutzerrechte der Gruppe "Domänen-Admins" oder äquivalente Rechte, um dieses Cmdlet auszuführen. Wenn die Zugriffssteuerungseinträge für authentifizierte Benutzer ebenfalls entfernt wurden, müssen Sie diesem Konto Zugriffssteuerungseinträge für den Lesezugriff auf die entsprechenden Container in der Gesamtstruktur-Stammdomäne hinzufügen. Dies ist unter [Entfernte Berechtigungen für authentifizierte Benutzer in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) beschrieben. Alternativ dazu können Sie ein Konto verwenden, das Mitglied der Gruppe "Organisations-Admins" ist.

**So legen Sie die erforderlichen Zugriffssteuerungseinträge für Computerobjekte fest**

1.  Melden Sie sich beim Domänencomputer mit einem Konto an, das Mitglied der Gruppe "Domänen-Admins" ist oder das über gleichwertige Benutzerrechte verfügt.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Führen Sie folgenden Befehl aus:
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    Wenn Sie den Parameter "Domain" nicht angeben, wird standardmäßig die lokale Domäne verwendet.
    
    Beispiel:
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  In der Beispielprotokolldatei "C:\\Logs\\OUPermissions.xml" würden Sie am Ende jeder Aufgabe nach dem Ausführungsergebnis **\<Erfolg\>** suchen und sicherstellen, dass keine Fehler vorliegen, und das Protokoll dann schließen. Sie können das folgende Cmdlet ausführen, um Berechtigungen zu testen:
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    Beispiel:
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    

    > [!NOTE]
    > Wenn Sie die Domänenvorbereitung für die Gesamtstruktur-Stammdomäne in einer gesperrten Active Directory-Umgebung ausführen, müssen Sie berücksichtigen, dass Lync Server auf die Schema- und Konfigurationscontainer von Active Directory zugreifen muss.<BR>Wenn die Standardberechtigung für authentifizierte Benutzer aus den Schema- bzw. Konfigurationscontainern in AD DS entfernt wurde, verfügen nur Mitglieder der Gruppe "Schema-Admins" (für Schemacontainer) bzw. "Organisations-Admins" (für Konfigurationscontainer) über Zugriff auf den jeweiligen Container. Da "Setup.exe", die Lync Server-Verwaltungsshell-Cmdlets und die Lync Server-Systemsteuerung auf diese Container zugreifen müssen, tritt bei Ausführen von Setup und bei der Installation der Verwaltungstools ein Fehler auf, wenn der ausführende Benutzer nicht über die Benutzerrechte der Gruppe "Schema-Admins" oder "Organisations-Admins" verfügt.<BR>Um dieses Problem zu beheben, müssen Sie der Gruppe "RTCUniversalGlobalWriteGroup" Lese- und Schreibberechtigungen für die Schema- und Konfigurationscontainer gewähren.


