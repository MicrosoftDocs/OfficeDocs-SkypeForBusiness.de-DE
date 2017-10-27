---
title: "Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation | Microsoft-Support"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Hier finden Sie Informationen zu allen Microsoft Teams-Funktionen, die Sie in Ihrer Office 365-Organisation aktivieren können, beispielsweise mandantenweite Einstellungen, E-Mail-Integration, Apps, Cloudspeicher und vieles mehr."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e789e83e02f226d09c67fece89b72ed52aee5711
ms.sourcegitcommit: 5e56010494a1325cec5a090dee04887a46093054
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
<a name="enable-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="0997c-103">Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="0997c-103">Enable Microsoft Teams features in your Office 365 organization</span></span>
======================================================

<span data-ttu-id="0997c-p101">Microsoft Teams hat mehrere Einstellungen, die auf Mandantenebene aktiviert oder deaktiviert werden können. Wenn Microsoft Teams für den Mandanten aktiviert ist, erben alle Benutzer, die ebenfalls für Microsoft Teams aktiviert sind, die Einstellungen auf Mandantenebene.</span><span class="sxs-lookup"><span data-stu-id="0997c-p101">Microsoft Teams has multiple settings that can be enabled or disabled at the tenant level. With Microsoft Teams enabled for the tenant, any user that is also enabled for Microsoft Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="0997c-106">Unten sehen Sie eine Liste der Funktionen, die Office 365-Administratoren in Microsoft Teams wahlweise aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="0997c-106">Below is the list of features an Office 365 Administrator can choose to enable or disable within Microsoft Teams.</span></span>

<span data-ttu-id="0997c-107">Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option „Ein“.</span><span class="sxs-lookup"><span data-stu-id="0997c-107">Unless otherwise noted, the default value for an option is On.</span></span>

<span data-ttu-id="0997c-p102">Hinweis: Office 365-Administratoren können Microsoft Teams jederzeit über das Office 365 Admin Center deaktivieren. Beachten Sie, dass Benutzer mit aktiven Lizenzen für Microsoft Teams die Kachel der Teams-App auch dann noch sehen, wenn Sie Teams deaktiviert haben. Details zum Entfernen von Lizenzen von Benutzern finden Sie unter „Verwalten des Benutzerzugriffs auf Microsoft Teams-Lizenzen“. Wenn Teams deaktiviert wurde, ist der Zugriff über den Microsoft Teams-Client blockiert, aber die über andere Clients und Dienste verfügbaren Daten sind nach wie vor verfügbar. Dies gilt zum Beispiel für Dateien aus SharePoint und OneDrive. Alle Daten verbleiben an Ort und Stelle, solange die Teams nicht explizit gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0997c-p102">Note: An Office 365 Administrator can turn off Microsoft Teams at any time via the Office 365 admin center. Be aware that users with active licenses for Microsoft Teams will continue to see the Teams app tile even if you turn off Teams. For details about how to remove licenses from users, see Manage user access to Microsoft Teams licenses. After Teams is disabled, access from the Microsoft Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive. All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="tenant-wide-settings"></a><span data-ttu-id="0997c-113">Mandantenweite Einstellungen</span><span class="sxs-lookup"><span data-stu-id="0997c-113">Tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="0997c-114">In **Mandantenweite Einstellungen** können Sie Optionen unter „Allgemein“, „E-Mail-Integration“, „Apps“ und „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0997c-114">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

### <a name="general"></a><span data-ttu-id="0997c-115">Allgemein</span><span class="sxs-lookup"><span data-stu-id="0997c-115">General</span></span>

<span data-ttu-id="0997c-116">Im Abschnitt „Allgemein“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0997c-116">The General section lets you configure the following settings for your organization:</span></span>

> ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="0997c-117">**„Show organizational chart in personal profile“ (Organigramm in persönlichem Profil anzeigen):** Wenn diese Einstellung aktiviert ist, wird das Organigrammsymbol auf der Visitenkarte des Benutzers angezeigt. Wenn auf das Symbol geklickt wird, wird das detaillierte Organigramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0997c-117">**Show organizational chart in personal profile:** When this setting is enabled, it shows the organizational chart icon in the user’s contact card and when clicked, it displays the detailed organizational chart.</span></span>

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

-   <span data-ttu-id="0997c-118">**„Use Skype for Business for recipients who don’t have Microsoft Teams“ (Für Empfänger, die Microsoft Teams nicht haben, Skype for Business verwenden):** Wenn diese Einstellung aktiviert ist, können Microsoft Teams-Benutzer Kontakt zu anderen Benutzern in der Organisation aufnehmen, die nicht über Skype for Business für Microsoft Teams aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="0997c-118">**Use Skype for Business for recipients who don’t have Microsoft Teams:** When this setting is enabled, it allows Microsoft Teams users to contact other users in the organization that are not enabled for Microsoft Teams via Skype for Business.</span></span>

-   <span data-ttu-id="0997c-119">**„Allow T-bot proactive help messages“ (Proaktive Hilfenachrichten von T-Bot zulassen):** Wenn diese Einstellung aktiviert ist, initiiert T-Bot eine private Chatsitzung mit Benutzern, um sie bei der Verwendung von Microsoft Teams zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0997c-119">**Allow T-bot proactive help messages:** When this setting is enabled, T-bot will initiate a private chat session with users to guide them in using Microsoft Teams.</span></span>

    ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="0997c-120">E-Mail-Integration</span><span class="sxs-lookup"><span data-stu-id="0997c-120">Email integration</span></span>
-----------------

<span data-ttu-id="0997c-p103">Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist. Auch wenn Benutzer nicht über die Berechtigung verfügen, eine Kanal-E-Mail-Adresse zu erstellen, und eine andere Person mit der entsprechenden Berechtigung diese Adresse erstellt, können die Benutzer über das Menü \<Weitere\> für den jeweiligen Kanal auf die Adresse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0997c-p103">Turn this feature on so that users can send an email to a channel in Microsoft Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors enabled for team members. And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the \<more icon\> menu for that channel.</span></span>

<span data-ttu-id="0997c-125">Im Abschnitt „E-Mail-Integration“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0997c-125">The Email integration section lets you configure the following settings for your organization:</span></span>

   ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image5.png)

-   <span data-ttu-id="0997c-126">**„Allow users to send emails to channels“ (Zulassen, dass Benutzer E-Mails an Kanäle senden):** Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden.</span><span class="sxs-lookup"><span data-stu-id="0997c-126">**Allow users to send emails to channels:** When enabled, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Microsoft Teams channel.</span></span>

> <span data-ttu-id="0997c-127">Um die E-Mail-Adresse des Kanals zu finden, klicken Sie neben dem Kanalnamen auf **Weitere Optionen**, und wählen Sie dann **E-Mail-Adresse abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="0997c-127">To find the channel’s e-mail address, click **More options** next to the channel name and then select **Get email address**.</span></span>

-   <span data-ttu-id="0997c-128">**„Restricted Senders List“ (Liste eingeschränkter Absender):** Die Domänen von Absendern können weiter eingeschränkt werden, um sicherzustellen, dass nur zulässige SMTP-Domänen E-Mails an die Microsoft Teams-Kanäle senden können.</span><span class="sxs-lookup"><span data-stu-id="0997c-128">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Microsoft Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="0997c-129">Apps</span><span class="sxs-lookup"><span data-stu-id="0997c-129">Apps</span></span>
----

<span data-ttu-id="0997c-130">Mit Apps in Microsoft Teams können Sie die für Ihr Team wichtigen Tools und Dienste ganz leicht in einen Kanal oder Chat integrieren.</span><span class="sxs-lookup"><span data-stu-id="0997c-130">Apps in Microsoft Teams are a terrific way to integrate the tools and services your team cares about, right into any channel or chat.</span></span>

<span data-ttu-id="0997c-131">Im Abschnitt **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0997c-131">The **Apps** section lets you configure the following settings for your organization:</span></span>

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

-   <span data-ttu-id="0997c-132">**Externe Apps in Microsoft Teams zulassen:** Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0997c-132">**Allow external apps in Microsoft Teams:** When enabled, users can add tabs and bots that are available to the Office 365 tenant.</span></span>
![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

-   <span data-ttu-id="0997c-133">**Querladen von externen Apps zulassen:** Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0997c-133">**Allow sideloading of external apps:** When enabled, users can install and enable custom bots and tabs.</span></span>

<a name="custom-cloud-storage"></a><span data-ttu-id="0997c-134">Benutzerdefinierter Cloudspeicher</span><span class="sxs-lookup"><span data-stu-id="0997c-134">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="0997c-p104">Zu den Optionen für Cloudspeicher in Microsoft Teams gehören zurzeit Box, Dropbox, Google Drive und ShareFile. Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Klicken oder tippen Sie auf die Umschaltfläche neben den Cloudspeicheranbietern, die Ihre Organisation verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="0997c-p104">Cloud storage options in Microsoft Teams currently include Box, Dropbox, Google Drive, and ShareFile. Users can upload and share files from cloud storage services in Microsoft Teams channels and chats. Click or tap the toggle switch next to the cloud storage providers that your organization wants to use.</span></span>

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="0997c-138">Benutzereinstellungen nach Lizenz</span><span class="sxs-lookup"><span data-stu-id="0997c-138">User settings by license</span></span>
------------------------

<span data-ttu-id="0997c-139">In **Benutzereinstellungen nach Lizenz** können Sie Optionen unter „Teams und Kanäle“, „Anrufe und Besprechungen“ und „Messaging“ aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0997c-139">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="0997c-140">Teams und Kanäle</span><span class="sxs-lookup"><span data-stu-id="0997c-140">Teams and channels</span></span>
------------------

<span data-ttu-id="0997c-p105">Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="0997c-p105">A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room). Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="0997c-p106">Als Administrator können Sie Teambesitzer und -mitglieder über das Dashboard „Gruppen“ im Office 365 Admin Center-Portal verwalten. Klicken Sie im Abschnitt „Teams und Kanäle“ auf den Link **Dashboard „Gruppen“ im Office 365 Admin Center zum Verwalten von Teams verwenden**.</span><span class="sxs-lookup"><span data-stu-id="0997c-p106">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center portal. In the Teams and channels section, click the link for **Use the Groups dashboard in the Office 365 admin center to manage teams**.</span></span>

<span data-ttu-id="0997c-p107">Sie können steuern, welche Benutzer in der Organisation Teams in Microsoft Teams erstellen können. Für Microsoft Teams gelten die gleichen Erstellungseinstellungen, die durch Office 365-Gruppen definiert werden. Weitere Informationen zum Verwalten von Office 365-Gruppen finden Sie unter [Erstellen von Office 365-Gruppen](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) und [Steuern, wer Office 365-Gruppen erstellen kann](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="0997c-p107">You can control which users in your organization can create teams in Microsoft Teams. The same creation settings defined by Office 365 groups apply to Microsoft Teams. For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/en-us/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/en-us/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

<span data-ttu-id="0997c-p108">HINWEIS: Sie können keine Teams über das Dashboard „Gruppen“ erstellen Teams müssen mit dem Microsoft Teams-Desktopclient oder der Web-App erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0997c-p108">NOTE: You can't create teams from the Groups dashboard. Teams must be created by using the Microsoft Teams desktop client or web app.</span></span>

<span data-ttu-id="0997c-p109">Standardmäßig können alle Benutzer Teams oder Gruppen erstellen. Benutzer können Teams erstellen, indem sie links im Microsoft Teams-Client (Desktop- oder Web-App) die Option „Teams“ auswählen. Anschließend wählen sie unten im Client unter der Teamliste die Option „Team erstellen“ aus.</span><span class="sxs-lookup"><span data-stu-id="0997c-p109">By default, every user can create a team or group. Users can create teams by choosing Teams on the left side in the Microsoft Teams client (desktop client or web app), and then choosing Create team at the bottom of the client, below the team list.</span></span>

<span data-ttu-id="0997c-p110">Zurzeit kann ein Office 365-Mandant maximal 500.000 Teams enthalten. Ein globaler Administrator kann beliebig viele Teams erstellen. Ein Benutzer kann 250 Teams erstellen. Ein Teambesitzer kann 2.500 Mitglieder zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0997c-p110">The default maximum number of teams that an Office 365 tenant can have is currently 500,000. A global admin can create an unlimited number of teams. A user can create 250 teams. A team owner can add 999 members to a team.</span></span>

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="0997c-p111">Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.</span><span class="sxs-lookup"><span data-stu-id="0997c-p111">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

### <a name="calls-and-meetings"></a><span data-ttu-id="0997c-161">Anrufe und Besprechungen</span><span class="sxs-lookup"><span data-stu-id="0997c-161">Calls and meetings</span></span>

<span data-ttu-id="0997c-p112">Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.</span><span class="sxs-lookup"><span data-stu-id="0997c-p112">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

<span data-ttu-id="0997c-166">Im Abschnitt **Anrufe und Besprechungen** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0997c-166">The **Calls and meetings** section lets you configure the following settings for your organization:</span></span>

> ![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

-   <span data-ttu-id="0997c-167">**„Allow scheduling for private meetings“ (Planen von privaten Besprechungen zulassen):** Wenn diese Option aktiviert ist, können Benutzer private Besprechungen planen, die nicht in einem Kanal aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="0997c-167">**Allow scheduling for private meetings:** When enabled, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="0997c-168">**„Allow ad-hoc channel meetup“ (Ad-hoc-Kanal-MeetUps zulassen):**</span><span class="sxs-lookup"><span data-stu-id="0997c-168">**Allow ad-hoc channel meetup:**</span></span>

-   <span data-ttu-id="0997c-169">**„Allow scheduling for channel meetings“ (Planen von Kanalbesprechungen zulassen):** Wenn diese Option aktiviert ist, können Benutzer eine Besprechung für einen Kanal planen, an der alle Kanalmitglieder ganz leicht mit einem einzigen Klick teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="0997c-169">**Allow scheduling for channel meetings:** When enabled, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="0997c-170">**„Allow videos in meetings“ (Videos in Besprechungen zulassen):** Gibt an, ob die Verwendung von Video in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0997c-170">**Allow videos in meetings:** Specifies whether the use of video is allowed within the meetings.</span></span>

-   <span data-ttu-id="0997c-171">**„Allow screen sharing in meetings“ (Bildschirmübertragung in Besprechungen zulassen):** Gibt an, ob Bildschirmübertragung in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="0997c-171">**Allow screen sharing in meetings:** Specifies whether screen sharing is allowed within the meetings.</span></span>

-   <span data-ttu-id="0997c-172">**„Allow private calling“ (Private Anrufe zulassen):** Wenn diese Option aktiviert ist, können Benutzer private Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="0997c-172">**Allow private calling:** When enabled, users can make private calls.</span></span>

<span data-ttu-id="0997c-p113">An einer Besprechung können maximal 80 Personen teilnehmen. In einem privaten Chat sind 20 Mitglieder möglich (einschließlich des Benutzers, der den Chat erstellt hat).</span><span class="sxs-lookup"><span data-stu-id="0997c-p113">The maximum number of people in a meeting is 80. There can be 20 members in a private chat, including the user who created the chat.</span></span>

### <a name="messaging"></a><span data-ttu-id="0997c-175">Messaging</span><span class="sxs-lookup"><span data-stu-id="0997c-175">Messaging</span></span> 

<span data-ttu-id="0997c-176">Im Abschnitt „Messaging“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0997c-176">The Messaging section lets you configure the following settings for your organization:</span></span>

![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="0997c-177">**Giphy aktivieren, damit Benutzer GIF-Dateien zu Unterhaltungen hinzufügen können:** Wenn diese Option aktiviert ist, können Benutzer animierte Bilder in den Unterhaltungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0997c-177">**Enable Giphy so users can add gifs to conversations:** When enabled, users can use animated pictures within the conversations.</span></span>

    -   <span data-ttu-id="0997c-p114">**„Content Rating“ (Inhaltsbewertung):** Wenn animierte Bilder aktiviert sind, kann eine Inhaltsbewertung angewendet werden, um den Typ der animierten Bilder einzuschränken, die in Unterhaltungen angezeigt werden können. Für die Inhaltsbewertung sind die folgenden Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0997c-p114">**Content Rating:** When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations. Available content rating options are:</span></span>

        -   <span data-ttu-id="0997c-180">„No restriction“ (Keine Einschränkung)</span><span class="sxs-lookup"><span data-stu-id="0997c-180">No restriction</span></span>

        -   <span data-ttu-id="0997c-181">Mittel (der Standardwert)</span><span class="sxs-lookup"><span data-stu-id="0997c-181">Moderate (the default value)</span></span>

        -   <span data-ttu-id="0997c-182">Streng</span><span class="sxs-lookup"><span data-stu-id="0997c-182">Strict</span></span>

-   <span data-ttu-id="0997c-183">**Memes aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können:** Wenn diese Option aktiviert ist, können Benutzer Internetmemes verwenden, um humorvolle Beiträge zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="0997c-183">**Enable memes that users can edit and add to conversations:** When enabled, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="0997c-184">**„Enable stickers that users can edit and add to conversations“ (Aufkleber aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können):** Wenn diese Option aktiviert ist, können Benutzer Bilder mit bearbeitbarem Text posten, um Kanalmitglieder auf etwas aufmerksam zu machen.</span><span class="sxs-lookup"><span data-stu-id="0997c-184">**Enable stickers that users can edit and add to conversations:** When enabled, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="0997c-185">**Zulassen, dass Eigentümer alle Nachrichten löschen:** Wenn diese Option aktiviert ist, können Kanalbesitzer alle Nachrichten in einem Kanal entfernen.</span><span class="sxs-lookup"><span data-stu-id="0997c-185">**Allow owners to delete all messages:** When enabled, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="0997c-186">**Zulassen, dass Benutzer eigene Nachrichten bearbeiten:** Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="0997c-186">**Allow users to edit their own messages:** When enabled, users can edit their own messages.</span></span>

-   <span data-ttu-id="0997c-187">**Zulassen, dass Benutzer eigene Nachrichten löschen:** Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten löschen.</span><span class="sxs-lookup"><span data-stu-id="0997c-187">**Allow users to delete their own messages:** When enabled, users can delete their own messages.</span></span>

-   <span data-ttu-id="0997c-188">**„Allow users to chat privately“ (Zulassen, dass Benutzer privat chatten):** Wenn diese Option aktiviert ist, können Benutzer an privaten Chats teilnehmen, die nicht für alle Teammitglieder, sondern nur für die Chatteilnehmer sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="0997c-188">**Allow users to chat privately:** When enabled, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>


| |  |  |
|---------|---------|---------|
|![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="0997c-189">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="0997c-189">Decision Point</span></span>         |<span data-ttu-id="0997c-190">Welche Einstellungen für Microsoft Teams wird Ihre Organisation aktivieren?</span><span class="sxs-lookup"><span data-stu-id="0997c-190">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="0997c-191">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0997c-191">Next Steps</span></span>        |<span data-ttu-id="0997c-192">Dokumentieren Sie diese Entscheidungen in [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0997c-192">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |

