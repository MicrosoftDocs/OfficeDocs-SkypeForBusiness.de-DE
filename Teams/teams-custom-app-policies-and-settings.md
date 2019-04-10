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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen Sie zum Verwalten von benutzerdefinierten app-Richtlinien und Einstellungen steuern, wer in Ihrer Organisation benutzerdefinierte apps im Microsoft-Teams hochladen können.
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749757"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

Als Administrator können Sie benutzerdefinierte app-Richtlinien und Einstellungen steuern, wer in Ihrer Organisation benutzerdefinierte apps, die Microsoft-Teams hochladen können. Administratoren entscheiden, welche Benutzer benutzerdefinierte apps hochladen können, und Administratoren und Team Besitzer zu ermitteln, ob bestimmte Teams in Ihrer Organisation benutzerdefinierte apps hinzugefügt werden können.  

## <a name="overview-of-custom-apps"></a>Übersicht über benutzerdefinierte apps

Benutzer können eine benutzerdefinierte Anwendung Hochladen ein app-Paket (in einer ZIP-Datei) direkt zu einem Team oder im Zusammenhang mit persönlichen Teams hinzufügen. Dies unterscheidet sich von wie apps über Teams app Store hinzugefügt werden. Hinzufügen einer benutzerdefinierten app durch ein app-Paket, auch bekannt als Sideloading, hochladen, können Sie die eine app zu testen, wie sie entwickelt wird, bevor es weit verteilt werden kann. Außerdem können Sie das Erstellen einer Apps für die interne Verwendung nur und mit Ihrem Team weitergeben, ohne es zum Teams app-Katalog im app Store Teams gesendet wird.

![eine benutzerdefinierte Anwendung hochladen](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Benutzerdefinierte app-Richtlinie und Einstellungen

Drei Komponenten bestimmen, ob ein Benutzer eine benutzerdefinierte Anwendung zu einem Team, vorführen genauere Kontrolle über hochladen kann, die ein Team benutzerdefinierte apps hinzufügen können, und der benutzerdefinierten apps teams hinzugefügt werden kann:

- [Benutzerdefinierte app Benutzerrichtlinie](#user-custom-app-policy)
- [Team benutzerdefinierte app-Einstellung](#team-custom-app-setting)
- [Benutzerdefinierte app Org geltende Einstellung](#org-wide-custom-app-setting)

Diese Einstellungen wirken sich nicht auf die Möglichkeit zum Blockieren von Drittanbieter-apps aus.  

### <a name="user-custom-app-policy"></a>Benutzerdefinierte app Benutzerrichtlinie

Im Rahmen der [Richtlinien für die app Setup](teams-app-setup-policies.md)können Administratoren richtlinieneinstellung **benutzerdefinierte apps Hochladen zulassen**, Kontrolle verwenden, ob ein Benutzer auf Teams benutzerdefinierte apps hochladen kann.
 
Wenn diese Einstellung deaktiviert ist:

- Der Benutzer kann nicht auf eine beliebige Team in Ihrer Organisation oder im persönlichen Kontext eine benutzerdefinierte Anwendung hochladen.
- Der Benutzer kann mit benutzerdefinierten apps, abhängig von der Einstellung für die gesamte Org benutzerdefinierte Anwendung interagieren.

Wenn diese Einstellung aktiviert ist:

- Der Benutzer kann benutzerdefinierte apps hochladen, Teams, die es ermöglichen und Teams für die sie Besitzer, abhängig von der Einstellung für die benutzerdefinierte Anwendung Org geltende sind.
- Der Benutzer kann benutzerdefinierte apps auf der persönlichen Kontext hochladen. 
- Der Benutzer kann mit benutzerdefinierten apps, abhängig von der Einstellung für die gesamte Org benutzerdefinierte Anwendung interagieren.

Sie können die Einstellungen zum Einschließen von apps, die Sie möchten in der globalen app-Setup-Richtlinie bearbeiten. Wenn Sie Teams für verschiedene Gruppen von Benutzern in Ihrer Organisation anpassen möchten, erstellen und eine oder mehrere benutzerdefinierte Anwendung Setup Richtlinien zuweisen.

#### <a name="set-a-user-custom-app-policy"></a>Legen Sie eine Benutzerrichtlinie für die benutzerdefinierte Anwendung

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Richtlinien einrichten**.
2. Wählen Sie **neue Richtlinie**aus.
3. Aktivieren Sie oder deaktivieren Sie der **benutzerdefinierten apps Hochladen zulassen**.
4. Wählen Sie weitere Einstellungen, die Sie für die Richtlinie möchten.
5. Klicken Sie auf **Speichern**.

### <a name="team-custom-app-setting"></a>Team benutzerdefinierte app-Einstellung

Administratoren und Team Besitzer können steuern, ob ein Team für benutzerdefinierte apps hinzugefügt werden kann. Diese Einstellung, **zulassen, dass Mitglieder benutzerdefinierte apps hochladen**, zusammen mit einer Benutzerrichtlinie benutzerdefinierte Anwendung bestimmt, die für ein bestimmtes Team benutzerdefinierte apps hinzufügen können.
 
Wenn diese Einstellung deaktiviert ist:

- Team Besitzer können benutzerdefinierte apps hinzufügen, wenn ihre benutzerdefinierte app-Richtlinie dies zulässt.
- Teammitglieder Team Besitzer werden nicht können nicht an das Team der benutzerdefinierten apps hinzufügen.

Wenn diese Einstellung aktiviert ist:

- Team Besitzer können benutzerdefinierte apps hinzufügen, wenn ihre benutzerdefinierte app-Richtlinie zulässt.
- Wenn ihre benutzerdefinierte app-Richtlinie ermöglicht, können Teammitglieder Team Besitzer werden nicht benutzerdefinierten apps hinzufügen.

#### <a name="configure-the-team-custom-app-setting"></a>Konfigurieren Sie die Einstellung Team benutzerdefinierte Anwendung

1. Wechseln Sie in Teams, an das Team, klicken Sie auf **Weitere Optionen ˙˙˙** > **Team verwalten**.
2. Klicken Sie auf **Einstellungen**, und erweitern Sie dann die **Berechtigung Mitglied**.
3. Aktivieren Sie oder deaktivieren Sie das Kontrollkästchen **zulassen, dass Mitglieder benutzerdefinierte apps hochladen** .

    ![Team benutzerdefinierte app-Einstellung](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Benutzerdefinierte app Org geltende Einstellung

Die benutzerdefinierte Anwendung Org geltende-Einstellung **Zulassen Interaktion mit benutzerdefinierten apps**, gilt für alle Benutzer in Ihrer Organisation und steuert, ob sie hochladen oder mit benutzerdefinierten apps interagieren können. Diese Einstellung überschreibt die Benutzer- und Team benutzerdefinierte app-Richtlinie und Einstellung. Es wurde als ein Master-Shape zum ein-/ausschalten während Sicherheitsereignisse dienen soll.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Konfigurieren Sie die Einstellung für die gesamte Org benutzerdefinierte Anwendung

1. Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Berechtigungsrichtlinien**.
2. Klicken Sie auf **gesamte Org app-Einstellungen**.
3. Aktivieren Sie unter **benutzerdefinierte apps**oder deaktivieren Sie der **Interaktion mit benutzerdefinierten apps zulassen**.

    ![Benutzerdefinierte app Org geltende Einstellung](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Wie benutzerdefinierte app-Richtlinien und Einstellungen zusammen funktionieren.

Die folgende Tabelle enthält eine Zusammenfassung die benutzerdefinierte app-Richtlinie und Einstellungen, zusammenarbeiten und deren kombinierten Auswirkung auf steuern, wer in Ihrer Organisation benutzerdefinierte apps auf Teams hochladen können.

Angenommen Sie, Sie nur Team Besitzer benutzerdefinierte apps für bestimmte Teams Hochladen zulassen möchten. Legen Sie die folgenden:
- Aktivieren Sie die Einstellung **Zulassen Interaktion mit benutzerdefinierten apps** in der Verwaltungskonsole von Microsoft-Teams.
- Deaktivieren Sie die **zulassen, dass Mitglieder benutzerdefinierte apps hochladen** für jedes Team zum Einschränken des Zugriffs werden soll.
- Erstellen Sie und weisen Sie eine benutzerdefinierte Anwendung Setup Richtlinie in der Verwaltungskonsole von Microsoft-Teams, mit der **Benutzer kann benutzerdefinierte apps hochladen** Einstellung aktiviert, und die Besitzer der Team zuweisen.

|Benutzerdefinierte app Org geltende Einstellung |Team benutzerdefinierte app-Einstellung |Benutzerdefinierte app Benutzerrichtlinie |Effekt  |
|---------|---------|---------|---------|
| Aus    | Aus    | Aus     |Interaktion mit alle benutzerdefinierten apps wird für Ihre Organisation blockiert. Benutzerdefinierte apps können nicht von allen Benutzern hochgeladen werden. PowerShell können Sie die benutzerdefinierte Anwendung entfernen.   |
| Aus     | Aus     | Ein        |Interaktion mit alle benutzerdefinierten apps wird für Ihre Organisation blockiert. Benutzerdefinierte apps können nicht von allen Benutzern hochgeladen werden. PowerShell können Sie die benutzerdefinierte Anwendung entfernen.         |
| Aus    | Ein        | Aus        |Interaktion mit alle benutzerdefinierten apps wird für Ihre Organisation blockiert. Benutzerdefinierte apps können nicht von allen Benutzern hochgeladen werden. Sie können Windows PowerShell verwenden, um benutzerdefinierte apps zu löschen.         |
| Aus    | Ein      | Ein       |Interaktion mit alle benutzerdefinierten apps wird für Ihre Organisation blockiert. Benutzerdefinierte apps können nicht von allen Benutzern hochgeladen werden. PowerShell können Sie die benutzerdefinierte Anwendung entfernen.         |
| Ein    | Aus       | Aus         |  Der Benutzer kann nicht benutzerdefinierten apps hochladen.      |
| Ein     | Aus       | Ein         | Wenn der Benutzer ein Teambesitzer ist, können sie benutzerdefinierte apps an das Team hochladen. Wenn der Benutzer ein Teambesitzer nicht ist, kann nicht an das Team der benutzerdefinierte apps hochgeladenen. Der Benutzer kann benutzerdefinierte apps im Zusammenhang mit persönlichen hochladen.     |
| Ein     | Ein     | Aus         | Der Benutzer kann nicht benutzerdefinierten apps hochladen.       |
| Ein    | Ein        | Ein        | Der Benutzer kann benutzerdefinierte apps hochladen, an das Team, unabhängig davon, ob der Benutzer ein Teambesitzer ist. Der Benutzer kann benutzerdefinierte apps im Zusammenhang mit persönlichen hochladen.       |

 ## <a name="related-topics"></a>Verwandte Themen
- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Verwalten von Richtlinien für das App-Setup in Microsoft Teams](teams-app-setup-policies.md)
- [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](teams-app-permission-policies.md)
