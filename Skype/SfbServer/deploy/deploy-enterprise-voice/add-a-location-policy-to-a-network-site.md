---
title: Hinzufügen einer Standortrichtlinie zu einem Netzwerkstandort in Skype for Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerkstandorten in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: ae35958d9ff95e32f129d3992d52145e3bef51b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848048"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Hinzufügen einer Standortrichtlinie zu einem Netzwerkstandort in Skype for Business Server
 
Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerkstandorten in Skype for Business Server Enterprise-VoIP. 
  
Die folgenden Beispiele zeigen, wie Sie die in ["Standortrichtlinien erstellen" in Skype for Business Server](create-location-policies.md) definierte **Standortrichtlinie "Redmond"** zu einem vorhandenen Netzwerkstandort hinzufügen und wie Sie einen neuen Netzwerkstandort erstellen, der die **Standortrichtlinie "Redmond"** verwendet.
  
Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell für die folgenden Cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.
    
    Weisen Sie die Standortrichtlinie mit dem Tag **"Redmond"** einem vorhandenen Netzwerkstandort mit dem Namen **"Redmond"** zu.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
2. Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.
    
    Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion, und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


