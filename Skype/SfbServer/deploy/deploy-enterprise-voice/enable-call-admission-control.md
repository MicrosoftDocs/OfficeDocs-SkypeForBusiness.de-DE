---
title: Aktivieren Sie die anrufsteuerung in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: Aktivieren Sie die anrufsteuerung in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 75021b33c616fd4118a612b6e0d582459cd33b8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881908"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>Aktivieren Sie die anrufsteuerung in Skype für Business Server
 
Aktivieren Sie die anrufsteuerung in Skype für Business Server Enterprise-VoIP. 
  
Nachdem Sie die Ihre Netzwerkeinstellungen für die Bereitstellung der Anrufsteuerung konfiguriert haben, müssen Sie die Anrufsteuerung aktivieren, um die Bandbreitenrichtlinien anzuwenden.
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>So aktivieren Sie die anrufsteuerung mithilfe von Skype für Business Server-Verwaltungsshell

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das Cmdlet „Set-CsNetworkConfiguration“ aus, um die Anrufsteuerung in Ihrem Netzwerk zu aktivieren. Führen Sie beispielsweise den folgenden Befehl aus:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    Wenn Sie die Anrufsteuerung in Ihrem Netzwerk deaktivieren möchten, führen Sie folgenden Befehl aus:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>So aktivieren Sie die anrufsteuerung mithilfe von Skype Business Server-Systemsteuerung

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.
    
3. Klicken Sie auf die Navigationsschaltfläche **Global**.
    
4. Klicken Sie in der Liste auf **Global** und wählen Sie anschließend im Menü **Bearbeiten** die Option **Details anzeigen** aus.
    
5. Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**.
    
    > [!NOTE]
    > Wenn Sie die Anrufsteuerung innerhalb Ihrer Bereitstellung deaktivieren möchten, deaktivieren Sie dieses Kontrollkästchen. 
  
6. Klicken Sie auf **Commit ausführen**. 
    
## <a name="see-also"></a>Siehe auch

[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)