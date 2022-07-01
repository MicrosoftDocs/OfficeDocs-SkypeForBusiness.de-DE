---
title: Verwalten Skype for Business Einstellungen im Microsoft Teams Admin Center
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
search.appverid: MET150
description: Erfahren Sie, wie Sie Einstellungen für Skype for Business-Features im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: 06c5cc4a199a7b29f2db97159850583d6927fc13
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563703"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Verwalten Skype for Business Einstellungen im Microsoft Teams Admin Center

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Als Administrator verwalten Sie im Microsoft Teams Admin Center Skype for Business Features für Skype for Business Benutzer in Ihrer Organisation. Sie können Einstellungen [für Ihre Organisation](#manage-skype-for-business-settings-for-your-organization) auf der **Seite Skype for Business** und Einstellungen [für einzelne Benutzer](#manage-skype-for-business-settings-for-individual-users) auf der Registerkarte **Skype for Business** der Benutzerdetailseiten verwalten.

Die **Seite Skype for Business** wird nur angezeigt, wenn der Koexistenzmodus für Ihre Organisation nicht **nur auf Teams** festgelegt ist. Ebenso wird die Registerkarte **Skype for Business** für einen Benutzer nur angezeigt, wenn der Koexistenzmodus des Benutzers nicht **nur Teams** ist. Weitere Informationen zu Koexistenzmodi finden [Sie unter "Grundlegendes zu Teams und Skype for Business Koexistenz und Interoperabilität](teams-and-skypeforbusiness-coexistence-and-interoperability.md)" und ["Festlegen Ihrer Koexistenz- und Upgradeeinstellungen](setting-your-coexistence-and-upgrade-settings.md)".

> [!NOTE]
> Skype for Business Einstellungen befanden sich zuvor im **Legacy-Portal** im Microsoft Teams Admin Center. Mit der Einstellung des Legacyportals haben wir die Einstellungen zu diesen neuen Speicherorten im Teams Admin Center für Skype for Business Verwaltung migriert.

Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) des globalen Administrators oder Skype for Business-Administrator zugewiesen sein, um Skype for Business Features im Microsoft Teams Admin Center verwalten zu können.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Verwalten Skype for Business Einstellungen für Ihre Organisation

Wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu den **organisationsweiten Einstellungen** >  **Skype for Business**. Von hier aus können Sie Skype-Besprechung Broadcast- und Anwesenheitsdatenschutz sowie Benachrichtigungen über mobile Geräte für alle Skype for Business Benutzer in Ihrer Organisation konfigurieren und verwalten.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Verwenden Sie die folgenden Einstellungen, um [Skype-Besprechung Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot der Einstellungen für Skype-Besprechung Übertragung im Admin Center.":::

- **Skype-Besprechung Broadcasts**: Aktivieren Sie diese Option, um Skype-Besprechung Broadcast für Ihre Organisation zu aktivieren. Nachdem Sie dieses Feature aktiviert haben, müssen Sie [Ihr Netzwerk für Skype-Besprechung Broadcast einrichten](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Siehe Vorschaufeatures**: Aktivieren Sie diese Option, um frühzeitigen Zugriff auf neue Features zu erhalten.
- **Organisatoren können anonyme Besprechungen planen**: Aktivieren Sie diese Option, wenn Sie Organisatoren das Erstellen von Liveereignissen ermöglichen möchten, mit denen jeder außerhalb Ihrer Organisation teilnehmen kann, ohne sich anmelden zu müssen. 
- **Aufzeichnen Skype-Besprechung Übertragen von Besprechungen**: Aktivieren Sie diese Option, damit Organisatoren und Referenten Besprechungen aufzeichnen können.  
- **Helpdesk-Support-URL für Teilnehmer**: Geben Sie die Support-URL Ihrer Organisation ein, die Besprechungsteilnehmer verwenden können, wenn sie während einer Besprechung Hilfe benötigen.

### <a name="presence-and-mobile-notifications"></a>Anwesenheits- und mobile Benachrichtigungen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Verwenden Sie die folgenden Einstellungen, um Skype for Business Datenschutz für Anwesenheitsinformationen und mobile Benachrichtigungen in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot der Anwesenheitseinstellungen im Admin Center.":::

#### <a name="presence"></a>Anwesenheit

Standardmäßig können Skype for Business Benutzer in Ihrer Organisation den Anwesenheitsstatus (z. B. "Verfügbar", "Beschäftigt" oder "Abwesend") anderer Skype for Business Benutzer anzeigen. Wählen Sie eine der folgenden Optionen aus, um festzulegen, wer die Anwesenheit Ihrer Skype for Business Benutzer sehen kann.

- **Anwesenheitsinformationen automatisch anzeigen**: Jeder Skype for Business Benutzer in Ihrer Organisation, der der **externen** oder **blockierten** Liste des Benutzers nicht hinzugefügt wurde, kann die Anwesenheit dieses Benutzers sehen.
- **Anzeigen von Anwesenheitsinformationen nur für die Kontakte eines Benutzers**: Jeder Skype for Business Benutzer in der Kontaktliste des Benutzers, der nicht zu seiner **externen** oder **blockierten** Liste hinzugefügt wird, kann die Anwesenheit dieses Benutzers sehen. Benutzer können diese Einstellung in Skype for Business überschreiben, indem sie zu **"Einstellungstools** >  > **"-Optionen** wechseln.

#### <a name="mobile-notifications"></a>Mobile Benachrichtigungen

Sie können festlegen, ob Ihre Skype for Business mobilen Benutzern Benachrichtigungen über eingehende und verpasste Chatnachrichten, Voicemailnachrichten und verpasste Anrufe über einen Pushbenachrichtigungsdienst erhalten. Je nach den in Ihrer Organisation verwendeten mobilen Geräten können Sie den **Microsoft-Pushbenachrichtigungsdienst**, den **Apple-Pushbenachrichtigungsdienst** oder beides verwenden.

Berücksichtigen Sie dabei Folgendes:

- Wenn Sie Pushbenachrichtigungen deaktivieren, erhalten Benutzer alle Benachrichtigungen, wenn sie das nächste Mal Skype for Business auf ihrem mobilen Gerät starten.
- Standardmäßig sind Pushbenachrichtigungen aktiviert. Einzelne Benutzer können sie in Skype for Business auf ihrem mobilen Gerät deaktivieren.
- Nachdem Sie Pushbenachrichtigungen ausgeschaltet haben, können sie benutzerseitig nicht wieder eingeschaltet werden. 

> [!IMPORTANT]
> Microsoft greift für die Bereitstellung von mobilen Skype for Business-Benachrichtigungen in Echtzeit für Windows Phone-, iPhone- und iPad-Benutzer auf andere Unternehmen zurück. Siehe diese [Datenschutzerklärung](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Verwalten Skype for Business Einstellungen für einzelne Benutzer

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Um Skype for Business Einstellungen für einzelne Benutzer zu verwalten, wechseln Sie im linken Navigationsbereich des Teams Admin Centers zu **"Benutzer**", klicken Sie auf den Anzeigenamen des Benutzers, um die Seite mit den Benutzerdetails zu öffnen, und wählen Sie dann die Registerkarte **"Skype for Business Einstellungen**" aus. Von hier aus können Sie externe Zugriffs- und Besprechungseinstellungen für den Benutzer konfigurieren.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot der Registerkarte &quot;Skype for Business&quot; auf der Seite &quot;Benutzerdetails&quot;.":::

### <a name="external-access-settings"></a>Einstellungen für externen Zugriff

Sie können selektiv zulassen oder blockieren, ob ein Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren kann.

- **Externe Skype for Business Benutzer**: Aktivieren Sie diese Option, wenn Sie dem Benutzer die Kommunikation mit Skype for Business Benutzern in Verbunddomänen ermöglichen möchten.
- **Externe Skype-Benutzer**: Aktivieren Sie diese Option, wenn Sie dem Benutzer die Kommunikation mit Skype-Benutzern ermöglichen möchten. 

### <a name="meeting-settings"></a>Besprechungseinstellungen

Sie können die folgenden Besprechungseinstellungen für den Benutzer konfigurieren.

- **Audio & Video**: Wählen Sie eine der folgenden Audio- und Videoeinstellungen aus:

    - **Keine**: Der Benutzer kann weder Audio noch Video verwenden.
    - **Nur Audio**: Der Benutzer kann Audio, aber kein Video verwenden.
    - **Audio und Video**: Der Benutzer kann Audio und Video verwenden.
    - **Audio und Video (HD):** Der Benutzer kann Audio und HD-Video verwenden.
    
- **Aufzeichnen von Unterhaltungen & Besprechungen**: Aktivieren Sie diese Option, damit der Benutzer Unterhaltungen und Besprechungen aufzeichnen kann.
- **Compliance**: Aktivieren Sie diese Option, wenn Sie gesetzlich verpflichtet sind, elektronisch gespeicherte Informationen aufzubewahren.