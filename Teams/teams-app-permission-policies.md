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
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45042991"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle apps oder bestimmte apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie verwalten App-Berechtigungsrichtlinien im Microsoft Teams Admin Center. Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

![Screenshot der APP-Berechtigungsrichtlinie](media/app-permission-policies.png)

> [!NOTE]
> Organisationsweite App-Einstellungen überschreiben die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und Benutzern zuweisen.

Wenn sich Ihre Organisation bereits in Teams befindet, werden die App-Einstellungen, die Sie in **Mandanten weiten Einstellungen** im Microsoft 365 Admin Center konfiguriert haben, in den organisationsweiten App-Einstellungen auf der Seite " [apps verwalten](manage-apps.md) " wiedergegeben. Wenn Sie noch nicht bei Microsoft Teams sind und gerade erst anfangen, sind alle apps standardmäßig in der globalen Richtlinie zulässig. Dazu gehören apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht werden.

Angenommen, Sie möchten alle Drittanbieter-apps blockieren und bestimmte apps von Microsoft für das HR-Team in Ihrer Organisation zulassen. Zunächst Wechseln Sie zur Seite " [apps verwalten](manage-apps.md) ", und vergewissern Sie sich, dass die apps, die Sie für das HR-Team zulassen möchten, auf der Organisationsebene zulässig sind. Erstellen Sie dann eine benutzerdefinierte Richtlinie mit dem Namen HR-App-Berechtigungsrichtlinie, legen Sie fest, dass die gewünschten apps blockiert und zugelassen werden, und weisen Sie Sie Benutzern im HR-Team zu.

> [!NOTE]
> Wenn Sie Teams in einer Microsoft 365 Government Community Cloud (gcc)-Umgebung bereitgestellt haben, lesen Sie [Verwalten von organisationsweiten App-Einstellungen für Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) , um mehr über die App-Einstellungen von Drittanbietern zu erfahren, die für gcc einzigartig sind.

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

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Verwalten von organisationsweiten App-Einstellungen für Microsoft 365 Government  

In einer Microsoft 365 Government-gcc-Bereitstellung von Teams ist es wichtig, die folgenden Informationen zu den App-Einstellungen von Drittanbietern zu kennen, die für gcc einzigartig sind.

In gcc sind alle apps von Drittanbietern standardmäßig blockiert. Darüber hinaus wird die folgende Notiz zum Verwalten von Drittanbieter-apps auf der Seite "App-Berechtigungsrichtlinien" im Microsoft Teams Admin Center angezeigt.

![Screenshot der APP-Berechtigungsrichtlinie in gcc](media/app-permission-policies-gcc.png)

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer apps von Drittanbietern installieren können. Organisationsweite App-Einstellungen Regeln das Verhalten für alle Benutzer und überschreiben alle anderen APP-Berechtigungsrichtlinien, die Benutzern zugewiesen sind. Sie können Sie verwenden, um schädliche oder problematische apps zu steuern.

1. Wählen Sie auf der Seite **Berechtigungsrichtlinien** die Option **organisationsweite App-Einstellungen**aus. Anschließend können Sie die gewünschten Einstellungen im Panel konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen](media/app-permission-policies-gcc-org-wide.png)
    
2. Deaktivieren oder aktivieren Sie unter **apps von Drittanbietern**diese Einstellungen, um den Zugriff auf Drittanbieter-apps zu steuern:

    - **Drittanbieter-apps zulassen**: Hiermit wird gesteuert, ob Benutzer apps von Drittanbietern verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine apps von Drittanbietern installieren oder verwenden. In einer Microsoft 365 Government-gcc-Bereitstellung von Teams ist diese Einstellung standardmäßig deaktiviert.
    - **Alle neuen Drittanbieter-apps zulassen, die standardmäßig im Store veröffentlicht**werden: Hiermit wird gesteuert, ob neue Drittanbieter-apps, die im App Store für Teams veröffentlicht werden, automatisch in Teams verfügbar sind. Diese Option kann nur festgesetzt werden, wenn Sie Drittanbieter-apps zulassen.

3. Fügen Sie unter **Blockierte apps**die apps hinzu, die Sie in Ihrer Organisation blockieren möchten. In einer Microsoft 365 Government-gcc-Bereitstellung von Teams werden alle Drittanbieter-apps standardmäßig dieser Liste hinzugefügt. Entfernen Sie für alle Drittanbieter-apps, die Sie in Ihrer Organisation zulassen möchten, die APP aus dieser Liste blockierter apps. Wenn Sie eine APP organisationsweit blockieren, wird die APP automatisch für alle Benutzer blockiert, unabhängig davon, ob Sie in einer APP-Berechtigungsrichtlinie zulässig ist.
4. Klicken Sie auf **Speichern** , damit die App-Einstellungen für die gesamte Organisation wirksam werden.

Wie bereits erwähnt, können Sie zum Zulassen von Drittanbieter-apps entweder die globale (organisationsweite Standardrichtlinie) bearbeiten und verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

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

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams](assign-policies.md)
