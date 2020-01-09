---
title: Verschieben eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Sie können einen Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel ist in der Spalte "Registrar Pool" pool01.contoso.net der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Führen Sie die folgenden Verfahren aus, um einen Benutzer in den Skype for Business Server 2019-Pool mit der Skype for Business Server 2019-Systemsteuerung und der Skype for Business Server-Verwaltungsshell zu verschieben.
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988960"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>Verschieben eines einzelnen Benutzers in den Pilot Pool

Sie können einen Benutzer aus Ihrem Legacy Pool in Ihren Skype for Business Server 2019-Pilot Pool mit der Skype for Business Server 2019-Systemsteuerung oder der Skype for Business Server 2019-Verwaltungsshell verschieben. Im folgenden Beispiel ist in der Spalte " **Registrar Pool** " **pool01.contoso.net** der Legacy Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Führen Sie die folgenden Verfahren aus, um einen Benutzer in den Skype for Business Server 2019-Pool mit der Skype for Business Server 2019-Systemsteuerung und der Skype for Business Server-Verwaltungsshell zu verschieben. 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Systemsteuerung
  
1. Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.
    
2. Öffnen Sie die **Skype for Business Server-System**Steuerung.
    
3. Klicken Sie auf **Benutzer**, klicken Sie auf **Suchen**, und klicken Sie dann auf **Suchen**.
    
4. Wählen Sie einen Benutzer aus, den Sie in den Skype for Business Server 2019-Pool verschieben möchten. In diesem Beispiel verschieben wir den Benutzer Sara Davis.
    
5. Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.
    
6. Wählen Sie in der Dropdownliste den Skype for Business Server 2019-Pool aus.
    
7. Klicken Sie auf **Aktion**und dann auf **ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
  
8. Überprüfen Sie, ob die Spalte des **registrierungspools** für den Benutzer jetzt den Skype for Business Server 2019-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde. 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>So verschieben Sie einen Benutzer mithilfe der Skype for Business Server 2019-Verwaltungsshell

1. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
2. Geben Sie an der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. Geben Sie als nächstes in der Befehlszeile Folgendes ein: 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. Die **RegistrarPool** -Identität verweist nun auf den Skype for Business Server 2019-Pool. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. 

    > [!NOTE]
    > Details zum Cmdlet " **Get-CsUser** " finden Sie unter **Get-Help Get-CsUser-detailed** .
  

