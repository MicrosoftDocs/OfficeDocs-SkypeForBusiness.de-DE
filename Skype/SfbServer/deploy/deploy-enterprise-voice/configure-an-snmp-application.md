---
title: Konfigurieren einer SNMP-Anwendung in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren Sie eine SNMP-Anwendung zur Arbeit mit E9-1-1 in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 9c325777b43c455016657caf4e15316a07282b52
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992435"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Konfigurieren einer SNMP-Anwendung in Skype für Business Server
 
Konfigurieren Sie eine SNMP-Anwendung zur Arbeit mit E9-1-1 in Skype für Business Server Enterprise-VoIP. 
  
Skype für Business Server umfasst eine standardmäßige webdienstschnittselle, die Sie mit dem Dienst Standortinformationen für Simple Network Management Protocol (SNMP) Clientanwendungen zu hergestellt, die Abgleich von MAC-Adressen mit Port- und Switchinformationen verwenden können. 
  
Wenn eine SNMP-Anwendung installiert ist und der Standortinformationen Dienst nicht in der Standortdatenbank Übereinstimmung gefunden, fragt der standortinformationsdienst die Anwendung automatisch mithilfe der MAC-Adresse vom Client. Der Standortinformationen-Dienst verwendet klicken Sie dann die Port- und Switch-Informationen von der SNMP-Anwendung zurückgegeben, um der Standortdatenbank erneut abzufragen.
  
> [!NOTE]
> MAC-Adressen sind nicht auf Computern unter Windows 8 verfügbar. 
  
### <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Siehe auch

["Set-cswebserviceconfiguration"](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

