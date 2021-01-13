---
title: Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Erfahren Sie mehr über Die Berechtigungsrichtlinien für Apps in Microsoft Teams und wie Sie damit steuern können, welche Apps für Benutzer in Ihrer Organisation verfügbar sind.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802495"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle Von Microsoft, Drittanbietern und Ihrer Organisation veröffentlichten Apps oder bestimmte Apps zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

Sie verwalten Richtlinien für Die Berechtigung für Apps im Microsoft Teams Admin Center. Sie können die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.

![Screenshot der Berechtigungsrichtlinie für die App](media/app-permission-policies.png)

> [!NOTE]
> Organisationsweite App-Einstellungen setzen die globale Richtlinie und alle benutzerdefinierten Richtlinien außer Kraft, die Sie erstellen und Benutzern zuweisen.

Wenn Sich Ihre Organisation bereits in Teams befindet, werden die **App-Einstellungen,** die Sie in mandantenweiten Einstellungen im Microsoft 365 Admin Center konfiguriert haben, in den organisationsweiten App-Einstellungen auf der Seite "Apps verwalten" [angezeigt.](manage-apps.md) Wenn Sie neu bei Teams sind und gerade erst beginnen, sind standardmäßig alle Apps in der globalen Richtlinie zulässig. Dazu gehören Apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden.

Beispielsweise möchten Sie alle Apps von Drittanbietern blockieren und bestimmte Apps von Microsoft für das Personalteam in Ihrer Organisation zulassen. Zuerst würden Sie zur [](manage-apps.md) Seite "Apps verwalten" wechseln und sicherstellen, dass die Apps, die Sie dem Personalteam zulassen möchten, auf Organisationsebene zulässig sind. Erstellen Sie dann eine benutzerdefinierte Richtlinie mit dem Namen "HR-App-Berechtigungsrichtlinie", legen Sie sie so fest, dass die von Ihnen verwendeten Apps blockiert und zulässig sind, und weisen Sie sie Benutzern im Personalteam zu.

> [!NOTE]
> Wenn Sie Teams in einer Microsoft 365 Government Community Cloud (GCC)-Umgebung bereitgestellt haben, finden Sie unter "Verwalten von [organisationsweiten App-Einstellungen für Microsoft 365 Government"](#manage-org-wide-app-settings-for-microsoft-365-government) weitere Informationen zu App-Einstellungen von Drittanbietern, die nur für GCC verfügbar sind.

## <a name="create-a-custom-app-permission-policy"></a>Erstellen einer benutzerdefinierten App-Berechtigungsrichtlinie

Wenn Sie die Apps steuern möchten, die für unterschiedliche Benutzergruppen in Ihrer Organisation verfügbar sind, erstellen Sie eine oder mehrere benutzerdefinierte App-Berechtigungsrichtlinien, und weisen Sie sie zu. Sie können separate benutzerdefinierte Richtlinien erstellen und zuweisen, die darauf basieren, ob Apps von Microsoft, Drittanbietern oder Ihrer Organisation veröffentlicht werden. Es ist wichtig zu wissen, dass Sie nach dem Erstellen einer benutzerdefinierten Richtlinie diese nicht mehr ändern können, wenn Apps von Drittanbietern in organisationsweiten App-Einstellungen deaktiviert sind.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den **Berechtigungsrichtlinien für Teams-Apps.**  >  
2. Klicken Sie auf **Hinzufügen**. <br>
    ![Screenshot der neuen Berechtigungsrichtlinie für Apps](media/app-permission-policies-new-policy.png)
3. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
4. Wählen **Sie unter "Microsoft-Apps",** **"Drittanbieter-Apps"** und **"Benutzerdefinierte** Apps" eine der folgenden Optionen aus:

    - **Alle Apps zulassen**
    - **Zulassen bestimmter Apps und Blockieren aller anderen Apps**
    - **Blockieren bestimmter Apps und Zulassen aller anderen Apps**
    - **Alle Apps blockieren**

5. Wenn Sie "Bestimmte Apps **zulassen" ausgewählt und andere blockiert haben,** fügen Sie die Apps hinzu, die Sie zulassen möchten:

    1. Wählen Sie **"Apps zulassen" aus.**
    1. Suchen Sie nach den Apps, die Sie zulassen möchten, und klicken Sie dann auf **"Hinzufügen".** Die Suchergebnisse werden nach dem Herausgeber der App gefiltert **(Microsoft-Apps,** Apps von Drittanbietern oder **benutzerdefinierte Apps).** 
    1. Wenn Sie die Liste der Apps ausgewählt haben, klicken Sie auf **"Zulassen".** 

6. Wenn Sie "Bestimmte Apps blockieren" ausgewählt haben und alle anderen **zulassen,** suchen Sie nach den Apps, die Sie blockieren möchten, fügen Sie sie hinzu, und klicken Sie dann auf **"Blockieren".**
7. Klicken Sie auf **Speichern**.

## <a name="edit-an-app-permission-policy"></a>Bearbeiten einer Berechtigungsrichtlinie für eine App

Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu den **Berechtigungsrichtlinien für Teams-Apps.**  >  
2. Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.
3. Nehmen Sie nun die gewünschten Änderungen vor. Sie können Einstellungen basierend auf dem Herausgeber der App verwalten und Apps basierend auf der Einstellung "Zulassen/Blockieren" hinzufügen und entfernen.
4. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Zuweisen einer Benutzerdefinierten App-Berechtigungsrichtlinie zu Benutzern

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Verwalten von organisationsweiten App-Einstellungen für Microsoft 365 Government  

Bei einer Microsoft 365 Government - GCC-Bereitstellung von Teams ist es wichtig, die folgenden Informationen zu den Einstellungen von Drittanbieter-Apps zu kennen, die nur für GCC verfügbar sind.

In GCC werden alle Apps von Drittanbietern standardmäßig blockiert. Darüber hinaus wird im Microsoft Teams Admin Center auf der Seite mit den Berechtigungsrichtlinien für Apps die folgende Notiz zum Verwalten von Apps von Drittanbietern angezeigt.

![Screenshot der Berechtigungsrichtlinie für Apps in GCC](media/app-permission-policies-gcc.png)

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer Apps von Drittanbietern installieren können. Organisationsweite App-Einstellungen steuern das Verhalten aller Benutzer und setzen alle anderen Benutzerberechtigungsrichtlinien für Apps außer Kraft. Sie können damit schädliche oder problematische Apps steuern.

1. Wählen Sie **auf der Seite "Berechtigungsrichtlinien"** **die organisationsweiten App-Einstellungen aus.** Anschließend können Sie die im Bereich angezeigten Einstellungen konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen](media/app-permission-policies-gcc-org-wide.png)
    
2. Deaktivieren **oder aktivieren Sie unter "Apps** von Drittanbietern" diese Einstellungen, um den Zugriff auf Apps von Drittanbietern zu steuern:

    - **Apps von Drittanbietern zulassen:** Damit wird bestimmt, ob Benutzer Apps von Drittanbietern verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Apps von Drittanbietern installieren oder verwenden. Bei einer Microsoft 365 Government - GCC-Bereitstellung von Teams ist diese Einstellung standardmäßig deaktiviert.
    - **Standardmäßig alle neuen Apps** von Drittanbietern zulassen, die im Store veröffentlicht werden: Mit dieser Steuerung wird festgelegt, ob neue Apps von Drittanbietern, die im Teams App Store veröffentlicht werden, automatisch in Teams verfügbar werden. Sie können diese Option nur festlegen, wenn Sie Apps von Drittanbietern zulassen.

3. Fügen **Sie unter "Blockierte** Apps" die Apps hinzu, die Sie organisationsweit blockieren möchten. Bei einer Microsoft 365 Government - GCC-Bereitstellung von Teams werden standardmäßig alle Apps von Drittanbietern dieser Liste hinzugefügt. Entfernen Sie die App für alle Apps von Drittanbietern, die Sie in Ihrer Organisation zulassen möchten, aus dieser Liste blockierter Apps. Wenn Sie eine App organisationsweit blockieren, wird die App automatisch für alle Benutzer blockiert, unabhängig davon, ob sie in den Berechtigungsrichtlinien für Apps zulässig ist.
4. Klicken **Sie auf "Speichern** für organisationsweite App-Einstellungen", um sie wirksam zu machen.

Wie bereits erwähnt, können Sie zum Zulassen von Apps von Drittanbietern entweder die globale Richtlinie (organisationsweite Standardrichtlinie) bearbeiten und verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-permission-policies"></a>Arbeiten mit Berechtigungsrichtlinien für Apps

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Welche App-Interaktionen wirken sich Berechtigungsrichtlinien darauf aus?
Berechtigungsrichtlinien steuern die App-Nutzung, indem die Installation, Ermittlung und Interaktion für Endbenutzer kontrolliert wird. Administratoren können Apps weiterhin im Microsoft Teams Admin Center verwalten, unabhängig von den ihnen zugewiesenen Berechtigungsrichtlinien.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Kann ich Branchen-Apps steuern?
Ja, Sie können Berechtigungsrichtlinien für Apps verwenden, um das Rollout und die Verteilung von benutzerdefinierten Apps zu steuern. Sie können eine benutzerdefinierte Richtlinie erstellen oder die globale Richtlinie bearbeiten, um benutzerdefinierte Apps basierend auf den Anforderungen Ihrer Organisation zu erlauben oder zu blockieren.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Wie beziehen sich Die Berechtigungsrichtlinien für Apps auf angeheftet Apps und auf Richtlinien zum Einrichten von Apps?

Sie können Richtlinien für die Einrichtung von Apps zusammen mit Berechtigungsrichtlinien für Apps verwenden. Vorab angeheftet Apps werden aus der Gruppe der aktivierten Apps für einen Benutzer ausgewählt. Wenn ein Benutzer über eine Berechtigungsrichtlinie für Apps verfügt, die eine App in seiner App-Setup-Richtlinie blockiert, wird diese App in Teams nicht angezeigt.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Kann ich mithilfe von Berechtigungsrichtlinien für Apps das Hochladen benutzerdefinierter Apps einschränken?

Sie können organisationsweite Einstellungen  auf der Seite "Apps verwalten" oder Richtlinien für das Einrichten von Apps verwenden, um das Hochladen benutzerdefinierter Apps für Ihre Organisation einzuschränken.  

Verwenden Sie benutzerdefinierte App-Richtlinien, um bestimmte Benutzer am Hochladen benutzerdefinierter Apps zu beschränken. Weitere Informationen finden Sie unter "Verwalten von Richtlinien und Einstellungen [für benutzerdefinierte Apps in Teams".](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Gilt das Blockieren einer App für mobile Teams-Clients?

Ja, wenn Sie eine App blockieren, wird diese App in allen Teams-Clients blockiert.  

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Wie sieht eine Benutzeroberfläche aus, wenn eine App blockiert wird?

Benutzer können nicht mit einer blockierten App oder deren Funktionen wie Bots, Registerkarten und Messagingerweiterungen interagieren. In einem freigegebenen Kontext, z. B. einem Team- oder Gruppenchat, können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden. Teams zeigt dem Benutzer an, wenn eine App blockiert ist.

Wenn beispielsweise eine App blockiert wird, können Benutzer keine der folgenden Aufgaben machen:

- Persönliches Hinzufügen der App oder zu einem Chat oder Team
- Senden von Nachrichten an den Bot der App
- Ausführen von Schaltflächenaktionen, die Informationen zurück an die App senden, z. B. Handlungsbedarfsmeldungen  
- Anzeigen der Registerkarte der App
- Einrichten von Connectors für den Empfang von Benachrichtigungen
- Verwenden der Nachrichtenerweiterung der App

Im alten Portal konnten Apps auf Organisationsebene kontrolliert werden, d. h., wenn eine App blockiert wird, wird sie für alle Benutzer in der Organisation blockiert. Das Blockieren einer App auf der Seite ["Apps verwalten"](manage-apps.md) funktioniert genauso.

Wenn für bestimmte Benutzer zugewiesene App-Berechtigungsrichtlinien, wenn eine App mit Bot oder Connectorfunktion zugelassen und dann blockiert wurde, und wenn die App dann nur für einige Benutzer in einem freigegebenen Kontext zulässig ist, können Mitglieder eines Gruppenchats oder Kanals, die nicht über die Berechtigung für diese App verfügen, den Nachrichtenverlauf und nachrichten anzeigen, die vom Bot oder Connector gepostet wurden. , kann aber nicht damit interagieren.

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Benutzern in Microsoft Teams Richtlinien zuweisen](assign-policies.md)
