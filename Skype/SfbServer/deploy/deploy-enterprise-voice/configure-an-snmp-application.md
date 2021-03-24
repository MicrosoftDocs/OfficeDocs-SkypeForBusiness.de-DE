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
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103631"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Konfigurieren einer SNMP-Anwendung in Skype for Business Server
 
Konfigurieren Sie eine SNMP-Anwendung für die Verwendung mit E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server enthält eine Standardwebdienstschnittstelle, mit der Sie den Standortinformationsdienst mit SNMP(Simple Network Management Protocol)-Anwendungen verbinden können, die MAC-Adressen mit Port- und Switchinformationen übereinstimmen. 
  
Wenn eine SNMP-Anwendung installiert ist und der Standortinformationsdienst in der Standortdatenbank keine Übereinstimmung findet, fragt der Standortinformationsdienst die Anwendung automatisch mithilfe der vom Client bereitgestellten MAC-Adresse ab. Der Standortinformationsdienst verwendet dann die port- und switch-Informationen, die von der SNMP-Anwendung zurückgegeben werden, um die Standortdatenbank erneut zu abfragen.
  
> [!NOTE]
> MAC-Adressen sind nicht auf Computern verfügbar, auf denen Windows 8. 
  
### <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)