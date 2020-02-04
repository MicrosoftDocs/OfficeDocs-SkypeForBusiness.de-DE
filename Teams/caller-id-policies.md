---
title: Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Rufnummernanzeige Richtlinien in Microsoft Teams verwenden und verwalten, um die Rufnummernanzeige von Teams-Benutzern in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: f5a1d52f10bb60ced33b05339f81ecd0a6a363f5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695590"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Rufnummernanzeige (auch als Anruf Leitungs-ID bezeichnet) zu ändern oder zu blockieren. Standardmäßig kann die Telefonnummer von Teams-Benutzern angezeigt werden, wenn Sie einen Anruf an ein PSTN-Telefon durchführen, und die Telefonnummer der PSTN-Anrufer kann angezeigt werden, wenn Sie einen Teams-Nutzer anrufen. Sie können die Richtlinien für die Rufnummernanzeige verwenden, um eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzuzeigen oder die Anzeige einer eingehenden Nummer zu blockieren.

Wenn Benutzer beispielsweise einen Anruf führen, können Sie die Rufnummernanzeige ändern, um die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer anzuzeigen.

Sie verwalten die Richtlinien für die Rufnummernanzeige, indem Sie im Microsoft Teams Admin Center zu den Richtlinien für die **VoIP** > **-Anruferkennung** wechseln. Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.

Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer. Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.

## <a name="create-a-custom-caller-id-policy"></a>Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien für Anrufer**.
2. Klicken Sie auf **Hinzufügen**.
![Screenshot der Seite "neue Rufnummernanzeige" im Admin Center](media/caller-id-policies-add-policy.png)
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie hier die gewünschten Einstellungen aus:

    - **Eingehende Anrufer-ID blockieren**: Aktivieren Sie diese Einstellung, um die Rufnummernanzeige für eingehende Anrufe zu blockieren.
    - **Benutzer können die Richtlinien für die Rufnummernanzeige außer Kraft setzen**: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie bezüglich der Anzeige der Rufnummer für Anrufer überschreiben können. Das bedeutet, dass Benutzer auswählen können, ob Sie Ihre Rufnummernanzeige anzeigen möchten.
    - **Rufnummernanzeige ersetzen**: Legen Sie die Anrufer-ID für die Benutzer angezeigt, indem Sie eine der folgenden Optionen auswählen:

        - **Nummer des Benutzers**: zeigt die Nummer des Benutzers an. 
        - **Dienstnummer**: Hier können Sie eine Dienst Telefonnummer einrichten, die als Rufnummernanzeige angezeigt werden soll.
        - **Anonym**: zeigt die Rufnummernanzeige als "Anonym" an.

    - **Dienstnummer, die zum Ersetzen der Rufnummernanzeige verwendet**werden soll: Wählen Sie eine Dienstnummer aus, um die Rufnummernanzeige der Benutzer zu ersetzen. Diese Option steht zur Verfügung, wenn Sie unter **Rufnummernanzeige ersetzen**die Option **Dienstnummer** ausgewählt haben.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-caller-id-policy"></a>Bearbeiten einer Rufnummernanzeige-Richtlinie

Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen. 

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien für Anrufer**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Ändern Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern

Um einem oder mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Microsoft Teams Admin Center verwenden. Um Benutzergruppen, z. B. einer Sicherheitsgruppe oder einer Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Skype for Business PowerShell-Modul verwenden.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Richtlinie für die Rufnummernanzeige zu einem Benutzer

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.
3. Wählen Sie unter **Anrufer-ID-Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>Zuweisen einer benutzerdefinierten Anruf Linien-ID-Richtlinie zu mehreren Benutzern gleichzeitig

Wenn Sie eine benutzerdefinierte Anruf Linien-ID-Richtlinie mehreren Benutzern gleichzeitig zuweisen möchten, lesen Sie [Bearbeiten der Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie zu **Microsoft Teams Admin Center** > -**VoIP** > **-Anruf Erkennungsrichtlinien**.
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Benutzer verwalten** aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Richtlinie zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).

In diesem Beispiel weisen wir eine benutzerdefinierte Richtlinie für die Rufnummernanzeige mit der Bezeichnung Support Caller ID-Richtlinie allen Benutzern in der Contoso-Support Gruppe zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Abrufen der Mitglieder der gewählten Gruppe.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe einer bestimmten Rufnummernanzeige-Richtlinie zu. In diesem Beispiel wird die Richtlinie für die Rufnummernanzeige unterstützt.
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

 ## <a name="related-topics"></a>Verwandte Themen

- [Neu – CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

