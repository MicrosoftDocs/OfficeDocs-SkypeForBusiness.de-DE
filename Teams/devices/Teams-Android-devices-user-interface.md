---
title: Festlegen Microsoft Teams Benutzeroberfläche für Android-Geräte
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
description: Hier erfahren Sie, wie Sie die Benutzeroberfläche auf Teams Android-Geräten festlegen.
ms.openlocfilehash: f743a0f51015e7bd8fdabd41d120a187774c3370
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725689"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Festlegen Microsoft Teams Benutzeroberfläche für Android-Geräte

Microsoft Teams Android-Geräte können eine bestimmte Benutzeroberfläche basierend auf dem Lizenztyp anzeigen, der dem angemeldeten Konto zugewiesen ist. Sie können dieses Verhalten überschreiben und steuern, welche Schnittstelle angezeigt wird. In diesem Artikel wird erläutert, wie die Standard-Benutzeroberfläche ausgewählt wird und wie Sie die Benutzeroberfläche mithilfe einer Powershell-Richtlinie ändern können.

Es gibt drei Arten von Benutzeroberflächen auf Teams Android-Geräten:

1. Benutzer
2. Gemeinsamer Bereich
3. Besprechung

Wenn [](/microsoftteams/user-access) Sie einem Konto, z. B. einer E3- oder E5-Lizenz, eine Benutzerlizenz zuweisen, zeigt das Teams-Gerät die standardmäßige Endbenutzerschnittstelle an, die in den meisten Benutzerszenarien vollständig unterstützt wird. Wenn ein Gerät jedoch eine bestimmte Funktion, z. B. ein Telefon in einem gemeinsamen Bereich oder einen Besprechungsraum, ausführen soll, gibt es bestimmte Benutzeroberflächen für diese Verwendungen.

Die folgenden drei Abbildungen zeigen, wie sich die Benutzeroberfläche basierend auf der Dem Benutzerkonto zugewiesenen Lizenz ändert. Im ersten Bild wird dem Benutzerkonto eine E5-Lizenz zugewiesen. Da es sich um eine Benutzerlizenz handelt, wird auf dem Gerät die Standard-Endbenutzerschnittstelle angezeigt:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Benutzeroberfläche":::

In dieser Abbildung wurde dem Benutzerkonto eine allgemeine Bereichslizenz [für Telefon zugewiesen.](/microsoftteams/set-up-common-area-phones) Häufig verwendete Telefone werden in erster Linie zum Anrufen und Empfangen von Telefonanrufen verwendet. Als solches wird die Wählta pad auf der Anzeige angezeigt:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Telefonschnittstelle in der Nähe":::

Schließlich zeigt diese Abbildung ein Benutzerkonto mit einer zugewiesenen [Microsoft Teams-Räume Standard-Lizenz.](/MicrosoftTeams/rooms/rooms-licensing) Teams-Räume Lizenzen sind für Besprechungsräume oder gemeinsame Räume gedacht. Daher ändert sich die Benutzeroberfläche, um die Teilnahme an einer Besprechung durch Anzeigen der Kalenderansicht zu einfach zu machen:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Besprechungsoberfläche":::

> [!NOTE]
> Das Ändern der Benutzeroberfläche wirkt sich nicht auf Ihre Möglichkeit zur Verwendung anderer lizenzierter Features aus. So können Sie beispielsweise, obwohl die Standardansicht der Teamräume-Lizenz die Kalenderansicht ist, dennoch Telefonanrufe über das Öffentliche Telefonnetz (PSTN) erstellen und empfangen, wenn das Konto ordnungsgemäß lizenziert und konfiguriert ist.

> [!IMPORTANT]
> Es gibt andere Elemente der -Schnittstelle, die sich ändern. Um beispielsweise zu verhindern, dass sich Endbenutzer von einem häufig verwendeten Telefon oder Besprechungsraumgerät abmelden, wird die Option "Abmelden" auf diesen Geräten in einen Teil des Einstellungsmenüs verschoben, für den Administratorberechtigungen erforderlich sind.

## <a name="override-automatic-user-interface-detection"></a>Außerkraft setzen der automatischen Erkennung der Benutzeroberfläche

In einigen Fällen können Sie einem Konto, das nicht der vorgesehenen Verwendung passt, eine Lizenz zuweisen. So können Sie beispielsweise einem Konto, das zum Anmelden bei einem Konto unter Android Teams-Räume, eine Benutzerlizenz zuweisen. Standardmäßig wird anstelle der Besprechungsraumoberfläche die Benutzeroberfläche der Endbenutzer angezeigt. Um die Standardschnittstelle zu überschreiben, erstellen Sie eine neue Teams [IP Telefon-Richtlinie,](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) und wenden Sie sie auf dieses Konto an.

> [!NOTE]
> Die dem Benutzerkonto zugewiesene Lizenz muss mindestens die gleichen Lizenzberechtigungen wie die gewünschte Benutzeroberfläche haben. Die common area Telefon-Lizenz lässt nur die Benutzeroberfläche für Telefone im gemeinsamen Bereich zu. Die Besprechungsraumlizenz ermöglicht Besprechungsraum und gemeinsame Telefon-Benutzeroberflächen. Eine E3- oder E5-Lizenz unterstützt alle Anmeldemodi.

Das folgende Beispiel zeigt, wie Sie die automatische Lizenzerkennung außer Kraft setzen. Gehen Sie in diesem Beispiel davon aus, dass einem Ressourcenkonto für Besprechungsraum conf-adams@contoso.com eine E3-Lizenz zugewiesen wurde. Wenn dieses Konto angemeldet ist, soll den Benutzern die Benutzeroberfläche des Besprechungsraums angezeigt werden.

### <a name="create-a-new-policy-and-assign-to-user"></a>Erstellen einer neuen Richtlinie und Zuweisen zu Benutzern

1. Starten Sie eine Remote Windows PowerShell Sitzung, und stellen Sie mithilfe Microsoft Teams folgenden Cmdlets eine Verbindung mit ihrem Computer herzustellen:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Erstellen Sie eine neue Teams-IP Telefon Richtlinie, und legen Sie den Anmeldemodus auf "MeetingSignIn" festgelegt:

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Sie können nun diese neue Richtlinie dem Ressourcenkonto des Besprechungsraums zuweisen:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Nachdem Sie die Richtlinie dem Ressourcenkonto des Besprechungsraums gewährt haben, müssen Sie warten, bis die Richtlinienzuweisung repliziert wurde. Sie müssen sich auch vom Gerät abmelden und wieder anmelden.
