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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Administratoren können den Typ von Audiokonferenz-und Endbenutzer-PSTN-anrufen steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: 20122d2bc258b8ac6040a103d62e20f81e46a364
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "37573331"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe

Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können. 

Steuerelemente für ausgehende Anrufe können auf Benutzerebene angewendet werden und bieten die folgenden zwei Steuerelemente, um die einzelnen ausgehenden Anrufe unabhängig voneinander zu beschränken. Standardmäßig sind beide Steuerelemente so eingestellt, dass Auslands-und Inlandsanrufe zugelassen werden. 

|Steuerelement|Beschreibung|Steuerelementoptionen|
|:-----|:-----|:-----|
|PSTN-Anrufe für Audiokonferenzen|Schränkt den ausgehenden Typ ein </br>Anrufe, die innerhalb von zulässig sind </br>Besprechungen, die von einem Benutzer organisiert werden.|International und Domestic (Standard)</br>Inlandsanruf</br>Keine|
|PSTN-Anrufe für Endbenutzer|Schränkt die Art der Anrufe ein </br>, die von einem Benutzer vorgenommen werden können.|International und Domestic (Standard)</br>Inlandsanruf</br>Keine|

   > [!NOTE]
   > Ein Anruf gilt als "Domestic", wenn sich die gewählte Rufnummer im selben Land befindet, in dem Office 365 für den Organisator der Besprechung eingerichtet wurde (im Fall von Audiokonferenzen) oder der Endbenutzer (im Fall von PSTN-anrufen des Endbenutzers). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Einschränken von ausgehenden Anrufen für Audiokonferenzen 

![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center** zeigt

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie oben auf der Seite auf **Bearbeiten**.

3. Klicken Sie neben **Audiokonferenzen**auf **Bearbeiten**.

4. Wählen Sie unter " **Wähl Berechtigung für Besprechungen**" die gewünschte Option für die Wahl Beschränkung aus.

5. Klicken Sie auf **Speichern**. 

![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1.  Wechseln Sie im **Skype for Business Admin Center**im linken Navigationsbereich zu **Audiokonferenz** > -**Benutzer**, und wählen Sie den Benutzer in der Liste der verfügbaren Benutzer aus.

2.  Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.

3.  Wählen Sie unter **Einschränkungen für Auswahlen in Besprechungen dieses Benutzers**die gewünschte Option für das Auswählen von Einschränkungen aus.

    ![Die Einschränkungen für Optionen für Auswahlen](media/restrictions-to-dial-outs.png)

5. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwenden von PowerShell**

Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie mit dem Namen OnlineDialOutPolicy gesteuert, die ein Einschränkungs Attribut für jede hat. Die Richtlinie kann nicht angepasst werden, es gibt jedoch vordefinierte Richtlinieninstanzen für jede Kombination der Einstellungen. 

Sie können das Cmdlet Get-CSOnlineDialOutPolicy verwenden, um die ausgehenden Anruf Richtlinien anzuzeigen und Sie Benutzern mithilfe des Cmdlets Grant-CSDialOutPolicy zuzuweisen. (Bitte beachten Sie, dass das Grant-Cmdlet das Wort "Online" nicht enthält, wie es das Get-Cmdlet tut.) 

Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.

|||
|:-----|:-----|
|Identity = ' Tag: DialoutCPCandPSTNInternational '    |    Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann auch ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.    |
|Identity = ' Tag: DialoutCPCDomesticPSTNInternational '  |    Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.    |
|    Identity = ' Tag: DialoutCPCDisabledPSTNInternational '    |    Der Benutzer in der Konferenz kann keine Anrufe tätigen. Dieser Nutzer kann ausgehende Anrufe an Auslands-und Inlands Nummern tätigen.    |
|    Identity = ' Tag: DialoutCPCInternationalPSTNDomestic '    |    Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann nur ausgehende Anrufe an eine inländische PSTN-Nummer tätigen.    |
|    Identity = ' Tag: DialoutCPCInternationalPSTNDisabled '    |    Der Benutzer in der Konferenz kann sich in Auslands-und Inlands Nummern einwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.    |
|    Identity = ' Tag: DialoutCPCandPSTNDomestic '    |    Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.    |
|    Identity = ' Tag: DialoutCPCDomesticPSTNDisabled '    |    Der Benutzer in der Konferenz kann sich nur an inländische Rufnummern anwählen, und dieser Nutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.    |
|    Identity = ' Tag: DialoutCPCDisabledPSTNDomestic '    |    Der Benutzer in der Konferenz kann keine Anrufe tätigen, und dieser Benutzer kann nur ausgehende Anrufe an inländische PSTN-Nummern tätigen.    |
|    Identity = ' Tag: DialoutCPCandPSTNDisabled '    |    Der Benutzer in der Konferenz kann keine Auswahlen vornehmen, und dieser Benutzer kann außer Notrufnummern keine ausgehenden Anrufe an eine PSTN-Nummer tätigen.    |
