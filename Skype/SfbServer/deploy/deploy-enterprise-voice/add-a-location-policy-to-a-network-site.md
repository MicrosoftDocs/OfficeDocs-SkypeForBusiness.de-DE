---
title: Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerk Websites in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: ef6395b2239256abce82612b4863a667ce3b27ab
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768278"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in Skype for Business Server
 
Zuweisen von E9-1-1-Standortrichtlinien zu Netzwerk Websites in Skype for Business Server Enterprise-VoIP 
  
In den folgenden Beispielen wird gezeigt, wie Sie die in Erstellen von [Standortrichtlinien in Skype for Business Server](create-location-policies.md) definierte **Redmond** -Standortrichtlinie zu einer vorhandenen Netzwerk Website hinzufügen und wie Sie eine neue Netzwerk Website erstellen, die die Standortrichtlinie für **Redmond** verwendet.
  
Details zum Arbeiten mit Netzwerk Websites finden Sie in der Dokumentation zur lync Server-Verwaltungsshell für die folgenden Cmdlets:
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem vorhandenen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie die folgenden Cmdlets aus, um einen vorhandenen Netzwerkstandort zu ändern.
    
    Weisen Sie die Ortungsrichtlinie mit dem Tag **Redmond** einem vorhandenen Netzwerkstandort namens **Redmond** zu.
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>So weisen Sie eine Ortungsrichtlinie einem neuen Netzwerkstandort zu

1. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie das folgende Cmdlet aus, um einen neuen Netzwerkstandort zu erstellen.
    
    Erstellen Sie einen neuen Netzwerkstandort in der Netzwerkregion und weisen Sie diesem Standort die Ortungsrichtlinie mit dem Tag **Redmond** zu.
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


