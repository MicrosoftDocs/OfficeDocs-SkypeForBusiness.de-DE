---
title: Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie benutzerdefinierte App-Richtlinien und-Einstellungen verwalten, um zu steuern, wer in Ihrer Organisation benutzerdefinierte apps in Microsoft Teams hochladen kann.
ms.openlocfilehash: c1aa7489761fb27f525fbb6eb8f2056ae3dd33c8
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548661"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> Die aktuelle Methode zum Verwalten von apps in Microsoft Teams finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).

Als Administrator können Sie benutzerdefinierte App-Richtlinien und-Einstellungen verwenden, um zu steuern, wer in Ihrer Organisation benutzerdefinierte apps in Microsoft Teams hochladen kann. Administratoren entscheiden, welche Benutzer benutzerdefinierte apps hochladen können, und Administratoren und Teambesitzer können ermitteln, ob bestimmte Teams in Ihrer Organisation benutzerdefinierte apps hinzufügen dürfen.  

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte apps

Benutzer können Teams eine benutzerdefinierte app hinzufügen, indem Sie ein App-Paket (in einer ZIP-Datei) direkt in ein Team oder in den persönlichen Kontext hochladen. Dies unterscheidet sich von der Art, wie apps im App Store von Teams hinzugefügt werden. Durch das Hinzufügen einer benutzerdefinierten app durch Hochladen eines App-Pakets, auch bekannt als Sideloading, können Sie eine APP testen, während Sie entwickelt wird, bevor Sie für eine breite Verbreitung bereit steht. Darüber hinaus können Sie eine app nur für die interne Verwendung erstellen und Sie für Ihr Team freigeben, ohne Sie im Teams-App-Shop im Teams-App-Katalog zu übermitteln.

![Screenshot mit der Option "benutzerdefinierte App hochladen" im App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Benutzerdefinierte App-Richtlinien und-Einstellungen

Drei Komponenten legen fest, ob ein Benutzer eine benutzerdefinierte app in ein Team hochladen kann, und gibt Ihnen eine granulare Kontrolle darüber, wer benutzerdefinierte apps zu einem Team hinzufügen kann und welche benutzerdefinierten apps in Teams hinzugefügt werden können:

- [Benutzerdefinierte App-Richtlinie](#user-custom-app-policy)
- [Einstellung für benutzerdefinierte Team-App](#team-custom-app-setting)
- [Organisationsweite benutzerdefinierte app-Einstellung](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit aus, Drittanbieter-apps zu blockieren.  

### <a name="user-custom-app-policy"></a>Benutzerdefinierte App-Richtlinie

Als Teil der [App-Setup Richtlinien](teams-app-setup-policies.md)können Administratoren eine Richtlinieneinstellung verwenden, das **Hochladen benutzerdefinierter apps ermöglichen**, um zu steuern, ob Benutzer benutzerdefinierte apps in Teams hochladen können.
 
Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann keine benutzerdefinierte app in ein beliebiges Team in Ihrer Organisation oder im persönlichen Kontext hochladen.
- Der Benutzer kann mit benutzerdefinierten apps interagieren, je nach der organisationsweiten benutzerdefinierten app-Einstellung.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann benutzerdefinierte apps in Teams hochladen, die dies zulassen, und für Teams, deren Besitzer Sie sind, je nach der organisationsweiten benutzerdefinierten app-Einstellung.
- Der Benutzer kann benutzerdefinierte apps in den persönlichen Kontext hochladen. 
- Der Benutzer kann mit benutzerdefinierten apps interagieren, je nach der organisationsweiten benutzerdefinierten app-Einstellung.

Sie können die Einstellungen in der globalen App-Setup Richtlinie bearbeiten, um die gewünschten apps einzubeziehen. Wenn Sie Teams für verschiedene Benutzergruppen in Ihrer Organisation anpassen möchten, erstellen Sie eine oder mehrere benutzerdefinierte App-Setup Richtlinien, und weisen Sie diese zu.

#### <a name="set-a-user-custom-app-policy"></a>Festlegen einer benutzerdefinierten App-Richtlinie

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Setup Richtlinien**für **Teams-apps** > .
2. Wählen Sie **neue Richtlinie**aus.
3. Aktivieren oder deaktivieren Sie das **Hochladen benutzerdefinierter apps zulassen**.
4. Wählen Sie alle anderen Einstellungen aus, die für die Richtlinie gelten sollen.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Einstellung für benutzerdefinierte Team-App

Administratoren und Teambesitzer können steuern, ob ein Team benutzerdefinierte apps hinzugefügt werden kann. Mit dieser Einstellung können **Mitglieder benutzerdefinierte apps hochladen**, zusammen mit der benutzerdefinierten App-Richtlinie bestimmt, wer benutzerdefinierte apps zu einem bestimmten Team hinzufügen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Team Besitzer können benutzerdefinierte apps hinzufügen, wenn deren benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können dem Team keine benutzerdefinierten apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Team Besitzer können benutzerdefinierte apps hinzufügen, wenn deren benutzerdefinierte App-Richtlinie dies zulässt.
- Teammitglieder, die keine Teambesitzer sind, können benutzerdefinierte apps hinzufügen, wenn deren benutzerdefinierte App-Richtlinie dies zulässt.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren der Einstellung für die benutzerdefinierte Team-App

1. Wechseln Sie in Microsoft Teams zum Team, klicken Sie auf **Weitere Optionen ̇ ̇ ̇** > **Team verwalten**.
2. Klicken Sie auf **Einstellungen**, und erweitern Sie dann **Mitglieder Berechtigungen**.
3. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Mitglieder können benutzerdefinierte apps hochladen** .

    ![Screenshot mit der Einstellung "benutzerdefinierte App für Team"](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Organisationsweite benutzerdefinierte app-Einstellung

Die organisationsweite benutzerdefinierte app-Einstellung, die **Interaktion mit benutzerdefinierten Apps ermöglicht**, gilt für alle Personen in Ihrer Organisation und steuert, ob Sie benutzerdefinierte apps hochladen oder mit ihnen interagieren können. Diese Einstellung überschreibt die Benutzer-und Team benutzerdefinierte App-Richtlinie und-Einstellung. Es dient als Master-on/off-Schalter während Sicherheitsereignissen.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren der organisationsweiten benutzerdefinierten app-Einstellung

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps** > -**Berechtigungsrichtlinien**.
2. Klicken Sie auf **organisationsweite App-Einstellungen**.
3. Aktivieren oder deaktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**.

    ![Screenshot mit den organisationsweiten benutzerdefinierten App-Einstellungen](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Zusammenarbeit von benutzerdefinierten App-Richtlinien und-Einstellungen

In dieser Tabelle werden die benutzerdefinierten App-Richtlinien und-Einstellungen, ihre Zusammenarbeit und ihre kombinierte Auswirkung auf die Steuerung der Personen in Ihrer Organisation, die benutzerdefinierte apps in Teams hochladen können, zusammengefasst.

Angenommen, Sie möchten nur Teambesitzern gestatten, benutzerdefinierte apps in bestimmte Teams hochzuladen. Sie würden folgendes einrichten:
- Aktivieren Sie im Microsoft Teams Admin Center die Einstellung **Interaktion mit benutzerdefinierten apps zulassen** .
- Deaktivieren Sie die Option **Mitglieder können benutzerdefinierte apps** für jedes Team hochladen, auf das Sie den Zugriff einschränken möchten.
- Erstellen Sie eine benutzerdefinierte App-Setup Richtlinie, und weisen Sie Sie im Microsoft Teams Admin Center zu, wenn die Einstellung **benutzerdefinierte apps hochladen** aktiviert ist, und weisen Sie Sie den Teambesitzern zu.

|Organisationsweite benutzerdefinierte app-Einstellung |Einstellung für benutzerdefinierte Team-App |Benutzerdefinierte App-Richtlinie |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation gesperrt. Benutzerdefinierte Apps können von niemandem hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte APP zu entfernen.   |
| Aus     | Aus     | Ein        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation gesperrt. Benutzerdefinierte Apps können von niemandem hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte APP zu entfernen.         |
| Aus    | Ein        | Aus        |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation gesperrt. Benutzerdefinierte Apps können von niemandem hochgeladen werden. Sie können Windows PowerShell verwenden, um benutzerdefinierte apps zu löschen.         |
| Aus    | Ein      | Ein       |Die Interaktion mit allen benutzerdefinierten Apps ist für Ihre Organisation gesperrt. Benutzerdefinierte Apps können von niemandem hochgeladen werden. Sie können PowerShell verwenden, um die benutzerdefinierte APP zu entfernen.         |
| Ein    | Aus       | Aus         |  Benutzer können keine benutzerdefinierten apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, kann er benutzerdefinierte apps in das Team hochladen. Wenn der Benutzer kein Teambesitzer ist, können Sie keine benutzerdefinierten apps in das Team hochladen. Der Benutzer kann benutzerdefinierte apps im persönlichen Kontext hochladen.     |
| Ein     | Ein     | Aus         | Benutzer können keine benutzerdefinierten apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte apps in das Team hochladen, unabhängig davon, ob der Benutzer ein Teambesitzer ist. Der Benutzer kann benutzerdefinierte apps im persönlichen Kontext hochladen.       |

 ## <a name="related-topics"></a>Verwandte Themen
- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Verwalten von Richtlinien für das App-Setup in Microsoft Teams](teams-app-setup-policies.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md)
