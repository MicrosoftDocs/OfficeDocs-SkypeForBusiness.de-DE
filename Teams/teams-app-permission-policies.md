---
title: Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
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
description: Erfahren Sie mehr über APP-Berechtigungsrichtlinien in Microsoft Teams und wie Sie Sie verwenden können, um zu steuern, welche apps für Benutzer in Ihrer Organisation verfügbar sind.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 4bde860f0f3e64899f4309706575c71862c754a5
ms.sourcegitcommit: 2e8a61abdd586bf8f0f88cac3b7d4ca4b9d9be34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44889994"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle apps oder bestimmte apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie verwalten App-Berechtigungsrichtlinien im Microsoft Teams Admin Center. Sie können die globale (org-Wide Standard)-Richtlinie verwenden oder benutzerdefinierte Richtlinien für einzelne Benutzer oder Benutzer in einer Gruppe erstellen und zuweisen. Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

![Screenshot der APP-Berechtigungsrichtlinie](media/app-permission-policies.png)

> [!NOTE]
> Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Organisationsweite App-Einstellungen überschreiben die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und Benutzern zuweisen.

Wenn sich Ihre Organisation bereits in Teams befindet, werden die App-Einstellungen, die Sie in **Mandanten weiten Einstellungen** im Microsoft 365 Admin Center konfiguriert haben, in den organisationsweiten App-Einstellungen auf der Seite " [apps verwalten](manage-apps.md) " wiedergegeben. Wenn Sie noch nicht bei Microsoft Teams sind und gerade erst anfangen, sind alle apps standardmäßig in der globalen Richtlinie zulässig. Dazu gehören apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht werden.

Angenommen, Sie möchten alle Drittanbieter-apps blockieren und bestimmte apps von Microsoft für das HR-Team in Ihrer Organisation zulassen. Zunächst Wechseln Sie zur Seite " [apps verwalten](manage-apps.md) ", und vergewissern Sie sich, dass die apps, die Sie für das HR-Team zulassen möchten, auf der Organisationsebene zulässig sind. Erstellen Sie dann eine benutzerdefinierte Richtlinie mit dem Namen HR-App-Berechtigungsrichtlinie, legen Sie fest, dass die gewünschten apps blockiert und zugelassen werden, und weisen Sie Sie Benutzern im HR-Team zu.

> [!NOTE]
> Wenn Sie Teams in einer Microsoft 365 Government-gcc-Umgebung bereitgestellt haben, lesen Sie [App-Berechtigungsrichtlinien für gcc](#app-permission-policies-for-gcc) , um mehr über die App-Einstellungen von Drittanbietern zu erfahren, die für gcc einzigartig sind.

## <a name="create-a-custom-app-permission-policy"></a>Erstellen einer benutzerdefinierten App-Berechtigungsrichtlinie

Wenn Sie die apps steuern möchten, die für unterschiedliche Benutzergruppen in Ihrer Organisation verfügbar sind, erstellen Sie eine oder mehrere benutzerdefinierte App-Berechtigungsrichtlinien, und weisen Sie diese zu. Sie können separate benutzerdefinierte Richtlinien erstellen und zuweisen, je nachdem, ob apps von Microsoft, Drittanbietern oder Ihrer Organisation veröffentlicht werden. Es ist wichtig zu wissen, dass Sie, nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, Sie nicht ändern können, wenn apps von Drittanbietern in den organisationsweiten App-Einstellungen deaktiviert sind.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps**-  >  **Berechtigungsrichtlinien**.
2. Klicken Sie auf **Hinzufügen**. <br>
    ![Screenshot der neuen App-Berechtigungsrichtlinie](media/app-permission-policies-new-policy.png)
3. Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.
4. Wählen Sie unter **Microsoft-apps**, **Drittanbieter-apps**und **benutzerdefinierte apps**eine der folgenden Optionen aus:

    - **Alle apps zulassen**
    - **Zulassen bestimmter apps und Blockieren aller anderen Personen**
    - **Blockieren bestimmter apps und zulassen aller anderen Personen**
    - **Blockieren aller apps**

5. Wenn Sie **bestimmte apps zulassen und andere blockieren**ausgewählt haben, fügen Sie die apps hinzu, die Sie zulassen möchten:

    1. Wählen Sie **apps zulassen**aus.
    1. Suchen Sie nach den apps, die Sie zulassen möchten, und klicken Sie dann auf **Hinzufügen**. Die Suchergebnisse werden nach dem App-Publisher (**Microsoft-apps**, **Drittanbieter-apps**oder **benutzerdefinierte apps**) gefiltert.
    1. Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **zulassen**. 

6. Wenn Sie **bestimmte apps blockieren und alle anderen Personen zulassen**ausgewählt haben, suchen Sie nach den apps, die Sie blockieren möchten, und fügen Sie Sie hinzu, und klicken Sie dann auf **blockieren**.
7. Klicken Sie auf **Speichern**.

## <a name="edit-an-app-permission-policy"></a>Bearbeiten einer APP-Berechtigungsrichtlinie

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps**-  >  **Berechtigungsrichtlinien**.
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie hier die gewünschten Änderungen vor. Sie können Einstellungen basierend auf dem App Publisher verwalten und apps basierend auf der Einstellung Zulassen/Blockieren hinzufügen und entfernen.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie für Benutzer

Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie einem oder mehreren Benutzern oder dem Skype for Business PowerShell-Modul zuzuweisen, um Benutzern in einer Gruppe eine benutzerdefinierte Richtlinie zuzuweisen, beispielsweise alle Benutzer in einer Sicherheitsgruppe oder Verteilergruppe.

### <a name="assign-a-custom-app-permission-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie für Benutzer

So weisen Sie einem Benutzer eine Richtlinie zu:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**.
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Wählen Sie unter **App-Berechtigungsrichtlinie**die APP-Berechtigungsrichtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
3. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.  

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps**-  >  **Berechtigungsrichtlinien**.
2. Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.
3. Wählen Sie **Nutzer verwalten** aus.
4. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
5. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a>Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie zu Benutzern in einer Gruppe

Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte App-Berechtigungsrichtlinie zuweisen. So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen. Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen. Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).

In diesem Beispiel weisen wir allen Benutzern in der Projektgruppe "Contoso Pharmaceuticals HR" eine benutzerdefinierte App-Berechtigungsrichtlinie mit dem Namen "HR-App-Berechtigungsrichtlinie" zu.  

> [!NOTE]
> Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.

Abrufen der GroupObject-ID der jeweiligen Gruppe.
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
Abrufen der Mitglieder der gewählten Gruppe.
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie allen Benutzern in der Gruppe eine bestimmte App-Berechtigungsrichtlinie zu. In diesem Beispiel handelt es sich um die Berechtigungsrichtlinie für HR-app.
```PowerShell
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.UserPrincipalName}
``` 
Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.

## <a name="app-permission-policies-for-gcc"></a>App-Berechtigungsrichtlinien für gcc

In einer Microsoft 365 Government-gcc-Bereitstellung von Teams ist es wichtig, die folgenden Informationen zu den App-Einstellungen von Drittanbietern zu kennen, die für gcc einzigartig sind.

In gcc sind alle apps von Drittanbietern standardmäßig blockiert. Darüber hinaus wird die folgende Notiz zum Verwalten von Drittanbieter-apps auf der Seite "App-Berechtigungsrichtlinien" im Microsoft Teams Admin Center angezeigt.

![Screenshot der APP-Berechtigungsrichtlinie in gcc](media/app-permission-policies-gcc.png)

Gehen Sie wie folgt vor, um eine Drittanbieter-App für einen Benutzer oder eine Gruppe von Benutzern in Ihrer Organisation zu aktivieren:

1. Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**, und bestätigen Sie dann in der Liste der apps, dass die Drittanbieter-APP, die Sie für eine Gruppe von Benutzern zulassen möchten, auf der Organisationsebene auf **blockiert** festgesetzt ist.

2. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams-apps**-  >  **Berechtigungsrichtlinien**, und bearbeiten Sie dann die globale Richtlinie, um die Drittanbieter-APP zu blockieren. Gehen Sie dazu so vor:
    1. Klicken Sie auf der Seite App-Berechtigungsrichtlinien auf **Global (org-Wide Standard)**, und klicken Sie dann auf **Bearbeiten**.
    2. Wählen Sie unter **apps von Drittanbietern**die Option **bestimmte apps blockieren und alle anderen zulassen**, die APP hinzufügen aus, und klicken Sie dann auf **Speichern**.

    > [!NOTE]
    > Es ist wichtig, dies zu tun, bevor Sie mit dem nächsten Schritt fortfahren, um die APP auf Organisationsebene zu ermöglichen. Dies liegt daran, dass alle Benutzer, für die die globale Richtlinie gilt, wenn die APP des Drittanbieters nicht in der globalen App-Berechtigungsrichtlinie blockiert ist, auf die Drittanbieter-App zugreifen können, wenn Sie Sie auf der Organisationsebene zulassen.

3. Zulassen der Drittanbieter-App auf Organisationsebene Gehen Sie dazu in der linken Navigationsleiste zu **Teams apps**  >  **Verwalten von apps**. Klicken Sie in der Liste der apps links neben dem APP-Namen, um die APP auszuwählen, und wählen Sie dann **zulassen**aus.
4. [Erstellen Sie eine benutzerdefinierte App-Berechtigungsrichtlinie](#create-a-custom-app-permission-policy) , um die APP zuzulassen, und weisen Sie dann die [Richtlinie](#assign-a-custom-app-permission-policy-to-users) den gewünschten Benutzern zu.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-permission-policies"></a>Arbeiten mit App-Berechtigungsrichtlinien

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Welche APP-Interaktionen wirken sich auf Berechtigungsrichtlinien aus?
Berechtigungsrichtlinien Regeln die APP-Verwendung durch Steuern der Installation, Ermittlung und Interaktion für Endbenutzer. Administratoren können weiterhin apps im Microsoft Teams Admin Center unabhängig von den Ihnen zugewiesenen Berechtigungsrichtlinien verwalten.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Kann ich Branchen-Apps (Business) steuern?
Ja, Sie können APP-Berechtigungsrichtlinien zum Steuern des Rollouts und der Verteilung von benutzerdefinierten (LOB-) Apps verwenden. Sie können eine benutzerdefinierte Richtlinie erstellen oder die globale Richtlinie bearbeiten, um benutzerdefinierte apps basierend auf den Anforderungen Ihrer Organisation zuzulassen oder zu blockieren.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Wie beziehen sich app-Berechtigungsrichtlinien auf angeheftete apps und App-Setup Richtlinien?

Sie können APP-Setup Richtlinien zusammen mit App-Berechtigungsrichtlinien verwenden. Vor angeheftete apps werden aus der Gruppe aktivierter Apps für einen Benutzer ausgewählt. Darüber hinaus wird die app in Teams nicht angezeigt, wenn ein Benutzer über eine APP-Berechtigungsrichtlinie verfügt, die eine app in Ihrer APP-Setup Richtlinie blockiert.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Kann ich App-Berechtigungsrichtlinien verwenden, um das Hochladen benutzerdefinierter apps zu beschränken?

Sie können organisationsweite Einstellungen auf der Seite " **apps verwalten** " oder App-Setup Richtlinien verwenden, um das Hochladen benutzerdefinierter Apps für Ihre Organisation zu beschränken.  

Verwenden Sie benutzerdefinierte App-Richtlinien, um bestimmte Benutzer vom Hochladen benutzerdefinierter apps zu beschränken. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und-Einstellungen in Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Gilt das Blockieren einer APP für Mobile Microsoft Teams?

Ja, wenn Sie eine APP blockieren, wird diese APP für alle Teams-Clients blockiert.  

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Was kann ein Benutzer erleben, wenn eine APP blockiert wird?

Benutzer können nicht mit einer blockierten APP oder deren Funktionen, wie Bots, Tabstopps und Messaging Erweiterungen interagieren. In einem freigegebenen Kontext wie einem Team-oder Gruppen-Chat können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden. Teams zeigt dem Benutzer an, wenn eine APP blockiert ist.

Wenn beispielsweise eine APP blockiert ist, können die Benutzer keine der folgenden Aktionen ausführen:

- Hinzufügen der app persönlich oder eines Chats oder Teams
- Senden von Nachrichten an den App-bot
- Durchführen von Schaltflächenaktionen, die Informationen zurück an die APP senden, wie etwa umsetzbare Nachrichten  
- Anzeigen der Registerkarte der APP
- Einrichten von Connectors zum Empfangen von Benachrichtigungen
- Verwenden der Messaging-Erweiterung der APP

Das Legacy Portal hat das Steuern von apps auf Organisationsebene ermöglicht, was bedeutet, dass eine APP blockiert wird, wenn Sie für alle Benutzer in der Organisation blockiert ist. Das Blockieren einer APP auf der Seite " [apps verwalten](manage-apps.md) " funktioniert genauso.

Für App-Berechtigungsrichtlinien, die bestimmten Benutzern zugewiesen wurden, wenn eine APP mit bot-oder connectorfunktion zugelassen und dann blockiert wurde und die APP dann nur für einige Benutzer in einem freigegebenen Kontext zulässig ist, können Mitglieder eines Gruppen-Chats oder Kanals, die keine Berechtigung für diese APP haben, das Nachrichtenprotokoll und die Nachrichten sehen, die vom bot oder Connector gepostet wurden. , kann aber nicht mit ihr interagieren.

## <a name="related-topics"></a>Verwandte Themen

- [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
- [Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
