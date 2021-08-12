---
title: Verwalten Skype for Business Einstellungen im Microsoft Teams Admin Center
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
description: Erfahren Sie, wie Sie die Einstellungen Skype for Business Features im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: f05bdd7dfb53e75d5cc83945985dd6b511635d5ab5792afc0291b5349433ae22
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280560"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Verwalten Skype for Business Einstellungen im Microsoft Teams Admin Center

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Als Administrator verwalten Microsoft Teams Admin Center die Skype for Business für Skype for Business in Ihrer Organisation. Sie können die Einstellungen [für Ihre](#manage-skype-for-business-settings-for-your-organization) Organisation **auf** [](#manage-skype-for-business-settings-for-individual-users) der Seite Skype for Business  und die Einstellungen für einzelne Benutzer auf der Registerkarte Skype for Business Benutzerdetailse seiten verwalten.

Die Seite "Koexistenz" **wird Skype for Business** angezeigt, wenn der Koexistenzmodus für Ihre Organisation nicht auf **"Teams festgelegt ist.** Ebenso wird die Registerkarte "Skype for Business" für einen Benutzer nur angezeigt, wenn der Koexistenzmodus **des Benutzers nicht Teams ist.**  Weitere Informationen zu Koexistenzmodi finden Sie unter Teams und Skype for Business [Koexistenz](teams-and-skypeforbusiness-coexistence-and-interoperability.md) und Interoperabilität und Festlegen der Einstellungen für [Koexistenz und Upgrade.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Skype for Business Einstellungen waren zuvor im **Legacyportal** im Microsoft Teams Admin Center. Mit der Einstellung des Legacyportals haben wir die Einstellungen an diese neuen Speicherorte im Teams Admin Center für die Verwaltung Skype for Business migriert.

Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) eines globalen Administrator oder Skype for Business zugewiesen sein, damit Skype for Business Features im Microsoft Teams Admin Center verwalten können.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Verwalten Skype for Business Einstellungen für Ihre Organisation

Navigieren Sie in der linken Navigationsleiste Microsoft Teams Admin Center zu **Organisationsweite Einstellungen**  >  **Skype for Business.** Von hier aus können Sie die Benachrichtigungen Skype-Besprechung Übertragungen, den Datenschutz für die Anwesenheitspräsenz und mobile Geräte für alle Skype for Business in Ihrer Organisation konfigurieren und verwalten.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Verwenden Sie die folgenden Einstellungen, um Skype-Besprechung [Broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot der Skype-Besprechung Übertragungseinstellungen im Admin Center":::

- **Skype-Besprechung Übertragungen:** Aktivieren Sie diese Option, um Skype-Besprechung Für Ihre Organisation zu aktivieren. Nachdem Sie dieses Feature aktiviert haben, müssen Sie Ihr Netzwerk für Skype-Besprechung [einrichten.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Siehe Vorschaufeatures:** Aktivieren Sie diese, um früh Zugriff auf neue Features zu erhalten.
- Organisatoren können anonyme Besprechungen planen: Aktivieren Sie diese Möglichkeit, wenn Organisatoren **Übertragungsereignisse** erstellen möchten, bei denen jeder außerhalb Ihrer Organisation teilnehmen kann, ohne sich anmelden zu müssen. 
- **Aufzeichnen Skype-Besprechung Übertragen** von Besprechungen: Aktivieren Sie diese Option, um Organisatoren und Organisatoren das Aufzeichnen von Besprechungen zu ermöglichen.  
- **Helpdesk-URL** für Teilnehmer: Geben Sie die Support-URL Ihrer Organisation ein, die die Besprechungsteilnehmer verwenden können, wenn sie während einer Besprechung Hilfe benötigen.

### <a name="presence-and-mobile-notifications"></a>Anwesenheits- und mobile Benachrichtigungen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Verwenden Sie die folgenden Einstellungen, um den Skype for Business Anwesenheitsanzeige und mobile Benachrichtigungen in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot der Anwesenheitseinstellungen im Admin Center":::

#### <a name="presence"></a>Anwesenheit

Standardmäßig können Skype for Business in Ihrer Organisation den Anwesenheitsstatus anderer Benutzer sehen (z. B. "Verfügbar", "Beschäftigt" oder "Skype for Business". Wählen Sie eine der folgenden Optionen aus, um die Personen, die das Anwesenheits ihres Kontos sehen können, Skype for Business festlegen.

- **Anwesenheitsinformationen** automatisch anzeigen: Jeder Skype for Business-Benutzer in Ihrer Organisation, der nicht  zur  Liste Extern oder Blockiert des Benutzers hinzugefügt wurde, kann die Anwesenheit dieses Benutzers sehen.
- Anwesenheitsinformationen nur für die Kontakte eines Benutzers **anzeigen:** Jeder Skype for Business-Benutzer in der Kontaktliste  des  Benutzers, der nicht zu seiner Liste Extern oder Blockiert hinzugefügt wurde, kann die Anwesenheit dieses Benutzers sehen. Benutzer können diese Einstellung im Skype for Business über Einstellungen  >  **Optionen für Tools** außer Kraft  >  **setzen.**

#### <a name="mobile-notifications"></a>Mobile Benachrichtigungen

Sie können festlegen, ob Skype for Business Ihrer mobilen Benutzer über einen Pushbenachrichtigungsdienst Benachrichtigungen über eingehende und verpasste Chatnachrichten, Voicemailnachrichten und verpasste Anrufe erhalten. Je nach den in Ihrer Organisation verwendeten mobilen Geräten können Sie **den Microsoft-Pushbenachrichtigungsdienst,** den **Apple-Pushbenachrichtigungsdienst** oder beides verwenden.

Berücksichtigen Sie dabei Folgendes:

- Wenn Sie Pushbenachrichtigungen deaktivieren, erhalten die Benutzer alle Benachrichtigungen, sobald sie das Skype for Business auf ihrem mobilen Gerät starten.
- Pushbenachrichtigungen sind standardmäßig aktiviert. Einzelne Benutzer können sie in ihrem mobilen Skype for Business deaktivieren.
- Nachdem Sie Pushbenachrichtigungen ausgeschaltet haben, können sie benutzerseitig nicht wieder eingeschaltet werden. 

> [!IMPORTANT]
> Microsoft greift für die Bereitstellung von mobilen Skype for Business-Benachrichtigungen in Echtzeit für Windows Phone-, iPhone- und iPad-Benutzer auf andere Unternehmen zurück. Weitere Informationen [finden Sie in den Datenschutzbestimmungen.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Verwalten Skype for Business Einstellungen für einzelne Benutzer

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Um Skype for Business-Einstellungen für einzelne Benutzer zu verwalten, wechseln Sie im linken Navigationsbereich des Teams Admin Centers zu Benutzer **,** klicken Sie auf den Anzeigenamen des Benutzers, um die Seite mit den Benutzerdetails zu öffnen, und wählen Sie dann die Registerkarte **Skype for Business-Einstellungen** aus. Von hier aus können Sie die Einstellungen für den externen Zugriff und die Besprechung für den Benutzer konfigurieren.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot der Registerkarte Skype for Business auf der Seite "Benutzerdetails"":::

### <a name="external-access-settings"></a>Einstellungen für externen Zugriff

Sie können selektiv zulassen oder blockieren, ob ein Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren kann.

- **Externe Skype for Business:** Aktivieren Sie dies, wenn Sie dem Benutzer die Kommunikation mit Skype for Business in Verbunddomänen ermöglichen möchten.
- **Externe Skype:** Aktivieren Sie dies, wenn Sie dem Benutzer die Kommunikation mit anderen benutzern Skype ermöglichen möchten. 

### <a name="meeting-settings"></a>Besprechungseinstellungen

Sie können die folgenden Besprechungseinstellungen für den Benutzer konfigurieren.

- **Audio & Video:** Wählen Sie eine der folgenden Audio- und Videoeinstellungen aus:

    - **Keine:** Der Benutzer kann kein Audio oder Video verwenden.
    - **Nur Audio:** Der Benutzer kann Audio, aber kein Video verwenden.
    - **Audio und Video:** Benutzer können Audio und Video verwenden.
    - **Audio und Video (HD):** Der Benutzer kann Audio- und HD-Video verwenden.
    
- **Aufzeichnen von Unterhaltungen &** Besprechungen: Aktivieren Sie diese Wendung, um dem Benutzer das Aufzeichnen von Unterhaltungen und Besprechungen zu ermöglichen.
- **Compliance:** Aktivieren Sie dies, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind.