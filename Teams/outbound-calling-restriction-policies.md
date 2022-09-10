---
title: Einschränkungen für ausgehende Anrufe – Audiokonferenzen & PSTN-Anrufe
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.topic: article
ms.service: msteams
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Administratoren können den Typ von Audiokonferenzen und Endbenutzer-PSTN-Anrufen steuern, die von Benutzern getätigt werden können.
ms.openlocfilehash: 67c138db8522ec6eee1f384e182f5c8d01ea40fd
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641766"
---
# <a name="outbound-calling-restriction-policies-for-audio-conferencing-and-user-pstn-calls"></a>Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe

Als Administrator können Sie steuerelemente für ausgehende Anrufe verwenden, um den Typ von Audiokonferenzen und PSTN-Anrufen (Public Switched Telephone Network) für Endbenutzer einzuschränken, die von Benutzern in Ihrer Organisation getätigt werden können.

Steuerelemente für ausgehende Anrufe können auf Benutzer- oder Mandantenbasis angewendet werden und stellen die folgenden zwei Steuerelemente bereit, um jeden Typ ausgehender Anrufe unabhängig einzuschränken. Standardmäßig sind beide Steuerelemente so festgelegt, dass internationale und inländische ausgehende Anrufe zulässig sind.

|Steuerung|Beschreibung|Steuerelementoptionen|
|:-----|:-----|:-----|
|PSTN-Anrufe für Audiokonferenzen|Schränkt den Typ des ausgehenden </br>Aufrufe, die von innen zulässig sind </br>Besprechungen, die von einem Benutzer organisiert wurden.|Beliebiges Ziel (Standard)</br>Im selben Land oder derselben Region wie der Organisator </br> [Nur Länder oder Regionen der Zone A](audio-conferencing-zones.md) </br>Nicht zulassen|
|PSTN-Anrufe für Endbenutzer|Schränkt den Anruftyp ein </br>die von einem Benutzer erstellt werden kann.|International und Inland (Standard)</br>Inlandsanruf</br>Keine|

Informationen dazu, welche Länder und Regionen als Zone A gelten, finden Sie unter ["Land" und "Regionszonen" für Audiokonferenzen](audio-conferencing-zones.md).

   > [!NOTE]
   > Ein Anruf wird als inland angesehen, wenn sich die gewählte Nummer in dem Land befindet, in dem Microsoft 365 oder Office 365 für den Organisator der Besprechung (bei Audiokonferenzen) oder den Endbenutzer (bei PSTN-Anrufen des Endbenutzers) eingerichtet wurde.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="restrict-audio-conferencing-outbound-calls"></a>Einschränken ausgehender Audiokonferenzanrufe

### <a name="using-the-microsoft-teams-admin-center"></a>Verwenden des Microsoft Teams Admin Centers

1. Wählen Sie im linken Navigationsbereich **"Benutzer**" aus, und wählen Sie dann den Anzeigenamen des Benutzers aus der Liste der verfügbaren Benutzer aus.

2. Wechseln Sie als Nächstes zu **Audiokonferenzen**, wählen Sie **"Bearbeiten"** aus.

3. Wählen Sie unter **"Ausgehende Anrufe aus Besprechungen**" die gewünschte Einwahleinschränkungsoption aus.

4. Klicken Sie auf **Speichern**.

### <a name="using-powershell"></a>Verwendung von PowerShell

Einschränkungen für ausgehende Anrufe werden durch eine einzelne Richtlinie namens "OnlineDialOutPolicy" gesteuert, die jeweils ein Einschränkungsattribut aufweist. Die Richtlinie kann nicht angepasst werden, vielmehr gibt es für jede Kombination der Einstellungen vordefinierte Richtlinieninstanzen.

Sie können das cmdlet Get-CSOnlineDialOutPolicy verwenden, um die Richtlinien für ausgehende Anrufe anzuzeigen und den folgenden Befehl für das Setup zu verwenden.

**Legen Sie die Richtlinie mit dem folgenden Cmdlet auf Benutzerebene** fest. (Das Cmdlet "Grant" enthält nicht das Wort "Online" wie das Cmdlet "Get".)

```powershell
Grant-CsDialoutPolicy -Identity <username> -PolicyName <policy name>    
```

**Legen Sie die Richtlinie auf Mandantenebene mit dem folgenden Cmdlet** fest.

```powershell
Grant-CsDialoutPolicy -PolicyName <policy name>  -Global 
```

Alle Benutzer des Mandanten, denen keine DFÜ-Richtlinie zugewiesen ist, erhalten diese Richtlinie. Andere Benutzer bleiben bei ihrer aktuellen Richtlinie.

**Überprüfen Sie die aktuelle Richtlinie auf Mandantenebene mit dem folgenden Cmdlet**.

```powershell
Get-CSOnlineDialOutPolicy -Identity Global
```

Die folgende Tabelle enthält eine Übersicht über die einzelnen Richtlinien.

|PowerShell-Cmdlet|Beschreibung|
|:-----|:-----|
|Identity='tag:DialoutCPCandPSTNInternational'    |    Der Benutzer in der Konferenz kann internationale und inländische Telefonnummern anrufen, und dieser Benutzer kann auch ausgehende Anrufe an internationale und inländische Nummern tätigen.    |
|Identity='tag:DialoutCPCDomesticPSTNInternational'  |    Der Benutzer in der Konferenz kann sich nur an Inlandsnummern auswählen, und dieser Benutzer kann ausgehende Anrufe an internationale und inländische Nummern tätigen.    |
|    Identity='tag:DialoutCPCDisabledPSTNInternational'    |    Der Benutzer in der Konferenz kann sich nicht auswählen. Dieser Benutzer kann ausgehende Anrufe an internationale und inländische Nummern tätigen.    |
|    Identity='tag:DialoutCPCInternationalPSTNDomestic'    |    Der Benutzer in der Konferenz kann sich an internationale und inländische Telefonnummern auswählen, und dieser Benutzer kann nur ausgehende Anrufe an die PSTN-Nummer im Inland tätigen.    |
|    Identity='tag:DialoutCPCInternationalPSTNDisabled'    |    Der Benutzer in der Konferenz kann sich an internationale und inländische Telefonnummern auswählen, und dieser Benutzer kann neben Notrufnummern keine ausgehenden Anrufe an die PSTN-Nummer tätigen.    |
|    Identity='tag:DialoutCPCandPSTNDomestic'    |    Der Benutzer in der Konferenz kann sich nur an Inlandsnummern auswählen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummern tätigen.    |
|    Identity='tag:DialoutCPCDomesticPSTNDisabled'    |    Der Benutzer in der Konferenz kann nur an Inlandsnummern anrufen, und dieser Benutzer kann neben Notrufnummern keine ausgehenden Anrufe an die PSTN-Nummer tätigen.    |
|    Identity='tag:DialoutCPCDisabledPSTNDomestic'    |    Der Benutzer in der Konferenz kann keine Anrufe tätigen, und dieser Benutzer kann nur ausgehende Anrufe an PSTN-Nummern tätigen.    |
|    Identity='tag:DialoutCPCandPSTNDisabled'    |    Der Benutzer in der Konferenz kann keine Ausgehende Anrufe tätigen, und dieser Benutzer kann neben Notrufnummern auch keine ausgehenden Anrufe an die PSTN-Nummer tätigen.    |
|    Identity='tag:DialoutCPCZoneAPSTNInternational'    |    Der Benutzer in der Konferenz kann sich nur in [Länder und Regionen der Zone A auswählen](audio-conferencing-zones.md), und dieser Benutzer kann ausgehende Anrufe an internationale und inländische Nummern tätigen.    |
|    Identity='tag:DialoutCPCZoneAPSTNDomestic'    |    Der Benutzer in der Konferenz kann sich nur in [Länder und Regionen der Zone A auswählen](audio-conferencing-zones.md), und dieser Benutzer kann nur ausgehende Anrufe an die PSTN-Nummer des Inlands tätigen.    |
|    Identity='tag:DialoutCPCZoneAPSTNDisabled'    |    Benutzer in der Konferenz können sich nur an [Länder und Regionen der Zone A](audio-conferencing-zones.md) auswählen, und dieser Benutzer kann neben Notrufnummern keine ausgehenden Anrufe an die PSTN-Nummer tätigen.    |
