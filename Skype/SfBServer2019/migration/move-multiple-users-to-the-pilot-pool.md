---
title: Verschieben Sie mehrerer Benutzer in den pilotpool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können mehrere Benutzer in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell aus Ihrem legacy-Pool verschieben.
ms.openlocfilehash: e96ef658f566f0e069f4db6e4f2f08e0410ea260
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028656"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Verschieben Sie mehrerer Benutzer in den pilotpool

Sie können mehrere Benutzer in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell aus Ihrem legacy-Pool verschieben.

 **In diesem Artikel**
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Systemsteuerung](#sectionSection0)
  
[So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Verwaltungsshell](#sectionSection1)
  
[So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype für Business Server 2019-Verwaltungsshell](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Systemsteuerung
<a name="sectionSection0"> </a>

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
3. Wählen Sie zwei Benutzer, die Sie in der Skype für Business Server 2019 Pool verschieben möchten. In diesem Beispiel wird es Benutzern Chen Yang und Claus Hansen verschoben.
    
     ![Migrieren von Benutzern zu bestimmten Register-pool](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. Wählen Sie im Menü **Aktion** **ausgewählte Benutzer in Pool verschieben**.
    
5. Wählen Sie aus der Dropdownliste die Skype für Business Server 2019 Pool aus.
    
6. Klicken Sie auf **Aktion**, und klicken Sie dann auf **ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
    
     ![Verschieben von Benutzern im Dialogfeld Registrar-Pool Ziel](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** für die Benutzer enthält nun die Skype für Business Server 2019 Pool, die angibt, dass die Benutzer erfolgreich verschoben wurden. 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie mehrere Benutzer mithilfe der Skype für Business Server 2019-Verwaltungsshell
<a name="sectionSection1"> </a>

1. Öffnen Sie die Skype für Business Server 2019-Verwaltungsshell. 
    
2.  In der Befehlszeile Folgendes ein, und Ersetzen Sie **User1** und **User2** durch die betreffenden Benutzernamen, den, die Sie verschieben möchten, und Ersetzen Sie **Pool_FQDN** durch den Namen des zielpools. In diesem Beispiel wird es Benutzern Hao Chen und Katie Jordanien verschoben. 
    
  ```
  Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
  ```

     ![Beispiel für PowerShell Get-CsUser-cmdlet](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. Geben Sie an der Befehlszeile Folgendes ein: 
    
  ```
  Get-CsUser -Identity "User1"
  ```

4. Die Identität des **Registrar-Pools** sollten nun auf den Pool verweisen, den Sie als **Pool_FQDN** im vorherigen Schritt angegeben haben. Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. Wiederholen Sie Schritt zu überprüfen, ob **Benutzer2** verschoben wurde. 
    
     ![Ausgabe von PowerShell Get-UsUser-Identity-Cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie alle Benutzer gleichzeitig mithilfe der Skype für Business Server 2019-Verwaltungsshell
<a name="sectionSection2"> </a>

In diesem Beispiel wurden alle Benutzer auf den Pool der Vorgängerversion (pool01.contoso.net) zurückgegeben. Die Skype für Business Server 2019-Verwaltungsshell verwenden, werden wir alle Benutzer gleichzeitig in die Skype für Business Server 2019 Pool (pool02.contoso.net) verschoben.
  
1. Öffnen Sie die Skype für Business Server 2019-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
  ```
  Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
  ```

     ![PowerShell-Cmdlets und die Ergebnisse in der-Verwaltungsshell](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. Führen Sie **Get-CsUser** für einen der Pilotbenutzer aus. 
    
  ```
  Get-CsUser -Identity "Hao Chen"
  ```

4. Die **Registrar-Pool** -Identität für jeden Benutzer zeigt jetzt auf den Pool, den Sie als **Pool_FQDN** im vorherigen Schritt angegeben haben. Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. 
    
5. Darüber hinaus können wir zeigt eine Liste von Benutzern in der Skype Business Server 2019-Systemsteuerung, und stellen Sie sicher, dass der Wert des Registrierungspools jetzt auf das Skype für Business Server 2019 Pool verweist.
    
     ![Skype für Benutzerliste Business Server 2019-Systemsteuerung](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

