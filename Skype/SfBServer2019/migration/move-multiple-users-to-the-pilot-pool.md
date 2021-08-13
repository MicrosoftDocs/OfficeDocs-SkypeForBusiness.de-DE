---
title: Verschieben mehrerer Benutzer in den Pilotpool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Mit Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell können Sie mehrere Benutzer aus Ihrem Legacypool in ihren Skype for Business Server 2019-Pilotpool verschieben.
ms.openlocfilehash: 689886060f14a47e82865a2ed66bfc3ff495dfdc3b1f44e6c5674294b4d21eb9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300651"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Verschieben mehrerer Benutzer in den Pilotpool

Mit Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell können Sie mehrere Benutzer aus Ihrem Legacypool in ihren Skype for Business Server 2019-Pilotpool verschieben.

 **Inhalt dieses Artikels**
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung](#sectionSection0)
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell](#sectionSection1)
  
[So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung
<a name="sectionSection0"> </a>

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie auf **"Benutzer",** auf **"Suchen"** und dann auf **"Suchen".**
    
3. Wählen Sie zwei Benutzer aus, die Sie in den Skype for Business Server 2019-Pool verschieben möchten. In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.
    
     ![Verschieben von Benutzern in einen bestimmten Registrierungspool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.
    
5. Wählen Sie in der Dropdownliste den Pool Skype for Business Server 2019 aus.
    
6. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
    
     ![Dialogfeld "Benutzer verschieben", Pool der Zielregistrierungsstelle](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Stellen Sie sicher, dass die Spalte **"Registrierungsstellenpool"** für die Benutzer nun den Pool Skype for Business Server 2019 enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell
<a name="sectionSection1"> </a>

1. Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell. 
    
2. Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **User1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie **pool_FQDN** durch den Namen des Zielpools. In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Beispiel für das Cmdlet "PowerShell Get-CsUser"](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Die **Registrierungspool**-Identität sollte jetzt auf den Pool zeigen, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden. Wiederholen Sie den Schritt, um zu überprüfen, ob **Benutzer2** verschoben wurde. 
    
     ![Ausgabe des Cmdlets "PowerShell Get-UsUser -Identity"](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype for Business Server 2019-Verwaltungsshell
<a name="sectionSection2"> </a>

In diesem Beispiel wurden alle Benutzer an den Legacypool (pool01.contoso.net) zurückgegeben. Mithilfe der Skype for Business Server 2019-Verwaltungsshell verschieben wir alle Benutzer gleichzeitig in den Skype for Business Server 2019-Pool (pool02.contoso.net).
  
1. Öffnen Sie die Skype for Business Server 2019-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Führen Sie **"Get-CsUser"** für einen der Pilotbenutzer aus. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Die Identität des **Registrierungsstellenpools** für jeden Benutzer verweist nun auf den Pool, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde. 
    
5. Darüber hinaus können wir die Liste der Benutzer in der Systemsteuerung Skype for Business Server 2019 anzeigen und überprüfen, ob der Wert des Registrierungsstellenpools jetzt auf den Pool Skype for Business Server 2019 verweist.
    
     ![Benutzerliste Skype for Business Server 2019-Systemsteuerung](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

