---
title: Verwalten von benutzerdefinierten App-Richtlinien und -Einstellungen
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
localization_priority: Normal
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
ms.openlocfilehash: e89a7aa3a2d016551695406551068cd07a2042e6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119214"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!NOTE]
> Informationen zur Verwendung von App Studio finden Sie unter Erste Schritte auf der Microsoft Teams-Plattform mit [C#/.NET](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) und App Studio Der letzte Schritt funktioniert noch nicht, daher müssen Sie die ZIP herunterladen und auf die alte Weise unter Hochladen eines App-Pakets in [Microsoft Teams installieren.](/microsoftteams/platform/concepts/apps/apps-upload)

Als Administrator können Sie benutzerdefinierte App-Richtlinien und -Einstellungen verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann. Administratoren entscheiden, welche Benutzer benutzerdefinierte Apps hochladen können, und Administratoren und Teambesitzer können bestimmen, ob bestimmte Teams in Ihrer Organisation zulassen, dass ihnen benutzerdefinierte Apps hinzugefügt werden.  Nachdem Sie die benutzerdefinierte App-Richtlinie bearbeitet haben, kann es einige Stunden dauern, bis Änderungen wirksam werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte Apps

Benutzer können eine benutzerdefinierte App zu Teams hinzufügen, indem sie ein App-Paket (in einer ZIP-Datei) direkt in ein Team oder in den persönlichen Kontext hochladen. Dies ist anders als das Hinzufügen von Apps über den Teams-App-Store. Wenn Sie eine benutzerdefinierte App hinzufügen, indem Sie ein App-Paket hochladen, das auch als Querladen bezeichnet wird, können Sie eine App während der Entwicklung testen, bevor sie weit verbreitet werden kann. Außerdem können Sie eine App nur für die interne Verwendung erstellen und für Ihr Team freigeben, ohne sie im Teams App Store an den Teams-App-Katalog zu übermitteln.

![Screenshot mit der Option zum Hochladen einer benutzerdefinierten App im App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Richtlinien und Einstellungen für benutzerdefinierte Apps

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte App in ein Team hochladen kann, wodurch Sie präzise steuern können, wer einem Team benutzerdefinierte Apps hinzufügen kann und zu welchen Teams benutzerdefinierte Apps hinzugefügt werden können:

- [Benutzerdefinierte Benutzer-App-Richtlinie](#user-custom-app-policy)
- [Einstellung der benutzerdefinierten Team-App](#team-custom-app-setting)
- [Organisationsweite Benutzerdefinierte App-Einstellung](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit aus, Apps von Drittanbietern zu blockieren.  

### <a name="user-custom-app-policy"></a>Benutzerdefinierte Benutzer-App-Richtlinie

Im Rahmen der [Richtlinien für die](teams-app-setup-policies.md)App-Einrichtung können Administratoren eine Richtlinieneinstellung , benutzerdefinierte Apps **hochladen,** verwenden, um zu steuern, ob ein Benutzer benutzerdefinierte Apps in Teams hochladen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierte App in ein Team in Ihrer Organisation oder im persönlichen Kontext hochladen.
- Der Benutzer kann abhängig von der organisationsweiten Einstellung der benutzerdefinierten App mit benutzerdefinierten Apps interagieren.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann benutzerdefinierte Apps in Teams hochladen, die dies zulassen, und in Teams, deren Besitzer er ist, abhängig von der organisationsweiten Einstellung der benutzerdefinierten App.
- Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen. 
- Der Benutzer kann abhängig von der organisationsweiten Einstellung der benutzerdefinierten App mit benutzerdefinierten Apps interagieren.

Sie können die Einstellungen in der globalen Einrichtungsrichtlinie für Apps bearbeiten, um die apps, die Sie wünschen, zu enthalten. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen und weisen Sie eine oder mehrere benutzerdefinierte App-Setuprichtlinien zu.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer benutzerdefinierten Benutzer-App-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Setuprichtlinien für Teams-Apps.**  >  
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie benutzerdefinierte **Apps hochladen.**
4. Wählen Sie alle anderen Einstellungen aus, die Sie für die Richtlinie verwenden möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Einstellung der benutzerdefinierten Team-App

Administratoren und Teambesitzer können steuern, ob ein Team zulässt, dass benutzerdefinierte Apps hinzugefügt werden. Mit dieser **Einstellung** können Mitglieder benutzerdefinierte Apps hochladen sowie die benutzerdefinierte App-Richtlinie eines Benutzers bestimmen, wer einem bestimmten Team benutzerdefinierte Apps hinzufügen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn die benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten Apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn die benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte Apps hinzufügen, wenn die benutzerdefinierte App-Richtlinie dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der benutzerdefinierten Team-App-Einstellung

1. Wechseln Sie in Teams zum Team, klicken Sie auf **Weitere Optionen**  >  
2. Klicken **Sie auf** Einstellungen , und erweitern Sie dann die Berechtigungen für **Mitglieder.**
3. Aktivieren oder löschen Sie das **Kontrollkästchen Mitglieder zum Hochladen benutzerdefinierter Apps** zulassen.

    ![Screenshot mit der Einstellung der benutzerdefinierten Team-App](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite Benutzerdefinierte App-Einstellung

Die **Organisationsweite** Einstellung Interaktion mit benutzerdefinierten [](manage-apps.md) Apps zulassen auf der Seite Apps verwalten gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie benutzerdefinierte Apps hochladen oder mit benutzerdefinierten Apps interagieren können. Diese Einstellung fungiert als Master-Ein-/Aus-Schalter für die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps. Er soll als Master-Ein-/Aus-Schalter bei Sicherheitsereignissen dienen. Benutzer- und Teamrichtlinieneinstellungen für benutzerdefinierte Apps werden nur wirksam, wenn die organisationsweite Einstellung für benutzerdefinierte Apps aktiviert ist, auch wenn die Richtlinieneinstellungen für benutzer- und teamspezifische Apps aktiviert sind.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten Benutzerdefinierten App-Einstellung

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.
2. Klicken Sie **auf Organisationsweite App-Einstellungen.**
3. Aktivieren **oder deaktivieren** Sie unter Benutzerdefinierte Apps die Interaktion mit **benutzerdefinierten Apps zulassen.**

    ![Screenshot der organisationsweiten benutzerdefinierten App-Einstellungen](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Zusammenarbeit von benutzerdefinierten App-Richtlinien und -Einstellungen

In dieser Tabelle werden die benutzerdefinierten App-Richtlinien und -Einstellungen, die Zusammenarbeit und deren kombinierte Auswirkung auf die Kontrolle zusammengefasst, wer in Ihrer Organisation benutzerdefinierte Apps in Teams hochladen kann.

Beispielsweise möchten Sie es nur Teambesitzern ermöglichen, benutzerdefinierte Apps in bestimmte Teams hochzuladen. Sie würden Folgendes festlegen:
- Aktivieren Sie die Einstellung **Interaktion mit benutzerdefinierten Apps zulassen** im Microsoft Teams Admin Center.
- Deaktivieren Sie die **Möglichkeit, dass Mitglieder benutzerdefinierte Apps für** jedes Team hochladen, auf das Sie den Zugriff einschränken möchten.
- Erstellen und Zuweisen einer benutzerdefinierten App-Setuprichtlinie im Microsoft Teams Admin Center mit aktivierter Einstellung **Benutzerdefinierte** Apps hochladen, und weisen Sie sie den Teambesitzern zu.

|Organisationsweite Benutzerdefinierte App-Einstellung |Einstellung der benutzerdefinierten Team-App |Benutzerdefinierte Benutzer-App-Richtlinie |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teamdienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teamdienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teamdienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können Windows PowerShell verwenden, um benutzerdefinierte Apps zu löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation blockiert. Benutzerdefinierte Apps können nur von einem Teamdienstadministrator oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann keine benutzerdefinierten Apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte Apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, kann er keine benutzerdefinierten Apps in das Team hochladen. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann keine benutzerdefinierten Apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte Apps in das Team hochladen, unabhängig davon, ob der Benutzer ein Teambesitzer ist. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.       |

## <a name="related-topics"></a>Verwandte Themen
 
[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](assign-policies.md)