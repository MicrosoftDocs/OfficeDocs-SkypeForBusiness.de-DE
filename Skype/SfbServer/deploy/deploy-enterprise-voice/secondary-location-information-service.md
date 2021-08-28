---
title: Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Konfigurieren Sie eine sekundäre Standortquelldatenbank (SECONDARY Location Source, SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b2db211ec9c1bc7d2459ad2dbc8cada4b87afa6e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618111"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
 
Konfigurieren Sie eine sekundäre Standortquelldatenbank (SECONDARY Location Source, SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server stellt eine Webdienstschnittstelle bereit, die Sie verwenden können, um den Standortinformationsdienst auf eine sekundäre SLS-Datenbank (Location Source) zu verweisen. Die Webdienstschnittstelle, die eine Verbindung mit der SLS-Datenbank herstellt, muss dem Standortinformationsdienst WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der Standortinformationsdienst zuerst die Standortdatenbank ab, und wenn keine Übereinstimmung gefunden wird, sendet er die Standortanforderung vom Client an die SLS-Datenbank. Wenn der Speicherort im SLS vorhanden ist, sendet der Standortinformationsdienst den Standort zurück an den Client. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine Datenbank für sekundären Speicherort

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)