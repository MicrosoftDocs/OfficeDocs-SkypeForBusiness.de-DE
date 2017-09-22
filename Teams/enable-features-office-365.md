---
title: "Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: overview
ms.service: msteams
description: "Hier finden Sie Informationen zu allen Microsoft Teams-Funktionen, die Sie in Ihrer Office 365-Organisation aktivieren können, beispielsweise mandantenweite Einstellungen, E-Mail-Integration, Apps, Cloudspeicher und vieles mehr."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 00038f5020e640071f65ae1d046369308834d807
ms.sourcegitcommit: 9e217129451afae32eb3cd27fb3ee591874c29c9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a>Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation
======================================================

Microsoft Teams hat mehrere Einstellungen, die auf Mandantenebene aktiviert oder deaktiviert werden können. Wenn Microsoft Teams für den Mandanten aktiviert ist, erben alle Benutzer, die ebenfalls für Microsoft Teams aktiviert sind, die Einstellungen auf Mandantenebene.

Unten sehen Sie eine Liste der Funktionen, die Office 365-Administratoren in Microsoft Teams wahlweise aktivieren oder deaktivieren können.

Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option „Ein“.

Hinweis: Office 365-Administratoren können Microsoft Teams jederzeit über das Office 365 Admin Center deaktivieren. Beachten Sie, dass Benutzer mit aktiven Lizenzen für Microsoft Teams die Kachel der Teams-App auch dann noch sehen, wenn Sie Teams deaktiviert haben. Details zum Entfernen von Lizenzen von Benutzern finden Sie unter „Verwalten des Benutzerzugriffs auf Microsoft Teams-Lizenzen“. Wenn Teams deaktiviert wurde, ist der Zugriff über den Microsoft Teams-Client blockiert, aber die über andere Clients und Dienste verfügbaren Daten sind nach wie vor verfügbar. Dies gilt zum Beispiel für Dateien aus SharePoint und OneDrive. Alle Daten verbleiben an Ort und Stelle, solange die Teams nicht explizit gelöscht werden.

<a name="tenant-wide-settings"></a>Mandantenweite Einstellungen 
---------------------

In **Mandantenweite Einstellungen** können Sie Optionen unter „Allgemein“, „E-Mail-Integration“, „Apps“ und „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher) aktivieren oder deaktivieren.

### <a name="general"></a>Allgemein

Im Abschnitt „Allgemein“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

> ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   **„Show organizational chart in personal profile“ (Organigramm in persönlichem Profil anzeigen):** Wenn diese Einstellung aktiviert ist, wird das Organigrammsymbol auf der Visitenkarte des Benutzers angezeigt. Wenn auf das Symbol geklickt wird, wird das detaillierte Organigramm angezeigt.

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   **„Use Skype for Business for recipients who don’t have Microsoft Teams“ (Für Empfänger, die Microsoft Teams nicht haben, Skype for Business verwenden):** Wenn diese Einstellung aktiviert ist, können Microsoft Teams-Benutzer Kontakt zu anderen Benutzern in der Organisation aufnehmen, die nicht über Skype for Business für Microsoft Teams aktiviert sind.

-   **„Allow T-bot proactive help messages“ (Proaktive Hilfenachrichten von T-Bot zulassen):** Wenn diese Einstellung aktiviert ist, initiiert T-Bot eine private Chatsitzung mit Benutzern, um sie bei der Verwendung von Microsoft Teams zu unterstützen.

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a>E-Mail-Integration
-----------------

Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist. Auch wenn Benutzer nicht über die Berechtigung verfügen, eine Kanal-E-Mail-Adresse zu erstellen, und eine andere Person mit der entsprechenden Berechtigung diese Adresse erstellt, können die Benutzer über das Menü \<Weitere\> für den jeweiligen Kanal auf die Adresse zugreifen.

Im Abschnitt „E-Mail-Integration“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

   ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   **„Allow users to send emails to channels“ (Zulassen, dass Benutzer E-Mails an Kanäle senden):** Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden.

> Um die E-Mail-Adresse des Kanals zu finden, klicken Sie neben dem Kanalnamen auf **Weitere Optionen**, und wählen Sie dann **E-Mail-Adresse abrufen** aus.

-   **„Restricted Senders List“ (Liste eingeschränkter Absender):** Die Domänen von Absendern können weiter eingeschränkt werden, um sicherzustellen, dass nur zulässige SMTP-Domänen E-Mails an die Microsoft Teams-Kanäle senden können.

<a name="apps"></a>Apps
----

Mit Apps in Microsoft Teams können Sie die für Ihr Team wichtigen Tools und Dienste ganz leicht in einen Kanal oder Chat integrieren.

Im Abschnitt **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   **Externe Apps in Microsoft Teams zulassen:** Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind.
![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   **Querladen von externen Apps zulassen:** Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren.

<a name="custom-cloud-storage"></a>Benutzerdefinierter Cloudspeicher
--------------------

Zu den Optionen für Cloudspeicher in Microsoft Teams gehören zurzeit Box, Dropbox, Google Drive und ShareFile. Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Klicken oder tippen Sie auf die Umschaltfläche neben den Cloudspeicheranbietern, die Ihre Organisation verwenden möchte.

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a>Benutzereinstellungen nach Lizenz
------------------------

In **Benutzereinstellungen nach Lizenz** können Sie Optionen unter „Teams und Kanäle“, „Anrufe und Besprechungen“ und „Messaging“ aktivieren oder deaktivieren.

<a name="teams-and-channels"></a>Teams und Kanäle
------------------

Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln.

Als Administrator können Sie Teambesitzer und -mitglieder über das Dashboard „Gruppen“ im Office 365 Admin Center-Portal verwalten. Klicken Sie im Abschnitt „Teams und Kanäle“ auf den Link **Dashboard „Gruppen“ im Office 365 Admin Center zum Verwalten von Teams verwenden**.

Sie können steuern, welche Benutzer in der Organisation Teams in Microsoft Teams erstellen können. Für Microsoft Teams gelten die gleichen Erstellungseinstellungen, die durch Office 365-Gruppen definiert werden. Weitere Informationen zum Verwalten von Office 365-Gruppen finden Sie unter [Erstellen von Office 365-Gruppen](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) und [Steuern, wer Office 365-Gruppen erstellen kann](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).

HINWEIS: Sie können keine Teams über das Dashboard „Gruppen“ erstellen Teams müssen mit dem Microsoft Teams-Desktopclient oder der Web-App erstellt werden.

Standardmäßig können alle Benutzer Teams oder Gruppen erstellen. Benutzer können Teams erstellen, indem sie links im Microsoft Teams-Client (Desktop- oder Web-App) die Option „Teams“ auswählen. Anschließend wählen sie unten im Client unter der Teamliste die Option „Team erstellen“ aus.

Zurzeit kann ein Office 365-Mandant maximal 500.000 Teams enthalten. Ein globaler Administrator kann beliebig viele Teams erstellen. Ein Benutzer kann 250 Teams erstellen. Ein Teambesitzer kann 999 Mitglieder zu einem Team hinzufügen.

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.

### <a name="calls-and-meetings"></a>Anrufe und Besprechungen

Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.

Im Abschnitt **Anrufe und Besprechungen** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

> ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   **„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen):** Wenn diese Option aktiviert ist, können Benutzer private Besprechungen planen, die nicht in einem Kanal aufgeführt sind.

-   **„Allow ad-hoc channel meetup“ (Ad-hoc-Kanal-MeetUps zulassen):**

-   **„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen):** Wenn diese Option aktiviert ist, können Benutzer eine Besprechung für einen Kanal planen, an der alle Kanalmitglieder ganz leicht mit einem einzigen Klick teilnehmen können.

-   **„Allow videos in meetings“ (Videos in Besprechungen zulassen):** Gibt an, ob die Verwendung von Video in Besprechungen zulässig ist.

-   **„Allow screen sharing in meetings“ (Bildschirmübertragung in Besprechungen zulassen):** Gibt an, ob Bildschirmübertragung in Besprechungen zulässig ist.

-   **„Allow private calling“ (Private Anrufe zulassen):** Wenn diese Option aktiviert ist, können Benutzer private Anrufe tätigen.

An einer Besprechung können maximal 80 Personen teilnehmen. In einem privaten Chat sind 20 Mitglieder möglich (einschließlich des Benutzers, der den Chat erstellt hat).

### <a name="messaging"></a>Messaging 

Im Abschnitt „Messaging“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   **Giphy aktivieren, damit Benutzer GIF-Dateien zu Unterhaltungen hinzufügen können:** Wenn diese Option aktiviert ist, können Benutzer animierte Bilder in den Unterhaltungen verwenden.

    -   **„Content Rating“ (Inhaltsbewertung):** Wenn animierte Bilder aktiviert sind, kann eine Inhaltsbewertung angewendet werden, um den Typ der animierten Bilder einzuschränken, die in Unterhaltungen angezeigt werden können. Für die Inhaltsbewertung sind die folgenden Optionen verfügbar:

        -   „No restriction“ (Keine Einschränkung)

        -   Mittel (der Standardwert)

        -   Streng

-   **Memes aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können:** Wenn diese Option aktiviert ist, können Benutzer Internetmemes verwenden, um humorvolle Beiträge zu verfassen.

-   **„Enable stickers that users can edit and add to conversations“ (Aufkleber aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können):** Wenn diese Option aktiviert ist, können Benutzer Bilder mit bearbeitbarem Text posten, um Kanalmitglieder auf etwas aufmerksam zu machen.

-   **Zulassen, dass Eigentümer alle Nachrichten löschen:** Wenn diese Option aktiviert ist, können Kanalbesitzer alle Nachrichten in einem Kanal entfernen.

-   **Zulassen, dass Benutzer eigene Nachrichten bearbeiten:** Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten bearbeiten.

-   **Zulassen, dass Benutzer eigene Nachrichten löschen:** Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten löschen.

-   **„Allow users to chat privately“ (Zulassen, dass Benutzer privat chatten):** Wenn diese Option aktiviert ist, können Benutzer an privaten Chats teilnehmen, die nicht für alle Teammitglieder, sondern nur für die Chatteilnehmer sichtbar sind.


| |  |  |
|---------|---------|---------|
|![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |Entscheidungspunkt         |Welche Einstellungen für Microsoft Teams wird Ihre Organisation aktivieren?         |
|![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |Nächste Schritte        |Dokumentieren Sie diese Entscheidungen in [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](Assign_roles_and_permissions_in_Microsoft_Teams.md).         |

