---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
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
description: Sie können einen Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren. Im Beispiel unten in der Spalte registrierungsstellenpool ist pool01.contoso.net der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer zu Ihrem Skype for Business Server 2019-Pool mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell zu migrieren.
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752507"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Verlagern eines einzelnen Benutzers in den Pilot Pool

Sie können einen Benutzer aus Ihrem Legacy Pool mithilfe Skype for Business Server 2019-Systemsteuerung oder Skype for Business Server 2019-Verwaltungsshell in Ihren Skype for Business Server 2019-Pilot Pool migrieren. Im Beispiel unten in der Spalte **registrierungsstellenpool** ist **pool01.contoso.net** der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer zu Ihrem Skype for Business Server 2019-Pool mit Skype for Business Server 2019-Systemsteuerung und Skype for Business Server Verwaltungsshell zu migrieren. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>So migrieren Sie einen Benutzer mithilfe der Systemsteuerung Skype for Business Server 2019
  
1. Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.
    
2. Öffnen Sie **Skype for Business Server System**Steuerung.
    
3. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
4. Wählen Sie einen Benutzer aus, den Sie in den Skype for Business Server 2019-Pool umlegen möchten. In diesem Beispiel verschieben wir Sara Davis.
    
5. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.
    
6. Wählen Sie in der Dropdownliste den Skype for Business Server Pool 2019 aus.
    
7. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
  
8. Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>So migrieren Sie einen Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell

1. Öffnen Sie die Skype for Business Server Management-Shell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Geben Sie anschließend an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Die **RegistrarPool** -Identität verweist nun auf den Pool Skype for Business Server 2019. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde. 

    > [!NOTE]
    > Ausführliche Informationen zum **Get-CsUser** -Cmdlet finden Sie unter: **Get-Help Get-CsUser-detailed**
  

