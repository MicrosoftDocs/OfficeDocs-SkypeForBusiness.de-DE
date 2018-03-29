---
title: Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a>Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business 2015
 
**Zusammenfassung:** Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.
  
Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Nutzern oder Nutzergruppen in einer Organisation getätigt werden dürfen. Weitere Informationen hierzu finden Sie unter [PSTN-Verwendungsdatensätzen](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie eine PSTN-Datensatz mithilfe von Skype Business Server-Systemsteuerung an

1. Öffnen von Skype Business Server-Systemsteuerung.
    
2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.
    
3. Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, den Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**. 
    
    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt. 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>So zeigen Sie PSTN-Verwendungsinformationen mithilfe von Skype für Business Server-Verwaltungsshell-Cmdlets an

- Zum Anzeigen von Informationen über alle PSTN-Nutzungen Geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:
    
  ```
  Get-CsPstnUsage
  ```

    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a>Siehe auch

#### 

[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business 2015](voice-policy-and-pstn-usage-records.md)

