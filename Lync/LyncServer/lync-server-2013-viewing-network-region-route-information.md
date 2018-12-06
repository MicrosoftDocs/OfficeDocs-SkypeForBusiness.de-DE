---
title: Anzeigen von Informationen zu Netzwerkregionsrouten
TOCTitle: Anzeigen von Informationen zu Netzwerkregionsrouten
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49890703
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu Netzwerkregionsrouten

 

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Verwenden Sie die folgenden Verfahren, um vorhandene Netzwerkregionsrouten in Systemsteuerung für Lync Server 2013 oder Verwaltungsshell für Lync Server 2013 anzuzeigen. Ausführliche Informationen zum Erstellen oder Ändern von Netzwerkregionsrouten finden Sie unter [Erstellen oder Ändern von Netzwerkregionsrouten](lync-server-2013-creating-or-modifying-network-region-routes.md).

## So zeigen Sie Informationen zu Netzwerkregionsrouten in Lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionsroute**.

4.  Klicken Sie auf der Seite **Regionsroute** auf die Regionsroute, die Sie anzeigen möchten.
    

    > [!NOTE]
    > Sie können nur jeweils eine Regionsroute anzeigen.



5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

## Anzeigen von Informationen zu Netzwerkregionsrouten mithilfe von Lync Server-PowerShell-Cmdlets

Informationen zu Netzwerkregionsrouten können auch mit dem Lync Server-PowerShell- und dem Get-CsNetworkInterRegionRoute-Cmdlet angezeigt werden. Dieses Cmdlet kann entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen von Informationen zu Netzwerkregionsrouten

  - Sie können Informationen zu allen Netzwerkregionsrouten anzeigen, indem Sie in der Lync Server-Verwaltungsshell den folgenden Befehl eingeben und dann die EINGABETASTE drücken:
    
        Get-CsNetworkInterRegionRoute
    
    Dadurch werden Informationen ähnlich wie die folgenden zurückgegeben:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.

## Siehe auch

#### Aufgaben

[Erstellen oder Ändern von Netzwerkregionsrouten](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Löschen von vorhandenen Netzwerkregionsrouten](lync-server-2013-deleting-existing-network-region-routes.md)

