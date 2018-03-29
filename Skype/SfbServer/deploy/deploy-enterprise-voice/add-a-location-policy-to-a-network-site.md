---
title: Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Skype for Business Server 2015
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Zuweisen von Richtlinien für E9-1-1-Speicherort zu Netzwerkstandorten in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a>Hinzufügen einer Ortungsrichtlinie zu einem Netzwerkstandort in Skype for Business Server 2015
 
Zuweisen von Richtlinien für E9-1-1-Speicherort zu Netzwerkstandorten in Skype für Business Server Enterprise-VoIP. 
  
Die folgenden Beispiele zeigen, wie in [Erstellen von Standortrichtlinien in Skype für Business Server 2015](create-location-policies.md) zu einem vorhandenen Netzwerkstandort definiert **Redmond** Standortrichtlinie hinzufügen und wie Sie einen neuen Netzwerkstandort zu erstellen, der den Standort **Redmond** verwendet Richtlinie.
  
Ausführliche Informationen zum Arbeiten mit Netzwerkstandorten finden Sie in der Dokumentation zu Lync Server-Verwaltungsshell für die folgenden Cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.
    
    Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.
    
    Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


