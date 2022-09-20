---
title: Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie mehr über App-Berechtigungsrichtlinien in Microsoft Teams und wie Sie die Verfügbarkeit von Apps für Ihre Endbenutzer steuern.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: d562e15627994339f4cb24ee8d3f28181ebf965b
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837365"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle oder nur bestimmte Apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

App-Berechtigungsrichtlinien verwalten Sie im Microsoft Teams Admin Center. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

![Screenshot einer App-Berechtigungsrichtlinie.](media/app-permission-policies.png)

> [!NOTE]
> Organisationsweite App-Einstellungen setzen die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und den Benutzern zuweisen, außer Kraft.

Wenn Ihre Organisation bereits Teams verwendet, werden die App-Einstellungen, die Sie in **Mandantenweite Einstellungen** im Microsoft 365 Admin Center konfiguriert haben, in den organisationsweiten App-Einstellungen auf der Seite [Apps verwalten](manage-apps.md) widergespiegelt. Wenn Sie neu bei Teams sind und gerade erst anfangen, sind standardmäßig alle Apps in der globalen Richtlinie erlaubt. Es umfasst Apps, die von Microsoft, Softwareanbietern von Drittanbietern und Ihrer Organisation veröffentlicht wurden.

Angenommen, Sie möchten nur einige bestimmte Apps für das HR-Team in Ihrer Organisation zulassen. Stellen Sie zunächst auf der Seite " [Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps) " sicher, dass die Apps, die Sie für das HR-Team zulassen möchten, auf Organisationsebene zulässig sind. Erstellen Sie dann eine benutzerdefinierte Richtlinie, legen Sie sie auf "Blockieren" und "Zulassen der gewünschten Apps" fest, und weisen Sie die Richtlinie Benutzern im Hr-Team zu.

> [!NOTE]
> Informationen zu App-Einstellungen von Drittanbietern, die für die Microsoft 365 Government Community Cloud High (GCCH)- und DoD-Umgebung (Department of Defense) eindeutig sind, finden Sie unter [Verwalten organisationsweiter App-Einstellungen für Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government).

## <a name="create-a-custom-app-permission-policy"></a>Erstellen einer benutzerdefinierten App-Berechtigungsrichtlinie

Verwenden Sie eine oder mehrere benutzerdefinierte App-Berechtigungsrichtlinien, wenn Sie die Apps steuern möchten, die für verschiedene Benutzergruppen verfügbar sind. Sie können separate benutzerdefinierte Richtlinien erstellen und zuweisen, je nachdem, ob die Apps von Microsoft, von Drittanbietern oder von Ihrer Organisation veröffentlicht werden. Nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, können Sie sie nicht mehr ändern, wenn Apps von Drittanbietern in organisationsweiten App-Einstellungen deaktiviert sind.

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **[Berechtigungsrichtlinien für](https://admin.teams.microsoft.com/policies/app-permission)** **Teams-Apps** >  zu.
1. Klicken Sie auf **Hinzufügen**.

   ![Screenshot der neuen App-Berechtigungsrichtlinie.](media/app-permission-policies-new-policy.png)

1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
1. Wählen Sie unter **Microsoft-Apps**, **Drittanbieter-Apps** und **Benutzerdefinierte Apps** eine der folgenden Optionen aus:

    * Alle Apps zulassen
    * Bestimmte Apps zulassen und alle anderen blockieren
    * Bestimmte Apps blockieren und alle anderen zulassen
    * Alle Apps blockieren

1. Wenn Sie **bestimmte Apps zulassen und alle anderen blockieren** ausgewählt haben, fügen Sie die Apps hinzu, die Sie zulassen möchten:

    1. Wählen Sie **Apps zulassen** aus.
    1. Suchen Sie nach den Apps, die Sie zulassen möchten, und wählen Sie dann **"Hinzufügen"** aus. Die Suchergebnisse werden nach dem **App-Entwickler (Microsoft-Apps, Drittanbieter-Apps** oder **benutzerdefinierte Apps**) gefiltert.
    1. Wenn Sie die Liste der Apps ausgewählt haben, wählen Sie **"Zulassen"** aus.

1. Wenn Sie **auf ähnliche Weise bestimmte Apps blockieren und alle anderen zulassen** ausgewählt haben, suchen Sie nach den Apps, die Sie blockieren möchten, und fügen Sie sie hinzu, und wählen Sie dann **"Blockieren"** aus.
1. Klicken Sie auf **Speichern**.

## <a name="edit-an-app-permission-policy"></a>Bearbeiten einer App-Berechtigungsrichtlinie

Sie können das Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie und benutzerdefinierter Richtlinien, die Sie erstellen.

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **[Berechtigungsrichtlinien für](https://admin.teams.microsoft.com/policies/app-permission)** **Teams-Apps** >  zu.
1. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.
1. Nehmen Sie nun die gewünschten Änderungen vor. Sie können Einstellungen basierend auf dem App-Entwickler verwalten und Apps basierend auf der Einstellung "Zulassen/Blockieren" hinzufügen und entfernen.
1. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie an Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Verwalten von organisationsweiten App-Einstellungen für Microsoft 365 Government  

In einer Microsoft 365 Government - GCC-, GCCH- und DoD-Bereitstellung von Teams werden alle Drittanbieter-Apps standardmäßig blockiert. In GCCH- und DOD-Clouds sind die Drittanbieter-Apps nicht verfügbar. Darüber hinaus wird in GCC der folgende Hinweis zum Verwalten von Drittanbieter-Apps auf der Seite "App-Berechtigungsrichtlinien" im Microsoft Teams Admin Center angezeigt.

:::image type="content" source="media/app-permission-policies-gcc.png" alt-text="Screenshot der App-Berechtigungsrichtlinie in GCCH und DoD.":::

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer Apps von Drittanbietern installieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft.

<!---
1. On the **Permission policies** page, select **Org-wide app settings**. You can then configure the settings you want in the panel. --->

### <a name="for-gcc-clouds"></a>Für GCC-Clouds

1. Wählen Sie auf der Seite "**[Apps verwalten](https://admin.teams.microsoft.com/policies/manage-apps)**" von **Teams-Apps** >  **organisationsweite App-Einstellungen** aus. Sie können in dem Fenster dann die gewünschten Einstellungen konfigurieren.

   ![Screenshot der organisationsweiten App-Einstellungen in GCC.](media/app-permission-policies-gcc-org-wide.png)

1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    * **Apps von Drittanbietern zulassen**: Mit dieser Option wird gesteuert, ob Benutzer Apps von Drittanbietern verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Drittanbieter-Apps installieren oder verwenden. In einer Microsoft 365 Government - GCCH- und DoD-Bereitstellung von Teams ist diese Einstellung standardmäßig deaktiviert.
    * **Standardmäßig neue Apps von Drittanbietern zulassen, die im Store veröffentlicht** werden: Mit dieser Option wird gesteuert, ob neue Apps von Drittanbietern, die im Teams-App Store veröffentlicht werden, automatisch in Teams verfügbar werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Fügen Sie unter **Blockierte Apps** die Apps hinzu, die Sie in Ihrer Organisation blockieren möchten. In einer Microsoft 365 Government - GCCH- und DoD-Bereitstellung von Teams werden standardmäßig alle Drittanbieter-Apps zu dieser Liste hinzugefügt. Wenn Sie eine Drittanbieter-App in Ihrer Organisation zulassen möchten, entfernen Sie diese App aus der Liste der blockierten Apps. Wenn Sie eine App organisationsweit blockieren, wird die App automatisch für alle Ihre Benutzer blockiert, unabhängig davon, ob sie in App-Berechtigungsrichtlinien zulässig ist.

1. Wählen Sie **Speichern** aus, damit die organisationsweiten App-Einstellungen wirksam werden.

Um Apps von Drittanbietern zuzulassen, bearbeiten und verwenden Sie entweder die globale Richtlinie (organisationsweite Standardrichtlinie), oder erstellen und weisen Sie benutzerdefinierte Richtlinien zu.

### <a name="for-gcch-and-dod-clouds"></a>Für GCCH- und DoD-Clouds

1. Melden Sie sich beim Teams Admin Center an, und greifen Sie auf **[Die Berechtigungsrichtlinien für](https://admin.teams.microsoft.com/policies/app-permission)** **Teams-Apps** >  zu.

1. Wählen Sie **organisationsweite App-Einstellungen** aus. Fügen Sie unter **Blockierte Apps** die Apps hinzu, die Sie in Ihrer Organisation blockieren möchten. In einer Microsoft 365 Government - GCCH- und DoD-Bereitstellung von Teams werden standardmäßig alle Drittanbieter-Apps zu dieser Liste hinzugefügt. Wenn Sie eine App organisationsweit blockieren, wird die App automatisch für alle Ihre Benutzer blockiert, unabhängig davon, ob sie in App-Berechtigungsrichtlinien zulässig ist.

   :::image type="content" source="media/app-permission-policies-gcch-dod-org-wide.png" alt-text="Screenshot der organisationsweiten App-Einstellungen in GCCH und DoD.":::

1. Wählen Sie **Speichern** aus, damit die organisationsweiten App-Einstellungen wirksam werden.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="work-with-app-permission-policies"></a>Arbeiten mit App-Berechtigungsrichtlinien

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Auf welche App-Interaktionen wirken sich die Berechtigungsrichtlinien aus?

Berechtigungsrichtlinien regeln die Verwendung von Apps, indem sie die Installation, Erkennung und Interaktion für Endbenutzer steuern. Administratoren können Apps weiterhin im Microsoft Teams Admin Center verwalten, unabhängig von den ihnen zugewiesenen Berechtigungsrichtlinien.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>Wie hängen App-Berechtigungsrichtlinien mit angehefteten Apps und App-Setuprichtlinien zusammen?

Sie können App-Setuprichtlinien zusammen mit App-Berechtigungsrichtlinien verwenden. Vorab angeheftete Apps werden aus der Menge der aktivierten Apps für einen Benutzer ausgewählt. Außerdem gilt, dass eine App, die in der App-Setuprichtlinie einer vom Benutzer verwendeten App-Berechtigungsrichtlinie blockiert wird, in Teams nicht angezeigt wird.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>Kann ich mit App-Berechtigungsrichtlinien das Hochladen von benutzerdefinierten Apps einschränken?

Sie können organisationsweite Einstellungen auf der Seite **Apps verwalten** oder App-Setuprichtlinien verwenden, um das Hochladen von benutzerdefinierten Apps für Ihre Organisation zu beschränken.  

Um das Hochladen von benutzerdefinierten Apps für bestimmte Benutzer einzuschränken, verwenden Sie benutzerdefinierte App-Richtlinien. Weitere Informationen finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>Gilt das Blockieren einer App auch für mobile Teams-Clients?

Ja, wenn Sie eine App blockieren, wird diese App auf allen Teams-Clients blockiert.  

### <a name="user-experience"></a>Benutzererfahrung

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>Was passiert beim Benutzer, wenn eine App blockiert wird?

Benutzer können mit einer blockierten App oder ihren Funktionen, wie Bots, Registerkarten und Messaging-Erweiterungen, nicht interagieren. In einem gemeinsamen Kontext, wie z. B. einem Team- oder Gruppenchat, können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden. Teams zeigt dem Benutzer an, wenn eine App blockiert ist.

Wenn beispielsweise eine App blockiert ist, können Benutzer keine der folgenden Aufgaben ausführen:

* Die App persönlich bzw. zu einem Chat oder Team hinzufügen
* Senden von Nachrichten an den Bot der App
* Tastenaktionen ausführen, die Informationen an die App zurücksenden, wie z. B. Aktionen erfordernde Nachrichten  
* Anzeigen der Registerkarte der App
* Connectors für den Empfang von Benachrichtigungen einrichten
* Verwenden der Messaging-Erweiterung der App

Das Legacyportal erlaubte die Steuerung von Apps auf Organisationsebene, d. h. blockierte Apps sind für alle Benutzer in der Organisation blockiert. Das Blockieren einer App auf der Seite [Apps verwalten](manage-apps.md) funktioniert genau so.

Wurden bestimmten Benutzern App-Berechtigungsrichtlinien zugewiesen, und wurde eine App mit Bot- oder Connectorfunktion zugelassen und dann blockiert und anschließend nur für einige Benutzer in einem freigegebenen Kontext zugelassen, können Mitglieder eines Gruppenchats oder Kanals, die keine Berechtigung für diese App haben, den Nachrichtenverlauf und die Nachrichten sehen, die vom Bot oder Connector gepostet wurden, können aber nicht mit ihm interagieren.

## <a name="see-also"></a>Siehe auch

* [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)
* [Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
* [Vergleich der Verfügbarkeit von Teams-Features](/office365/servicedescriptions/teams-service-description#feature-availability)
