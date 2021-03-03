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
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie benutzerdefinierte Richtlinien und Einstellungen für Apps verwalten, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821005"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!NOTE]
> Informationen zur Verwendung von App Studio finden Sie unter "Erste Schritte auf der Microsoft #A0 mit [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) und App Studio". Der letzte Schritt funktioniert noch nicht. Sie müssen also die #A1 herunterladen und auf die alte Art unter "Hochladen eines #A2 in [Microsoft Teams"](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)installieren.

Als Administrator können Sie benutzerdefinierte Richtlinien und Einstellungen für Apps verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte Apps in Microsoft Teams hochladen kann. Administratoren entscheiden, welche Benutzer benutzerdefinierte Apps hochladen können, und Administratoren und Teambesitzer können bestimmen, ob bestimmte Teams in Ihrer Organisation das Hinzufügen von benutzerdefinierten Apps zulassen.  Nach dem Bearbeiten der benutzerdefinierten App-Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte Apps

Benutzer können eine benutzerdefinierte App zu Teams hinzufügen, indem sie ein App-Paket (in einer ZIP-Datei) direkt in ein Team oder im persönlichen Kontext hochladen. Dies ist anders als die Art, in der Apps über den Teams App Store hinzugefügt werden. Durch das Hinzufügen einer benutzerdefinierten App durch Hochladen eines App-Pakets, das auch als Querladen bezeichnet wird, können Sie eine App während der Entwicklung testen, bevor sie für eine breite Verteilung bereit ist. Außerdem können Sie eine App nur für interne Nutzung erstellen und für Ihr Team freigeben, ohne sie an den Teams-App-Katalog im Teams App Store zu übermitteln.

![Screenshot der Option zum Hochladen einer benutzerdefinierten App im App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Richtlinie und Einstellungen für benutzerdefinierte Apps

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte App in ein Team hochladen kann, wodurch Sie präzise steuern können, wer einem Team benutzerdefinierte Apps hinzufügen kann und zu welchen Teams benutzerdefinierte Apps hinzugefügt werden können:

- [Benutzerdefinierte Benutzer-App-Richtlinie](#user-custom-app-policy)
- [Benutzerdefinierte Team-App-Einstellung](#team-custom-app-setting)
- [Organisationsweite Einstellung für benutzerdefinierte Apps](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit zum Blockieren von Apps von Drittanbietern aus.  

### <a name="user-custom-app-policy"></a>Benutzerdefinierte Benutzer-App-Richtlinie

Im Rahmen von Richtlinien [für](teams-app-setup-policies.md)das Einrichten von Apps können Administratoren mithilfe der Richtlinieneinstellung **"Benutzerdefinierte** Apps hochladen" steuern, ob ein Benutzer benutzerdefinierte Apps in Teams hochladen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierte App in ein Team in Ihrer Organisation oder im persönlichen Kontext hochladen.
- Abhängig von der organisationsweiten Einstellung der benutzerdefinierten App kann der Benutzer mit benutzerdefinierten Apps interagieren.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann – je nach organisationsweiter Einstellung der benutzerdefinierten App – benutzerdefinierte Apps in Teams hochladen, die dies zulassen, und in Teams, deren Besitzer sie sind.
- Der Benutzer kann benutzerdefinierte Apps in den persönlichen Kontext hochladen. 
- Abhängig von der organisationsweiten Einstellung der benutzerdefinierten App kann der Benutzer mit benutzerdefinierten Apps interagieren.

Sie können die Einstellungen in der globalen Einrichtungsrichtlinie für Apps bearbeiten, um die apps, die Sie wünschen, enthalten zu können. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen und weisen Sie eine oder mehrere benutzerdefinierte Richtlinien für die Einrichtung von Apps zu.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer benutzerdefinierten Benutzer-App-Richtlinie

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den Setuprichtlinien **für**  >  **Teams-Apps.**
2. Klicken Sie auf **Hinzufügen**.
3. Aktivieren oder deaktivieren Sie **"Benutzerdefinierte Apps hochladen".**
4. Wählen Sie alle anderen Einstellungen aus, die Sie für die Richtlinie verwenden möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Benutzerdefinierte Team-App-Einstellung

Administratoren und Teambesitzer können steuern, ob einem Team benutzerdefinierte Apps hinzugefügt werden dürfen. Diese **Einstellung,**"Mitgliedern das Hochladen benutzerdefinierter Apps erlauben" sowie die benutzerdefinierte App-Richtlinie eines Benutzers bestimmen, wer einem bestimmten Team benutzerdefinierte Apps hinzufügen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten Apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Teambesitzer können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte Apps hinzufügen, wenn ihre benutzerdefinierte App-Richtlinie dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der Benutzerdefinierten Team-App-Einstellung

1. Wechseln Sie in Teams zum Team, und klicken Sie auf **"Weitere Optionen"**  >  
2. Klicken Sie **auf "Einstellungen",** und erweitern Sie dann **die Mitgliedsberechtigungen.**
3. Aktivieren oder aktivieren Sie das **Kontrollkästchen "Mitgliedern das Hochladen benutzerdefinierter Apps erlauben".**

    ![Screenshot der Benutzerdefinierten Team-App-Einstellung](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite Einstellung für benutzerdefinierte Apps

Die **Einstellung "Interaktion mit** benutzerdefinierten Apps [](manage-apps.md) organisationsweit zulassen" auf der Seite "Apps verwalten" gilt für alle Benutzer in Ihrer Organisation und bestimmt, ob sie benutzerdefinierte Apps hochladen oder damit interagieren können. Diese Einstellung fungiert als Master-Ein/Aus-Schalter für die Richtlinieneinstellungen der benutzerdefinierten Benutzer- und Team-App. Er soll als Master-Ein/Aus-Schalter bei Sicherheitsereignissen dienen. Die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps werden nur wirksam, wenn die organisationsweite Einstellung für benutzerdefinierte Apps aktiviert ist, auch wenn die Richtlinieneinstellungen für benutzerdefinierte Benutzer- und Team-Apps aktiviert sind.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten Einstellung für benutzerdefinierte Apps

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Apps**  >  **verwalten".**
2. Klicken Sie **auf "Organisationsweite App-Einstellungen".**
3. Aktivieren **oder deaktivieren** Sie unter "Benutzerdefinierte Apps" die "Interaktion mit **benutzerdefinierten Apps zulassen".**

    ![Screenshot der organisationsweiten benutzerdefinierten App-Einstellungen](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Zusammenarbeit von Richtlinien und Einstellungen für benutzerdefinierte Apps

In dieser Tabelle sind die benutzerdefinierten Richtlinien und Einstellungen für Apps, ihre Zusammenarbeit und ihre kombinierte Auswirkung auf die Steuerung zusammengefasst, wer in Ihrer Organisation benutzerdefinierte Apps in Teams hochladen kann.

Sie möchten beispielsweise zulassen, dass nur Teambesitzer benutzerdefinierte Apps in bestimmte Teams hochladen können. Sie würden Folgendes festlegen:
- Aktivieren Sie die Einstellung **"Interaktion mit benutzerdefinierten Apps zulassen"** im Microsoft Teams Admin Center.
- Deaktivieren Sie "Mitgliedern **das Hochladen benutzerdefinierter Apps für** jedes Team erlauben", für das Sie den Zugriff einschränken möchten.
- Erstellen und weisen Sie im Microsoft Teams Admin  Center mit aktivierter Einstellung "Benutzerdefinierte Apps hochladen" eine benutzerdefinierte App-Setuprichtlinie zu, und weisen Sie sie den Teambesitzern zu.

|Organisationsweite Einstellung für benutzerdefinierte Apps |Benutzerdefinierte Team-App-Einstellung |Benutzerdefinierte Benutzer-App-Richtlinie |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem außer einem Teams Service Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem außer einem Teams Service Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem außer einem Teams Service Admin oder einem globalen Administrator hochgeladen werden. Mithilfe von Windows PowerShell können Sie benutzerdefinierte Apps löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps wird für Ihre Organisation blockiert. Benutzerdefinierte Apps können von niemandem außer einem Teams Service Admin oder einem globalen Administrator hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte App zu entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann keine benutzerdefinierten Apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte Apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, kann er keine benutzerdefinierten Apps in das Team hochladen. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann keine benutzerdefinierten Apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte Apps in das Team hochladen, unabhängig davon, ob es sich bei dem Benutzer um einen Teambesitzer handelt. Der Benutzer kann benutzerdefinierte Apps im persönlichen Kontext hochladen.       |

## <a name="related-topics"></a>Verwandte Themen
 
[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)