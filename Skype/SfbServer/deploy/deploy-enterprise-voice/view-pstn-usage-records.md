---
title: Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business
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
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Informationen zum Anzeigen von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell.'
ms.openlocfilehash: 6a447f7aeb9db0a7ca858cf58df10273c28b533b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109831"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business

**Zusammenfassung:** Informationen zum Anzeigen von PSTN-Verwendungsdatensätzen mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell.

Ein Verwendungsdatensatz für das Telefonnetz (Public Switched Telephone Network, PSTN) gibt eine Anrufklasse (z. B. intern, lokal oder fern) an, die von verschiedenen Benutzern oder Benutzergruppen in einer Organisation vorgenommen werden kann. Ausführliche Informationen finden Sie unter [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) in der Planungsdokumentation.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie einen PSTN-Verwendungsdatensatz mithilfe der Skype for Business Server-Systemsteuerung an

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.

3. Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>So zeigen Sie PSTN-Verwendungsinformationen mithilfe von Skype for Business Server Management Shell-Cmdlets an

- Geben Sie den folgenden Befehl in die Skype for Business Server Management Shell ein, um Informationen zu allen Ihren PSTN-Verwendungen eins zu sehen, und drücken Sie dann die EINGABETASTE:

  ```powershell
  Get-CsPstnUsage
  ```

    Es werden etwa folgende Informationen zurückgegeben:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern einer Sprachrichtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)