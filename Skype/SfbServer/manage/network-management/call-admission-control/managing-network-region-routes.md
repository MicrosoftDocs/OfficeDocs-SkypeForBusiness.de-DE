---
title: Verwalten von netzwerkregionsrouten
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Eine netzwerkregionenroute definiert die Route zwischen zwei netzwerkregionen. Jedem netzwerkregionenpaar in der die Bereitstellung der anrufsteuerung erfordert eine netzwerkregionenroute.
ms.openlocfilehash: 98d7f0ce8f6cb89aa443c5dc8863afd34c355ff3
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223157"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Verwalten von netzwerkregionsrouten in Skype für Business Server

Eine *netzwerkregionenroute* definiert die Route zwischen zwei netzwerkregionen. Jedem netzwerkregionenpaar in der die Bereitstellung der anrufsteuerung erfordert eine netzwerkregionenroute. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen. Verwenden Sie die Verfahren in diesem Artilce zum Anzeigen, erstellen, ändern oder Löschen von netzwerkregionenrouten.

## <a name="view-network-region-route-information"></a>Informationen zur Ansicht netzwerkregion route 

Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen. Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird. Verwenden Sie die folgenden Verfahren zum Anzeigen von vorhandenen netzwerkregionsrouten in Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>Zum Anzeigen von Informationen zur netzwerkregion Route in Skype Business Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie anzeigen möchten.


    > [!NOTE]  
    > Sie können nur jeweils eine regionsroute anzeigen.


5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zu Netzwerkregionsrouten mithilfe von Windows PowerShell-Cmdlets

Informationen zur netzwerkregion Route kann mithilfe von Windows PowerShell und das Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden. Dieses Cmdlet kann von der Skype für Business Server-Verwaltungsshell oder von einer remote Windows PowerShell-Sitzung ausgeführt werden. 

### <a name="to-view-network-region-route-information"></a>So zeigen Sie Informationen zur netzwerkregion Route an

  - Informationen zu allen netzwerkregionsrouten anzeigen möchten, geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
        Get-CsNetworkInterRegionRoute
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Weitere Informationen finden Sie im Hilfethema für das Cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Erstellen oder Ändern von netzwerkregionsrouten

Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen. Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird. Die Skype Business Server-Systemsteuerung können Sie netzwerkregionsrouten konfigurieren. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregionenroute. Verwenden Sie dieses Thema zum Erstellen oder Ändern einer netzwerkregionenroute. 

### <a name="to-create-a-network-region-route"></a>Erstellen Sie eine netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf **neu**.

5.  Geben Sie in **neue Regionenroute**einen Wert in das Feld **Name** ein.
   
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype für Business Server-Bereitstellung eindeutig sein.

6.  Aus der **netzwerkregion \#1** Dropdown-Listenfeld, wählen Sie eine der zwei Regionen aus, die über diese Route verbunden werden.

7.  Aus der **netzwerkregion \#2** Dropdown-Liste, wählen Sie die anderen Region für diese Route. Diese Region muss die Region für die netzwerkregion ausgewählt anders \#1.

8.  Verwenden Sie das Listenfeld **netzwerkregionenverbindungen** , regionenverbindungen der Route hinzuzufügen. Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf einer regionenverbindung Route hinzufügen, und klicken Sie dann auf **OK**.
    
    > [!NOTE]  
    > Weiterhin klicken Sie auf die Schaltfläche **Hinzufügen** , um weitere Verbindungen hinzuzufügen, oder wählen Sie einen Link, und klicken Sie auf **Entfernen** , um eine Verbindung zu entfernen.

9.  Klicken Sie auf **Commit ausführen**.


### <a name="to-modify-a-network-region-route"></a>So ändern Sie eine netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In **Regionenroute bearbeiten**können Sie über diese Route verbundenen Regionen und die der Route zugeordneten regionenverbindungen ändern.

7.  Klicken Sie auf **Commit ausführen**.


## <a name="delete-existing-network-region-routes"></a>Löschen von vorhandenen netzwerkregionsrouten

Jeder Region innerhalb einer Call Admission Control (, CAC) Konfiguration benötigen eine Möglichkeit zum Zugriff auf allen anderen Regionen. Während die regionenverbindungen bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route welche verknüpften Pfad, der die Verbindung von einer Region zur anderen nimmt wird. Die Skype Business Server-Systemsteuerung können Sie netzwerkregionsrouten konfigurieren. Aus der Skype Business Server-Systemsteuerung können Sie erstellen, ändern oder löschen eine netzwerkregionenroute. Verwenden Sie in diesem Thema, um vorhandene netzwerkregionsrouten zu löschen. 

### <a name="to-delete-a-network-region-route"></a>So löschen Sie eine netzwerkregionenroute

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regionenroute**.

4.  Klicken Sie auf der Seite **Regionenroute** auf die regionenroute, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehrere regionenroute zu einem Zeitpunkt löschen. Zu diesem Zweck, drücken Sie STRG, und wählen Sie mehrere Routen zwischen Regionen aus, während Sie die STRG-Taste gedrückt halten. Oder, um alle Routen zwischen Regionen auszuwählen, klicken Sie auf **Alles markieren** im Menü **Bearbeiten** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie anschließend auf **OK**.



## <a name="see-also"></a>Siehe auch

[Verwalten von netzwerkregionen in Skype für Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  