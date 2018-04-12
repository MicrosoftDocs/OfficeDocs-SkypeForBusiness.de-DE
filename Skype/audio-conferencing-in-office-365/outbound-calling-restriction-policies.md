---
title: Ausgehende aufrufende einschränkungsrichtlinien für Audiokonferenzen und Benutzer PSTN-Anrufe
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 2/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Administratoren können den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: ae6039f967b95ebd0c5934105f4e6fb044e431b4
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2018
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Ausgehende aufrufende einschränkungsrichtlinien für Audiokonferenzen und Benutzer PSTN-Anrufe

Als Administrator können Sie ausgehende Anrufe Steuerelemente verwenden, um den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe zu beschränken, die von Benutzern in Ihrer Organisation hergestellt werden kann. 

Ausgehende Anrufe für jeden Benutzer einzeln angewendet werden kann und ermöglichen die folgenden zwei Steuerelemente, um jede Art von ausgehenden Anrufen unabhängig voneinander zu beschränken. Standardmäßig werden beide Steuerelemente festgelegt, um internationaler und ausgehende Anrufe zu ermöglichen. 

|Steuerelement|Beschreibung|Steueroptionen|
|:-----|:-----|:-----|
|Audio-Konferenzen PSTN-Anrufe|Legt eine Beschränkung auf den Typ des ausgehenden </br>Anrufe, die innerhalb zulässig sind </br>von einem Benutzer organisierte Besprechungen.|Internationalisierung und National (Standard)</br>Inlandsanruf</br>Keine|
|Endbenutzer-PSTN-Anrufe|Legt eine Beschränkung auf den Typ von Anrufen </br>können von einem Benutzer vorgenommen werden.|Internationalisierung und National (Standard)</br>Inlandsanruf</br>Keine|

   > [!NOTE]
   > Ein Aufruf ist bestimmt nationalen, wenn die gewählte Rufnummer in demselben Land als das Land ist, die in Office 365 für den Organisator der Besprechung (im Fall von Audiokonferenzen) oder die Endbenutzer (im Fall von Endbenutzer PSTN-Anrufe) festgelegt wurde. 


## <a name="restrict-audio-conferencing-outbound-calls-using-the-skype-for-business-admin-center"></a>Einschränken von Audiokonferenzen ausgehende Anrufe mithilfe der Skype für Business Administrationscenter 


1.  Navigieren Sie zum **Office 365 Admin Center** > **Skype for Business**.
2.  Wechseln Sie in der Skype für Business-Verwaltungskonsole im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.
3.  In the Action pane, click **Edit**.
4.  Wählen Sie unter **Dial-Outs von Besprechungen dieses Benutzers Einschränkungen**die gewünschte Option der Dial-Out-Einschränkung.

    ![Die Einschränkungen auf DFÜ-Outs-Optionen](../images/restrictions-to-dial-outs.png)

5. Klicken Sie auf **Speichern**.

## <a name="restrict-audio-conferencing-and-end-user-outbound-calls-using-powershell"></a>Einschränken von Konferenz- und Endbenutzer ausgehende Audioanrufe von PowerShell

Ausgehende Anrufe Einschränkungen werden durch eine einzelne Richtlinie aufgerufen OnlineDialOutPolicy über ein Attribut Einschränkung für jede gesteuert. Die Richtlinie kann nicht angepasst werden, vielmehr vordefinierte Policy-Instanzen für jede Kombination der Einstellungen vorhanden sind. 

Das Cmdlet Get-CSOnlineDialOutPolicy können Sie zeigen Sie die ausgehenden aufrufenden Richtlinien und weisen Sie diese Benutzer mit dem Cmdlet Grant-CSDialOutPolicy. (Beachten Sie, dass das Cmdlet Grant das Wort "Online" enthalten, nicht wie das Get-Cmdlet.) 

Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.

|||
|:-----|:-----|
|Identität = 'Tag: DialoutCPCandPSTNInternational'    |    Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann auch ausgehende Anrufe bei Nummern internationaler und tätigen.    |
|Identität = 'Tag: DialoutCPCDomesticPSTNInternational'  |    Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer ausgehende Anrufe bei Nummern internationaler und machen kann.    |
|    Identität = 'Tag: DialoutCPCDisabledPSTNInternational'    |    Benutzer in der Konferenz ist nicht möglich alle Zugriffsnummern stellen. Diese Benutzer kann ausgehende Anrufe bei Nummern internationaler und tätigen.    |
|    Identität = 'Tag: DialoutCPCInternationalPSTNDomestic'    |    Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummer nationalen tätigen.    |
|    Identität = 'Tag: DialoutCPCInternationalPSTNDisabled'    |    Benutzer in der Konferenz kann eine ausgehende Verbindung internationaler und Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.    |
|    Identität = 'Tag: DialoutCPCandPSTNDomestic'    |    Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.    |
|    Identität = 'Tag: DialoutCPCDomesticPSTNDisabled'    |    Benutzer in der Konferenz kann nur eine ausgehende Verbindung nationalen Zahlen kann, und dieser Benutzer ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen.    |
|    Identität = 'Tag: DialoutCPCDisabledPSTNDomestic'    |    Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann nur ausgehenden Anrufe an PSTN-Nummern nationalen tätigen.    |
|    Identität = 'Tag: DialoutCPCandPSTNDisabled'    |    Benutzer in der Konferenz kann keine Client-stellen, und dieser Benutzer kann keine ausgehende Anrufe an PSTN-Nummer neben Notfall Zahlen tätigen.    |
