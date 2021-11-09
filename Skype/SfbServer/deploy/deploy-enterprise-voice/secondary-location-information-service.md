---
title: Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren Sie eine sekundäre SlS-Datenbank (Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 7c41debb07ab8d1aece05b24f515f159f5be0dae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860802"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
 
Konfigurieren Sie eine sekundäre SlS-Datenbank (Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den Standortinformationsdienst auf eine SEKUNDÄRE Standortquelle (Secondary Location Source, SLS)-Datenbank zu verweisen. Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Standortinformationsdienst WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der Standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet er die Standortanforderung vom Client an die SLS-Datenbank. Wenn der Speicherort im SLS vorhanden ist, sendet der Standortinformationsdienst den Standort zurück an den Client. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine Datenbank für sekundären Speicherort

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** **"Alle Programme",** **"Skype for Business 2015"** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)