---
title: Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection: ''
f1.keywords:
- CSH
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.overview
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.presence
- ms.teamsadmincenter.org-widesettings.skypeforbusiness.skypemeetingbroadcast
- ms.teamsadmincenter.users.skypeforbusiness.settings
ms.custom: ''
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie einstellungen für Skype for Business-Funktionen im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: 944a5f8101b8355f4a2cc3e18966e5eb01b94be9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834215"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Als Administrator verwalten Sie im Microsoft Teams Admin Center die Skype for Business-Funktionen für Skype for Business-Benutzer in Ihrer Organisation. Sie können die Einstellungen [für Ihre](#manage-skype-for-business-settings-for-your-organization) Organisation auf [](#manage-skype-for-business-settings-for-individual-users) der **Skype for** Business-Seite und die Einstellungen für einzelne Benutzer auf der **Registerkarte "Skype for Business"** der Benutzerdetailsetailseiten verwalten.

Die Skype **for** Business-Seite wird nur angezeigt, wenn der Koexistenzmodus für Ihre Organisation nicht nur auf **Teams festgelegt ist.** Ebenso wird die Registerkarte **"Skype for Business"** für einen Benutzer nur angezeigt, wenn der Koexistenzmodus des Benutzers nicht nur **Teams ist.** Weitere Informationen zu Koexistenzmodi finden Sie unter "Verstehen der Koexistenz und Interoperabilität von Teams und [Skype for Business"](teams-and-skypeforbusiness-coexistence-and-interoperability.md) sowie unter Festlegen der Einstellungen für Koexistenz und [Upgrade.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Skype for Business-Einstellungen waren zuvor im **Legacyportal im** Microsoft Teams Admin Center verfügbar. Mit der Einstellung des alten Portals haben wir die Einstellungen an diese neuen Speicherorte im Teams Admin Center für Skype for Business Management migriert.

Ihnen muss die [Azure AD-Administratorrolle](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) eines globalen Admins oder eines Skype for Business-Administrator zugewiesen sein, um Skype for Business-Funktionen im Microsoft Teams Admin Center verwalten zu können.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Verwalten von Skype for Business-Einstellungen für Ihre Organisation

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **den organisationsweiten**  >  **Einstellungen für Skype for Business.** Von hier aus können Sie Skype Meeting Broadcast, den Anwesenheitsschutz und Benachrichtigungen über mobile Geräte für alle Skype for Business-Benutzer in Ihrer Organisation konfigurieren und verwalten.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Verwenden Sie die folgenden Einstellungen zum Verwalten von [Skype Meeting Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in Ihrer Organisation.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot der Einstellungen für Skype Meeting Broadcast im Admin Center":::

- **Skype Meeting Broadcasts:** Aktivieren Sie diese Option, um Skype Meeting Broadcast für Ihre Organisation zu aktivieren. Nachdem Sie diese Funktion aktiviert haben, müssen Sie Ihr Netzwerk [für Skype Meeting Broadcast einrichten.](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Vorschaufeatures:** Aktivieren Sie diese, um frühzeitigen Zugriff auf neue Features zu erhalten.
- **Organisatoren können anonyme** Besprechungen planen: Aktivieren Sie diese Möglichkeit, wenn Organisatoren Übertragungsereignisse erstellen lassen möchten, bei denen jeder außerhalb Ihrer Organisation teilnehmen kann, ohne sich anmelden zu müssen. 
- **Aufzeichnen von Skype Meeting Broadcast-Besprechungen:** Aktivieren Sie diese Option, um Organisatoren und Organisatoren das Aufzeichnen von Besprechungen zu ermöglichen.  
- **Helpdesk-Support-URL** für Teilnehmer: Geben Sie die Support-URL Ihrer Organisation ein, die Besprechungsteilnehmer verwenden können, wenn sie während einer Besprechung Hilfe benötigen.

### <a name="presence-and-mobile-notifications"></a>Anwesenheits- und mobile Benachrichtigungen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Verwenden Sie die folgenden Einstellungen, um den Datenschutz für Anwesenheitsanzeigen und mobile Benachrichtigungen in Skype for Business in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot der Anwesenheitseinstellungen im Admin Center":::

#### <a name="presence"></a>Anwesenheit

Standardmäßig können Skype for Business-Benutzer in Ihrer Organisation den Anwesenheitsstatus (z. B. "Verfügbar", "Beschäftigt" oder "Ab jetzt") anderer Skype for Business-Benutzer sehen. Wählen Sie eine der folgenden Optionen aus, um die Personen zu wählen, die die Anwesenheit Ihrer Skype for Business-Benutzer sehen können.

- **Automatische Anzeige von** Anwesenheitsinformationen: Jeder Skype for Business-Benutzer in Ihrer  Organisation,  der nicht zur Liste "Extern" oder "Blockiert" des Benutzers hinzugefügt wurde, kann die Anwesenheitsinformationen dieses Benutzers sehen.
- **Anwesenheitsinformationen** nur für die Kontakte eines Benutzers anzeigen: Jeder Skype for Business-Benutzer, der  nicht  zur Liste "Extern" oder "Blockiert" des Benutzers hinzugefügt wurde, kann die Anwesenheitsinformationen des Benutzers sehen. Benutzer können diese Einstellung in Skype for Business über die Optionen unter  >  **"Einstellungen" außer Kraft**  >  **setzen.**

#### <a name="mobile-notifications"></a>Mobile Benachrichtigungen

Sie können festlegen, ob Ihre Skype for Business Mobile-Benutzer Benachrichtigungen über eingehende und verpasste Chatnachrichten, Voicemailnachrichten und verpasste Anrufe über einen Pushbenachrichtigungsdienst erhalten. Je nach den in Ihrer Organisation verwendeten mobilen Geräten können Sie den **Microsoft Push Notification Service,** den Apple Push **Notification Service** oder beides verwenden.

Berücksichtigen Sie dabei Folgendes:

- Wenn Sie Pushbenachrichtigungen deaktivieren, erhalten benutzer beim nächsten Start von Skype for Business auf ihrem Mobilgerät alle Benachrichtigungen.
- Pushbenachrichtigungen sind standardmäßig aktiviert. Einzelne Benutzer können sie in Skype for Business auf ihrem Mobilgerät deaktivieren.
- Nachdem Sie Pushbenachrichtigungen ausgeschaltet haben, können sie benutzerseitig nicht wieder eingeschaltet werden. 

> [!IMPORTANT]
> Microsoft greift für die Bereitstellung von mobilen Skype for Business-Benachrichtigungen in Echtzeit für Windows Phone-, iPhone- und iPad-Benutzer auf andere Unternehmen zurück. Weitere Informationen [finden Sie in den Datenschutzbestimmungen.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Verwalten von Skype for Business-Einstellungen für einzelne Benutzer

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Um Skype for Business-Einstellungen für einzelne Benutzer zu verwalten, wechseln Sie in der linken Navigationsleiste des Teams Admin **Centers** zu "Benutzer", klicken Sie auf den Anzeigenamen des Benutzers, um die Seite mit den Benutzerdetails zu öffnen, und wählen Sie dann die Registerkarte **"Skype for** Business-Einstellungen" aus. Von hier aus können Sie externe Zugriffs- und Besprechungseinstellungen für den Benutzer konfigurieren.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot der Registerkarte "Skype for Business" auf der Seite "Benutzerdetails"":::

### <a name="external-access-settings"></a>Einstellungen für externen Zugriff

Sie können selektiv zulassen oder blockieren, ob ein Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren kann.

- **Externe Skype for Business-Benutzer:** Aktivieren Sie dies, wenn Sie es dem Benutzer ermöglichen möchten, in Partnerdomänen mit Skype for Business-Benutzern zu kommunizieren.
- **Externe Skype-Benutzer:** Aktivieren Sie dies, wenn Sie dem Benutzer die Kommunikation mit den Skype-Benutzern gestatten möchten. 

### <a name="meeting-settings"></a>Besprechungseinstellungen

Sie können die folgenden Besprechungseinstellungen für den Benutzer konfigurieren.

- **Audio & Video:** Wählen Sie eine der folgenden Audio- und Videoeinstellungen aus:

    - **Keine:** Der Benutzer kann kein Audio oder Video verwenden.
    - **Nur Audio:** Der Benutzer kann Audio, aber kein Video verwenden.
    - **Audio und Video:** Benutzer können Audio und Video verwenden.
    - **Audio und Video (HD):** Benutzer können Audio- und HD-Video verwenden.
    
- **Aufzeichnen von unterhaltungen &** Besprechungen: Aktivieren Sie diese, um dem Benutzer das Aufzeichnen von Unterhaltungen und Besprechungen zu ermöglichen.
- **Compliance:** Aktivieren Sie dies, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind. 
