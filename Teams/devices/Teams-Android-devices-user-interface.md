---
title: Festlegen der Benutzeroberfläche von Microsoft Teams Android-Geräten
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: Erfahren Sie, wie Sie die Benutzeroberfläche auf Android-Geräten von Teams festlegen.
ms.openlocfilehash: 830609d1bf02c38a2301c0d5a1b9e62ac836c908
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606834"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Festlegen der Benutzeroberfläche von Microsoft Teams Android-Geräten

Microsoft Teams Android-Geräte können eine bestimmte Benutzeroberfläche basierend auf dem Lizenztyp anzeigen, der dem angemeldeten Konto zugewiesen ist. Sie können dieses Verhalten überschreiben und steuern, welche Schnittstelle angezeigt wird. In diesem Artikel wird beschrieben, wie die Standard-Benutzeroberfläche ausgewählt wird und wie Sie die Benutzeroberfläche mithilfe einer Powershell-Richtlinie ändern können.

Es gibt drei Arten von Benutzeroberflächen auf Android-Geräten von Teams:

1. Benutzer
2. Gemeinsamer Bereich
3. Besprechung

Wenn Sie einem Konto, z. B. einer E3- oder E5-Lizenz, [eine Benutzerlizenz zuweisen](/microsoftteams/user-access) , zeigt das Teams-Gerät die Standardmäßige Benutzeroberfläche an, die für die meisten Benutzerszenarien vollständig bereitgestellt wird. Wenn ein Gerät jedoch eine bestimmte Funktion ausführt, z. B. ein Telefon für gemeinsame Bereiche oder einen Besprechungsraum, gibt es für diese Verwendungen bestimmte Benutzeroberflächen.

Die folgenden drei Bilder zeigen, wie sich die Benutzeroberfläche basierend auf der dem Benutzerkonto zugewiesenen Lizenz ändert. 

## <a name="end-user-interface"></a>Benutzeroberfläche 

Dem Benutzerkonto wird eine E5-Lizenz zugewiesen. Dies ist eine Benutzerlizenz, daher zeigt das Gerät die Standard-Benutzeroberfläche an:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Benutzeroberfläche.":::

## <a name="common-area-interface"></a>Schnittstelle für gemeinsame Bereiche

In dieser Abbildung wurde dem Benutzerkonto eine [Telefonlizenz für gemeinsame Bereiche](/microsoftteams/set-up-common-area-phones) zugewiesen. Telefone im einheitlichen Bereich werden in erster Linie zum Tätigen und Empfangen von Telefonanrufen verwendet. Daher wird die Wähltastatur auf dem Display angezeigt:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Telefonschnittstelle für gemeinsame Bereiche.":::

## <a name="meeting-interface"></a>Besprechungsschnittstelle

Diese Abbildung zeigt ein Benutzerkonto mit einer [zugewiesenen Microsoft Teams-Räume Lizenz](/MicrosoftTeams/rooms/rooms-licensing). Teams-Räume-Lizenzen sind für die Verwendung in Besprechungsräumen oder freigegebenen Räumen vorgesehen, sodass sich die Benutzeroberfläche ändert, um die Teilnahme an einer Besprechung durch Anzeigen der Kalenderansicht zu vereinfachen:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Besprechungsschnittstelle.":::

> [!NOTE]
> Das Ändern der Benutzeroberfläche wirkt sich nicht auf die Verwendung anderer lizenzierter Features aus. Obwohl die Standardansicht der Teamrooms-Lizenz beispielsweise die Kalenderansicht ist, können Sie dennoch PSTN-Telefonanrufe tätigen und empfangen, wenn das Konto ordnungsgemäß lizenziert und konfiguriert ist.

> [!IMPORTANT]
> Es gibt andere Elemente der Schnittstelle, die sich ändern. Um beispielsweise zu verhindern, dass sich Endbenutzer von einem Telefon- oder Besprechungsraumgerät für gemeinsame Bereiche abmelden, wird die Option "Abmelden" auf diesen Geräten in einen Teil des Einstellungsmenüs verschoben, für den Administratorberechtigungen erforderlich sind.

## <a name="override-automatic-user-interface-detection"></a>Automatische Erkennung der Benutzeroberfläche außer Kraft setzen

In einigen Fällen können Sie eine Lizenz einem Konto zuweisen, das nicht der beabsichtigten Verwendung entspricht. Beispielsweise können Sie einem Konto, das sich bei Teams-Räume unter Android anmelden soll, eine Benutzerlizenz zuweisen. Standardmäßig wird die Benutzeroberfläche des Besprechungsraums anstelle der Benutzeroberfläche des Besprechungsraums angezeigt. Um die Standardschnittstelle außer Kraft zu setzen, erstellen Sie eine neue [Microsoft Teams-IP-Telefonrichtlinie](/powershell/module/skype/new-csteamsipphonepolicy) , und wenden Sie sie auf dieses Konto an.

> [!NOTE]
> Die dem Benutzerkonto zugewiesene Lizenz muss mindestens über die gleichen Lizenzberechtigungen verfügen wie die gewünschte Benutzeroberfläche. Die Common Area Phone-Lizenz lässt nur die Benutzeroberfläche des Telefons für gemeinsame Bereiche zu. Die Besprechungsraumlizenz ermöglicht Besprechungsraum- und Telefon-Benutzeroberflächen für gemeinsame Bereiche. Eine E3- oder E5-Lizenz unterstützt alle Anmeldemodi.

Im Folgenden finden Sie ein Beispiel für das Außerkraftsetzen der automatischen Lizenzerkennung. Gehen Sie in diesem Beispiel davon aus, dass einem Ressourcenkonto für Besprechungsräume mit dem Namen conf-adams@contoso.com eine E3-Lizenz zugewiesen wurde. Wenn dieses Konto angemeldet ist, soll benutzern die Benutzeroberfläche des Besprechungsraums angezeigt werden.

### <a name="create-a-new-policy-and-assign-to-user"></a>Erstellen einer neuen Richtlinie und Zuweisen zum Benutzer

1. Starten Sie eine Remote-Windows PowerShell-Sitzung, und stellen Sie mit dem folgenden Cmdlet eine Verbindung mit Microsoft Teams her:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Erstellen Sie eine neue Microsoft Teams-IP-Telefonrichtlinie, und legen Sie den Anmeldemodus auf "MeetingSignIn" fest:

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Sie können diese neue Richtlinie jetzt dem Ressourcenkonto für Besprechungsräume zuweisen:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Nachdem Sie die Richtlinie dem Ressourcenkonto des Besprechungsraums gewährt haben, müssen Sie warten, bis die Richtlinienzuweisung repliziert wird. Sie müssen sich auch vom Gerät abmelden und wieder anmelden.

## <a name="impact-on-microsoft-teams-admin-center"></a>Auswirkungen auf das Microsoft Teams Admin Center

Mit dem Microsoft Teams Admin Center können Sie Microsoft Teams-Geräte verwalten. Weitere Informationen zum Verwalten von Geräten mithilfe des Teams Admin Centers finden [Sie unter Verwalten Ihrer Geräte in Microsoft Teams](device-management.md).


Das Teams Admin Center bietet die Möglichkeit, Teams-Telefone zu verwalten. Telefone werden basierend auf ihrer Funktion in einer von drei Registerkarten gefiltert: Benutzertelefone, Telefone für gemeinsame Bereiche und Konferenztelefone. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Telefonkopfzeile im Teams Admin Center.":::

Wie bei der Benutzeroberflächenerkennung werden Teams-Telefone basierend auf der Lizenz kategorisiert, die dem Konto zugewiesen ist, das sich beim Telefon anmeldet. Wenn sich beispielsweise ein Konto, dem eine Telefonlizenz für gemeinsame Bereiche zugewiesen ist, bei einem Telefon anmeldet, wird dieses Telefon sowohl im Standardabschnitt **"Alle Telefone** " als auch im Abschnitt " **Telefone im allgemeinen Bereich** " angezeigt.

Wenn sie möchten, dass ein Telefon in einem anderen Abschnitt angezeigt wird, können Sie dem Telefon entweder eine andere Lizenz zuweisen oder eine Ip-Telefonrichtlinie für Teams erstellen und zuweisen, wie [oben beschrieben](#override-automatic-user-interface-detection).
