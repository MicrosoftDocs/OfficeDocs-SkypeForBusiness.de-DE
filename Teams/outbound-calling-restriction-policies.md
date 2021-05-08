---
title: Einschränkungen für ausgehende Anrufe – Audiokonferenzen & PSTN-Anrufe
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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Administratoren können die Art von Audiokonferenzen und PSTN-Anrufen für Endbenutzer steuern, die von Benutzern vorgenommen werden können.
ms.openlocfilehash: e085f996226a59d88339b20e64dd06f68ef566ce
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908654"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe

Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können. 

Steuerelemente für ausgehende Anrufe können pro Benutzer angewendet werden und bieten die folgenden beiden Steuerelemente zum unabhängigen Einschränken der einzelnen Arten von ausgehenden Anrufen. Standardmäßig sind beide Steuerelemente so eingestellt, dass sie internationale und ausgehende Anrufe im Inland zulassen. 

|Steuerelement|Beschreibung|Steuerelementoptionen|
|:-----|:-----|:-----|
|PSTN-Anrufe für Audiokonferenzen|Schränkt den Ausgehenden Typ ein. </br>Aufrufe, die von innerhalb </br>von einem Benutzer organisierte Besprechungen.|Beliebiges Ziel (Standard)</br>Im selben Land oder in derselben Region wie der Organisator </br> [Nur Länder oder Regionen in](audio-conferencing-zones.md) Zone A </br>Nicht zulassen|
|PSTN-Anrufe für Endbenutzer|Beschränkt die Art der Anrufe </br>die von einem Benutzer vorgenommen werden können.|International und Inland (Standard)</br>Inlandsanruf</br>Keine|

Wenn Sie herausfinden müssen, welche Länder und Regionen als Zone A gelten, lesen Sie Länder- und [Regionszonen für Audiokonferenzen.](audio-conferencing-zones.md)

   > [!NOTE]
   > Ein Anruf gilt als Inlandsnummer, wenn sich die gewählte Nummer in demselben Land befindet, in dem Microsoft 365 oder Office 365 für den Organisator der Besprechung (im Fall von Audiokonferenzen) oder für den Endbenutzer (bei PstN-Anrufen des Endbenutzers) eingerichtet wurde. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Einschränken ausgehender Anrufe bei Audiokonferenzen

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und klicken Sie dann in der Liste der verfügbaren Benutzer auf den Anzeigenamen des Benutzers.

3. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.

4. Wählen **Sie unter Auswahl aus Besprechungen** die Option zum Einwählen aus, die Sie verwenden möchten.

5. Klicken Sie auf **Speichern**. 

![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**

1. Wechseln Sie **im Skype for Business Admin Center** in der linken Navigationsleiste zu Audio **conferencing** Users , und wählen Sie den Benutzer aus der Liste der  >  verfügbaren Benutzer aus.

2. Klicken Sie im Bereich „Aktion" auf **Bearbeiten**.

3.  Wählen **Sie unter Einschränkungen für Das Auswählen** aus Besprechungen dieses Benutzers die Option für Die Auswahleinschränkung aus.

      ![Einschränkungen für Auswahloptionen](media/restrictions-to-dial-outs.png)
      

4. Klicken Sie auf **Speichern**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Verwendung von PowerShell**

Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie mit dem Namen OnlineDialOutPolicy gesteuert, die jeweils über ein Einschränkungsattribut verfügt. Die Richtlinie kann nicht angepasst werden, sondern es gibt vordefinierte Richtlinieninstanzen für jede Kombination der Einstellungen. 

Mit dem cmdlet Get-CSOnlineDialOutPolicy ausgehende Anrufe können Sie die Richtlinien für ausgehende Anrufe anzeigen und mithilfe des cmdlets Grant-CSDialOutPolicy Benutzern zuweisen. (Beachten Sie, dass das Cmdlet Grant nicht wie das Cmdlet "Get" das Wort "Online" enthält.) 

Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.

|||
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    Benutzer in der Konferenz können internationale und inlandsnummern anrufen, und dieser Benutzer kann auch ausgehende Anrufe an internationale nummern und Nummern im Inland anrufe.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    Nutzer der Konferenz können nur Inlandsnummern anrufen, und dieser Benutzer kann ausgehende Anrufe an internationale und inlandsnummern abwählen.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    Benutzer der Konferenz können keine Herausrufe erstellen. Dieser Benutzer kann ausgehende Anrufe an internationale und Inlandsnummern anrufe.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    Benutzer in der Konferenz können internationale und Inlandsnummern anrufen, und dieser Benutzer kann nur ausgehende Anrufe an die PSTN-Nummer im Inland anrufe.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    Benutzer in der Konferenz können internationale und Inlandsnummern anrufen, und dieser Benutzer kann neben den Notrufnummern auch keine ausgehenden Anrufe an die PSTN-Nummer abwählen.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    Benutzer in der Konferenz können nur Nummern im Inland anrufen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummern im Inland erstellen.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    Benutzer in der Konferenz können nur Inlandsnummer anrufen, und dieser Benutzer kann neben den Notrufnummern auch keine ausgehenden Anrufe an die PSTN-Nummer abwählen.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    Benutzer der Konferenz können keine ausgehenden Anrufe erstellen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummern im Inland erstellen.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    Der Benutzer der Konferenz kann keine ausgehenden Anrufe erstellen, und dieser Benutzer kann neben den Notrufnummern auch keine ausgehenden Anrufe an die PSTN-Nummer erstellen.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    Nutzer der Konferenz können nur Länder und Regionen der [Zone A](audio-conferencing-zones.md)anrufen, und dieser Benutzer kann ausgehende Anrufe an internationale und inlandsnummern abwählen.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    Nutzer der Konferenz können nur Länder und Regionen der [Zone A](audio-conferencing-zones.md)anrufen, und dieser Benutzer kann nur ausgehende Anrufe an die PSTN-Nummer im Inland erstellen.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    Nutzer der Konferenz können nur Länder und Regionen der Zone [A](audio-conferencing-zones.md)anrufen, und dieser Benutzer kann neben den Notrufnummern auch keine ausgehenden Anrufe an die PSTN-Nummer mehr abwählen.    |
