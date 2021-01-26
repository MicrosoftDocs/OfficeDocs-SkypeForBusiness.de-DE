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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Konfigurieren Sie eine sekundäre Standortquellendatenbank (SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830645"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a>Konfigurieren eines sekundären Standortinformationsdiensts in Skype for Business Server
 
Konfigurieren Sie eine sekundäre Standortquellendatenbank (SLS) für E9-1-1 in Skype for Business Server Enterprise-VoIP. 
  
Skype for Business Server bietet eine Webdienstschnittstelle, mit der Sie den Standortinformationsdienst auf eine sekundäre Standortquellendatenbank (Secondary Location Source, SLS) verweisen können. Die Webdienstschnittstelle, die eine Verbindung mit der DATENBANK sls herstellt, muss dem Standortinformationsdienst WSDL entsprechen. Wenn sowohl eine Standortdatenbank als auch eine sekundäre Standortdatenbank konfiguriert sind, fragt der Standortinformationsdienst zuerst die Standortdatenbank ab und sendet die Standortanforderung vom Client an die SLS-Datenbank, wenn keine Übereinstimmung gefunden wird. Wenn der Standort im SLS vorhanden ist, sendet der Standortinformationsdienst den Standort zurück an den Client. 
  
### <a name="to-configure-a-secondary-location-database"></a>So konfigurieren Sie eine sekundäre Standortdatenbank

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
2. Führen Sie das folgende Cmdlet aus, um die URL für den Speicherort der SLS-Datenbank zu konfigurieren. 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a>Siehe auch

[Set-CsWebServiceConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

