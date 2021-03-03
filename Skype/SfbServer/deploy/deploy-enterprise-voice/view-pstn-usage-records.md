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
ms.openlocfilehash: abf9f3ec9ce1e2801de2c6017d12fd64df0c8954
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830535"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie mithilfe der Skype for Business Server-Systemsteuerung oder der Skype for Business Server-Verwaltungsshell PSTN-Verwendungsdatensätze anzeigen.

Ein Verwendungsdatensatz für das Telefonnetz (Public Switched Telephone Network, PSTN) gibt eine Anrufklasse an (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche), die von verschiedenen Benutzern oder Benutzergruppen in einer Organisation vorgenommen werden können. Ausführliche Informationen finden Sie unter [PSTN Usage Records](https://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie einen PstN-Verwendungsdatensatz mithilfe der Skype for Business Server-Systemsteuerung an

1. Öffnen Sie die Skype for Business Server-Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.

3. Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>So zeigen Sie Mithilfe von Skype for Business Server -Verwaltungsshell-Cmdlets Informationen zur PstN-Verwendung an

- Geben Sie den folgenden Befehl in der Skype for Business Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Ihren PSTN-Verwendungen ein:

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

