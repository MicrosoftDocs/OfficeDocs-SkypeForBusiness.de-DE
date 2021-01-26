---
title: Verwalten von Netzwerkregionsrouten
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eine Netzwerkregionsroute definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine Netzwerkregionsroute erforderlich.
ms.openlocfilehash: 23dec126511b941ff3e25b22c37cbba0854b13bc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816435"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Verwalten von Netzwerkregionsrouten in Skype for Business Server

Eine *Netzwerkregionsroute* definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine Netzwerkregionsroute erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen. Verwenden Sie die Verfahren in dieser Artilce zum Anzeigen, Erstellen, Ändern oder Löschen von Netzwerkregionsrouten.

## <a name="view-network-region-route-information"></a>Anzeigen von Informationen zur Netzwerkregionsroute 

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Verwenden Sie die folgenden Verfahren, um vorhandene Netzwerkregionsrouten in der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell anzeigen. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>So zeigen Sie Informationen zur Netzwerkregionsroute in der Skype for Business Server-Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionsroute** auf die Regionsroute, die Sie anzeigen möchten.


    > [!NOTE]  
    > Sie können nur jeweils eine Regionsroute anzeigen.


5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Informationen zur Netzwerkregionsroute mithilfe Windows PowerShell Cmdlets

Informationen zur Netzwerkregionsroute können mithilfe von Windows PowerShell und dem cmdlet Get-CsNetworkInterRegionRoute angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. 

### <a name="to-view-network-region-route-information"></a>So zeigen Sie Informationen zur Netzwerkregionsroute an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkregionsrouten den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsNetworkInterRegionRoute
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.


## <a name="create-or-modify-network-region-routes"></a>Erstellen oder Ändern von Netzwerkregionsrouten

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Netzwerkregionsrouten zu konfigurieren. In der Skype for Business Server-Systemsteuerung können Sie eine Netzwerkregionsroute erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um eine Netzwerkregionsroute zu erstellen oder zu ändern. 

### <a name="to-create-a-network-region-route"></a>So erstellen Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenroute** im Feld **Name** einen Wert ein.
   
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype for Business Server-Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste "Netzwerkregion **\# 1"** eine der beiden Regionen aus, die über diese Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste "Netzwerkregion **\# 2"** die andere Region für diese Route aus. Diese Region muss sich von der Für Netzwerkregion 1 ausgewählten Region \# unterscheiden.

8.  Fügen Sie der Route über das Listenfeld **Netzwerkregionenverbindungen** Regionenverbindungen hinzu. Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf eine Regionenverbindung, die Sie dieser Route hinzufügen möchten, und klicken Sie anschließend auf **OK**.
    
    > [!NOTE]  
    > Klicken Sie erneut auf die Schaltfläche **Hinzufügen**, um weitere Verbindungen hinzuzufügen, oder wählen Sie eine Verbindung aus, und klicken Sie auf **Entfernen**, um eine Verbindung zu entfernen.

9.  Klicken Sie auf **Commit**.


### <a name="to-modify-a-network-region-route"></a>So ändern Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In **Regionenroute bearbeiten** können Sie die über diese Route verbundenen Regionen und die der Route zugeordneten Regionenverbindungen ändern.

7.  Klicken Sie auf **Commit**.


## <a name="delete-existing-network-region-routes"></a>Löschen vorhandener Netzwerkregionsrouten

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Sie können die Skype for Business Server-Systemsteuerung verwenden, um Netzwerkregionsrouten zu konfigurieren. In der Skype for Business Server-Systemsteuerung können Sie eine Netzwerkregionsroute erstellen, ändern oder löschen. In diesem Thema wird beschrieben, wie vorhandene Netzwerkregionenrouten gelöscht werden. 

### <a name="to-delete-a-network-region-route"></a>So löschen Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehrere Regionenrouten in einem Arbeitsschritt löschen. Wählen Sie dazu mit gedrückter STRG-TASTE mehrere Regionenrouten aus. Wenn Sie alle Regionenrouten auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.



## <a name="see-also"></a>Siehe auch

[Verwalten von Netzwerkregionen in Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
