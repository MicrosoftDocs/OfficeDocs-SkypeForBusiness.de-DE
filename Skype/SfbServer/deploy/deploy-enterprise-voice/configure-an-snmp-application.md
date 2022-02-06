---
title: Konfigurieren einer SNMP-Anwendung in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren Sie eine SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP.
---

# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Konfigurieren einer SNMP-Anwendung in Skype for Business Server
 
Konfigurieren Sie eine SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server enthält eine standardmäßige Webdienstschnittstelle, mit der Sie den Standortinformationsdienst mit SNMP-Anwendungen (Simple Network Management Protocol) verbinden können, die MAC-Adressen mit Port- und Switchinformationen abgleichen. 
  
Wenn eine SNMP-Anwendung installiert ist und der Standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der Standortinformationsdienst die Anwendung automatisch mithilfe der vom Client bereitgestellten MAC-Adresse ab. Der Standortinformationsdienst verwendet dann die port- und switch-Informationen, die von der SNMP-Anwendung zurückgegeben werden, um die Standortdatenbank erneut abfragt.
  
> [!NOTE]
> MAC-Adressen sind auf Computern, auf denen Windows 8 ausgeführt wird, nicht verfügbar. 
  
### <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)