---
title: Konfigurieren einer SNMP-Anwendung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Konfigurieren einer SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 2462c7af4473f8c29cf0e068ddc86b391d7e1df2
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233721"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a>Konfigurieren einer SNMP-Anwendung in Skype for Business Server
 
Konfigurieren einer SNMP-Anwendung für die Arbeit mit E9-1-1 in Skype for Business Server Enterprise-VoIP 
  
Skype for Business Server enthält eine standardmäßige Webdienstschnittstelle, mit der Sie den standortinformationsdienst mit SNMP-Anwendungen (Simple Network Management Protocol) verbinden können, die Mac-Adressen mit Port-und Switch-Informationen entsprechen. 
  
Wenn eine SNMP-Anwendung installiert ist und der standortinformationsdienst keine Übereinstimmung in der Standortdatenbank findet, fragt der standortinformationsdienst die Anwendung automatisch mit der vom Client angegebenen MAC-Adresse ab. Der standortinformationsdienst verwendet dann die von der SNMP-Anwendung zurückgegebenen Port-und Switch-Informationen, um die Standortdatenbank erneut abzufragen.
  
> [!NOTE]
> Mac-Adressen stehen auf Computern unter Windows 8 nicht zur Verfügung. 
  
### <a name="to-configure-the-snmp-application-url"></a>So konfigurieren Sie die URL für die SNMP-Anwendung

1.  Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für die SNMP-Anwendung zu konfigurieren. 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Satz-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

