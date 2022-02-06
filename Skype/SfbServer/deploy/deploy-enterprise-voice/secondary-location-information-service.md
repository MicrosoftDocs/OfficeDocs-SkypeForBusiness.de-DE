---
title: Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: 'Konfigurieren Einer sekundären Standortquelldatenbank (SECONDARY Location Source, SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP.'
---

# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
 
Konfigurieren Einer sekundären Standortquelldatenbank (SECONDARY Location Source, SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server stellt eine Webdienstschnittstelle bereit, die Sie verwenden können, um den Standortinformationsdienst auf eine SEKUNDÄRE Standortquelle (Secondary Location Source, SLS)-Datenbank zu verweisen. Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Standortinformationsdienst WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der Standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet er die Standortanforderung vom Client an die SLS-Datenbank. Wenn der Speicherort im SLS vorhanden ist, sendet der Standortinformationsdienst den Standort zurück an den Client. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine Datenbank für sekundären Speicherort

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start**", auf **"Alle Programme**", auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)