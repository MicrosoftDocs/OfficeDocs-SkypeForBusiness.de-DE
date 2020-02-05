---
title: Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die PSTN-Nutzungsdatensätze mithilfe des Skype for Business Server-Control Panels oder der Skype for Business Server-Verwaltungsshell anzeigen können.'
ms.openlocfilehash: 1f6cbd5bb013cd57f9304c3b0eb0c64ac7dabcff
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766918"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Anzeigen von PSTN-Nutzungsdaten Sätzen in Skype for Business

**Zusammenfassung:** Informationen zum Anzeigen von PSTN-Nutzungsdaten Sätzen mithilfe des Skype for Business Server-Control Panels oder der Skype for Business Server-Verwaltungsshell.

Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Nutzern oder Nutzergruppen in einer Organisation getätigt werden dürfen. Ausführliche Informationen finden Sie unter [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie einen PSTN-Verwendungs Eintrag mithilfe der Skype for Business Server-Systemsteuerung an

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.

3. Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, den Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>So zeigen Sie die Informationen zur PSTN-Nutzung mithilfe der Cmdlets der Skype for Business Server-Verwaltungsshell an

- Wenn Sie Informationen zu allen PSTN-Nutzungen anzeigen möchten, geben Sie in der Skype for Business Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie dann die EINGABETASTE:

  ```powershell
  Get-CsPstnUsage
  ```

    Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)

