---
title: Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams.
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Anrufer-ID-Richtlinien in Microsoft Teams verwenden und verwalten, um die Anrufer-ID Teams Benutzer in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: a511e86efcaba8ec5dd81718bf768cc45fbf2ad0
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605431"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams.

> [!NOTE]
> Verwenden Sie die PowerShell-Cmdlets New-CsCallingLineIdentity oder Set-CsCallingLineIdentity im Teams PowerShell-Modul 2.3.1 oder höher, um die Anrufer-ID auf die Telefonnummer eines Ressourcenkontos und den Namen des Anrufers zu setzen. (Diese Optionen sind derzeit nicht im Microsoft Teams Admin Center verfügbar.) 

Wenn ein Benutzer Teams einen Anruf bei einem PSTN-Telefon anruft, wird standardmäßig die Telefonnummer des Teams Benutzers angezeigt. Ebenso wird die Telefonnummer des PSTN-Anrufers angezeigt, wenn Teams Einen Anrufer anruft.

Als Administrator können Sie Anrufer-ID-Richtlinien verwenden, um die Anrufer-ID (auch als Anruferleitungs-ID bekannt) zu ändern oder zu blockieren. Mithilfe von Anrufer-ID-Richtlinien können Sie eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzeigen, die ausgehende Telefonnummer blockieren, die Anzeige einer eingehenden Nummer blockieren oder den Anrufernamen (Calling Party Name, CNAM) festlegen. Wenn ein Benutzer beispielsweise einen Anruf anruft, können Sie die Anrufer-ID so ändern, dass die Haupttelefonnummer und der Firmenname der Organisation anstelle der Telefonnummer des Benutzers angezeigt werden.

Sie können Anrufer-ID-Richtlinien verwalten, indem Sie zu den Richtlinien **für** die Sprachanruf-ID  >   im Microsoft Teams Admin Center gehen. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

## <a name="create-a-custom-caller-id-policy"></a>Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **für**  >  **die Sprachanruf-ID.**
2. Klicken Sie auf **Hinzufügen**. <br>
![Screenshot der Richtlinienseite "Neue Anrufer-ID" im Admin Center.](media/caller-id-policies-add-policy.png)
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie hier die einstellungen aus, die Sie verwenden möchten:

    - **Eingehende Anrufer-ID blockieren:** Aktivieren Sie diese Einstellung, um die Anzeige der Anrufer-ID eingehender Anrufe zu blockieren.
    - **Richtlinie für Anrufer-ID** außer Kraft setzen: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie im Hinblick auf die Anzeige ihrer Rufnummer für Anrufer außer Kraft setzen können. Dies bedeutet, dass Benutzer auswählen können, ob sie ihre Anrufer-ID anzeigen. Weitere Informationen finden Sie unter [Steuerung der ausgehenden Anrufer-ID durch Endbenutzer.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)
    - **Ersetzen Sie die Anrufer-ID durch**: Legen Sie die anrufer-ID, die für Benutzer angezeigt werden soll, durch Auswahl einer der folgenden Optionen vor:

        - **Benutzernummer:** Zeigt die Nummer des Benutzers an. 
        - **Servicenummer:** Hiermit können Sie eine Servicetelefonnummer festlegen, die als Anrufer-ID angezeigt werden soll.
        - **Anonym:** Zeigt die Anrufer-ID als Anonym an.

    - **Ersetzen Sie die Anrufer-ID durch diese Dienstnummer:** Wählen Sie eine Leistungsnummer aus, die die Anrufer-ID der Benutzer ersetzen soll. Diese Option ist verfügbar, wenn Sie **in Ersetzen** der **Anrufer-ID** durch die Option Servicenummer ausgewählt haben.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-caller-id-policy"></a>Bearbeiten einer Anrufer-ID-Richtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen. 

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **für**  >  **die Sprachanruf-ID.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Ändern Sie die Einstellungen, die Sie wünschen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Verwandte Themen

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)