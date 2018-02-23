---
title: "Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 01/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: "Hier finden Sie Informationen zu allen Microsoft Teams-Funktionen, die Sie in Ihrer Office 365-Organisation aktivieren oder deaktivieren können, beispielsweise mandantenweite Einstellungen, E-Mail-Integration, Apps, Cloudspeicher und vieles mehr."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8d91d166651cce5adf0ff07a19b29b90047e98e0
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a>Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation
======================================================

Microsoft Teams hat mehrere Einstellungen, die auf Office 365-Mandantenebene aktiviert oder deaktiviert werden können. Wenn Microsoft Teams für einen Mandanten aktiviert ist, erben alle Benutzer, die ebenfalls für Microsoft Teams aktiviert sind, die Einstellungen auf Mandantenebene.

Unten sehen Sie eine Liste der Funktionen, die Office 365-Administratoren in Microsoft Teams aktivieren oder deaktivieren können. 

Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option „Ein“.

> [!NOTE] 
> Um die Administratoreinstellungen für Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden: 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> Office 365-Administratoren können Microsoft Teams jederzeit im Office 365 Admin Center deaktivieren. Beachten Sie, dass Benutzer mit aktiven Lizenzen für Microsoft Teams die Kachel der Microsoft Teams-App auch dann noch sehen, wenn Sie Microsoft Teams deaktiviert haben. Details zum Entfernen von Lizenzen von Benutzern finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md). Wenn Microsoft Teams deaktiviert wurde, ist der Zugriff über den Microsoft Teams-Client blockiert, aber die über andere Clients und Dienste verfügbaren Daten sind nach wie vor verfügbar. Dies gilt zum Beispiel für Dateien aus SharePoint und OneDrive. Alle Daten verbleiben an Ort und Stelle, solange die Teams nicht explizit gelöscht werden.

<a name="office-365-tenant-wide-settings"></a>Mandantenweite Einstellungen in Office 365 
---------------------

In **Mandantenweite Einstellungen** können Sie Optionen unter „Allgemein“, „E-Mail-Integration“, „Apps“ und „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher) aktivieren oder deaktivieren.

Um **mandantenweite Einstellungen** für Microsoft Teams zu bearbeiten, wechseln Sie zum Office 365 Admin Center. Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus.

### <a name="general"></a>Allgemein

Im Abschnitt „Allgemein“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

> ![Screenshot des Abschnitts „Allgemein“ in „Mandantenweite Einstellungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **Show organizational chart in personal profile** (Organigramm in persönlichem Profil anzeigen): Wenn diese Einstellung aktiviert ist, wird das Organigrammsymbol auf der Visitenkarte des Benutzers angezeigt. Durch Klicken auf das Symbol wird das detaillierte Organigramm angezeigt.

    ![Screenshot des Organigrammsymbols auf der Visitenkarte eines Benutzers](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Screenshot eines Organigramms](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-  **Use Skype for Business for recipients who don’t have Teams** (Für Empfänger, die Microsoft Teams nicht haben, Skype for Business verwenden): Wenn diese Einstellung aktiviert ist, werden Microsoft Teams-Unterhaltungen für Benutzer, die nicht für Microsoft Teams aktiviert sind, automatisch in Skype for Business angezeigt.  

-   **Allow T-bot proactive help messages** (Proaktive Hilfenachrichten von T-Bot zulassen): Wenn diese Einstellung aktiviert ist, initiiert T-Bot private Chatsitzungen mit Benutzern, um ihnen bei der Verwendung von Microsoft Teams zu helfen.

    ![Screenshot des T-Bot-Abschnitts auf der Benutzeroberfläche von Microsoft Teams](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>E-Mail-Integration
-----------------

Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist. Auch wenn Benutzer nicht über die Berechtigung verfügen, eine Kanal-E-Mail-Adresse zu erstellen, und eine andere Person mit der entsprechenden Berechtigung diese Adresse erstellt, können die Benutzer über das Menü **Weitere Optionen** für den jeweiligen Kanal auf die Adresse zugreifen.

Konfigurieren Sie unter **Email integration** (E-Mail-Integration) die folgenden Einstellungen für Ihre Organisation: 

   ![Screenshot des Abschnitts „E-Mail-Integration“ in „Mandantenweite Einstellungen“](media/QS-edu-email-integration.png)

-   **Allow users to send emails to channels** (Zulassen, dass Benutzer E-Mails an Kanäle senden): Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden. 

 
-   **Allow users to send emails to channels** (Zulassen, dass Benutzer E-Mails an Kanäle senden): Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden. 

    Um die E-Mail-Adresse des Kanals zu finden, klicken Sie auf das Menü **Weitere Optionen** für den Kanal, und wählen Sie dann **E-Mail-Adresse abrufen** aus. 

-   **Restricted Senders List** (Liste eingeschränkter Absender): Die Domänen von Absendern können weiter eingeschränkt werden, um sicherzustellen, dass nur E-Mails aus zulässigen SMTP-Domänen an die Microsoft Teams-Kanäle gesendet werden können.

<a name="apps"></a>Apps
----

Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist. 

Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren: 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- **Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind. 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- **Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen. 

- **Allow sideloading of external apps** (Querladen von externen Apps zulassen): Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren. 

Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md). 



<a name="custom-cloud-storage"></a>Benutzerdefinierter Cloudspeicher
--------------------

Zu den Optionen für Cloudspeicher in Microsoft Teams gehören zurzeit Box, Dropbox, Google Drive und ShareFile. Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte. 

![Screenshot des Abschnitts „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher)](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Benutzereinstellungen nach Lizenz
------------------------

In **Benutzereinstellungen nach Lizenz** können Sie Optionen unter „Teams und Kanäle“, „Anrufe und Besprechungen“ und „Messaging“ aktivieren oder deaktivieren.

<a name="teams-and-channels"></a>Teams und Kanäle
------------------

Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln.

Zurzeit kann ein Office 365-Mandant maximal 500.000 Teams enthalten. Ein globaler Administrator kann beliebig viele Teams erstellen. Ein Benutzer kann 250 Teams erstellen. Ein Teambesitzer kann 2500 Mitglieder zu einem Team hinzufügen.

Als Administrator können Sie Teambesitzer und -mitglieder über das Dashboard „Gruppen“ im Office 365 Admin Center verwalten. Wenn Sie mehr wissen möchten, klicken Sie unter **Teams und Kanäle** auf **Use the Groups dashboard in the Office 365 admin center to manage teams** (Dashboard „Gruppen“ im Office 365 Admin Center zum Verwalten von Teams verwenden).

Sie können steuern, welche Benutzer in der Organisation Teams in Microsoft Teams erstellen können. Für Microsoft Teams gelten die gleichen Erstellungseinstellungen, die durch Office 365-Gruppen definiert werden. Weitere Informationen zum Verwalten von Office 365-Gruppen finden Sie unter [Erstellen von Office 365-Gruppen](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) und [Steuern, wer Office 365-Gruppen erstellen kann](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

> [!NOTE]
> Sie können keine Teams über das Dashboard „Gruppen“ erstellen Teams müssen mit dem Microsoft Teams-Desktopclient oder der Web-App erstellt werden.

Standardmäßig können alle Benutzer Teams oder Gruppen erstellen. Wählen Sie links im Microsoft Teams-Client (Desktopclient oder Web-App) die Option **Teams** aus. Wählen Sie dann unten im Client unter der Teamliste die Option **Create and join team** (Team erstellen und beitreten) aus.

![Screenshot des Abschnitts „Benutzereinstellungen nach Lizenz“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.

## <a name="calls-and-meetings"></a>Anrufe und Besprechungen

Konfigurieren Sie unter **Anrufe und Besprechungen** die folgenden Einstellungen für Ihre Organisation:

![Screenshot des Abschnitts „Anrufe und Besprechungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

An einer Besprechung können maximal 80 Personen teilnehmen. In einem privaten Chat sind 20 Mitglieder möglich (einschließlich des Benutzers, der den Chat erstellt hat).

-   **Allow scheduling for private meetings** (Planen von privaten Besprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer private Besprechungen planen, die nicht in einem Kanal aufgeführt sind.

-   **Allow ad-hoc channel meetup** (Ad-hoc-Kanal-MeetUps zulassen)

-   **Allow scheduling for channel meetings** (Planen von Kanalbesprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer eine Besprechung für einen Kanal planen, an der alle Kanalmitglieder ganz leicht mit einem einzigen Klick teilnehmen können.

-   **Allow videos in meetings** (Video in Besprechungen zulassen): Gibt an, ob die Verwendung von Video in Besprechungen zulässig ist.

-   **Allow screen sharing in meetings** (Bildschirmübertragung in Besprechungen zulassen): Gibt an, ob Bildschirmübertragung in Besprechungen zulässig ist.

-   **Allow private calling** (Private Anrufe zulassen): Wenn diese Option aktiviert ist, können Benutzer private Anrufe tätigen.

## <a name="messaging"></a>Messaging 

Im Abschnitt „Messaging“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

![Screenshot des Abschnitts „Messaging“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Enable Giphy so users can add gifs to conversations** (Giphy aktivieren, damit Benutzer GIF-Dateien zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer animierte Bilder in den Unterhaltungen verwenden.

-   **Content Rating** (Inhaltsbewertung): Wenn animierte Bilder aktiviert sind, kann eine Inhaltsbewertung angewendet werden, um den Typ der animierten Bilder einzuschränken, die in Unterhaltungen angezeigt werden können. Für die Inhaltsbewertung sind die folgenden Optionen verfügbar:

    -   „No restriction“ (Keine Einschränkung)
    -   Mittel (der Standardwert)
    -   Streng

-   **Enable memes that users can edit and add to conversations** (Memes aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Internetmemes verwenden, um humorvolle Beiträge zu verfassen.

-   **Enable stickers that users can edit and add to conversations** (Aufkleber aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Bilder mit bearbeitbarem Text posten, um Kanalmitglieder auf etwas aufmerksam zu machen.

-   **Allow owners to delete all messages** (Zulassen, dass Besitzer alle Nachrichten löschen): Wenn diese Option aktiviert ist, können Kanalbesitzer alle Nachrichten in einem Kanal entfernen.

-   **Allow users to edit their own messages** (Zulassen, dass Benutzer eigene Nachrichten bearbeiten): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten bearbeiten.

-   **Allow users to delete their own messages** (Zulassen, dass Benutzer eigene Nachrichten löschen): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten löschen.

-   **Allow users to chat privately** (Zulassen, dass Benutzer privat chatten): Wenn diese Option aktiviert ist, können Benutzer an privaten Chats teilnehmen, die nicht für alle Teammitglieder, sondern nur für die Chatteilnehmer sichtbar sind.


| |  |  |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Entscheidungspunkt         |Welche Einstellungen für Microsoft Teams wird Ihre Organisation aktivieren?         |
|![Symbol für „Nächste Schritte“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Nächste Schritte        |Dokumentieren Sie diese Entscheidungen in [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).         |

