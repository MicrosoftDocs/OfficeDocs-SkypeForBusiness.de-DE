---
title: Verwalten Sie Microsoft-Teams-Features in Office 365-Organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Hier finden Sie Informationen zu allen Microsoft Teams-Funktionen, die Sie in Ihrer Office 365-Organisation aktivieren oder deaktivieren können, beispielsweise mandantenweite Einstellungen, E-Mail-Integration, Apps, Cloudspeicher und vieles mehr.
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
<<<<<<< HEAD
ms.openlocfilehash: 87871cb46c1b9e584308b75376622473a3131888
ms.sourcegitcommit: 50446359cd7c359eb2536176545291c723392e47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2018
---
<a name="turn-on-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="e74b8-103">Aktivieren von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="e74b8-103">Turn on Microsoft Teams features in your Office 365 organization</span></span>
=======
ms.openlocfilehash: d4e450f4ffcb178a19d185b14d65b7adb880924b
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
<a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="764ac-103">Verwalten Sie Microsoft-Teams-Features in Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="764ac-103">Manage Microsoft Teams features in your Office 365 organization</span></span>
>>>>>>> d35080a47f5dfe74511fef792bebd70e09a2e978
======================================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<<<<<<< HEAD
<span data-ttu-id="e74b8-p101">Microsoft Teams hat mehrere Einstellungen, die auf Office 365-Mandantenebene aktiviert oder deaktiviert werden können. Wenn Microsoft Teams für einen Mandanten aktiviert ist, erben alle Benutzer, die ebenfalls für Microsoft Teams aktiviert sind, die Einstellungen auf Mandantenebene.</span><span class="sxs-lookup"><span data-stu-id="e74b8-p101">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level. With Teams turned on for a tenant, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="e74b8-106">Unten sehen Sie eine Liste der Funktionen, die Office 365-Administratoren in Microsoft Teams aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="e74b8-107">Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option „Ein“.</span><span class="sxs-lookup"><span data-stu-id="e74b8-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="e74b8-108">Um die Administratoreinstellungen für Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="e74b8-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="e74b8-109">Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="e74b8-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> <span data-ttu-id="e74b8-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span><span class="sxs-lookup"><span data-stu-id="e74b8-110">https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="e74b8-p103">Office 365-Administratoren können Microsoft Teams jederzeit im Office 365 Admin Center deaktivieren. Beachten Sie, dass Benutzer mit aktiven Lizenzen für Microsoft Teams die Kachel der Microsoft Teams-App auch dann noch sehen, wenn Sie Microsoft Teams deaktiviert haben. Details zum Entfernen von Lizenzen von Benutzern finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md). Wenn Microsoft Teams deaktiviert wurde, ist der Zugriff über den Microsoft Teams-Client blockiert, aber die über andere Clients und Dienste verfügbaren Daten sind nach wie vor verfügbar. Dies gilt zum Beispiel für Dateien aus SharePoint und OneDrive. Alle Daten verbleiben an Ort und Stelle, solange die Teams nicht explizit gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-p103">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center. Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams. For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md). After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive. All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="e74b8-116">Mandantenweite Einstellungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="e74b8-116">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="e74b8-117">In **Mandantenweite Einstellungen** können Sie Optionen unter „Allgemein“, „E-Mail-Integration“, „Apps“ und „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e74b8-117">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="e74b8-118">Um **mandantenweite Einstellungen** für Microsoft Teams zu bearbeiten, wechseln Sie zum Office 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="e74b8-118">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="e74b8-119">Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="e74b8-119">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="e74b8-120">Allgemein</span><span class="sxs-lookup"><span data-stu-id="e74b8-120">General</span></span>

<span data-ttu-id="e74b8-121">Im Abschnitt „Allgemein“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e74b8-121">The General section lets you configure the following settings for your organization:</span></span>

> ![Screenshot des Abschnitts „Allgemein“ in „Mandantenweite Einstellungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="e74b8-123">**Show organizational chart in personal profile** (Organigramm in persönlichem Profil anzeigen): Wenn diese Einstellung aktiviert ist, wird das Organigrammsymbol auf der Visitenkarte des Benutzers angezeigt. Durch Klicken auf das Symbol wird das detaillierte Organigramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e74b8-123">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>
=======
<span data-ttu-id="764ac-104">Teams hat mehrere Einstellungen, die aktiviert oder deaktiviert werden können, auf der Ebene der Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="764ac-104">Teams has multiple settings that can be turned on or turned off at the Office 365 tenant level.</span></span> <span data-ttu-id="764ac-105">Mit den Teams, die aktiviert werden wird jeder Benutzer, die auch für Teams aktiviert ist die Einstellungen der Mandanten-Ebene erben.</span><span class="sxs-lookup"><span data-stu-id="764ac-105">With Teams enabled, any user that is also enabled for Teams will inherit the settings from the tenant level.</span></span>

<span data-ttu-id="764ac-106">Unten sehen Sie eine Liste der Funktionen, die Office 365-Administratoren in Microsoft Teams aktivieren oder deaktivieren können.</span><span class="sxs-lookup"><span data-stu-id="764ac-106">Below is the list of features an Office 365 administrator can turn on or turn off in Teams.</span></span> 

<span data-ttu-id="764ac-107">Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option „Ein“.</span><span class="sxs-lookup"><span data-stu-id="764ac-107">Unless otherwise noted, the default value for an option is On.</span></span>

> [!NOTE] 
> <span data-ttu-id="764ac-108">Um die Administratoreinstellungen für Microsoft Teams zu verwalten, wechseln Sie zum Office 365 Admin Center. Öffnen Sie **Einstellungen** > **Dienste und Add-Ins**, und wählen Sie dann **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="764ac-108">To manage admin settings for Teams, go to the Office 365 admin center and open **Settings** > **Services & add-ins**, then choose **Microsoft Teams**.</span></span> <span data-ttu-id="764ac-109">Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="764ac-109">If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

> [!IMPORTANT]
> <span data-ttu-id="764ac-p103">Office 365-Administratoren können Microsoft Teams jederzeit im Office 365 Admin Center deaktivieren. Beachten Sie, dass Benutzer mit aktiven Lizenzen für Microsoft Teams die Kachel der Microsoft Teams-App auch dann noch sehen, wenn Sie Microsoft Teams deaktiviert haben. Details zum Entfernen von Lizenzen von Benutzern finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](user-access.md). Wenn Microsoft Teams deaktiviert wurde, ist der Zugriff über den Microsoft Teams-Client blockiert, aber die über andere Clients und Dienste verfügbaren Daten sind nach wie vor verfügbar. Dies gilt zum Beispiel für Dateien aus SharePoint und OneDrive. Alle Daten verbleiben an Ort und Stelle, solange die Teams nicht explizit gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="764ac-p103">An Office 365 admin can turn off Microsoft Teams at any time in the Office 365 admin center. Be aware that users with active Microsoft Teams licenses will continue to see the Teams app tile even if you turn off Teams. For details about how to remove licenses from users, see [Manage user access to Microsoft Teams](user-access.md). After Teams is disabled, access from the Teams client is blocked, but data available through other clients and services is still available, such as files via SharePoint and OneDrive. All data remains in place unless the teams are explicitly deleted.</span></span>

<a name="office-365-tenant-wide-settings"></a><span data-ttu-id="764ac-115">Mandantenweite Einstellungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="764ac-115">Office 365 tenant-wide settings</span></span> 
---------------------

<span data-ttu-id="764ac-116">In **Mandantenweite Einstellungen** können Sie Optionen unter „Allgemein“, „E-Mail-Integration“, „Apps“ und „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher) aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="764ac-116">In **Tenant-wide settings**, you can turn on or turn off options in General, Email integration, Apps, and Custom cloud storage.</span></span>

<span data-ttu-id="764ac-117">Um **mandantenweite Einstellungen** für Microsoft Teams zu bearbeiten, wechseln Sie zum Office 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="764ac-117">To edit **Tenant-wide settings** for Teams, go to the Office 365 admin center.</span></span> <span data-ttu-id="764ac-118">Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus.</span><span class="sxs-lookup"><span data-stu-id="764ac-118">Choose **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span>

### <a name="general"></a><span data-ttu-id="764ac-119">Allgemein</span><span class="sxs-lookup"><span data-stu-id="764ac-119">General</span></span>

<span data-ttu-id="764ac-120">Im Abschnitt „Allgemein“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="764ac-120">The General section lets you configure the following settings for your organization:</span></span>

> ![Screenshot des Abschnitts „Allgemein“ in „Mandantenweite Einstellungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image1.png)

-   <span data-ttu-id="764ac-122">**Show organizational chart in personal profile** (Organigramm in persönlichem Profil anzeigen): Wenn diese Einstellung aktiviert ist, wird das Organigrammsymbol auf der Visitenkarte des Benutzers angezeigt. Durch Klicken auf das Symbol wird das detaillierte Organigramm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="764ac-122">**Show organizational chart in personal profile:** When this setting is turned on, it shows the organizational chart icon in the user’s contact card, and when clicked, it displays the detailed organizational chart.</span></span>
>>>>>>> d35080a47f5dfe74511fef792bebd70e09a2e978

    ![Screenshot des Organigrammsymbols auf der Visitenkarte eines Benutzers](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image2.png)

    ![Screenshot eines Organigramms](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image3.png)

<<<<<<< HEAD
-  <span data-ttu-id="e74b8-126">**Use Skype for Business for recipients who don’t have Teams** (Für Empfänger, die Microsoft Teams nicht haben, Skype for Business verwenden): Wenn diese Einstellung aktiviert ist, werden Microsoft Teams-Unterhaltungen für Benutzer, die nicht für Microsoft Teams aktiviert sind, automatisch in Skype for Business angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e74b8-126">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="e74b8-127">**Allow T-bot proactive help messages** (Proaktive Hilfenachrichten von T-Bot zulassen): Wenn diese Einstellung aktiviert ist, initiiert T-Bot private Chatsitzungen mit Benutzern, um ihnen bei der Verwendung von Microsoft Teams zu helfen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-127">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Screenshot des T-Bot-Abschnitts auf der Benutzeroberfläche von Microsoft Teams](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="e74b8-129">E-Mail-Integration</span><span class="sxs-lookup"><span data-stu-id="e74b8-129">Email integration</span></span>
-----------------

<span data-ttu-id="e74b8-130">Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-130">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="e74b8-131">Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind.</span><span class="sxs-lookup"><span data-stu-id="e74b8-131">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="e74b8-132">Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e74b8-132">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="e74b8-133">Auch wenn Benutzer nicht über die Berechtigung verfügen, eine Kanal-E-Mail-Adresse zu erstellen, und eine andere Person mit der entsprechenden Berechtigung diese Adresse erstellt, können die Benutzer über das Menü **Weitere Optionen** für den jeweiligen Kanal auf die Adresse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-133">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="e74b8-134">Konfigurieren Sie unter **Email integration** (E-Mail-Integration) die folgenden Einstellungen für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="e74b8-134">Configure the following **Email integration** settings for your organization:</span></span> 

   ![Screenshot des Abschnitts „E-Mail-Integration“ in „Mandantenweite Einstellungen“](media/QS-edu-email-integration.png)

-   <span data-ttu-id="e74b8-136">**Allow users to send emails to channels** (Zulassen, dass Benutzer E-Mails an Kanäle senden): Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-136">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of a Teams channel.</span></span> 

 
-   <span data-ttu-id="e74b8-137">**Allow users to send emails to channels** (Zulassen, dass Benutzer E-Mails an Kanäle senden): Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-137">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="e74b8-138">Um die E-Mail-Adresse des Kanals zu finden, klicken Sie auf das Menü **Weitere Optionen** für den Kanal, und wählen Sie dann **E-Mail-Adresse abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="e74b8-138">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="e74b8-139">**Restricted Senders List** (Liste eingeschränkter Absender): Die Domänen von Absendern können weiter eingeschränkt werden, um sicherzustellen, dass nur E-Mails aus zulässigen SMTP-Domänen an die Microsoft Teams-Kanäle gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-139">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="e74b8-140">Apps</span><span class="sxs-lookup"><span data-stu-id="e74b8-140">Apps</span></span>
----

<span data-ttu-id="e74b8-p106">Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e74b8-p106">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="e74b8-144">Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e74b8-144">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="e74b8-146">**Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e74b8-146">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="e74b8-148">**Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-148">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="e74b8-149">Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="e74b8-149">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="e74b8-150">Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-150">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="e74b8-151">**Allow sideloading of external apps** (Querladen von externen Apps zulassen): Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e74b8-151">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="e74b8-152">Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="e74b8-152">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="e74b8-153">Benutzerdefinierter Cloudspeicher</span><span class="sxs-lookup"><span data-stu-id="e74b8-153">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="e74b8-154">Zu den Optionen für Cloudspeicher in Microsoft Teams gehören zurzeit Box, Dropbox, Google Drive und ShareFile.</span><span class="sxs-lookup"><span data-stu-id="e74b8-154">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="e74b8-155">Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben.</span><span class="sxs-lookup"><span data-stu-id="e74b8-155">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="e74b8-156">Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="e74b8-156">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![Screenshot des Abschnitts „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher)](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="user-settings-by-license"></a><span data-ttu-id="e74b8-158">Benutzereinstellungen nach Lizenz</span><span class="sxs-lookup"><span data-stu-id="e74b8-158">User settings by license</span></span>
=======
-  <span data-ttu-id="764ac-125">**Use Skype for Business for recipients who don’t have Teams** (Für Empfänger, die Microsoft Teams nicht haben, Skype for Business verwenden): Wenn diese Einstellung aktiviert ist, werden Microsoft Teams-Unterhaltungen für Benutzer, die nicht für Microsoft Teams aktiviert sind, automatisch in Skype for Business angezeigt.</span><span class="sxs-lookup"><span data-stu-id="764ac-125">**Use Skype for Business for recipients who don’t have Teams:** When this setting is turned on, Teams conversations automatically show up in Skype for Business for users that aren't enabled for Teams.</span></span>  

-   <span data-ttu-id="764ac-126">**Allow T-bot proactive help messages** (Proaktive Hilfenachrichten von T-Bot zulassen): Wenn diese Einstellung aktiviert ist, initiiert T-Bot private Chatsitzungen mit Benutzern, um ihnen bei der Verwendung von Microsoft Teams zu helfen.</span><span class="sxs-lookup"><span data-stu-id="764ac-126">**Allow T-bot proactive help messages:** When this setting is turned on, T-bot will initiate a private chat session with users to help them use Teams.</span></span>

    ![Screenshot des T-Bot-Abschnitts auf der Benutzeroberfläche von Microsoft Teams](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image4.png)

<a name="email-integration"></a><span data-ttu-id="764ac-128">E-Mail-Integration</span><span class="sxs-lookup"><span data-stu-id="764ac-128">Email integration</span></span>
-----------------

<span data-ttu-id="764ac-129">Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können.</span><span class="sxs-lookup"><span data-stu-id="764ac-129">Turn on this feature so users can send email to a channel in Teams, using the channel email address.</span></span> <span data-ttu-id="764ac-130">Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind.</span><span class="sxs-lookup"><span data-stu-id="764ac-130">Users can do this for any channel belonging to a team they own.</span></span> <span data-ttu-id="764ac-131">Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="764ac-131">Users can also send emails to any channel in a team that has adding connectors enabled for team members.</span></span> <span data-ttu-id="764ac-132">Auch wenn Benutzer nicht über die Berechtigung verfügen, eine Kanal-E-Mail-Adresse zu erstellen, und eine andere Person mit der entsprechenden Berechtigung diese Adresse erstellt, können die Benutzer über das Menü **Weitere Optionen** für den jeweiligen Kanal auf die Adresse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="764ac-132">And, even if a user doesn’t have permission to create a channel email address, if someone who does have permission creates that address, the user can access it from the **More options** menu for that channel.</span></span>

<span data-ttu-id="764ac-133">Konfigurieren Sie unter **Email integration** (E-Mail-Integration) die folgenden Einstellungen für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="764ac-133">Configure the following **Email integration** settings for your organization:</span></span> 

   ![Screenshot des Abschnitts „E-Mail-Integration“ in „Mandantenweite Einstellungen“](media/QS-edu-email-integration.png)


-   <span data-ttu-id="764ac-135">**Allow users to send emails to channels** (Zulassen, dass Benutzer E-Mails an Kanäle senden): Wenn diese Option aktiviert ist, werden Mailhooks aktiviert, und Benutzer können Nachrichten in einem Kanal posten, indem sie eine E-Mail an die E-Mail-Adresse des Microsoft Teams-Kanals senden.</span><span class="sxs-lookup"><span data-stu-id="764ac-135">**Allow users to send emails to channels:** When turned on, mail hooks are enabled, and users can post messages to a channel by sending an email to the email address of Teams channel.</span></span> 

    <span data-ttu-id="764ac-136">Um die E-Mail-Adresse des Kanals zu finden, klicken Sie auf das Menü **Weitere Optionen** für den Kanal, und wählen Sie dann **E-Mail-Adresse abrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="764ac-136">To find the email address for a channel, click the **More options** menu for the channel and then select **Get email address**.</span></span> 

-   <span data-ttu-id="764ac-137">**Restricted Senders List** (Liste eingeschränkter Absender): Die Domänen von Absendern können weiter eingeschränkt werden, um sicherzustellen, dass nur E-Mails aus zulässigen SMTP-Domänen an die Microsoft Teams-Kanäle gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="764ac-137">**Restricted Senders List:** Senders domains can be further restricted to ensure that only allowed SMTP domains can send emails to the Teams channels.</span></span>

<a name="apps"></a><span data-ttu-id="764ac-138">Apps</span><span class="sxs-lookup"><span data-stu-id="764ac-138">Apps</span></span>
----

<span data-ttu-id="764ac-p106">Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="764ac-p106">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external App behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="764ac-142">Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="764ac-142">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="764ac-144">**Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="764ac-144">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="764ac-146">**Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="764ac-146">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog.</span></span> <span data-ttu-id="764ac-147">Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten.</span><span class="sxs-lookup"><span data-stu-id="764ac-147">Turn off this switch if you want to control new apps.</span></span> <span data-ttu-id="764ac-148">Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen.</span><span class="sxs-lookup"><span data-stu-id="764ac-148">Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="764ac-149">**Allow sideloading of external apps** (Querladen von externen Apps zulassen): Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="764ac-149">**Allow sideloading of external apps**: When this switch is turned on, users can install and enable custom bots and tabs.</span></span> 

<span data-ttu-id="764ac-150">Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="764ac-150">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 



<a name="custom-cloud-storage"></a><span data-ttu-id="764ac-151">Benutzerdefinierter Cloudspeicher</span><span class="sxs-lookup"><span data-stu-id="764ac-151">Custom cloud storage</span></span>
--------------------

<span data-ttu-id="764ac-152">Zu den Optionen für Cloudspeicher in Microsoft Teams gehören zurzeit Box, Dropbox, Google Drive und ShareFile.</span><span class="sxs-lookup"><span data-stu-id="764ac-152">Cloud storage options in Teams currently include Box, Dropbox, Google Drive, and ShareFile.</span></span> <span data-ttu-id="764ac-153">Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben.</span><span class="sxs-lookup"><span data-stu-id="764ac-153">Users can upload and share files from cloud storage services in Teams channels and chats.</span></span> <span data-ttu-id="764ac-154">Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="764ac-154">Turn on the switch for the cloud storage providers that your organization wants to use.</span></span> 

![Screenshot des Abschnitts „Custom cloud storage“ (Benutzerdefinierter Cloudspeicher)](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image7.png)

<a name="settings-by-userlicense-type"></a><span data-ttu-id="764ac-156">Geben Sie die Einstellungen von User-Lizenz</span><span class="sxs-lookup"><span data-stu-id="764ac-156">Settings by user/license type</span></span>
>>>>>>> d35080a47f5dfe74511fef792bebd70e09a2e978
------------------------
<span data-ttu-id="764ac-157">Wenn Sie Microsoft-Teams für Ihre Organisation zunächst einrichten, verwendet Sie die **Einstellungen werden vom Typ User-Lizenz** -Dropdownmenü, wählen Sie einen Lizenztyp und Teams dann für alle Benutzer des betreffenden Lizenztyps eingeschaltet.</span><span class="sxs-lookup"><span data-stu-id="764ac-157">When you set up Microsoft Teams for your organization initially, you used the the **Settings by user/license type** drop-down menu to select a license type and then turned Teams on for all users of that license type.</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

<<<<<<< HEAD
<span data-ttu-id="e74b8-159">In **Benutzereinstellungen nach Lizenz** können Sie Optionen unter „Teams und Kanäle“, „Anrufe und Besprechungen“ und „Messaging“ aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e74b8-159">In **User settings by license**, you can turn on or turn off options in Teams and channels, Calls and meetings, and Messaging.</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="e74b8-160">Teams und Kanäle</span><span class="sxs-lookup"><span data-stu-id="e74b8-160">Teams and channels</span></span>
------------------

<span data-ttu-id="e74b8-p109">Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="e74b8-p109">A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room). Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="e74b8-164">Zurzeit kann ein Office 365-Mandant maximal 500.000 Teams enthalten.</span><span class="sxs-lookup"><span data-stu-id="e74b8-164">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="e74b8-165">Ein globaler Administrator kann beliebig viele Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-165">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="e74b8-166">Ein Benutzer kann 250 Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-166">A user can create 250 teams.</span></span> <span data-ttu-id="e74b8-167">Ein Teambesitzer kann 2500 Mitglieder zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-167">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="e74b8-168">Als Administrator können Sie Teambesitzer und -mitglieder über das Dashboard „Gruppen“ im Office 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="e74b8-168">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="e74b8-169">Wenn Sie mehr wissen möchten, klicken Sie unter **Teams und Kanäle** auf **Use the Groups dashboard in the Office 365 admin center to manage teams** (Dashboard „Gruppen“ im Office 365 Admin Center zum Verwalten von Teams verwenden).</span><span class="sxs-lookup"><span data-stu-id="e74b8-169">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="e74b8-170">Sie können steuern, welche Benutzer in der Organisation Teams in Microsoft Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-170">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="e74b8-171">Für Microsoft Teams gelten die gleichen Erstellungseinstellungen, die durch Office 365-Gruppen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-171">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="e74b8-172">Weitere Informationen zum Verwalten von Office 365-Gruppen finden Sie unter [Erstellen von Office 365-Gruppen](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) und [Steuern, wer Office 365-Gruppen erstellen kann](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="e74b8-172">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="e74b8-173">Sie können keine Teams über das Dashboard „Gruppen“ erstellen</span><span class="sxs-lookup"><span data-stu-id="e74b8-173">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="e74b8-174">Teams müssen mit dem Microsoft Teams-Desktopclient oder der Web-App erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-174">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="e74b8-175">Standardmäßig können alle Benutzer Teams oder Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-175">By default, every user can create a team or group.</span></span> <span data-ttu-id="e74b8-176">Wählen Sie links im Microsoft Teams-Client (Desktopclient oder Web-App) die Option **Teams** aus. Wählen Sie dann unten im Client unter der Teamliste die Option **Create and join team** (Team erstellen und beitreten) aus.</span><span class="sxs-lookup"><span data-stu-id="e74b8-176">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![Screenshot des Abschnitts „Benutzereinstellungen nach Lizenz“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="e74b8-p115">Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.</span><span class="sxs-lookup"><span data-stu-id="e74b8-p115">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="e74b8-182">Anrufe und Besprechungen</span><span class="sxs-lookup"><span data-stu-id="e74b8-182">Calls and meetings</span></span>

<span data-ttu-id="e74b8-183">Konfigurieren Sie unter **Anrufe und Besprechungen** die folgenden Einstellungen für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="e74b8-183">Configure the following **Calls and meetings** settings for your organization:</span></span>

![Screenshot des Abschnitts „Anrufe und Besprechungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="e74b8-p116">An einer Besprechung können maximal 80 Personen teilnehmen. In einem privaten Chat sind 20 Mitglieder möglich (einschließlich des Benutzers, der den Chat erstellt hat).</span><span class="sxs-lookup"><span data-stu-id="e74b8-p116">The maximum number of people in a meeting is 80. There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="e74b8-187">**Allow scheduling for private meetings** (Planen von privaten Besprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer private Besprechungen planen, die nicht in einem Kanal aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="e74b8-187">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="e74b8-188">**Allow ad-hoc channel meetup** (Ad-hoc-Kanal-MeetUps zulassen): Wenn diese Option aktiviert ist, können Benutzer schnell eine Besprechung für einen Kanal starten, der zur sofortigen Verwendung oder für einen bestimmten Zweck erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e74b8-188">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="e74b8-189">**Allow scheduling for channel meetings** (Planen von Kanalbesprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer eine Besprechung für einen Kanal planen, an der alle Kanalmitglieder ganz leicht mit einem einzigen Klick teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-189">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="e74b8-190">**Allow videos in meetings** (Video in Besprechungen zulassen): Gibt an, ob die Verwendung von Video in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e74b8-190">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="e74b8-191">**Allow screen sharing in meetings** (Bildschirmübertragung in Besprechungen zulassen): Gibt an, ob Bildschirmübertragung in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="e74b8-191">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="e74b8-192">**Allow private calling** (Private Anrufe zulassen): Wenn diese Option aktiviert ist, können Benutzer private Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-192">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="e74b8-193">Messaging</span><span class="sxs-lookup"><span data-stu-id="e74b8-193">Messaging</span></span> 

<span data-ttu-id="e74b8-194">Im Abschnitt „Messaging“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e74b8-194">The Messaging section lets you configure the following settings for your organization:</span></span>

![Screenshot des Abschnitts „Messaging“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="e74b8-196">**Enable Giphy so users can add gifs to conversations** (Giphy aktivieren, damit Benutzer GIF-Dateien zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer animierte Bilder in den Unterhaltungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e74b8-196">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="e74b8-197">**Content Rating** (Inhaltsbewertung): Wenn animierte Bilder aktiviert sind, kann eine Inhaltsbewertung angewendet werden, um den Typ der animierten Bilder einzuschränken, die in Unterhaltungen angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="e74b8-197">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="e74b8-198">Für die Inhaltsbewertung sind die folgenden Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="e74b8-198">Available content rating options are:</span></span>

    -   <span data-ttu-id="e74b8-199">„No restriction“ (Keine Einschränkung)</span><span class="sxs-lookup"><span data-stu-id="e74b8-199">No restriction</span></span>
    -   <span data-ttu-id="e74b8-200">Mittel (der Standardwert)</span><span class="sxs-lookup"><span data-stu-id="e74b8-200">Moderate (the default value)</span></span>
    -   <span data-ttu-id="e74b8-201">Streng</span><span class="sxs-lookup"><span data-stu-id="e74b8-201">Strict</span></span>

-   <span data-ttu-id="e74b8-202">**Enable memes that users can edit and add to conversations** (Memes aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Internetmemes verwenden, um humorvolle Beiträge zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-202">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="e74b8-203">**Enable stickers that users can edit and add to conversations** (Aufkleber aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Bilder mit bearbeitbarem Text posten, um Kanalmitglieder auf etwas aufmerksam zu machen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-203">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="e74b8-204">**Allow owners to delete all messages** (Zulassen, dass Besitzer alle Nachrichten löschen): Wenn diese Option aktiviert ist, können Kanalbesitzer alle Nachrichten in einem Kanal entfernen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-204">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="e74b8-205">**Allow users to edit their own messages** (Zulassen, dass Benutzer eigene Nachrichten bearbeiten): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="e74b8-205">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="e74b8-206">**Allow users to delete their own messages** (Zulassen, dass Benutzer eigene Nachrichten löschen): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten löschen.</span><span class="sxs-lookup"><span data-stu-id="e74b8-206">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="e74b8-207">**Allow users to chat privately** (Zulassen, dass Benutzer privat chatten): Wenn diese Option aktiviert ist, können Benutzer an privaten Chats teilnehmen, die nicht für alle Teammitglieder, sondern nur für die Chatteilnehmer sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="e74b8-207">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>
=======
 <span data-ttu-id="764ac-158">Einige Beispiele für User-Lizenz-Typen sind **Business & Enterprise** und **Gast**.</span><span class="sxs-lookup"><span data-stu-id="764ac-158">Some examples of user/license types are **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="764ac-159">(Wenn Sie eine Education SKU-Lizenz verfügen, **Education - Fakultät und Mitarbeiter** oder **Education - Student** sind verfügbar.) ![-Steuerelement für Set-Benutzerlizenz](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span><span class="sxs-lookup"><span data-stu-id="764ac-159">(If you have an Education SKU license, **Education - Faculty and Staff** or **Education - Student** are available.)![Control for Set user license](media/enable-microsoft-teams-features-in-your-office-365-organization-image13.png)</span></span>

<span data-ttu-id="764ac-160">Sie können mehrere Lizenztypen innerhalb Ihrer Organisation, **beispielsweise sowohl Business & Enterprise** und **Gast**haben.</span><span class="sxs-lookup"><span data-stu-id="764ac-160">You can you have multiple license types within your organization, for example, both **Business & Enterprise** and **Guest**.</span></span> <span data-ttu-id="764ac-161">Microsoft-Teams können nur von Benutzern basierend auf der Lizenzen, die ihnen zugewiesenen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="764ac-161">Microsoft Teams can only differentiate users based on the licenses you've assigned them.</span></span> <span data-ttu-id="764ac-162">Sie können die aktivieren oder deaktivieren Sie Optionen für diese Benutzer in **Teams und Kanäle**, **Anrufe und Besprechungen**und **Messaging**.</span><span class="sxs-lookup"><span data-stu-id="764ac-162">You can turn on or turn off options for these users in **Teams and channels**, **Calls and meetings**, and **Messaging**.</span></span> <span data-ttu-id="764ac-163">Wenn Sie nur einen Lizenztyp verwenden, sollten Sie die Einstellungen als Mandanten geltende Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="764ac-163">If you use only one license type, consider the settings here as tenant-wide settings.</span></span>
> [!NOTE]
> <span data-ttu-id="764ac-164">Weitere Informationen zu Gast Access finden Sie unter [Aktivieren oder Deaktivieren der Gastzugriff auf Microsoft-Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="764ac-164">For more details about guest access, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

<a name="teams-and-channels"></a><span data-ttu-id="764ac-165">Teams und Kanäle</span><span class="sxs-lookup"><span data-stu-id="764ac-165">Teams and channels</span></span>
------------------

<span data-ttu-id="764ac-p111">Teams sollen Gruppen von Personen zusammenbringen, die eng zusammenarbeiten, um ihre Produktivität zu verbessern. Möglich sind dynamische Teams für projektbasierte Aufgaben (zum Beispiel Einführung eines Produkts oder Einrichtung eines gemeinsamen digitalen Arbeitsraums). Eine weitere Möglichkeit sind ständige Teams, die die interne Struktur Ihrer Organisation widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="764ac-p111">A team is designed to bring together a group of people who work closely to get things done. Teams can be dynamic for project-based work (for example, launching a product or creating a digital war room). Or, teams can be ongoing, to reflect the internal structure of your organization.</span></span>

<span data-ttu-id="764ac-169">Zurzeit kann ein Office 365-Mandant maximal 500.000 Teams enthalten.</span><span class="sxs-lookup"><span data-stu-id="764ac-169">The maximum number of teams that an Office 365 tenant can have is currently 500,000.</span></span> <span data-ttu-id="764ac-170">Ein globaler Administrator kann beliebig viele Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="764ac-170">A global admin can create an unlimited number of teams.</span></span> <span data-ttu-id="764ac-171">Ein Benutzer kann 250 Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="764ac-171">A user can create 250 teams.</span></span> <span data-ttu-id="764ac-172">Ein Teambesitzer kann 2500 Mitglieder zu einem Team hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="764ac-172">A team owner can add 2500 members to a team.</span></span>

<span data-ttu-id="764ac-173">Als Administrator können Sie Teambesitzer und -mitglieder über das Dashboard „Gruppen“ im Office 365 Admin Center verwalten.</span><span class="sxs-lookup"><span data-stu-id="764ac-173">As an admin, you can manage team owners and members by using the Groups dashboard in the Office 365 admin center.</span></span> <span data-ttu-id="764ac-174">Wenn Sie mehr wissen möchten, klicken Sie unter **Teams und Kanäle** auf **Use the Groups dashboard in the Office 365 admin center to manage teams** (Dashboard „Gruppen“ im Office 365 Admin Center zum Verwalten von Teams verwenden).</span><span class="sxs-lookup"><span data-stu-id="764ac-174">To learn more, click **Use the Groups dashboard in the Office 365 admin center to manage teams** under **Teams and channels**.</span></span>

<span data-ttu-id="764ac-175">Sie können steuern, welche Benutzer in der Organisation Teams in Microsoft Teams erstellen können.</span><span class="sxs-lookup"><span data-stu-id="764ac-175">You can control which users in your organization can create teams in Teams.</span></span> <span data-ttu-id="764ac-176">Für Microsoft Teams gelten die gleichen Erstellungseinstellungen, die durch Office 365-Gruppen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="764ac-176">The same creation settings defined by Office 365 groups apply to Teams.</span></span> <span data-ttu-id="764ac-177">Weitere Informationen zum Verwalten von Office 365-Gruppen finden Sie unter [Erstellen von Office 365-Gruppen](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) und [Steuern, wer Office 365-Gruppen erstellen kann](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span><span class="sxs-lookup"><span data-stu-id="764ac-177">For more information about managing Office 365 groups, see [Create Office 365 groups](https://support.office.com/article/Create-Office-365-groups-74a1ef8b-3844-4d08-9980-9f8f7a36000f) and [Control who can create Office 365 Groups](https://support.office.com/article/Control-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>

> [!NOTE]
> <span data-ttu-id="764ac-178">Sie können keine Teams über das Dashboard „Gruppen“ erstellen</span><span class="sxs-lookup"><span data-stu-id="764ac-178">You can't create teams from the Groups dashboard.</span></span> <span data-ttu-id="764ac-179">Teams müssen mit dem Microsoft Teams-Desktopclient oder der Web-App erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="764ac-179">Teams must be created by using the Teams desktop client or web app.</span></span>

<span data-ttu-id="764ac-180">Standardmäßig können alle Benutzer Teams oder Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="764ac-180">By default, every user can create a team or group.</span></span> <span data-ttu-id="764ac-181">Wählen Sie links im Microsoft Teams-Client (Desktopclient oder Web-App) die Option **Teams** aus. Wählen Sie dann unten im Client unter der Teamliste die Option **Create and join team** (Team erstellen und beitreten) aus.</span><span class="sxs-lookup"><span data-stu-id="764ac-181">Choose **Teams** on the left side in the Teams client (desktop client or web app), then choose **Create and join team** at the bottom of the client, below the team list.</span></span>

![Screenshot des Abschnitts „Benutzereinstellungen nach Lizenz“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image8.png)

<span data-ttu-id="764ac-p117">Kanäle sind Unterkategorien von Teams. Alle Teammitglieder können Kanäle hinzufügen und sich an den Unterhaltungen im Kanal beteiligen. Sie können einen Kanal für eine Aktivität oder eine Abteilung erstellen. Unterhaltungen, Dateien und Wikis sind zwar kanalspezifisch, aber für alle Teammitglieder sichtbar.</span><span class="sxs-lookup"><span data-stu-id="764ac-p117">Channels are subcategories of teams. Anyone on the team can add a channel and participate in the conversations in a channel. You might create a channel for an activity or for a department. Conversations, files, and wikis are specific to each channel, but all members of the team can see them.</span></span>

## <a name="calls-and-meetings"></a><span data-ttu-id="764ac-187">Anrufe und Besprechungen</span><span class="sxs-lookup"><span data-stu-id="764ac-187">Calls and meetings</span></span>

<span data-ttu-id="764ac-188">Konfigurieren Sie unter **Anrufe und Besprechungen** die folgenden Einstellungen für Ihre Organisation:</span><span class="sxs-lookup"><span data-stu-id="764ac-188">Configure the following **Calls and meetings** settings for your organization:</span></span>

![Screenshot des Abschnitts „Anrufe und Besprechungen“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image9.png)

<span data-ttu-id="764ac-p118">An einer Besprechung können maximal 80 Personen teilnehmen. In einem privaten Chat sind 20 Mitglieder möglich (einschließlich des Benutzers, der den Chat erstellt hat).</span><span class="sxs-lookup"><span data-stu-id="764ac-p118">The maximum number of people in a meeting is 80. There can be 20 members in a private chat, including the user who created the chat.</span></span>

-   <span data-ttu-id="764ac-192">**Allow scheduling for private meetings** (Planen von privaten Besprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer private Besprechungen planen, die nicht in einem Kanal aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="764ac-192">**Allow scheduling for private meetings**: When turned on, users can schedule private meetings that are not listed in any channel.</span></span>

-   <span data-ttu-id="764ac-193">**Allow ad-hoc channel meetup** (Ad-hoc-Kanal-MeetUps zulassen): Wenn diese Option aktiviert ist, können Benutzer schnell eine Besprechung für einen Kanal starten, der zur sofortigen Verwendung oder für einen bestimmten Zweck erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="764ac-193">**Allow ad-hoc channel meetup**: When turned on, users can quickly start a meeting for a channel that has been created for an immediate or specific purpose.</span></span>

-   <span data-ttu-id="764ac-194">**Allow scheduling for channel meetings** (Planen von Kanalbesprechungen zulassen): Wenn diese Option aktiviert ist, können Benutzer eine Besprechung für einen Kanal planen, an der alle Kanalmitglieder ganz leicht mit einem einzigen Klick teilnehmen können.</span><span class="sxs-lookup"><span data-stu-id="764ac-194">**Allow scheduling for channel meetings**: When turned on, users can schedule a meeting for a channel that all channel members can easily join with a single click.</span></span>

-   <span data-ttu-id="764ac-195">**Allow videos in meetings** (Video in Besprechungen zulassen): Gibt an, ob die Verwendung von Video in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="764ac-195">**Allow videos in meetings:** Specifies whether the use of video is allowed in meetings.</span></span>

-   <span data-ttu-id="764ac-196">**Allow screen sharing in meetings** (Bildschirmübertragung in Besprechungen zulassen): Gibt an, ob Bildschirmübertragung in Besprechungen zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="764ac-196">**Allow screen sharing in meetings**: Specifies whether screen sharing is allowed in meetings.</span></span>

-   <span data-ttu-id="764ac-197">**Allow private calling** (Private Anrufe zulassen): Wenn diese Option aktiviert ist, können Benutzer private Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="764ac-197">**Allow private calling**: When turned on, users can make private calls.</span></span>

## <a name="messaging"></a><span data-ttu-id="764ac-198">Messaging</span><span class="sxs-lookup"><span data-stu-id="764ac-198">Messaging</span></span> 

<span data-ttu-id="764ac-199">Im Abschnitt „Messaging“ können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="764ac-199">The Messaging section lets you configure the following settings for your organization:</span></span>

![Screenshot des Abschnitts „Messaging“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image10.png)

-   <span data-ttu-id="764ac-201">**Enable Giphy so users can add gifs to conversations** (Giphy aktivieren, damit Benutzer GIF-Dateien zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer animierte Bilder in den Unterhaltungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="764ac-201">**Enable Giphy so users can add gifs to conversations**: When turned on, users can use animated pictures within the conversations.</span></span>

-   <span data-ttu-id="764ac-202">**Content Rating** (Inhaltsbewertung): Wenn animierte Bilder aktiviert sind, kann eine Inhaltsbewertung angewendet werden, um den Typ der animierten Bilder einzuschränken, die in Unterhaltungen angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="764ac-202">**Content Rating**: When animated images are turned on, content rating can be applied to restrict the type of animated images that can be displayed in conversations.</span></span> <span data-ttu-id="764ac-203">Für die Inhaltsbewertung sind die folgenden Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="764ac-203">Available content rating options are:</span></span>

    -   <span data-ttu-id="764ac-204">„No restriction“ (Keine Einschränkung)</span><span class="sxs-lookup"><span data-stu-id="764ac-204">No restriction</span></span>
    -   <span data-ttu-id="764ac-205">Mittel (der Standardwert)</span><span class="sxs-lookup"><span data-stu-id="764ac-205">Moderate (the default value)</span></span>
    -   <span data-ttu-id="764ac-206">Streng</span><span class="sxs-lookup"><span data-stu-id="764ac-206">Strict</span></span>

-   <span data-ttu-id="764ac-207">**Enable memes that users can edit and add to conversations** (Memes aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Internetmemes verwenden, um humorvolle Beiträge zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="764ac-207">**Enable memes that users can edit and add to conversations**: When turned on, users can use internet memes to make humorous posts.</span></span>

-   <span data-ttu-id="764ac-208">**Enable stickers that users can edit and add to conversations** (Aufkleber aktivieren, die Benutzer bearbeiten und zu Unterhaltungen hinzufügen können): Wenn diese Option aktiviert ist, können Benutzer Bilder mit bearbeitbarem Text posten, um Kanalmitglieder auf etwas aufmerksam zu machen.</span><span class="sxs-lookup"><span data-stu-id="764ac-208">**Enable stickers that users can edit and add to conversations**: When turned on, users can post images with editable text to get channel members attention.</span></span>

-   <span data-ttu-id="764ac-209">**Allow owners to delete all messages** (Zulassen, dass Besitzer alle Nachrichten löschen): Wenn diese Option aktiviert ist, können Kanalbesitzer alle Nachrichten in einem Kanal entfernen.</span><span class="sxs-lookup"><span data-stu-id="764ac-209">**Allow owners to delete all messages**: When turned on, channel owners can remove all messages in a channel.</span></span>

-   <span data-ttu-id="764ac-210">**Allow users to edit their own messages** (Zulassen, dass Benutzer eigene Nachrichten bearbeiten): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="764ac-210">**Allow users to edit their own messages**: When turned on, users can edit their own messages.</span></span>

-   <span data-ttu-id="764ac-211">**Allow users to delete their own messages** (Zulassen, dass Benutzer eigene Nachrichten löschen): Wenn diese Option aktiviert ist, können Benutzer ihre eigenen Nachrichten löschen.</span><span class="sxs-lookup"><span data-stu-id="764ac-211">**Allow users to delete their own messages**: When turned on, users can delete their own messages.</span></span>

-   <span data-ttu-id="764ac-212">**Allow users to chat privately** (Zulassen, dass Benutzer privat chatten): Wenn diese Option aktiviert ist, können Benutzer an privaten Chats teilnehmen, die nicht für alle Teammitglieder, sondern nur für die Chatteilnehmer sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="764ac-212">**Allow users to chat privately**: When turned on, users can engage in private chats that are visible only to the people in the chat, instead of everyone on the team.</span></span>
>>>>>>> d35080a47f5dfe74511fef792bebd70e09a2e978


| |  |  |
|---------|---------|---------|
<<<<<<< HEAD
|![Entscheidungspunktsymbol](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="e74b8-209">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="e74b8-209">Decision Point</span></span>         |<span data-ttu-id="e74b8-210">Welche Einstellungen für Microsoft Teams wird Ihre Organisation aktivieren?</span><span class="sxs-lookup"><span data-stu-id="e74b8-210">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="e74b8-212">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e74b8-212">Next Steps</span></span>        |<span data-ttu-id="e74b8-213">Dokumentieren Sie diese Entscheidungen in [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="e74b8-213">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |
=======
|![Entscheidungspunktsymbol](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image11.png)     |<span data-ttu-id="764ac-214">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="764ac-214">Decision Point</span></span>         |<span data-ttu-id="764ac-215">Welche Einstellungen für Microsoft Teams wird Ihre Organisation aktivieren?</span><span class="sxs-lookup"><span data-stu-id="764ac-215">What settings for Microsoft Teams will your organization enable?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image12.png)     |<span data-ttu-id="764ac-217">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="764ac-217">Next Steps</span></span>        |<span data-ttu-id="764ac-218">Dokumentieren Sie diese Entscheidungen in [Zuweisen von Rollen und Berechtigungen in Microsoft Teams](assign-roles-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="764ac-218">Document these decisions in the table in [Assign roles and permissions in Microsoft Teams](assign-roles-permissions.md).</span></span>         |
>>>>>>> d35080a47f5dfe74511fef792bebd70e09a2e978

