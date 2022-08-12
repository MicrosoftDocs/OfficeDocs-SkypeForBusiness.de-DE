---
title: Verwalten der Richtlinien und Einstellungen für benutzerdefinierte Apps
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwalten, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 45b6ec9809fe0c86f1a4acb69ef78c5c5f30f230
ms.sourcegitcommit: 63dcc92b2d5d50e2c0c074a1209625e16086ca45
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2022
ms.locfileid: "67299134"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

Als Administrator können Sie mithilfe von Richtlinien und Einstellungen für benutzerdefinierte Apps steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann. Administratoren entscheiden, welche Benutzer benutzerdefinierte Apps hochladen können, und Administratoren und Teambesitzer können bestimmen, ob in den einzelnen Teams in Ihrer Organisation benutzerdefinierte Apps hinzugefügt werden können.  Nachdem Sie die benutzerdefinierte App-Richtlinie bearbeitet haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Entwickler in Ihrer Organisation können eine benutzerdefinierte App zu Teams hinzufügen, indem sie ein App-Paket (in einer ZIP-Datei) direkt in ein Team oder in den persönlichen Kontext hochladen. Dies unterscheidet sich von der Art und Weise, wie Apps über den Teams App Store hinzugefügt werden. Das Hinzufügen einer benutzerdefinierten App durch Hochladen eines App-Pakets, auch bekannt als Querladen, ermöglicht es bestimmten Benutzern in Ihrer Organisation, eine App zu testen, bevor sie für die weite Verbreitung bereit ist.

## <a name="custom-app-policy-and-settings"></a>Benutzerdefinierte App-Richtlinie und -Einstellungen

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte App in ein Team hochladen kann, sodass Sie genau steuern können, wer einem Team benutzerdefinierte Apps hinzufügen kann und welchen Teams benutzerdefinierte Apps hinzugefügt werden können:

- [Benutzerdefinierte App-Richtlinie](#user-custom-app-policy)
- [Teameinstellung für benutzerdefinierte Apps](#team-custom-app-setting)
- [Organisationsweite Einstellung für benutzerdefinierte Apps](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit aus, Apps von Drittanbietern zu blockieren.  

### <a name="user-custom-app-policy"></a>Benutzerrichtlinie für benutzerdefinierte Apps

Im Rahmen von [App-Setuprichtlinien](teams-app-setup-policies.md) können Administratoren die Richtlinieneinstellung **Hochladen benutzerdefinierter Apps** zulassen verwenden, um zu steuern, ob ein Benutzer benutzerdefinierte Apps in Teams hochladen kann.

Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierten Apps in Teams in Ihrer Organisation oder in den persönlichen Kontext hochladen.
- Der Benutzer kann abhängig von der organisationsweiten Einstellung für benutzerdefinierte Apps mit benutzerdefinierten Apps interagieren.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann abhängig von der organisationsweiten Einstellung für benutzerdefinierte Apps benutzerdefinierte Apps in Teams, die dies zulassen, und in Teams, deren Besitzer er ist, hochladen.
- Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen.
- Der Benutzer kann abhängig von der organisationsweiten Einstellung für benutzerdefinierte Apps mit benutzerdefinierten Apps interagieren.

Sie können die Einstellungen in der globalen App-Setuprichtlinie so bearbeiten, dass sie die gewünschten Apps enthalten. Wenn Sie Teams für unterschiedliche Benutzergruppen in Ihrer Organisation anpassen möchten, können Sie eine oder mehrere Setuprichtlinien für benutzerdefinierte Apps erstellen und zuweisen.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer benutzerdefinierten App-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Einrichtungsrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie **Hochladen benutzerdefinierter Apps zulassen**.
4. Wählen Sie alle anderen Einstellungen aus, die Sie für die Richtlinie festlegen möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Teameinstellung für benutzerdefinierte Apps

Administratoren und Teambesitzer können steuern, ob ein Team das Hinzufügen von benutzerdefinierten Apps zulässt. Diese Einstellung **Mitgliedern erlauben, benutzerdefinierte Apps hochzuladen** bestimmt in Kombination mit der Benutzerrichtlinie für benutzerdefinierte Apps, wer einem bestimmten Team benutzerdefinierte Apps hinzufügen kann.

Wenn diese Einstellung deaktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre Richtlinie für benutzerdefinierte Apps dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten Apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre Richtlinie für benutzerdefinierte Apps dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte Apps hinzufügen, wenn ihre Richtlinie für benutzerdefinierte Apps dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der benutzerdefinierten Team-App-Einstellung

1. Wechseln Sie in Teams zum Team, klicken Sie auf **Weitere Optionen ...** >  **Team verwalten**.
2. Klicken Sie auf **Einstellungen**, und erweitern Sie dann die **Mitgliederberechtigungen**.
3. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Mitgliedern erlauben, benutzerdefinierte Apps hochzuladen**.

    ![Screenshot der benutzerdefinierten Team-App-Einstellung.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite Einstellung für benutzerdefinierte Apps

Die Einstellung **Interaktion mit benutzerdefinierten Apps zulassen** auf der Seite [Apps verwalten](manage-apps.md) gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie benutzerdefinierte Apps hochladen oder mit ihnen interagieren können. Diese Einstellung fungiert als Haupt-Ein/Aus-Schalter für die benutzerdefinierten App-Richtlinieneinstellungen für Benutzer und Teams. Sie dient als Ein-/Aus-Hauptschalter während Sicherheitsereignissen. Daher werden benutzerdefinierte App-Richtlinieneinstellungen für Benutzer und Teams nur wirksam, wenn die organisationsweite benutzerdefinierte App-Einstellung aktiviert ist, auch wenn benutzerdefinierte App-Richtlinieneinstellungen für Benutzer und Teams aktiviert sind.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten benutzerdefinierten App-Einstellung

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf **Organisationsweite App-Einstellungen**.
3. Aktivieren oder deaktivieren Sie unter **Benutzerdefinierte Apps** die Option **Interaktion mit benutzerdefinierten Apps zulassen**.

    ![Screenshot zeigt organisationsweite benutzerdefinierte App-Einstellungen.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Zusammenarbeit von Richtlinien und Einstellungen für benutzerdefinierte Apps

Diese Tabelle enthält eine Zusammenfassung der Richtlinie und Einstellungen für benutzerdefinierte Apps, ihrer Zusammenarbeit und der kombinierten Auswirkung auf die Steuerung, wer in Ihrer Organisation benutzerdefinierte Apps in Teams hochladen kann.

Angenommen, Sie möchten nur Teambesitzern erlauben, benutzerdefinierte Apps in bestimmte Teams hochzuladen. Sie würden Folgendes festlegen:

- Aktivieren Sie die Einstellung **Interaktion mit benutzerdefinierten Apps zulassen** im Microsoft Teams Admin Center.
- Deaktivieren Sie **Mitgliedern erlauben benutzerdefinierte Apps hochzuladen** für jedes Team, auf das Sie den Zugriff beschränken möchten.
- Erstellen und zuweisen Sie eine benutzerdefinierte App-Setuprichtlinie im Microsoft Teams Admin Center, wobei die Einstellung **Benutzerdefinierte Apps hochladen** aktiviert ist, und weisen Sie sie den Teambesitzern zu.

|Organisationsweite Einstellung für benutzerdefinierte Apps |Teameinstellung für benutzerdefinierte Apps |Benutzerrichtlinie für benutzerdefinierte Apps |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams-Dienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams-Dienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams-Dienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können Windows PowerShell verwenden, um benutzerdefinierte Apps zu löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams-Dienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann keine benutzerdefinierten Apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte Apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, kann er keine benutzerdefinierten Apps in das Team hochladen. Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann keine benutzerdefinierten Apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte Apps in das Team hochladen, unabhängig davon, ob er ein Teambesitzer ist. Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen.       |

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies-users-and-groups.md)
