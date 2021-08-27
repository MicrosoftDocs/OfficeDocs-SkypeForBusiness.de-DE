---
title: Verschieben eines einzelnen Benutzers in den Pilotpool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Sie können einen Benutzer aus Ihrem Legacypool in Den Skype for Business Server 2019-Pilotpool verschieben, indem Sie Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell verwenden. Im folgenden Beispiel in der Spalte "Registrierungsstellenpool" ist pool01.contoso.net der Legacypool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell in ihren Skype for Business Server 2019-Pool zu verschieben.
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596159"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Verschieben eines einzelnen Benutzers in den Pilotpool

Sie können einen Benutzer aus Ihrem Legacypool in Den Skype for Business Server 2019-Pilotpool verschieben, indem Sie Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell verwenden. Im folgenden Beispiel in der Spalte **"Registrierungsstellenpool"** ist **pool01.contoso.net** der Legacypool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell in ihren Skype for Business Server 2019-Pool zu verschieben. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung
  
1. Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.
    
2. Öffnen **Sie Skype for Business Server Systemsteuerung.**
    
3. Klicken Sie auf **"Benutzer",** auf **"Suchen"** und dann auf **"Suchen".**
    
4. Wählen Sie einen Benutzer aus, den Sie in den Skype for Business Server 2019-Pool verschieben möchten. In diesem Beispiel verschieben wir Sara Davis.
    
5. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.
    
6. Wählen Sie in der Dropdownliste den Pool Skype for Business Server 2019 aus.
    
7. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
  
8. Stellen Sie sicher, dass die Spalte **"Registrierungsstellenpool"** für den Benutzer nun den Pool Skype for Business Server 2019 enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Geben Sie anschließend an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Die **RegistrarPool-Identität** verweist jetzt auf den Skype for Business Server 2019-Pool. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde. 

    > [!NOTE]
    > Ausführliche Informationen zum **Cmdlet "Get-CsUser"** finden Sie unter:Get-Help **Get-CsUser -Detailed**
  

