---
title: Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie mehr über App-Berechtigungsrichtlinien in Microsoft Teams und darüber, wie Sie damit steuern, welche Apps Benutzern in Ihrer Organisation zur Verfügung stehen.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: e4a09c92fad10f91abad697a92764429deed3bf8
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643079"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Verwalten von App-Berechtigungsrichtlinien in Microsoft Teams

Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche Apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen. Sie können alle oder nur bestimmte Apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren. Wenn Sie eine App blockieren, kann sie von Benutzern, die unter die Richtlinie fallen, nicht aus dem App-Shop für Microsoft Teams installiert werden. Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.

App-Berechtigungsrichtlinien verwalten Sie im Microsoft Teams Admin Center. Sie können die globale (organisationsweite Standard-) Richtlinie verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen. Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen. Nach Bearbeiten oder Zuweisen einer Richtlinie kann es einige Stunden dauern, bis die Änderungen wirksam werden.

![Screenshot der App-Berechtigungsrichtlinie.](media/app-permission-policies.png)

> [!NOTE]
> Organisationsweite App-Einstellungen setzen die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und den Benutzern zuweisen, außer Kraft.

Wenn Ihre Organisation bereits Teams verwendet, werden die App-Einstellungen, die Sie in **Mandantenweite Einstellungen** im Microsoft 365 Admin Center konfiguriert haben, in den organisationsweiten App-Einstellungen auf der Seite [Apps verwalten](manage-apps.md) widergespiegelt. Wenn Sie neu bei Teams sind und gerade erst anfangen, sind standardmäßig alle Apps in der globalen Richtlinie erlaubt. Dies umfasst von Microsoft, Drittanbietern und Ihrer Organisation veröffentlichte Apps.

Angenommen, Sie möchten alle Apps von Drittanbietern blockieren und bestimmte Apps von Microsoft für das HR-Team in Ihrem Unternehmen zulassen. Zuerst würden Sie auf der Seite [Apps verwalten](manage-apps.md) sicherstellen, dass die Apps, die Sie für das HR-Team zulassen möchten, auf der Organisationsebene erlaubt sind. Dann erstellen Sie eine benutzerdefinierte Richtlinie mit dem Namen "App-Berechtigungsrichtlinie für HR", konfigurieren sie so, dass die gewünschten Apps blockiert und zugelassen werden, und weisen sie den Benutzern im HR-Team zu.

> [!NOTE]
> Wenn Sie Teams in einer Umgebung von Microsoft 365 Government Community Cloud High (GCCH) und Department of Defense (DoD) bereitgestellt haben, finden Sie unter Verwalten von organisationsweiten [App-Einstellungen für Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) weitere Informationen zu App-Einstellungen von Drittanbietern, die für GCCH und DoD eindeutig sind.

## <a name="create-a-custom-app-permission-policy"></a>Erstellen einer benutzerdefinierten App-Berechtigungsrichtlinie

Wenn Sie die für verschiedene Benutzergruppen in Ihrer Organisation verfügbaren Apps steuern möchten, können Sie eine oder mehrere benutzerdefinierte App-Berechtigungsrichtlinien erstellen und zuweisen. Sie können separate benutzerdefinierte Richtlinien erstellen und zuweisen, je nachdem, ob die Apps von Microsoft, von Drittanbietern oder von Ihrer Organisation veröffentlicht werden. Sie sollten unbedingt berücksichtigen, dass Sie nach dem Erstellen einer benutzerdefinierten Richtlinie diese nicht mehr ändern können, wenn Drittanbieter-Apps in den organisationsweiten App-Einstellungen deaktiviert sind.

1. Anmelden beim [Teams Admin Center](https://admin.teams.microsoft.com/dashboard)
1. Wechseln Sie im linken Bereich zu **AppsPermissionsrichtlinien** >  Teams **AppsPermission**.
1. Klicken Sie auf **Hinzufügen**.
    ![Screenshot der neuen App-Berechtigungsrichtlinie.](media/app-permission-policies-new-policy.png)
1. Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.
1. Wählen Sie unter **Microsoft-Apps**, **Drittanbieter-Apps** und **Benutzerdefinierte Apps** eine der folgenden Optionen aus:

    - **Alle Apps zulassen**
    - **Bestimmte Apps zulassen und alle anderen blockieren**
    - **Bestimmte Apps blockieren und alle anderen zulassen**
    - **Alle Apps blockieren**

1. Wenn Sie **Bestimmte Apps zulassen und alle anderen blockieren** ausgewählt haben, fügen Sie die Apps hinzu, die Sie zulassen möchten:

    1. Wählen Sie **Apps zulassen** aus.
    1. Suchen Sie nach den Apps, die Sie zulassen möchten, und klicken Sie dann auf **Hinzufügen**. Die Suchergebnisse werden nach dem App-Herausgeber gefiltert (**Microsoft-Apps**, **Drittanbieter-Apps** oder **Benutzerdefinierte Apps**).
    1. Wenn Sie die Liste der Apps ausgewählt haben, klicken Sie auf **Zulassen**.

1. Wenn Sie bestimmte Apps blockieren und alle anderen zulassen ausgewählt **haben, suchen** Sie nach den Apps, die Sie blockieren möchten, fügen Sie sie hinzu, und wählen Sie dann **Blockieren aus**.
1. Klicken Sie auf **Speichern**.

## <a name="edit-an-app-permission-policy"></a>Bearbeiten einer App-Berechtigungsrichtlinie

Sie können das Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der globalen Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.

1. Wechseln Sie im linken Bereich des Microsoft Teams Admin Center zu Richtlinien **Teams** >  **Permission.**
1. Wählen Sie die Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken, und wählen Sie dann **Bearbeiten** aus.
1. Nehmen Sie nun die gewünschten Änderungen vor. Sie können die Einstellungen basierend auf dem App-Herausgeber verwalten und Apps basierend auf der Einstellung "Zulassen/Blockieren" hinzufügen und entfernen.
1. Klicken Sie auf **Speichern**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie an Benutzer

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Verwalten von organisationsweiten App-Einstellungen für Microsoft 365 Government  

Bei einer Microsoft 365 Government - GCCH und DoD-Bereitstellung von Teams ist es wichtig, die folgenden Informationen zu App-Einstellungen von Drittanbietern zu kennen, die für GCCH und DoD eindeutig sind.

Im GCC sind alle Apps von Drittanbietern standardmäßig blockiert. Außerdem finden Sie auf der Seite mit den App-Berechtigungsrichtlinien im Microsoft Teams Admin Center den folgenden Hinweis zur Verwaltung von Drittanbieter-Apps.

:::image type="content" source="media/app-permission-policies-gcc-trimmed.png" alt-text="Screenshot der App-Berechtigungsrichtlinie in GCCH und DoD" lightbox="media/app-permission-policies-gcc.png":::

> [!NOTE]
> In GCCH und DOD-Wolken sind die Drittanbieter-Apps nicht verfügbar.

Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, ob Benutzer Apps von Drittanbietern installieren können. Organisationsweite App-Einstellungen regeln das Verhalten für alle Benutzer und setzen alle anderen App-Berechtigungsrichtlinien, die den Benutzern zugewiesen wurden, außer Kraft. Sie können sie verwenden, um bösartige oder problematische Apps zu kontrollieren.

1. Wählen Sie auf der Seite **Berechtigungsrichtlinien** die Option **Organisationsweite App-Einstellungen** aus. Sie können in dem Fenster dann die gewünschten Einstellungen konfigurieren.

    ![Screenshot der organisationsweiten App-Einstellungen.](media/app-permission-policies-gcc-org-wide.png)

1. Aktivieren oder deaktivieren Sie unter **Drittanbieter-Apps** diese Einstellungen, um den Zugriff auf Drittanbieter-Apps zu steuern:

    - **Drittanbieter-Apps zulassen**: Steuert, ob Benutzer Drittanbieter-Apps verwenden können. Wenn Sie diese Einstellung deaktivieren, können Ihre Benutzer keine Drittanbieter-Apps installieren oder verwenden. In einer Microsoft 365 Government - GCCH und DoD-Bereitstellung von Teams ist diese Einstellung standardmäßig deaktiviert.
    - **Alle neuen Drittanbieter-Apps, die im Store veröffentlicht werden, standardmäßig zulassen**: Steuert, ob neue Drittanbieter-Apps, die im Teams-App-Store veröffentlicht werden, automatisch in Teams verfügbar gemacht werden. Sie können diese Option nur aktivieren, wenn Sie Drittanbieter-Apps zulassen.

1. Fügen Sie unter **Blockierte Apps** die Apps hinzu, die Sie in Ihrer Organisation blockieren möchten. In einer Microsoft 365 Government - GCCH und DoD-Bereitstellung von Teams werden standardmäßig alle Drittanbieter-Apps dieser Liste hinzugefügt. Wenn Sie eine Drittanbieter-App in Ihrer Organisation zulassen möchten, entfernen Sie diese App aus der Liste der blockierten Apps. Wenn Sie eine App organisationsweit blockieren, wird die App automatisch für alle Ihre Benutzer blockiert, unabhängig davon, ob sie in einer App-Berechtigungsrichtlinie erlaubt ist.
1. Wählen **Sie Speichern** aus, damit die Organisationsweiten App-Einstellungen wirksam werden.

Wie bereits erwähnt, können Sie, um Apps von Drittanbietern zuzulassen, entweder die globale (organisationsweite Standard-) Richtlinie bearbeiten und verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.

## <a name="faq"></a>Häufig gestellte Fragen

### <a name="working-with-app-permission-policies"></a>Verwenden von App-Berechtigungsrichtlinien

#### <a name="what-app-interactions-do-permission-policies-affect"></a>Auf welche App-Interaktionen wirken sich die Berechtigungsrichtlinien aus?

Berechtigungsrichtlinien regeln die Verwendung von Apps, indem sie die Installation, Erkennung und Interaktion für Endbenutzer steuern. Administratoren können Apps weiterhin im Microsoft Teams Admin Center verwalten, unabhängig von den ihnen zugewiesenen Berechtigungsrichtlinien.

#### <a name="can-i-control-line-of-business-lob-apps"></a>Kann ich Branchen-Apps steuern?

Ja, Sie können App-Berechtigungsrichtlinien verwenden, um das Rollout und die Verteilung von benutzerdefinierten (Branchen-) Apps zu steuern. Sie können eine benutzerdefinierte Richtlinie erstellen oder die globale Richtlinie bearbeiten, um benutzerdefinierte Apps basierend auf den Anforderungen Ihrer Organisation zuzulassen oder zu blockieren.

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

Wenn eine App blockiert ist, können Benutzer zum Beispiel die folgenden Aktionen nicht ausführen:

- Die App persönlich bzw. zu einem Chat oder Team hinzufügen
- Nachrichten an den Bot der App senden
- Tastenaktionen ausführen, die Informationen an die App zurücksenden, wie z. B. Aktionen erfordernde Nachrichten  
- Registerkarte einer App anzeigen
- Connectors für den Empfang von Benachrichtigungen einrichten
- Messaging-Erweiterung der App programmieren

Das Legacyportal erlaubte die Steuerung von Apps auf Organisationsebene, d. h. blockierte Apps sind für alle Benutzer in der Organisation blockiert. Das Blockieren einer App auf der Seite [Apps verwalten](manage-apps.md) funktioniert genau so.

Wurden bestimmten Benutzern App-Berechtigungsrichtlinien zugewiesen, und wurde eine App mit Bot- oder Connectorfunktion zugelassen und dann blockiert und anschließend nur für einige Benutzer in einem freigegebenen Kontext zugelassen, können Mitglieder eines Gruppenchats oder Kanals, die keine Berechtigung für diese App haben, den Nachrichtenverlauf und die Nachrichten sehen, die vom Bot oder Connector gepostet wurden, können aber nicht mit ihm interagieren.

## <a name="related-topics"></a>Verwandte Themen

[Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md)

[Zuweisen von Richtlinien zu Benutzern in Teams](policy-assignment-overview.md)
