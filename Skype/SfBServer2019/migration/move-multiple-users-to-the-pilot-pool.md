---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Sie können mehrere Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben.
ms.openlocfilehash: 62cf398a55be9c17526e8d607642db236ae57a3f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813273"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Verschieben mehrerer Benutzer in den Pilot Pool

Sie können mehrere Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben.

 **In diesem Artikel**
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung](#sectionSection0)
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell](#sectionSection1)
  
[So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung
<a name="sectionSection0"> </a>

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
2. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
3. Wählen Sie zwei Benutzer aus, die Sie in den Skype for Business Server 2019-Pool verschieben möchten. In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.
    
     ![Verschieben von Benutzern in einen bestimmten Registrierungspool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.
    
5. Wählen Sie in der Dropdownliste den Skype for Business Server 2019-Pool aus.
    
6. Klicken Sie auf **Aktion**und dann auf **ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
    
     ![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell
<a name="sectionSection1"> </a>

1. Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell. 
    
2. Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie **pool_FQDN** durch den Namen des Ziel Pools. In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Beispiel für ein PowerShell-Cmdlet "Get-CsUser"](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde. 
    
     ![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell
<a name="sectionSection2"> </a>

In diesem Beispiel wurden alle Benutzer an den Legacy Pool (pool01.contoso.net) zurückgegeben. Mit der Skype for Business Server 2019-Verwaltungsshell werden alle Benutzer gleichzeitig in den Skype for Business Server 2019-Pool (pool02.contoso.net) verschoben.
  
1. Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Führen **Sie Get-CsUser** für einen der Pilotbenutzer aus. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Die Identität des **registrierungspools** für jeden Benutzer verweist nun auf den Pool, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. 
    
5. Darüber hinaus können wir die Liste der Benutzer in der Systemsteuerung von Skype for Business Server 2019 anzeigen und überprüfen, ob der Wert des registrierungspools nun auf den Skype for Business Server 2019-Pool verweist.
    
     ![Skype for Business Server 2019 Control Panel-Benutzerliste](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

