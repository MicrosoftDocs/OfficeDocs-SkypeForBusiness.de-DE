---
title: Aktivieren der Anrufsteuerung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Aktivieren Sie die Anrufsteuerung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 16accf41f2c5abcef6f4de10ebd73b2d163adacb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585755"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Aktivieren der Anrufsteuerung in Skype for Business Server
 
Aktivieren Sie die Anrufsteuerung in Skype for Business Server Enterprise-VoIP. 
  
Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>So aktivieren Sie die Anrufsteuerung mithilfe Skype for Business Server Verwaltungsshell

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das Cmdlet "Set-CsNetworkConfiguration" aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>So aktivieren Sie die Anrufsteuerung mithilfe Skype for Business Server Systemsteuerung

1. Öffnen Sie Skype for Business Server Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Global**.
    
4. Klicken Sie in der Liste auf **Global**, und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen**.
    
5. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.
    
    > [!NOTE]
    > Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen. 
  
6. Klicken Sie auf **Commit**. 
    
## <a name="see-also"></a>Siehe auch

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)