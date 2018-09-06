---
title: Anzeigen von PSTN-Verwendungseinträge in Skype für Unternehmen
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: 7e0cf091c1fd6afbfde6fc4a35ba049e75deaf4f
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250266"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Anzeigen von PSTN-Verwendungseinträge in Skype für Unternehmen

**Zusammenfassung:** Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.

Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Nutzern oder Nutzergruppen in einer Organisation getätigt werden dürfen. Weitere Informationen hierzu finden Sie unter [PSTN-Verwendungsdatensätzen](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.

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

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Unternehmen](voice-policy-and-pstn-usage-records.md)

