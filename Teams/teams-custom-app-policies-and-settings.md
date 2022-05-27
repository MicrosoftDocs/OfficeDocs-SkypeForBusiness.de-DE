---
title: Verwalten von benutzerdefinierten App-Richtlinien und -Einstellungen
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
description: Erfahren Sie, wie Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwalten, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681386"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!NOTE]
> Wenn Sie App Studio verwenden möchten, sehen Sie [sich Erste Schritte auf der Microsoft Teams-Plattform mit C#/.NET und App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) an. Der letzte Schritt funktioniert noch nicht. Daher müssen Sie die ZIP-Datei herunterladen und auf die alte Weise bei [Hochladen einem App-Paket installieren, um Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).

Als Administrator können Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann. Administratoren entscheiden, welche Benutzer benutzerdefinierte Apps hochladen können, und Administratoren und Teambesitzer können bestimmen, ob bestimmte Teams in Ihrer Organisation benutzerdefinierte Apps hinzufügen können.  Nachdem Sie die benutzerdefinierte App-Richtlinie bearbeitet haben, kann es einige Stunden dauern, bis Änderungen wirksam werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte Apps

Benutzer können eine benutzerdefinierte App zu Teams hinzufügen, indem sie ein App-Paket (in einer .zip Datei) direkt in ein Team oder im persönlichen Kontext hochladen. Dies unterscheidet sich von der Vorgehensweise, wie Apps über den Teams App Store hinzugefügt werden. Wenn Sie eine benutzerdefinierte App hinzufügen, indem Sie ein App-Paket hochladen, das auch als Querladen bezeichnet wird, können Sie eine App während der Entwicklung testen, bevor sie für die breite Verteilung bereit ist. Außerdem können Sie eine App nur für die interne Verwendung erstellen und für Ihr Team freigeben, ohne sie an den Teams App-Katalog im Teams App Store zu übermitteln.

![Screenshot, der das Hochladen einer benutzerdefinierten App-Option im App Store zeigt.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Benutzerdefinierte App-Richtlinie und -Einstellungen

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte App in ein Team hochladen kann, wodurch Sie präzise steuern können, wer benutzerdefinierte Apps zu einem Team hinzufügen kann und welche benutzerdefinierten Teams-Apps hinzugefügt werden können:

- [Benutzerdefinierte App-Richtlinie](#user-custom-app-policy)
- [Benutzerdefinierte Team-App-Einstellung](#team-custom-app-setting)
- [Organisationsweite benutzerdefinierte App-Einstellung](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit aus, Apps von Drittanbietern zu blockieren.  

### <a name="user-custom-app-policy"></a>Benutzerdefinierte App-Richtlinie

Im Rahmen von [App-Setuprichtlinien](teams-app-setup-policies.md) können Administratoren eine Richtlinieneinstellung **Hochladen benutzerdefinierte Apps** verwenden, um zu steuern, ob ein Benutzer benutzerdefinierte Apps in Teams hochladen kann.

Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierte App in ein Team in Ihrer Organisation oder im persönlichen Kontext hochladen.
- Der Benutzer kann abhängig von der organisationsweiten Benutzerdefinierten App-Einstellung mit benutzerdefinierten Apps interagieren.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann benutzerdefinierte Apps in Teams hochladen, die dies zulassen, und in Teams, für die er Besitzer ist, abhängig von der organisationsweiten benutzerdefinierten App-Einstellung.
- Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen.
- Der Benutzer kann abhängig von der organisationsweiten Benutzerdefinierten App-Einstellung mit benutzerdefinierten Apps interagieren.

Sie können die Einstellungen in der globalen App-Setuprichtlinie bearbeiten, um die gewünschten Apps einzuschließen. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen und weisen Sie eine oder mehrere benutzerdefinierte App-Setuprichtlinien zu.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer benutzerdefinierten App-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Einrichtungsrichtlinien**.
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie **Hochladen benutzerdefinierte Apps**.
4. Wählen Sie alle anderen Einstellungen aus, die Sie für die Richtlinie verwenden möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Benutzerdefinierte Team-App-Einstellung

Administratoren und Teambesitzer können steuern, ob ein Team das Hinzufügen benutzerdefinierter Apps zulässt. Diese Einstellung, **Mitgliedern das Hochladen benutzerdefinierter Apps** erlauben, bestimmt zusammen mit der benutzerdefinierten App-Richtlinie eines Benutzers, wer benutzerdefinierte Apps zu einem bestimmten Team hinzufügen kann.

Wenn diese Einstellung deaktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn die benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten Apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der benutzerdefinierten Team-App-Einstellung

1. Wechseln Sie in Teams zum Team, klicken Sie auf **"Weitere Optionen" ...** >  **Team verwalten**.
2. Klicken Sie auf **Einstellungen**, und erweitern Sie dann die **Mitgliederberechtigungen**.
3. Aktivieren oder deaktivieren Sie das Kontrollkästchen " **Mitgliedern das Hochladen benutzerdefinierter Apps erlauben** ".

    ![Screenshot der benutzerdefinierten Team-App-Einstellung.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite benutzerdefinierte App-Einstellung

Die Einstellung " **Interaktion mit benutzerdefinierten Apps** organisationsweit zulassen" auf der Seite ["Apps verwalten](manage-apps.md) " gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie benutzerdefinierte Apps hochladen oder mit ihnen interagieren können. Diese Einstellung fungiert als Master-Ein-/Aus-Schalter für die benutzerdefinierten App-Richtlinieneinstellungen des Benutzers und des Teams. Es soll als Master-Ein-/Aus-Schalter während Sicherheitsereignissen dienen. Daher werden benutzerdefinierte App-Richtlinieneinstellungen für Benutzer und Teams erst wirksam, wenn die organisationsweite benutzerdefinierte App-Einstellung aktiviert ist, auch wenn benutzerdefinierte App-Richtlinieneinstellungen für Benutzer und Teams aktiviert sind.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten Einstellung für benutzerdefinierte Apps

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie auf **Organisationsweite App-Einstellungen**.
3. Aktivieren oder deaktivieren Sie unter **"Benutzerdefinierte Apps**" **die Option "Interaktion mit benutzerdefinierten Apps zulassen**".

    ![Screenshot der organisationsweiten benutzerdefinierten App-Einstellungen.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Zusammenarbeit von benutzerdefinierten App-Richtlinien und -Einstellungen

Diese Tabelle enthält eine Zusammenfassung der benutzerdefinierten App-Richtlinie und -Einstellungen, ihrer Zusammenarbeit und ihrer kombinierten Auswirkungen auf die Steuerung, wer in Ihrer Organisation benutzerdefinierte Apps in Teams hochladen kann.

Angenommen, Sie möchten beispielsweise zulassen, dass nur Teambesitzer benutzerdefinierte Apps in bestimmte Teams hochladen. Sie würden Folgendes festlegen:

- Aktivieren Sie die Einstellung "**Interaktion mit benutzerdefinierten Apps zulassen**" im Microsoft Teams Admin Center.
- Deaktivieren Sie die Option **"Mitgliedern das Hochladen benutzerdefinierter Apps** für jedes Team erlauben", für das Sie den Zugriff einschränken möchten.
- Erstellen und Zuweisen einer benutzerdefinierten App-Setuprichtlinie im Microsoft Teams Admin Center mit aktivierter **Einstellung für Hochladen benutzerdefinierten Apps** und Zuweisen zu den Teambesitzern.

|Organisationsweite benutzerdefinierte App-Einstellung |Benutzerdefinierte Team-App-Einstellung |Benutzerdefinierte App-Richtlinie |Wirkung  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams Service-Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams Service-Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams Service-Admin oder einem globalen Administrator hochgeladen werden. Sie können Windows PowerShell verwenden, um benutzerdefinierte Apps zu löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teams Service-Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann keine benutzerdefinierten Apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte Apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, kann er keine benutzerdefinierten Apps in das Team hochladen. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann keine benutzerdefinierten Apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte Apps in das Team hochladen, unabhängig davon, ob der Benutzer ein Teambesitzer ist. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.       |

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies-users-and-groups.md)
