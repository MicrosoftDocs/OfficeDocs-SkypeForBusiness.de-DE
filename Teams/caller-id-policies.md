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
description: Erfahren Sie, wie Sie Anrufer-ID-Richtlinien in Microsoft Teams verwenden und verwalten, um die Anrufer-ID von Teams-Benutzern in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: cd15245523cdc3f5fb3625a2b4cfdae4deebb7d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102781"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams.

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Anrufer-ID zu ändern oder zu blockieren (auch bekannt als Anrufer-Zeilen-ID). Standardmäßig kann die Telefonnummer der Teams-Benutzer angezeigt werden, wenn sie einen Anruf bei einem PSTN-Telefon machen, und die Telefonnummer der PSTN-Anrufer wird angezeigt, wenn sie einen Teams-Benutzer anrufen. Mithilfe von Anrufer-ID-Richtlinien können Sie eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzeigen oder die Anzeige einer eingehenden Nummer blockieren.

Wenn Benutzer beispielsweise einen Anruf machen, können Sie die Anrufer-ID so ändern, dass die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer angezeigt wird.

Sie verwalten Anrufer-ID-Richtlinien, indem Sie im Microsoft Teams Admin Center zu **Voice**  >  **Caller-ID-Richtlinien** gehen. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

## <a name="create-a-custom-caller-id-policy"></a>Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **Caller ID-Richtlinien.**
2. Klicken Sie auf **Hinzufügen**. <br>
![Screenshot der neuen Anrufer-ID-Richtlinienseite im Admin Center](media/caller-id-policies-add-policy.png)
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie hier die einstellungen aus, die Sie verwenden möchten:

    - **Eingehende Anrufer-ID** blockieren: Aktivieren Sie diese Einstellung, um die Anzeige der Anrufer-ID eingehender Anrufe zu blockieren.
    - **Setzen Sie die Anrufer-ID-Richtlinie** außer Kraft: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie zum Anzeigen ihrer Nummer für Anrufer außer Kraft setzen können. Dies bedeutet, dass Benutzer auswählen können, ob ihre Anrufer-ID angezeigt werden soll. Weitere Informationen finden Sie unter [Endbenutzersteuerung der ausgehenden Anrufer-ID](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id).
    - **Ersetzen Sie die Anrufer-ID durch**: Legen Sie die für Benutzer angezeigte Anrufer-ID durch Auswählen einer der folgenden Optionen so vor:

        - **Benutzernummer:** Zeigt die Nummer des Benutzers an. 
        - **Servicenummer:** Hiermit können Sie eine Diensttelefonnummer festlegen, die als Anrufer-ID angezeigt werden soll.
        - **Anonym:** Zeigt die Anrufer-ID als anonym an.

    - **Ersetzen Sie die Anrufer-ID durch diese Dienstnummer:** Wählen Sie eine Dienstnummer aus, um die Anrufer-ID der Benutzer zu ersetzen. Diese Option ist verfügbar, wenn Sie **unter** Ersetzen der **Anrufer-ID** die Option Dienstnummer durch ausgewählt haben.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-caller-id-policy"></a>Bearbeiten einer Anrufer-ID-Richtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen. 

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Voice**  >  **Caller ID-Richtlinien.**
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Ändern Sie die einstellungen, die Sie wünschen, und klicken Sie dann auf **Speichern.**

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Verwandte Themen

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)