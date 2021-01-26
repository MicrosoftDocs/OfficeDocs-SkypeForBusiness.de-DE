---
title: Konfigurieren einer SNMP-Anwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren Sie eine SNMP-Anwendung für die Verwendung mit E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804155"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Konfigurieren einer SNMP-Anwendung in Skype for Business Server
 
Konfigurieren Sie eine SNMP-Anwendung für die Verwendung mit E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server enthält eine standardmäßige Webdienstschnittstelle, mit der Sie den Standortinformationsdienst mit Anwendungen des Simple Network Management Protocol (SNMP) verbinden können, die mit Port- und Switchinformationen übereinstimmen. 
  
Wenn eine SNMP-Anwendung installiert ist und der Standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der Standortinformationsdienst die Anwendung automatisch mithilfe der vom Client bereitgestellten MAC-Adresse ab. Der Standortinformationsdienst verwendet dann den port- und switch-Informationen, die von der SNMP-Anwendung zurückgegeben werden, um die Standortdatenbank erneut abfragen.
  
> [!NOTE]
> Auf Computern, auf denen ein Client ausgeführt wird, sind keine Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

