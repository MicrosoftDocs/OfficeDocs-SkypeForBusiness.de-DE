---
title: Festlegen der Benutzeroberfläche für Microsoft Teams Android-Geräte
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die Benutzeroberfläche auf Teams Android-Geräten festlegen.
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327351"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Festlegen der Benutzeroberfläche für Microsoft Teams Android-Geräte

Microsoft Teams Android-Geräte können eine bestimmte Benutzeroberfläche basierend auf dem Dem angemeldeten Konto zugewiesenen Lizenztyp anzeigen. Sie können dieses Verhalten überschreiben und steuern, welche Schnittstelle angezeigt wird. In diesem Artikel wird beschrieben, wie die Standard-Benutzeroberfläche ausgewählt wird und wie Sie die Benutzeroberfläche mithilfe einer PowerShell-Richtlinie ändern können.

Es gibt drei Arten von Benutzeroberflächen auf Teams Android-Geräten:

1. Benutzer
2. Gemeinsamer Bereich
3. Besprechung

Wenn Sie einem Konto [eine Benutzerlizenz zuweisen,](/microsoftteams/user-access) z. B. eine E3- oder E5-Lizenz, zeigt das Teams Gerät die Standard-Endbenutzerschnittstelle an, die für die meisten Benutzerszenarien vollständig verwendet wird. Wenn ein Gerät jedoch eine bestimmte Funktion ausführt, z. B. ein Telefon für gemeinsame Bereiche oder einen Besprechungsraum, gibt es bestimmte Benutzeroberflächen für diese Verwendungen.

Die folgenden drei Bilder zeigen, wie sich die Benutzeroberfläche basierend auf der dem Benutzerkonto zugewiesenen Lizenz ändert. In der ersten Abbildung wird dem Benutzerkonto eine E5-Lizenz zugewiesen. Dies ist eine Benutzerlizenz, sodass das Gerät die Standard-Endbenutzerschnittstelle anzeigt:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Benutzeroberfläche für den Benutzermodus":::

In dieser Abbildung wurde dem Benutzerkonto eine [Telefonlizenz](/microsoftteams/set-up-common-area-phones)für gemeinsame Bereiche zugewiesen. Telefone in öffentlichen Bereichen werden in erster Linie zum Tätigen und Empfangen von Telefonanrufen verwendet. Daher wird die Wähltastatur auf dem Display angezeigt:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Telefonschnittstelle für gemeinsame Bereiche":::

Diese Abbildung zeigt schließlich ein Benutzerkonto mit einer [zugewiesenen Microsoft Teams-Räume Standardlizenz.](/MicrosoftTeams/rooms/rooms-licensing) Teams-Räume Lizenzen sollen in Besprechungsräumen oder freigegebenen Räumen verwendet werden, sodass sich die Benutzeroberfläche ändert, um die Teilnahme an einer Besprechung durch Anzeigen der Kalenderansicht zu vereinfachen:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Besprechungsschnittstelle":::

> [!NOTE]
> Das Ändern der Benutzeroberfläche wirkt sich nicht auf die Möglichkeit aus, andere lizenzierte Features zu verwenden. Auch wenn die Standardansicht der Team rooms-Lizenz beispielsweise die Kalenderansicht ist, können Sie trotzdem PsTN-Telefonanrufe (Public Switch Telephone Network) tätigen und empfangen, wenn das Konto ordnungsgemäß lizenziert und konfiguriert ist.

> [!IMPORTANT]
> Es gibt andere Elemente der Schnittstelle, die sich ändern. Um beispielsweise zu verhindern, dass sich Endbenutzer von einem Telefon oder Besprechungsraumgerät für gemeinsame Bereiche abmelden, wird die Option "Abmelden" auf diesen Geräten in einen Teil des Einstellungsmenüs verschoben, für den Administratorberechtigungen erforderlich sind.

## <a name="override-automatic-user-interface-detection"></a>Außerkraftsetzen der automatischen Benutzeroberflächenerkennung

In einigen Fällen können Sie einem Konto, das nicht der beabsichtigten Verwendung entspricht, eine Lizenz zuweisen. Beispielsweise können Sie einem Konto, das sich bei Teams-Räume unter Android anmelden soll, eine Benutzerlizenz zuweisen. Standardmäßig wird die Benutzeroberfläche des Endbenutzers anstelle der Benutzeroberfläche des Besprechungsraums angezeigt. Um die Standardschnittstelle außer Kraft zu setzen, erstellen Sie eine neue [Teams IP-Telefon-Richtlinie,](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) und wenden Sie sie auf dieses Konto an.

> [!NOTE]
> Die dem Benutzerkonto zugewiesene Lizenz muss mindestens über die gleichen Lizenzberechtigungen wie die gewünschte Benutzeroberfläche verfügen. Die Lizenz für den gemeinsamen Bereich Telefon lässt nur die Benutzeroberfläche des Telefons für gemeinsame Bereiche zu. Die Besprechungsraumlizenz ermöglicht Die Benutzeroberflächen für Besprechungsräume und Telefone für gemeinsame Bereiche. Eine E3- oder E5-Lizenz unterstützt alle Anmeldemodi.

Es folgt ein Beispiel für die Außerkraftsetzung der automatischen Lizenzerkennung. In diesem Beispiel wird davon ausgegangen, dass einem Besprechungsraumressourcenkonto mit dem Namen conf-adams@contoso.com eine E3-Lizenz zugewiesen wurde. Wenn dieses Konto angemeldet ist, soll benutzern die Benutzeroberfläche des Besprechungsraums angezeigt werden.

### <a name="create-a-new-policy-and-assign-to-user"></a>Erstellen einer neuen Richtlinie und Zuweisen zum Benutzer

1. Starten Sie eine Remotesitzung Windows PowerShell, und stellen Sie mit dem folgenden Cmdlet eine Verbindung mit Microsoft Teams her:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Erstellen Sie eine neue Teams IP-Telefon-Richtlinie, und legen Sie den Anmeldemodus auf "MeetingSignIn" fest:

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Sie können diese neue Richtlinie nun dem Ressourcenkonto für Besprechungsräume zuweisen:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Nachdem Sie die Richtlinie dem Besprechungsraumressourcenkonto gewährt haben, müssen Sie warten, bis die Richtlinienzuweisung repliziert wurde. Sie müssen sich auch vom Gerät abmelden und sich wieder anmelden.
