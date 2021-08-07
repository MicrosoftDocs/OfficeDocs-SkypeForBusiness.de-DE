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
description: 'Zusammenfassung: Erfahren Sie, wie Sie PSTN-Verwendungsdatensätze mithilfe der Skype for Business Server Systemsteuerung oder der Skype for Business Server-Verwaltungsshell anzeigen.'
ms.openlocfilehash: 4f36f263238c1c50299ff22756eaf7e6eed100141d15b3b7250a70a9a11adddf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305887"
---
# <a name="view-pstn-usage-records-in-skype-for-business"></a>Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business

**Zusammenfassung:** Erfahren Sie, wie Sie PSTN-Verwendungsdatensätze mithilfe der Skype for Business Server Systemsteuerung oder der Skype for Business Server-Verwaltungsshell anzeigen.

Ein PSTN-Verwendungseintrag (Public Switched Telephone Network) gibt eine Anrufklasse (z. B. interne, lokale oder Ferngespräche) an, die von verschiedenen Benutzern oder Benutzergruppen in einer Organisation getätigt werden kann. Ausführliche Informationen finden Sie unter [PSTN Usage Records](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-usage-records) in der Planungsdokumentation.

### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a>So zeigen Sie einen PSTN-Verwendungseintrag mithilfe Skype for Business Server Systemsteuerung an

1. Öffnen Sie Skype for Business Server Systemsteuerung.

2. Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.

3. Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.

    > [!NOTE]
    > Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.

### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a>So zeigen Sie PSTN-Verwendungsinformationen mithilfe Skype for Business Server-Verwaltungsshell-Cmdlets an

- Um Informationen zu allen PsTN-Verwendungen anzuzeigen, geben Sie den folgenden Befehl in die Skype for Business Server Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:

  ```powershell
  Get-CsPstnUsage
  ```

    Es werden etwa folgende Informationen zurückgegeben:

<pre>
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
</pre>

## <a name="see-also"></a>Siehe auch

[Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in Skype for Business](voice-policy-and-pstn-usage-records.md)