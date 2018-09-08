---
title: Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: e811062bbec9e3b6caf368e010b751e496c1b305
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885122"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren einer sekundären standortinformationsdienst in Skype für Business Server
 
Konfigurieren einer sekundären Standortdatenbank Quelle (SLS) für E9-1-1 in Skype für Business Server Enterprise-VoIP. 
  
Skype für Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den standortinformationsdienst mit einer sekundären Standort Quelle (SLS)-Datenbank zu verweisen. Web-Service-Schnittstelle, die mit der SLS-Datenbank verbindet muss Standortinformationen Service-WSDL-Datei entsprechen. Wenn eine Standortdatenbank und die sekundäre Standortdatenbank konfiguriert sind, der standortinformationsdienst zuerst fragt die Standortdatenbank und keine Übereinstimmung gefunden wird, sendet die Anforderung vom Client an der SLS-Datenbank. Wenn Sie der Speicherort der SLS vorhanden ist, sendet der Standortinformationen-Dienst klicken Sie dann den Speicherort an den Client zurück. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine sekundäre Standortdatenbank

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

["Set-cswebserviceconfiguration"](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

