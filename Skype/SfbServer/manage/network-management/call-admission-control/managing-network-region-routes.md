---
title: Verwalten von Routen im Netzwerkbereich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eine Netzwerk Regions Route definiert die Route zwischen zwei netzwerkregionen. Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk Regions Route erforderlich.
ms.openlocfilehash: 5e0c099b8c461873b96963c721d835f1ccdf4705
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817494"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Verwalten von Netzwerkregionsrouten in Skype for Business Server

Eine *Netzwerk Regions Route* definiert die Route zwischen zwei netzwerkregionen. Für jedes Paar von netzwerkregionen in der Bereitstellung für die Anrufsteuerung ist eine Netzwerk Regions Route erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen. Verwenden Sie die Verfahren in diesem Artilce, um Netzwerkbereichs Routen anzuzeigen, zu erstellen, zu ändern oder zu löschen.

## <a name="view-network-region-route-information"></a>Anzeigen von Routeninformationen zu netzwerkregionen 

Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird. Gehen Sie wie folgt vor, um vorhandene Netzwerkbereichs Routen in der Skype for Business Server-Systemsteuerung oder in der Skype for Business Server-Verwaltungsshell anzuzeigen. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>So zeigen Sie netzwerkregion-Routeninformationen in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Route des Bereichs** auf die Route, die Sie anzeigen möchten.


    > [!NOTE]  
    > Sie können jeweils nur eine Regions Route anzeigen.


5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Routeninformationen des Netzwerkbereichs mithilfe von Windows PowerShell-Cmdlets

Netzwerkregion-Routeninformationen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

### <a name="to-view-network-region-route-information"></a>So zeigen Sie netzwerkregion-Routeninformationen an

  - Wenn Sie Informationen zu allen Routen des Netzwerkbereichs anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkInterRegionRoute
    
    Es werden etwa folgende Informationen zurückgegeben:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .


## <a name="create-or-modify-network-region-routes"></a>Erstellen oder Ändern von Netzwerkbereichs Routen

Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Strecken des Netzwerkbereichs zu konfigurieren. Über die Skype for Business Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um eine Netzwerk Regions Route zu erstellen oder zu ändern. 

### <a name="to-create-a-network-region-route"></a>So erstellen Sie eine Netzwerk Regions Route

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Region Route** auf **neu**.

5.  Geben **Sie in das**Feld Name einen Wert in das Feld **Name** ein.
   
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **netzwerkregion \#1** einen der beiden Regionen aus, die mit dieser Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste **netzwerkregion \#2** den anderen Bereich für diese Route aus. Diese Region muss sich von der für netzwerkregion \#1 ausgewählten Region unterscheiden.

8.  Verwenden Sie das Listenfeld **Netzwerk Gebiets Links** , um der Route Bereichs Links hinzuzufügen. Klicken Sie auf die Schaltfläche **Hinzufügen** , um die Seite **Regions Link** anzuzeigen. Klicken Sie auf einen Regions Link, der zu dieser Route hinzugefügt werden soll, und klicken Sie dann auf **OK**.
    
    > [!NOTE]  
    > Klicken Sie weiter auf die Schaltfläche **Hinzufügen** , um weitere Links hinzuzufügen, oder wählen Sie einen Link aus, und klicken Sie auf **Entfernen** , um einen Link zu entfernen.

9.  Klicken Sie auf **Commit ausführen**.


### <a name="to-modify-a-network-region-route"></a>So ändern Sie eine Route des Netzwerkbereichs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Region Route** auf die Route, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In der **Route "Region bearbeiten**" können Sie die Regionen ändern, die mit dieser Route verbunden sind, und die der Route zugeordneten Regions Verknüpfungen.

7.  Klicken Sie auf **Commit ausführen**.


## <a name="delete-existing-network-region-routes"></a>Löschen vorhandener Strecken des Netzwerkbereichs

Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Strecken des Netzwerkbereichs zu konfigurieren. Über die Skype for Business Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um vorhandene Netzwerkbereichs Routen zu löschen. 

### <a name="to-delete-a-network-region-route"></a>So löschen Sie eine Route des Netzwerkbereichs

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**, und klicken Sie dann auf **Regions Route**.

4.  Klicken Sie auf der Seite **Region Route** auf die Route, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehr als eine Regions Route gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Bereichs Routen aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Regions Routen auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen** .

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.



## <a name="see-also"></a>Siehe auch

[Verwalten von Netzwerkregionen in Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
