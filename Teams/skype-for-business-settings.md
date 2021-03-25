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
description: Erfahren Sie, wie Sie Einstellungen für Skype for Business-Features im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: 6e1052b4f4a0e85d4d18123b3c0a0f051f6065f8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117003"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Als Administrator verwalten Sie im Microsoft Teams Admin Center Skype for Business-Funktionen für Skype for Business-Benutzer in Ihrer Organisation. Sie können Einstellungen für [Ihre](#manage-skype-for-business-settings-for-your-organization) Organisation auf der [](#manage-skype-for-business-settings-for-individual-users) **Skype for Business-Seite** und Einstellungen für einzelne Benutzer auf der Registerkarte Skype **for Business** der Benutzerdetailsetailseiten verwalten.

Die Seite Skype **for Business** wird nur angezeigt, wenn der Koexistenzmodus für Ihre Organisation nicht nur auf **Teams festgelegt ist.** Ebenso wird die Registerkarte **Skype for Business** für einen Benutzer nur angezeigt, wenn der Koexistenzmodus des Benutzers nicht nur Teams **ist.** Weitere Informationen zu Koexistenzmodi finden Sie unter Verstehen der Koexistenz und Interoperabilität von Teams und [Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) sowie Festlegen ihrer [Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

> [!NOTE]
> Skype for Business-Einstellungen waren zuvor im **Legacyportal** im Microsoft Teams Admin Center. Mit der Einstellung des Altenportals haben wir die Einstellungen an diese neuen Speicherorte im Teams Admin Center für Skype for Business Management migriert.

Ihnen muss die [Azure AD-Administratorrolle](/azure/active-directory/roles/permissions-reference) eines globalen Oder Skype for Business-Administrators zugewiesen sein, um Skype for Business-Features im Microsoft Teams Admin Center verwalten zu können.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Verwalten von Skype for Business-Einstellungen für Ihre Organisation

Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen**  >  **Skype for Business**. Von hier aus können Sie Skype Meeting Broadcast, Anwesenheitsschutz und Benachrichtigungen auf mobilen Geräten für alle Skype for Business-Benutzer in Ihrer Organisation konfigurieren und verwalten.

### <a name="skype-meeting-broadcast"></a>Skype Meeting Broadcast

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Verwenden Sie die folgenden Einstellungen, um [skype meeting broadcast](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot der Skype Meeting Broadcast-Einstellungen im Admin Center":::

- **Skype-Liveübertragungen:** Aktivieren Sie diese Option, um skype meeting broadcast für Ihre Organisation zu aktivieren. Nachdem Sie dieses Feature aktiviert haben, müssen Sie Ihr Netzwerk [für Skype Meeting Broadcast einrichten.](/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast)
- **Siehe Vorschaufeatures:** Aktivieren Sie dies, um frühzeitigen Zugriff auf neue Features zu erhalten.
- **Organisatoren können anonyme** Besprechungen planen: Aktivieren Sie dies, wenn Sie Organisatoren die Erstellung von Übertragungsereignissen ermöglichen möchten, die es allen Personen außerhalb Ihrer Organisation ermöglichen, an der Besprechung teilzunehmen, ohne sich anmelden zu müssen. 
- **Aufzeichnen von Skype-Besprechungsübertragungsbesprechungen:** Aktivieren Sie diese Option, um Organisatoren und Organisatoren das Aufzeichnen von Besprechungen zu ermöglichen.  
- **Helpdesk-Support-URL für** Teilnehmer: Geben Sie die Support-URL Ihrer Organisation ein, die Besprechungsteilnehmer verwenden können, wenn sie während einer Besprechung Hilfe benötigen.

### <a name="presence-and-mobile-notifications"></a>Anwesenheits- und mobile Benachrichtigungen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Verwenden Sie die folgenden Einstellungen zum Verwalten von Skype for Business-Anwesenheitsschutz und mobilen Benachrichtigungen in Ihrer Organisation.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot der Anwesenheitseinstellungen im Admin Center":::

#### <a name="presence"></a>Anwesenheit

Standardmäßig können Skype for Business-Benutzer in Ihrer Organisation den Anwesenheitsstatus (z. B. "Verfügbar", "Beschäftigt" oder "Ab") anderer Skype for Business-Benutzer sehen. Wählen Sie eine der folgenden Optionen aus, um zu festlegen, wer die Anwesenheit Ihrer Skype for Business-Benutzer sehen kann.

- **Anwesenheitsinformationen** automatisch anzeigen: Jeder Skype for Business-Benutzer in Ihrer Organisation,  der  nicht zur Liste "Extern" oder "Blockiert" des Benutzers hinzugefügt wurde, kann die Anwesenheit dieses Benutzers sehen.
- **Anzeigen von** Anwesenheitsinformationen nur für die Kontakte eines Benutzers: Jeder Skype for Business-Benutzer  in  der Kontaktliste des Benutzers, der nicht zu seiner Liste "Extern" oder "Blockiert" hinzugefügt wurde, kann die Anwesenheit dieses Benutzers sehen. Benutzer können diese Einstellung in Skype for Business überschreiben, indem sie zu **Einstellungen**  >  **Tools Optionen**  >  **gehen.**

#### <a name="mobile-notifications"></a>Mobile Benachrichtigungen

Sie können festlegen, ob Ihre Skype for Business Mobile-Benutzer über einen Pushbenachrichtigungsdienst Benachrichtigungen über eingehende und verpasste Chatnachrichten, Voicemailnachrichten und verpasste Anrufe erhalten. Abhängig von den mobilen Geräten, die in Ihrer Organisation verwendet werden, können Sie den **Microsoft Push Notification Service,** den **Apple Push Notification Service** oder beides verwenden.

Berücksichtigen Sie dabei Folgendes:

- Wenn Sie Pushbenachrichtigungen deaktivieren, erhalten Benutzer alle Benachrichtigungen, wenn sie Skype for Business das nächste Mal auf ihrem mobilen Gerät starten.
- Standardmäßig sind Pushbenachrichtigungen aktiviert. Einzelne Benutzer können sie in Skype for Business auf ihrem mobilen Gerät deaktivieren.
- Nachdem Sie Pushbenachrichtigungen ausgeschaltet haben, können sie benutzerseitig nicht wieder eingeschaltet werden. 

> [!IMPORTANT]
> Microsoft greift für die Bereitstellung von mobilen Skype for Business-Benachrichtigungen in Echtzeit für Windows Phone-, iPhone- und iPad-Benutzer auf andere Unternehmen zurück. Lesen Sie [diese Datenschutzbestimmungen.](https://go.microsoft.com/fwlink/p/?linkid=247732)

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Verwalten von Skype for Business-Einstellungen für einzelne Benutzer

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Um Skype for Business-Einstellungen für einzelne Benutzer zu verwalten, wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Benutzer,** klicken Sie auf den Anzeigenamen des Benutzers, um die Seite mit den Benutzerdetails zu öffnen, und wählen Sie dann die **Registerkarte Skype for Business-Einstellungen** aus. Hier können Sie die Einstellungen für den externen Zugriff und die Besprechung für den Benutzer konfigurieren.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot der Registerkarte Skype for Business auf der Seite "Benutzerdetails"":::

### <a name="external-access-settings"></a>Einstellungen für externen Zugriff

Sie können selektiv zulassen oder blockieren, ob ein Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren kann.

- **Externe Skype for Business-Benutzer:** Aktivieren Sie dieses Guthaben, wenn Sie dem Benutzer die Kommunikation mit Skype for Business-Benutzern in Verbunddomänen ermöglichen möchten.
- **Externe Skype-Benutzer:** Aktivieren Sie dieses Guthaben, wenn Sie dem Benutzer die Kommunikation mit Skype-Benutzern ermöglichen möchten. 

### <a name="meeting-settings"></a>Besprechungseinstellungen

Sie können die folgenden Besprechungseinstellungen für den Benutzer konfigurieren.

- **Audio & Video:** Wählen Sie eine der folgenden Audio- und Videoeinstellungen aus:

    - **Keine:** Der Benutzer kann keine Audio- oder Videodaten verwenden.
    - **Nur Audio:** Der Benutzer kann Audio, aber kein Video verwenden.
    - **Audio und Video:** Der Benutzer kann Audio und Video verwenden.
    - **Audio und Video (HD):** Benutzer können Audio- und Hd-Video verwenden.
    
- **Aufzeichnen von Unterhaltungen & Besprechungen:** Aktivieren Sie diese Möglichkeit, damit der Benutzer Unterhaltungen und Besprechungen aufzeichnen kann.
- **Compliance:** Aktivieren Sie dies, wenn Sie gesetzlich verpflichtet sind, elektronisch gespeicherte Informationen zu speichern.