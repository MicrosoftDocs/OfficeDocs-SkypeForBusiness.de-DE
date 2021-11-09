---
title: Verwalten von Netzwerkregionenrouten
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Eine Netzwerkregionsroute definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine Netzwerkregionsroute erforderlich.
ms.openlocfilehash: 18bee9a28eed10affae1b0dab855c379709b37bb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864752"
---
# <a name="managing-network-region-routes-in-skype-for-business-server"></a>Verwalten von Netzwerkregionsrouten in Skype for Business Server

Eine *Netzwerkregionsroute* definiert die Route zwischen zwei Netzwerkregionen. Für jedes Netzwerkregionenpaar in Ihrer Anrufsteuerungsbereitstellung ist eine Netzwerkregionsroute erforderlich. So kann jede Netzwerkregion innerhalb der Bereitstellung auf alle anderen Regionen zugreifen. Verwenden Sie die Verfahren in dieser Artilce, um Netzwerkregionenrouten anzuzeigen, zu erstellen, zu ändern oder zu löschen.

## <a name="view-network-region-route-information"></a>Anzeigen von Netzwerkregionenrouteninformationen 

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Verwenden Sie die folgenden Verfahren, um vorhandene Netzwerkregionenrouten in Skype for Business Server Systemsteuerung oder Skype for Business Server Verwaltungsshell anzuzeigen. 

### <a name="to-view-network-region-route-information-in-skype-for-business-server-control-panel"></a>So zeigen Sie Netzwerkregionen-Routeninformationen in Skype for Business Server Systemsteuerung an

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionsroute** auf die Regionsroute, die Sie anzeigen möchten.


    > [!NOTE]
    > Sie können nur jeweils eine Regionsroute anzeigen.


5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.


### <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Netzwerkregionenrouteninformationen mithilfe Windows PowerShell Cmdlets

Informationen zur Netzwerkregionenroute können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden. Dieses Cmdlet kann entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. 

### <a name="to-view-network-region-route-information"></a>So zeigen Sie Informationen zur Netzwerkregionsroute an

  - Geben Sie zum Anzeigen von Informationen zu allen Netzwerkregionenrouten den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
    **Get-CsNetworkInterRegionRoute**
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
    Identität: TransAmericaRoute<br/>
    NetworkRegionLinks : {NorthwestToNortheast}<br/>
    InterNetworkRegionRouteID : TransAmericaRoute<br/>
    NetworkRegionID1 : Pacific Northwest<br/>
    NetworkRegionID2 : Nordost<br/>

For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.


## <a name="create-or-modify-network-region-routes"></a>Erstellen oder Ändern von Netzwerkregionenrouten

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Sie können die Skype for Business Server Systemsteuerung verwenden, um Netzwerkregionenrouten zu konfigurieren. In der Skype for Business Server Systemsteuerung können Sie eine Netzwerkregionenroute erstellen, ändern oder löschen. Verwenden Sie dieses Thema, um eine Netzwerkregionenroute zu erstellen oder zu ändern. 

### <a name="to-create-a-network-region-route"></a>So erstellen Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf **Neu**.

5.  Geben Sie im Abschnitt **Neue Regionenroute** im Feld **Name** einen Wert ein.
   
    > [!NOTE]  
    > Dieser Wert muss innerhalb Ihrer Skype for Business Server Bereitstellung eindeutig sein.

6.  Wählen Sie in der Dropdownliste **"Netzwerkregion \# 1"** eine der beiden Regionen aus, die über diese Route verbunden werden sollen.

7.  Wählen Sie in der Dropdownliste **"Netzwerkregion \# 2"** die andere Region für diese Route aus. Diese Region muss sich von der Region unterscheiden, die für die Netzwerkregion 1 ausgewählt \# wurde.

8.  Fügen Sie der Route über das Listenfeld **Netzwerkregionenverbindungen** Regionenverbindungen hinzu. Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf eine Regionenverbindung, die Sie dieser Route hinzufügen möchten, und klicken Sie anschließend auf **OK**.
    
    > [!NOTE]  
    > Klicken Sie erneut auf die Schaltfläche **Hinzufügen**, um weitere Verbindungen hinzuzufügen, oder wählen Sie eine Verbindung aus, und klicken Sie auf **Entfernen**, um eine Verbindung zu entfernen.

9.  Klicken Sie auf **Commit**.


### <a name="to-modify-a-network-region-route"></a>So ändern Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie ändern möchten.

5.  Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.

6.  In **Regionenroute bearbeiten** können Sie die über diese Route verbundenen Regionen und die der Route zugeordneten Regionenverbindungen ändern.

7.  Klicken Sie auf **Commit**.


## <a name="delete-existing-network-region-routes"></a>Löschen vorhandener Netzwerkregionenrouten

Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen. Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt. Sie können die Skype for Business Server Systemsteuerung verwenden, um Netzwerkregionenrouten zu konfigurieren. In der Skype for Business Server Systemsteuerung können Sie eine Netzwerkregionenroute erstellen, ändern oder löschen. In diesem Thema wird beschrieben, wie vorhandene Netzwerkregionenrouten gelöscht werden. 

### <a name="to-delete-a-network-region-route"></a>So löschen Sie eine Netzwerkregionenroute

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsAdministrator" zugewiesen ist, bei einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 

3.  Klicken Sie in der linken Navigationsleiste auf **"Netzwerkkonfiguration"** und dann auf **"Regionenroute".**

4.  Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie löschen möchten.

    > [!NOTE]  
    > Sie können mehrere Regionenrouten in einem Arbeitsschritt löschen. Wählen Sie dazu mit gedrückter STRG-TASTE mehrere Regionenrouten aus. Wenn Sie alle Regionenrouten auswählen möchten, klicken Sie im Menü **Bearbeiten** auf **Alle auswählen**.

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.



## <a name="see-also"></a>Siehe auch

[Verwalten von Netzwerkregionen in Skype for Business Server](managing-network-regions.md)

[New-CsNetworkInterRegionRoute](/powershell/module/skype/New-CsNetworkInterRegionRoute)  

[Set-CsNetworkInterRegionRoute](/powershell/module/skype/Set-CsNetworkInterRegionRoute) 
 
[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/Get-CsNetworkInterRegionRoute)