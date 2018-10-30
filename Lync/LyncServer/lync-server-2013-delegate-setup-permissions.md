---
title: 'Lync Server 2013: Delegieren von Setupberechtigungen'
TOCTitle: Delegieren von Setupberechtigungen
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412735(v=OCS.15)
ms:contentKeyID: 49294907
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Delegieren von Setupberechtigungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn Sie Benutzern oder Gruppen, die Lync Server 2013 bereitstellen, keine Mitgliedschaft in der Gruppe "Domänen-Admins" gewähren möchten, können Sie Mitgliedern der Gruppe "RTCUniversalServerAdmins" die Ausführung des Cmdlets **Enable-CsTopology**  Windows PowerShell auf Servern mit Lync Server 2013 ermöglichen. Standardmäßig verfügen Mitglieder der Gruppe "RTCUniversalServerAdmins" nicht über die Berechtigung zum Ausführen dieses Cmdlets. Sie erteilen Berechtigungen zum Ausführen von **Enable-CsTopology** auf Servern mit Lync Server, indem Sie mithilfe des Cmdlets **Grant-CsSetupPermission** eine Organisationseinheit angeben, in der sich Computerobjekte für den Server mit Lync Server 2013 befinden.

Während der Domänenvorbereitung, die bei der Installation von Lync Server durchgeführt wird, werden nicht automatisch die Berechtigungen hinzugefügt, die Mitgliedern der Gruppe "RTCUniversalServerAdmins" die Ausführung des Cmdlets Enable-CsTopology ermöglichen. Dies bedeutet, dass Sie standardmäßig ein Domänenadministrator sein müssen, um eine Topologie zu aktivieren. Um Mitgliedern der Gruppe "RTCUniversalServerAdmins" das Recht zum Aktivieren einer Topologie zu erteilen, müssen Sie das Cmdlet Grant-CsSetupPermissions ausführen. Außerdem müssen Sie dieses Cmdlet für jeden Active Directory-Container mit Computern ausführen, auf denen Lync Server ausgeführt wird.

Beachten Sie, dass dieses Cmdlet nur der Gruppe "RTCUniversalServerAdmins" Berechtigungen erteilt; das Cmdlet kann keiner anderen Sicherheitsgruppe oder einzelnen Benutzern Berechtigungen gewähren.


> [!NOTE]
> <STRONG>Enable-CsTopology</STRONG> ist das wichtigste Cmdlet, mit dem Sie der Gruppe "RTCUniversalServerAdmins" das Einrichten und Bereitstellen von Lync Server 2013 ermöglichen.



## So erteilen Sie der Gruppe "RTCUniversalServerAdmins" die Möglichkeit zum Ausführen von "Enable-CsTopology"

1.  Melden Sie sich bei einem Server als Mitglied der Gruppe "Domänen-Admins" für die Domäne an, in der der delegierte Benutzer **Enable-CsTopology** ausführen soll.

2.  Öffnen Sie die Verwaltungsshell für Lync Server 2013. Die Verwaltungsshell für Lync Server 2013 wird automatisch auf jedem Front-End-Server oder jedem Computer installiert, auf dem die Lync Server 2013-Verwaltungstools installiert wurden. Ausführliche Informationen zur Verwaltungsshell für Lync Server 2013 finden Sie unter [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation.

3.  Führen Sie das folgenden Cmdlet in der Verwaltungsshell für Lync Server 2013 aus:
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    

    > [!NOTE]
    > Wenn die Organisationseinheit nicht die oberste Ebene ist, müssen Sie den vollständigen Domänennamen angeben.

    
    Im folgenden Beispiel wird als Organisationseinheit "Lync Servers" in der Domäne "contoso.com" festgelegt.
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

