---
title: Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 03de4369b8473142e7a76e3698bb9fe7f129d546
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server-2015"></a>Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server 2015
 
Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP. 
  
Skype für Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den standortinformationsdienst mit einer sekundären Standort Quelle (SLS)-Datenbank zu verweisen. Web-Service-Schnittstelle, die mit der SLS-Datenbank verbindet muss Standortinformationen Service-WSDL-Datei entsprechen. Wenn eine Standortdatenbank und die sekundäre Standortdatenbank konfiguriert sind, der standortinformationsdienst zuerst fragt die Standortdatenbank und keine Übereinstimmung gefunden wird, sendet die Anforderung vom Client an der SLS-Datenbank. Wenn Sie der Speicherort der SLS vorhanden ist, sendet der Standortinformationen-Dienst klicken Sie dann den Speicherort an den Client zurück. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine sekundäre Standortdatenbank

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

#### 

["Set-cswebserviceconfiguration"](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

