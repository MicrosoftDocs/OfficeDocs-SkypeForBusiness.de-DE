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
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Rufnummernanzeige Richtlinien in Microsoft Teams verwenden und verwalten, um die Rufnummernanzeige von Teams-Benutzern in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: 95771336e71e56752483519cd089b1c755ec11d3
ms.sourcegitcommit: 25c30baec1c969eef95b725251a3f4ad3706a19d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2019
ms.locfileid: "36622091"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Rufnummernanzeige (auch als Anruf Leitungs-ID bezeichnet) zu ändern oder zu blockieren. Standardmäßig kann die Telefonnummer von Teams-Benutzern angezeigt werden, wenn Sie einen Anruf an ein PSTN-Telefon durchführen, und die Telefonnummer der PSTN-Anrufer kann angezeigt werden, wenn Sie einen Teams-Nutzer anrufen. Sie können die Richtlinien für die Rufnummernanzeige verwenden, um eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzuzeigen oder die Anzeige einer eingehenden Nummer zu blockieren.

Wenn Benutzer beispielsweise einen Anruf führen, können Sie die Rufnummernanzeige ändern, um die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer anzuzeigen.

Sie verwalten die Richtlinien für die Rufnummernanzeige, indem Sie im Microsoft Teams Admin Center zu den Richtlinien für die **VoIP** > **-Anruferkennung** wechseln. Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und diesen Benutzern zuweisen. Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.

Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen. Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer. Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer.

## <a name="create-a-custom-caller-id-policy"></a>Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien**für Anrufer.
2. Klicken Sie auf **Hinzufügen**.
![Screenshot der Seite "neue Rufnummernanzeige" im Admin Center](media/caller-id-policies-add-policy.png)
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie hier die gewünschten Einstellungen aus:

    - **Eingehende Anrufer-ID blockieren**: Aktivieren Sie diese Einstellung, um die Rufnummernanzeige für eingehende Anrufe zu blockieren.
    - **Benutzer können die Richtlinie für die Rufnummernanzeige außer Kraft setzen**: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie außer Kraft setzen können. Das bedeutet, dass Benutzer auswählen können, ob Sie Ihre Rufnummernanzeige anzeigen oder die Rufnummernanzeige eines eingehenden Anrufs blockieren möchten.
    - **Rufnummernanzeige ersetzen**: Legen Sie die Anrufer-ID für die Benutzer angezeigt, indem Sie eine der folgenden Optionen auswählen:

        - **Nummer des Benutzers**: zeigt die Nummer des Benutzers an. 
        - **Dienstnummer**: Hier können Sie eine Dienst Telefonnummer einrichten, die als Rufnummernanzeige angezeigt werden soll.
        - **Anonym**: zeigt die Rufnummernanzeige als "Anonym" an.

    - **Dienstnummer, die zum Ersetzen der Rufnummernanzeige verwendet**werden soll: Wählen Sie eine Dienstnummer aus, um die Rufnummernanzeige der Benutzer zu ersetzen. Diese Option steht zur Verfügung, wenn Sie unter **Rufnummernanzeige ersetzen**die Option **Dienstnummer** ausgewählt haben.

5. Klicken Sie auf **Speichern**.

## <a name="edit-a-caller-id-policy"></a>Bearbeiten einer Rufnummernanzeige-Richtlinie

Sie können die globale Richtlinie oder alle von Ihnen erstellten benutzerdefinierten Richtlinien bearbeiten. 

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien**für Anrufer.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken und dann auf **Bearbeiten**klicken.
3. Ändern Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.

## <a name="assign-a-custom-caller-id-policy-to-users"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern

Mit dem Microsoft Teams Admin Center können Sie einem oder mehreren Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuweisen, um Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a>Zuweisen einer benutzerdefinierten Richtlinie für die Rufnummernanzeige zu einem Benutzer

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.
2. Klicken Sie auf **Richtlinien**und dann neben **zugewiesene Richtlinien**auf **Bearbeiten**.
3. Wählen Sie unter **Anrufer-ID-Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a>Zuweisen einer benutzerdefinierten Anruf Linien-ID-Richtlinie zu mehreren Benutzern gleichzeitig

Wenn Sie eine benutzerdefinierte Anruf Linien-ID-Richtlinie mehreren Benutzern gleichzeitig zuweisen möchten, lesen Sie [Bearbeiten der Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).

Oder Sie können auch die folgenden Aktionen ausführen:

1. Wechseln Sie zu **Microsoft Teams Admin Center** > -**VoIP** > **-Anruf Erkennungsrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.
3. Wählen Sie **Benutzer verwalten**aus.
4. Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus. Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.
5. Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Richtlinie zuweisen. So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).

In diesem Beispiel weisen wir eine benutzerdefinierte Richtlinie für die Rufnummernanzeige mit der Bezeichnung Support Caller ID-Richtlinie allen Benutzern in der Contoso-Support Gruppe zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.
```
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
Rufen Sie die Mitglieder der angegebenen Gruppe ab.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe einer bestimmten Rufnummernanzeige-Richtlinie zu. In diesem Beispiel wird die Richtlinie für die Rufnummernanzeige unterstützt.
```
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.EmailAddress}
``` 
Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.

 ## <a name="related-topics"></a>Verwandte Themen

- [Neu – CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

