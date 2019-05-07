---
title: Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können den Typ des audio-Konferenzen und Endbenutzer-PSTN-Anrufe steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: acd75df192211465071940148e35bc7e269c7976
ms.sourcegitcommit: d1b14268efe334aa93a6889f25fcfe46e07d5daa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "33584223"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe

Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können. 

Ausgehende Anrufe für jeden Benutzer einzeln angewendet werden kann und ermöglichen die folgenden zwei Steuerelemente, um jede Art von ausgehenden Anrufen unabhängig voneinander zu beschränken. Standardmäßig werden beide Steuerelemente festgelegt, um internationaler und ausgehende Anrufe zu ermöglichen. 

|Steuerung|Beschreibung|Steueroptionen|
|:-----|:-----|:-----|
|Audio-Konferenzen PSTN-Anrufe|Legt eine Beschränkung auf den Typ des ausgehenden </br>Anrufe, die innerhalb zulässig sind </br>von einem Benutzer organisierte Besprechungen.|Internationalisierung und National (Standard)</br>Inlandsanruf</br>Keine|
|Endbenutzer-PSTN-Anrufe|Legt eine Beschränkung auf den Typ von Anrufen </br>können von einem Benutzer vorgenommen werden.|Internationalisierung und National (Standard)</br>Inlandsanruf</br>Keine|

   > [!NOTE]
   > Ein Aufruf gilt nationalen, wenn die Rufnummer in demselben Land ist, auf dem Office 365 für den Organisator der Besprechung (im Fall von Audiokonferenzen) oder die Endbenutzer (im Fall von Endbenutzer PSTN-Anrufe) eingerichtet wurde. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Einschränken von Audiokonferenzen ausgehende Anrufe 

![Teams-Logo-30x30.png](../images/teams-logo-30x30.png) **mithilfe der Verwaltungskonsole von Microsoft-Teams**

1. Im linken Navigationsbereich klicken Sie auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie am oberen Rand der Seite auf **Bearbeiten**.

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.

4. Wählen Sie unter **Dial-Out - Berechtigung von Besprechungen**die gewünschte Option der Dial-Out-Einschränkung.

5. Klicken Sie auf **Speichern**. 

![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**

1.  Wechseln Sie in der **Skype für Business Administrationscenter**, im linken Navigationsbereich zu **Audiokonferenzen** > **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer.

2.  Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.

3.  Wählen Sie unter **Dial-Outs von Besprechungen dieses Benutzers Einschränkungen**die gewünschte Option der Dial-Out-Einschränkung.

    ![Die Einschränkungen auf DFÜ-Outs-Optionen](../images/restrictions-to-dial-outs.png)

5. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Verwenden von PowerShell**

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
