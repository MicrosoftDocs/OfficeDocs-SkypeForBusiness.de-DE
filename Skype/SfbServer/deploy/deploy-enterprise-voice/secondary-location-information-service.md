---
title: Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren Sie eine SLS-Datenbank (Secondary Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 1743a4c5f49fcc01fe2f0878c596e0d1bb530621
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001996"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren eines sekundären Standort Informationsdiensts in Skype for Business Server
 
Konfigurieren Sie eine SLS-Datenbank (Secondary Location Source) für E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server bietet eine Webdienstschnittstelle, die Sie verwenden können, um den standortinformationsdienst auf eine SLS-Datenbank (Secondary Location Source) zu verweisen. Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Location Information Service-WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet die standortanforderung vom Client an die SLS-Datenbank. Wenn der Standort im SLS vorhanden ist, sendet der standortinformationsdienst den Standort dann zurück an den Client. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine sekundäre Standortdatenbank

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Satz-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

