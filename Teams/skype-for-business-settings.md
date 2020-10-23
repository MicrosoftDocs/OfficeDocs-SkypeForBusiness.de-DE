---
title: Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center
author: lanachin
ms.author: v-lanac
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
description: Hier erfahren Sie, wie Sie Einstellungen für Skype for Business-Features im Microsoft Teams Admin Center verwalten.
ms.openlocfilehash: 7248d57c5a2efb49714bf9e43c4e367ef454bfd0
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739233"
---
# <a name="manage-skype-for-business-settings-in-the-microsoft-teams-admin-center"></a>Verwalten von Skype for Business-Einstellungen im Microsoft Teams Admin Center

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Als Administrator können Sie im Microsoft Teams Admin Center die Skype for Business-Funktionen für Skype for Business-Benutzer in Ihrer Organisation verwalten. Sie können die Einstellungen [für Ihre Organisation](#manage-skype-for-business-settings-for-your-organization) auf der Seite **Skype for Business** und den Einstellungen [für einzelne Benutzer](#manage-skype-for-business-settings-for-individual-users) auf der Registerkarte **Skype for Business** auf den Benutzerdetail Seiten verwalten.

Im Microsoft Teams Admin Center wird nur die Seite **Skype for Business** angezeigt, wenn der Koexistenzmodus für Ihre Organisation nicht **nur auf Teams**festgesetzt ist. Auf ähnliche Weise wird nur die Registerkarte " **Skype for Business** " für einen Benutzer angezeigt, wenn der Koexistenzmodus des Benutzers nicht **nur Teams**ist. Weitere Informationen zu Koexistenzmodus finden Sie Untergrund [Legendes zu Teams und zur Koexistenz und Interoperabilität von Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md) und [Festlegen ihrer Koexistenz-und Aktualisierungseinstellungen](setting-your-coexistence-and-upgrade-settings.md).

> [!NOTE]
> Skype for Business-Einstellungen befanden sich zuvor im **Legacy-Portal** im Microsoft Teams Admin Center. Mit der Pensionierung des Legacy-Portals haben wir die Einstellungen an diese neuen Standorte im Team Admin Center für Skype for Business Management migriert.

## <a name="manage-skype-for-business-settings-for-your-organization"></a>Verwalten von Skype for Business-Einstellungen für Ihre Organisation

Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den **organisationsweiten Einstellungen**für  >  **Skype for Business**. Von hier aus können Sie Skype-Live Konferenzen, Anwesenheitsdaten und Benachrichtigungen über mobile Geräte für alle Skype for Business-Benutzer in Ihrer Organisation konfigurieren und verwalten.

### <a name="skype-meeting-broadcast"></a>Skype-Livekonferenzen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-broadcast"> </a>
<!-- Do not remove the bookmark link above. -->

Verwenden Sie die folgenden Einstellungen, um Skype-Live [Konferenz](https://support.microsoft.com/office/what-is-a-skype-meeting-broadcast-c472c76b-21f1-4e4b-ab58-329a6c33757d) in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-meeting-broadcast.png" alt-text="Screenshot der Einstellungen für Skype-Live Konferenz im Admin Center":::

- **Skype**-Live Konferenz: Aktivieren Sie diese Option, um Skype-Live Konferenz für Ihre Organisation zu aktivieren. Nachdem Sie dieses Feature aktiviert haben, müssen Sie [Ihr Netzwerk für Skype-Live Konferenz einrichten](https://docs.microsoft.com/skypeforbusiness/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast).
- **Weitere Informationen finden Sie unter Vorschau Features**: Aktivieren Sie diese Option, um früh Zugriff auf neue Features zu erhalten.
- **Organisatoren können anonyme Besprechungen planen**: Aktivieren Sie diese Option, wenn Sie den Organisatoren die Möglichkeit geben möchten, Broadcast Ereignisse zu erstellen, mit denen Personen außerhalb Ihrer Organisation teilnehmen können, ohne sich anmelden zu müssen. 
- **Aufzeichnen von Skype**-Live Konferenz Besprechungen: Aktivieren Sie diese Option, damit Organisatoren und Referenten Besprechungen aufzeichnen können.  
- **Helpdesk-Support-URL für Teilnehmer**: Geben Sie die Support-URL Ihrer Organisation ein, die von Besprechungsteilnehmern verwendet werden kann, wenn Sie während einer Besprechung Hilfe benötigen.

### <a name="presence-and-mobile-notifications"></a>Benachrichtigungen zu Anwesenheits-und Mobilfunkanschlüssen

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-org-wide-presence-mobile"> </a>
<!-- Do not remove the bookmark link above. -->


Verwenden Sie die folgenden Einstellungen, um Skype for Business Presence-Datenschutz und Mobile Benachrichtigungen in Ihrer Organisation zu verwalten.

:::image type="content" source="media/skype-for-business-settings-presence-mobile.png" alt-text="Screenshot der Anwesenheitseinstellungen im Admin Center":::

#### <a name="presence"></a>Anwesenheit

Standardmäßig können Skype for Business-Benutzer in Ihrer Organisation den Anwesenheitsstatus (wie "verfügbar", "beschäftigt" oder "Abwesend") von anderen Skype for Business-Benutzern sehen. Wählen Sie eine der folgenden Optionen aus, um festzulegen, wer das vorhanden sein von Skype for Business-Benutzern sehen kann.

- **Anwesenheitsinformationen automatisch anzeigen**: alle Skype for Business-Benutzer in Ihrer Organisation, die der **externen** oder **blockierten** Liste des Benutzers nicht hinzugefügt wurden, können die Anwesenheit des Benutzers sehen.
- **Anzeigen von Anwesenheitsinformationen nur für die Kontakte eines Benutzers**: jeder Skype for Business-Benutzer in der Kontaktliste des Benutzers, der nicht zu seiner **externen** oder **blockierten** Liste hinzugefügt wird, kann die Anwesenheit dieses Benutzers sehen. Benutzer können diese Einstellung in Skype for Business außer Kraft setzen, indem Sie zu den Optionen für die **Einstellungs**  >  **Tools**wechseln  >  **Options**.

#### <a name="mobile-notifications"></a>Mobile Benachrichtigungen

Sie können festlegen, ob Ihre Skype for Business Mobile-Benutzer Benachrichtigungen über eingehende und verpasste Sofortnachrichten, Sprachnachrichten und verpasste Anrufe über einen Push-Benachrichtigungsdienst erhalten. Je nach den mobilen Geräten, die in Ihrer Organisation verwendet werden, können Sie den **Microsoft Push-Benachrichtigungsdienst**, den **Apple Push-Benachrichtigungsdienst**oder beides verwenden.

Berücksichtigen Sie dabei Folgendes:

- Wenn Sie Push-Benachrichtigungen deaktivieren, erhalten die Benutzer alle Benachrichtigungen beim nächsten Start von Skype for Business auf Ihrem mobilen Gerät.
- Standardmäßig sind Push-Benachrichtigungen aktiviert. Einzelne Benutzer können Sie in Skype for Business auf Ihrem mobilen Gerät deaktivieren.
- Nachdem Sie Pushbenachrichtigungen ausgeschaltet haben, können sie benutzerseitig nicht wieder eingeschaltet werden. 

> [!IMPORTANT]
> Microsoft greift für die Bereitstellung von mobilen Skype for Business-Benachrichtigungen in Echtzeit für Windows Phone-, iPhone- und iPad-Benutzer auf andere Unternehmen zurück. Lesen Sie diese [Datenschutzbestimmungen](https://go.microsoft.com/fwlink/p/?linkid=247732).

## <a name="manage-skype-for-business-settings-for-individual-users"></a>Verwalten von Skype for Business-Einstellungen für einzelne Benutzer

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="sfb-user-settings"> </a>
<!-- Do not remove the bookmark link above. -->

Wenn Sie die Skype for Business-Einstellungen für einzelne Benutzer verwalten möchten, wechseln Sie in der linken Navigationsleiste des Teams Admin Center zu **Benutzer**, klicken Sie auf den Anzeigenamen des Benutzers, um die Seite Benutzer Details zu öffnen, und wählen Sie dann die Registerkarte **Skype for Business-Einstellungen** aus. Hier können Sie den externen Zugriff und die Besprechungseinstellungen für den Benutzer konfigurieren.

:::image type="content" source="media/skype-for-business-settings-user.png" alt-text="Screenshot der Registerkarte "Skype for Business" auf der Seite "Benutzer Details"":::

### <a name="external-access-settings"></a>Einstellungen für externen Zugriff

Sie können selektiv zulassen oder blockieren, ob ein Benutzer mit Personen außerhalb Ihrer Organisation kommunizieren kann.

- **Externe Skype for Business-Benutzer**: Aktivieren Sie diese Option, wenn Sie dem Benutzer die Kommunikation mit Skype for Business-Benutzern in Föderationsdomänen gestatten möchten.
- **Externe Skype-Nutzer**: Aktivieren Sie diese Option, wenn Sie dem Nutzer erlauben möchten, mit Skype-Nutzern zu kommunizieren. 

### <a name="meeting-settings"></a>Besprechungseinstellungen

Sie können die folgenden Besprechungseinstellungen für den Benutzer konfigurieren.

- **Audio & Video**: Wählen Sie eine der folgenden Audio-und Videoeinstellungen aus:

    - **Keine**: der Benutzer kann keine Audio-oder Videofunktion verwenden.
    - **Nur Audio**: der Benutzer kann Audio, aber nicht Video verwenden.
    - **Audio und Video**: Benutzer können Audio-und Videodaten verwenden.
    - **Audio und Video (HD)**: Benutzer können Audio-und High-Definition-Video verwenden.
    
- **Aufzeichnen von Unterhaltungen & Besprechungen**: Aktivieren Sie diese Option, damit der Benutzer Unterhaltungen und Besprechungen aufzeichnen kann.
- **Compliance**: Aktivieren Sie diese Option, wenn Sie gesetzlich dazu verpflichtet sind, elektronisch gespeicherte Informationen aufzubewahren. 
