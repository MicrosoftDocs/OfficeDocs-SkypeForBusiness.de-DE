---
title: Mehrere Benutzer in den Pilot Pool migrieren
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
description: Sie können mehrere Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren.
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753427"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Mehrere Benutzer in den Pilot Pool migrieren

Sie können mehrere Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren.

 **Inhalt dieses Artikels**
  
[So können Sie mehrere Benutzer mithilfe der Systemsteuerung von Skype for Business Server 2019 migrieren](#sectionSection0)
  
[So migrieren Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell](#sectionSection1)
  
[So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell aus](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>So können Sie mehrere Benutzer mithilfe der Systemsteuerung von Skype for Business Server 2019 migrieren
<a name="sectionSection0"> </a>

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
3. Wählen Sie zwei Benutzer aus, die Sie zum Pool Skype for Business Server 2019 migrieren möchten. In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.
    
     ![Migrieren von Benutzern zu einem bestimmten Register Pool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.
    
5. Wählen Sie in der Dropdownliste den Skype for Business Server Pool 2019 aus.
    
6. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
    
     ![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Stellen Sie sicher, dass die Spalte **Registrierungspool** für die Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>So migrieren Sie mehrere Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell
<a name="sectionSection1"> </a>

1. Öffnen Sie die Skype for Business Server 2019 Management Shell. 
    
2. Geben Sie an der Befehlszeile Folgendes ein, und ersetzen Sie **User1** und **Benutzer2** durch bestimmte Benutzernamen, die Sie wechseln möchten, und ersetzen Sie **pool_FQDN** durch den Namen des Ziel Pools. In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan. 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![Beispiel für das PowerShell Get-CsUser-Cmdlet](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. Die **Registrierungspool**-Identität sollte jetzt auf den Pool zeigen, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden. Wiederholen Sie den Schritt, um zu überprüfen, ob **Benutzer2** verschoben wurde. 
    
     ![Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell aus
<a name="sectionSection2"> </a>

In diesem Beispiel wurden alle Benutzer an den Legacy Pool (pool01.contoso.net) zurückgegeben. Mithilfe der Skype for Business Server 2019-Verwaltungsshell werden alle Benutzer gleichzeitig in den Skype for Business Server 2019-Pool (pool02.contoso.net) verlagert.
  
1. Öffnen Sie die Skype for Business Server 2019 Management Shell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Führen **Sie Get-CsUser** für einen der Pilotbenutzer aus. 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. Die Identität des **Registrierungsstellen Pools** für jeden Benutzer verweist nun auf den Pool, den Sie im vorherigen Schritt als **pool_FQDN** angegeben haben. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde. 
    
5. Darüber hinaus können wir die Liste der Benutzer in der Skype for Business Server 2019-Systemsteuerung anzeigen und überprüfen, ob der Wert des Registrierungsstellen Pools nun auf den Skype for Business Server 2019-Pool zeigt.
    
     ![Skype for Business Server 2019-Benutzerliste der Systemsteuerung](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

