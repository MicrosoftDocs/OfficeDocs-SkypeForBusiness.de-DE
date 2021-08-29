---
title: Verwalten von Richtlinien und Einstellungen für benutzerdefinierte Apps
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
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
description: Erfahren Sie, wie Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwalten, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Ihrem Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: c00c06f86e55ed0f2c8b28315c6d83cc36ef3c25
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58634829"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!NOTE]
> Informationen zur Verwendung von App Studio finden Sie unter Erste Schritte auf der Microsoft Teams-Plattform mit [C#/.NET](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) und App Studio Der letzte Schritt funktioniert noch nicht. Daher müssen Sie die ZIP-Datei herunterladen und auf die alte Weise installieren Hochladen einem App-Paket, um Microsoft Teams [zu installieren.](/microsoftteams/platform/concepts/apps/apps-upload)

Als Administrator können Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps auf Ihre Microsoft Teams. Administratoren entscheiden, welche Benutzer benutzerdefinierte Apps hochladen können, und Administratoren und Teambesitzer können bestimmen, ob bestimmte Teams in Ihrer Organisation benutzerdefinierte Apps hinzufügen dürfen.  Nachdem Sie die Benutzerdefinierte App-Richtlinie bearbeitet haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte Apps

Benutzer können einer App eine benutzerdefinierte Teams hinzufügen, indem sie ein App-Paket (in einer .zip-Datei) direkt in ein Team oder im persönlichen Kontext hochladen. Dies ist anders als das Hinzufügen von Apps Teams App Store. Durch Das Hinzufügen einer benutzerdefinierten App durch Hochladen eines App-Pakets, das auch als Querladen bezeichnet wird, können Sie eine App während der Entwicklung testen, bevor sie für die breite Verteilung bereit ist. Außerdem können Sie eine App nur für interne Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Teams-App-Katalog im Teams-App Store zu übermitteln.

![Screenshot mit der Option "Benutzerdefinierte App hochladen" im App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Richtlinien und Einstellungen für benutzerdefinierte Apps

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte App in ein Team hochladen kann, wodurch Sie präzise steuern können, wer einem Team benutzerdefinierte Apps hinzufügen kann und zu welchen teams benutzerdefinierten Apps hinzugefügt werden kann:

- [Richtlinie für benutzerdefinierte Benutzer-Apps](#user-custom-app-policy)
- [Einstellung für benutzerdefinierte Team-Apps](#team-custom-app-setting)
- [Organisationsweite Einstellung für benutzerdefinierte Apps](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit zum Blockieren von Drittanbieter-Apps aus.  

### <a name="user-custom-app-policy"></a>Richtlinie für benutzerdefinierte Benutzer-Apps

Im Rahmen [von](teams-app-setup-policies.md)Richtlinien für das Einrichten von Apps können Administratoren mithilfe einer Richtlinieneinstellung **Hochladen** benutzerdefinierten Apps steuern, ob ein Benutzer benutzerdefinierte Apps auf Teams.
 
Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierte App in ein Team in Ihrer Organisation oder im persönlichen Kontext hochladen.
- Abhängig von der organisationsweiten Einstellung der benutzerdefinierten App kann der Benutzer mit benutzerdefinierten Apps interagieren.

Wenn diese Einstellung aktiviert ist:

- Abhängig von der organisationsweiten Einstellung für benutzerdefinierte Apps kann der Benutzer benutzerdefinierte Apps in Teams hochladen, die dies zulassen, und in Teams, deren Besitzer sie sind.
- Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen. 
- Abhängig von der organisationsweiten Einstellung der benutzerdefinierten App kann der Benutzer mit benutzerdefinierten Apps interagieren.

Sie können die Einstellungen in der globalen App-Setuprichtlinie bearbeiten und die von Ihnen verwendeten Apps enthalten. Wenn Sie Einstellungen für Teams Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen Sie eine oder mehrere benutzerdefinierte App-Setuprichtlinien, und weisen Sie sie zu.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer Benutzerdefinierten Benutzer-App-Richtlinie

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu Richtlinien **Teams**  >  **Apps.**
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie Hochladen **Benutzerdefinierte Apps.**
4. Wählen Sie alle anderen Einstellungen aus, die Sie für die Richtlinie verwenden möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Einstellung für benutzerdefinierte Team-Apps

Administratoren und Teambesitzer können steuern, ob ein Team das Hinzufügen benutzerdefinierter Apps zulässt. Diese **Einstellung,** Zulassen, dass Mitglieder benutzerdefinierte Apps hochladen, und die benutzerdefinierte App-Richtlinie eines Benutzers bestimmt, wer einem bestimmten Team benutzerdefinierte Apps hinzufügen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, sofern ihre Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten Apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der Einstellung für die benutzerdefinierte Team-App

1. Wechseln Teams Team, und klicken Sie auf **Weitere Optionen**  >  
2. Klicken **Einstellungen** auf , und erweitern Sie **dann Mitgliedsberechtigungen**.
3. Aktivieren oder aktivieren Sie das **Kontrollkästchen Mitgliedern das Hochladen benutzerdefinierter Apps** erlauben.

    ![Screenshot der Einstellung für die benutzerdefinierte Team-App](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite Einstellung für benutzerdefinierte Apps

Die **Einstellung Interaktion mit benutzerdefinierten** Benutzerdefinierten Apps zulassen auf der Seite Apps verwalten gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie benutzerdefinierte Apps hochladen oder damit interagieren können. [](manage-apps.md) Diese Einstellung fungiert als Master-Ein-/Ausschalter für die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps. Er soll als Master-Ein-/Ausschalter bei Sicherheitsereignissen dienen. Die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps werden nur wirksam, wenn die organisationsweite Einstellung für benutzerdefinierte Apps aktiviert ist, auch wenn die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps aktiviert sind.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten Einstellung für benutzerdefinierte Apps

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken **Sie auf Organisationsweite App-Einstellungen**.
3. Aktivieren **oder deaktivieren** Sie unter Benutzerdefinierte Apps das Bzw. die Deaktivieren von Interaktion mit **benutzerdefinierten Apps zulassen.**

    ![Screenshot der organisationsweiten benutzerdefinierten App-Einstellungen](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Wie benutzerdefinierte App-Richtlinien und -Einstellungen zusammenarbeiten

In dieser Tabelle sind die benutzerdefinierten App-Richtlinien und -Einstellungen, ihre Kombination und ihre kombinierte Auswirkung auf die Steuerung, wer in Ihrer Organisation benutzerdefinierte Apps auf Ihre App hochladen kann, Teams.

Sie möchten beispielsweise zulassen, dass nur Teambesitzer benutzerdefinierte Apps in bestimmte Teams hochladen können. Sie würden folgendes festlegen:

- Aktivieren Sie die **Einstellung Interaktion mit benutzerdefinierten Apps zulassen** im Microsoft Teams Admin Center.
- Deaktivieren Sie das **Deaktivieren von Mitgliedern das Hochladen benutzerdefinierter Apps für** jedes Team erlauben, auf das Sie den Zugriff einschränken möchten.
- Erstellen und zuweisen Sie im Microsoft Teams Admin Center eine benutzerdefinierte App-Setuprichtlinie, bei der die **Einstellung Hochladen** benutzerdefinierte Apps aktiviert ist, und weisen Sie sie den Teambesitzern zu.

|Organisationsweite Einstellung für benutzerdefinierte Apps |Einstellung für benutzerdefinierte Team-Apps |Richtlinie für benutzerdefinierte Benutzer-Apps |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem mit Ausnahme eines Teams dienstadministrators oder eines globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem mit Ausnahme eines Teams dienstadministrators oder eines globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem mit Ausnahme eines Dienstadministrators oder eines globalen Teams hochgeladen werden. Sie können Benutzerdefinierte Windows PowerShell mithilfe von Benutzerdefinierten Apps löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem mit Ausnahme eines Teams dienstadministrators oder eines globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann keine benutzerdefinierten Apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte Apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, kann er keine benutzerdefinierten Apps in das Team hochladen. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann keine benutzerdefinierten Apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte Apps in das Team hochladen, unabhängig davon, ob es sich bei dem Benutzer um einen Teambesitzer handelt. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.       |

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies-users-and-groups.md)