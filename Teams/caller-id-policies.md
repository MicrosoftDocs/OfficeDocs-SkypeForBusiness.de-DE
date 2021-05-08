---
title: Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams.
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie Anrufer-ID-Richtlinien in Microsoft Teams verwenden und verwalten, um die Anrufer-ID Teams Benutzer in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102781"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams.

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Als Administrator können Sie Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Anrufer-ID (auch als Anruferleitungs-ID bekannt) zu ändern oder zu blockieren. Standardmäßig ist die Telefonnummer der Teams-Benutzer zu sehen, wenn sie bei einem PSTN-Telefon anrufen, und die Telefonnummer der PSTN-Anrufer ist zu sehen, wenn sie einen Anruf bei einem Teams-Benutzer treffen. Mithilfe von Anrufer-ID-Richtlinien können Sie eine alternative Telefonnummer für Teams Benutzer in Ihrer Organisation anzeigen oder die Anzeige einer eingehenden Nummer blockieren.

Wenn Benutzer beispielsweise einen Anruf machen, können Sie die Anrufer-ID so ändern, dass die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer angezeigt wird.

Sie verwalten Anrufer-ID-Richtlinien, indem Sie zu den Richtlinien **für** die Sprachanruf-ID im Microsoft Teams  >   Admin Center gehen. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

## <a name="create-a-custom-caller-id-policy"></a>Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **für**  >  **die Sprachanruf-ID.**
2. Klicken Sie auf **Hinzufügen**. <br>
![Screenshot der Richtlinienseite "Neue Anrufer-ID" im Admin Center](media/caller-id-policies-add-policy.png)
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie hier die einstellungen aus, die Sie verwenden möchten:

    - **Eingehende Anrufer-ID blockieren:** Aktivieren Sie diese Einstellung, um die Anzeige der Anrufer-ID eingehender Anrufe zu blockieren.
    - **Richtlinie für Anrufer-ID** außer Kraft setzen: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie im Hinblick auf die Anzeige ihrer Rufnummer für Anrufer außer Kraft setzen können. Dies bedeutet, dass Benutzer auswählen können, ob sie ihre Anrufer-ID anzeigen. Weitere Informationen finden Sie unter [Steuerung der ausgehenden Anrufer-ID durch Endbenutzer.](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)
    - **Ersetzen Sie die Anrufer-ID durch**: Legen Sie die anrufer-ID, die für Benutzer angezeigt werden soll, durch Auswahl einer der folgenden Optionen vor:

        - **Benutzernummer:** Zeigt die Nummer des Benutzers an. 
        - **Servicenummer:** Hiermit können Sie eine Servicetelefonnummer festlegen, die als Anrufer-ID angezeigt werden soll.
        - **Anonym:** Zeigt die Anrufer-ID als Anonym an.

    - **Ersetzen Sie die Anrufer-ID durch diese Servicenummer:** Wählen Sie eine Leistungsnummer aus, die die Anrufer-ID der Benutzer ersetzen soll. Diese Option ist verfügbar, wenn Sie **in Ersetzen** der **Anrufer-ID** durch die Option Servicenummer ausgewählt haben.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-caller-id-policy"></a>Bearbeiten einer Anrufer-ID-Richtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen. 

1. Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu Richtlinien **für**  >  **die Sprachanruf-ID.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Ändern Sie die Einstellungen, die Sie wünschen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Verwandte Themen

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)