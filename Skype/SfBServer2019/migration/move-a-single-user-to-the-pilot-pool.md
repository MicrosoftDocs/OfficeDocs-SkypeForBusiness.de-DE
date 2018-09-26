---
title: Verschieben eines einzelnen Benutzers in den pilotpool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können einen Benutzer aus Ihrem vorversionspool in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel, in der Spalte Registrierungspool pool01.contoso.net Pool der Vorgängerversion ist, und alle sechs dieser Benutzer mit diesem Pool verbunden sind. Verwenden Sie die folgenden Verfahren, um einen Benutzer in Ihrer Skype für mithilfe von Skype für Business Server 2019-Systemsteuerung und Skype für Business Server-Verwaltungsshell Business Server 2019 Pool verschieben.
ms.openlocfilehash: f04cccf29fd88bf1da95f4d67f6e47c51b878717
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028810"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Verschieben eines einzelnen Benutzers in den pilotpool

Sie können einen Benutzer aus Ihrem vorversionspool in Ihrer Skype für Business Server 2019 pilot Pool mit Skype für Business Server 2019-Systemsteuerung oder Skype für Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel, in der Spalte **registrierungspool** **pool01.contoso.net** Pool der Vorgängerversion ist, und alle sechs dieser Benutzer mit diesem Pool verbunden sind. Verwenden Sie die folgenden Verfahren, um einen Benutzer in Ihrer Skype für mithilfe von Skype für Business Server 2019-Systemsteuerung und Skype für Business Server-Verwaltungsshell Business Server 2019 Pool verschieben. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>Zum Verschieben eines Benutzers mithilfe der Skype für Business Server 2019-Systemsteuerung
  
1. Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.
    
2. **Skype für Business Server-Systemsteuerung**zu öffnen.
    
3. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
4. Wählen Sie einen Benutzer, den Sie in der Skype für Business Server 2019 Pool verschieben möchten. In diesem Beispiel wird es Benutzer Sara Davis verschoben.
    
5. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.
    
6. Wählen Sie aus der Dropdownliste die Skype für Business Server 2019 Pool aus.
    
7. Klicken Sie auf **Aktion**, und klicken Sie dann auf **ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
  
8. Stellen Sie sicher, dass die Spalte **Registrierungsstellenpool** für den Benutzer enthält nun die Skype für Business Server 2019 Pool, die angibt, dass der Benutzer erfolgreich verschoben wurde. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>Zum Verschieben eines Benutzers mithilfe der Skype für Business Server 2019-Verwaltungsshell

1. Öffnen Sie die Skype für Business Server-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
  ```
  Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
  ```

3. Geben Sie im nächsten Schritt in der Befehlszeile Folgendes ein: 
    
  ```
  Get-CsUser -Identity "David Pelton"
  ```

4. Die Identität des **RegistrarPool** zeigt jetzt auf das Skype für Business Server 2019 Pool. Das Vorhandensein von diese Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. 

    > [!NOTE]
    > Weitere Informationen zum **Get-CsUser** -Cmdlet ausführen: **Get-Help Get-CsUser-Detailed**
  

