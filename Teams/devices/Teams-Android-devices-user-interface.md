---
title: Festlegen Microsoft Teams Benutzeroberfläche für Android-Geräte
ms.author: mitressl
author: flinchbot
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
description: Hier erfahren Sie, wie Sie die Benutzeroberfläche auf Teams Android-Geräten festlegen.
ms.openlocfilehash: 32f5129330bf46657f126fc00f7eddc2fc30f090
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279383"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Festlegen Microsoft Teams Benutzeroberfläche für Android-Geräte

Microsoft Teams Android-Geräten können eine bestimmte Benutzeroberfläche basierend auf dem Lizenztyp anzeigen, der dem angemeldeten Konto zugewiesen ist. Sie können dieses Verhalten überschreiben und steuern, welche Schnittstelle angezeigt wird. In diesem Artikel wird erläutert, wie die Standard-Benutzeroberfläche ausgewählt wird und wie Sie die Benutzeroberfläche mithilfe einer Powershell-Richtlinie ändern können.

Es gibt drei Arten von Benutzeroberflächen auf Teams Android-Geräten:

1. Benutzer
2. Gemeinsamer Bereich
3. Besprechung

Wenn Sie [einem](/microsoftteams/user-access) Konto, z. B. einer E3- oder E5-Lizenz, eine Benutzerlizenz zuweisen, zeigt das Teams-Gerät die standardmäßige Endbenutzerschnittstelle an, die in den meisten Benutzerszenarien vollständig unterstützt wird. Wenn ein Gerät jedoch eine bestimmte Funktion, z. B. ein Telefon in einem gemeinsamen Bereich oder einen Besprechungsraum, ausführen soll, gibt es bestimmte Benutzeroberflächen für diese Verwendungen.

Die folgenden drei Abbildungen zeigen, wie sich die Benutzeroberfläche basierend auf der Dem Benutzerkonto zugewiesenen Lizenz ändert. 

## <a name="end-user-interface"></a>Endbenutzerschnittstelle 

Dem Benutzerkonto wird eine E5-Lizenz zugewiesen. Dies ist eine Benutzerlizenz, daher zeigt das Gerät die Standard-Endbenutzerschnittstelle an:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Benutzeroberfläche.":::

## <a name="common-area-interface"></a>Schnittstelle für gemeinsame Fläche

In dieser Abbildung wurde dem Benutzerkonto eine gemeinsame Telefon [zugewiesen](/microsoftteams/set-up-common-area-phones). Häufig verwendete Telefone werden in erster Linie zum Anrufen und Empfangen von Telefonanrufen verwendet. Als solches wird die Wählta pad auf der Anzeige angezeigt:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Telefonschnittstelle im allgemeinen Bereich.":::

## <a name="meeting-interface"></a>Besprechungsoberfläche

Diese Abbildung zeigt ein Benutzerkonto mit einer [Microsoft Teams-Räume Standard zugewiesenen](/MicrosoftTeams/rooms/rooms-licensing) Lizenz. Teams-Räume Lizenzen sollen in Besprechungsräumen oder gemeinsam genutzten Räumen verwendet werden. Daher ändert sich die Benutzeroberfläche, um die Teilnahme an einer Besprechung durch Anzeigen der Kalenderansicht zu einfach zu machen:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Besprechungsoberfläche.":::

> [!NOTE]
> Das Ändern der Benutzeroberfläche wirkt sich nicht auf Ihre Möglichkeit zur Verwendung anderer lizenzierter Features aus. So können Sie beispielsweise, obwohl die Standardansicht der Teamräume-Lizenz die Kalenderansicht ist, dennoch Telefonanrufe über das Öffentliche Telefonnetz (PSTN, Public Switch Telephone Network) herstellen und empfangen, wenn das Konto ordnungsgemäß lizenziert und konfiguriert ist.

> [!IMPORTANT]
> Es gibt andere Elemente der -Schnittstelle, die sich ändern. Um beispielsweise zu verhindern, dass sich Endbenutzer von einem häufig verwendeten Telefon oder Besprechungsraumgerät abmelden, wird die Option "Abmelden" auf diesen Geräten in einen Teil des Einstellungsmenüs verschoben, für den Administratorberechtigungen erforderlich sind.

## <a name="override-automatic-user-interface-detection"></a>Außerkraft setzen der automatischen Erkennung der Benutzeroberfläche

In einigen Fällen können Sie einem Konto, das nicht der vorgesehenen Verwendung zu entsprechen, eine Lizenz zuweisen. Beispielsweise können Sie einem Konto, das zum Anmelden bei einem Konto auf Android-Geräten Teams-Räume, eine Benutzerlizenz zuweisen. Standardmäßig wird anstelle der Besprechungsraumoberfläche die Endbenutzerschnittstelle angezeigt. Um die Standardschnittstelle zu überschreiben, erstellen Sie eine neue Teams [IP Telefon-Richtlinie,](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) und wenden Sie sie auf dieses Konto an.

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

## <a name="impact-on-microsoft-teams-admin-center"></a>Auswirkungen auf Microsoft Teams Admin Center

Microsoft Teams Admin Center können Sie Ihre Microsoft Teams verwalten. Weitere Informationen zum Verwalten von Geräten mit Teams Admin Center finden Sie unter [Verwalten Ihrer Geräte in Microsoft Teams](device-management.md).


Teams Admin Center bietet die Möglichkeit, Ihre Teams zu verwalten. Telefone werden basierend auf ihrer Funktion auf eine von drei Registerkarten gefiltert: Telefone von Benutzern, Telefone in der Nähe und Telefonkonferenzen. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Kopfzeile eines Telefons im Teams Admin Center.":::

Wie bei der Benutzeroberflächenerkennung werden Teams Smartphones basierend auf der Lizenz kategorisiert, die dem Konto zugewiesen ist, das sich beim Telefon anmeldet. Wenn sich z. B. ein Konto, dem eine allgemeine Bereichslizenz für Telefone zugewiesen ist, bei einem Telefon anmelden, wird dieses Telefon sowohl im standardmäßigen Abschnitt Alle Telefone als auch im Abschnitt Telefone im allgemeinen **Bereich angezeigt.** 

Wenn ein Telefon in einem anderen Abschnitt angezeigt werden soll, können Sie entweder dem Telefon eine andere Lizenz zuweisen oder wie oben beschrieben eine Teams-IP-Telefon-Richtlinie erstellen und [zuweisen](#override-automatic-user-interface-detection).
