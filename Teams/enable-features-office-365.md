---
title: Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/29/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Ihrer Office 365-Organisation Microsoft Teams-Apps einschließlich Registerkarten, Connectors, Bots oder einer Kombination aus diesen drei Komponenten aktivieren bzw. deaktivieren.
localization_priority: Priority
ms.custom:
- NewAdminCenter_Update
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a36c0a23076c5aa172824fe85103c57a8494dbf
ms.sourcegitcommit: a378848c5aeb8e2b25300024318de792454d905b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/28/2018
ms.locfileid: "27458478"
---
# <a name="manage-microsoft-teams-features-in-your-office-365-organization"></a><span data-ttu-id="f5227-103">Verwalten von Microsoft Teams-Funktionen in Ihrer Office 365-Organisation</span><span class="sxs-lookup"><span data-stu-id="f5227-103">Manage Microsoft Teams features in your Office 365 organization</span></span>

<span data-ttu-id="f5227-p101">Alle Teams-Einstellungen werden in Kürze zum neuen Admin Center für Microsoft Teams und Skype for Business migriert. Apps werden als einzige Teams-Funktion im Office 365 Admin Center verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f5227-p101">All Teams settings will soon be migrated to the new Microsoft Teams & Skype for Business Admin Center. The only Teams feature that is managed in the Office 365 admin center is Apps.</span></span> 

<span data-ttu-id="f5227-106">Wenn nichts anderes angegeben ist, lautet der Standardwert für die jeweilige Option **Ein**.</span><span class="sxs-lookup"><span data-stu-id="f5227-106">Unless otherwise noted, the default value for an option is **On**.</span></span>

## <a name="office-365-tenant-wide-settings"></a><span data-ttu-id="f5227-107">Mandantenweite Einstellungen in Office 365</span><span class="sxs-lookup"><span data-stu-id="f5227-107">Office 365 tenant-wide settings</span></span> 

<span data-ttu-id="f5227-108">Unter **Mandantenweite Einstellungen** können Sie Apps aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5227-108">In **Tenant-wide settings**, you can turn on or turn off Apps.</span></span>

<span data-ttu-id="f5227-p102">Zum Bearbeiten der **mandantenweiten Einstellungen** für Microsoft Teams wechseln Sie zum Admin Center für Microsoft Teams und Skype for Business. Wählen Sie **Legacy portal** (Legacyportal) aus. Wählen Sie **Einstellungen** > **Dienste und Add-Ins** > **Microsoft Teams** aus. Wenn Sie als Office 365-Administrator angemeldet sind, können Sie diesen Link verwenden:</span><span class="sxs-lookup"><span data-stu-id="f5227-p102">To edit **Tenant-wide settings** for Teams, go to the Microsoft Teams & Skype for Business Admin Center, and select **Legacy portal**. Choose **Settings** > **Services & add-ins** > **Microsoft Teams**. If you're signed in as an Office 365 admin, this link should take you there:</span></span> 
>  
> https://portal.office.com/adminportal/home#/Settings/ServicesAndAddIns  

### <a name="apps"></a><span data-ttu-id="f5227-112">Apps</span><span class="sxs-lookup"><span data-stu-id="f5227-112">Apps</span></span>

<span data-ttu-id="f5227-p103">Apps sind Registerkarten, Connectors und Bots bzw. eine beliebige Kombination dieser drei Elemente, die von einem Drittanbieterdienst bereitgestellt werden. Im Office 365 Admin Center können Microsoft Teams-Administratorrichtlinien konfiguriert werden, um zu steuern, welche externen Drittanbieter-Apps zulässig sind. Mit diesen Richtlinien können Sie festlegen, welche Apps zulässig bzw. nicht zulässig sind, das Verhalten neuer externer Apps definieren und angeben, ob das Querladen von Apps zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="f5227-p103">Apps are tabs, connectors, bots, or any combination of these three, provided by a third-party service. There are Teams admin policies that can be configured in the Office 365 admin center to control which external third-party apps are allowed. These policies let you specify which apps are allowed and disallowed, new external app behavior, and whether side-loading apps is allowed.</span></span> 

<span data-ttu-id="f5227-116">Unter **Apps** können Sie die folgenden Einstellungen für Ihre Organisation konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f5227-116">Under **Apps**, you can configure the following settings for your organization:</span></span> 

![Screenshot des Abschnitts „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.png)

- <span data-ttu-id="f5227-118">**Allow external apps in Microsoft Teams** (Externe Apps in Microsoft Teams zulassen): Wenn diese Option aktiviert ist, können Benutzer Registerkarten und Bots hinzufügen, die für den Office 365-Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f5227-118">**Allow external apps in Microsoft Teams**: When this switch is turned on, users can add tabs and bots that are available to the Office 365 tenant.</span></span> 
 
    ![Screenshot des Steuerelements zum Zulassen externer Apps im Abschnitt „Apps“](media/Enable_Microsoft_Teams_features_in_your_Office_365_organization_image6.2.png)

- <span data-ttu-id="f5227-p104">**Enable new external apps by default** (Neue externe Apps standardmäßig aktivieren): Wenn diese Option aktiviert ist, können Benutzer neue Apps aktivieren, sobald diese zum Microsoft Teams-App-Katalog hinzugefügt werden. Deaktivieren Sie diese Option, wenn Sie neue Apps steuern möchten. Wenn Sie die Option deaktiviert haben, müssen Sie natürlich daran denken, neue Apps regelmäßig zu überprüfen, damit Ihrer Organisation keine tollen neuen Apps entgehen.</span><span class="sxs-lookup"><span data-stu-id="f5227-p104">**Enable new external apps by default**: When this switch is turned on, users can activate new apps as soon as they're added to the Teams app catalog. Turn off this switch if you want to control new apps. Of course, if you turn it off, you have to remember to review new apps periodically so your organization doesn't miss out on cool new apps.</span></span> 

- <span data-ttu-id="f5227-123">**Querladen externer Apps zulassen**: Wenn diese Option aktiviert ist, können Benutzer benutzerdefinierte Bots und Registerkarten installieren und aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5227-123">**Allow sideloading of external apps**: When this switch is turned on, users can install and turn on custom bots and tabs.</span></span> 

<span data-ttu-id="f5227-124">Weitere Informationen finden Sie unter [Administratoreinstellungen für Apps in Microsoft Teams](admin-settings.md).</span><span class="sxs-lookup"><span data-stu-id="f5227-124">To learn more, read [Admin settings for apps in Teams](admin-settings.md).</span></span> 

## <a name="teams-org-wide-settings"></a><span data-ttu-id="f5227-125">Organisationsweite Einstellungen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f5227-125">Teams org-wide settings</span></span>

<span data-ttu-id="f5227-126">Sie können organisationsweite Benutzereinstellungen im Admin Center für Microsoft Teams und Skype for Business steuern.</span><span class="sxs-lookup"><span data-stu-id="f5227-126">You can control organization-wide user settings in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="f5227-127">Zum Bearbeiten der organisationsweiten Einstellungen wechseln Sie zum Admin Center für Microsoft Teams und Skype for Business. Wählen Sie **Org-wide settings** (Organisationsweite Einstellungen) aus.</span><span class="sxs-lookup"><span data-stu-id="f5227-127">To edit org-wide settings, go to the Microsoft Skype for Business Admin Center, and then select **Org-wide settings**.</span></span> <span data-ttu-id="f5227-128">Sie können die folgenden Einstellungen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f5227-128">You can configure the following settings.</span></span>

### <a name="external-access"></a><span data-ttu-id="f5227-129">Externer Zugriff</span><span class="sxs-lookup"><span data-stu-id="f5227-129">External access</span></span>

<span data-ttu-id="f5227-p106">**Externer Zugriff** ermöglicht Ihren Microsoft Teams- und Skype for Business-Benutzern die Kommunikation mit Benutzern außerhalb der Organisation. Um den externen Zugriff zu konfigurieren, wechseln Sie zu [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md) (Microsoft Teams-Benutzern das Chatten und Kommunizieren mit Benutzern in einer anderen Microsoft Teams-Organisation ermöglichen).</span><span class="sxs-lookup"><span data-stu-id="f5227-p106">**External access** lets your Teams and Skype for Business users communicate with users who are outside of your organization. To configure external access, go to [Let your Teams users chat and communicate with users in another Teams organization](let-your-teams-users-communicate-with-other-people.md).</span></span>

### <a name="guest-access"></a><span data-ttu-id="f5227-132">Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="f5227-132">Guest access</span></span>

<span data-ttu-id="f5227-p107">**Gastzugriff** in Microsoft Teams ermöglicht Teams in Ihrer Organisation, mit Personen außerhalb der Organisation zusammenzuarbeiten, indem ihnen Zugriff auf Teams und Kanäle gewährt wird. Alle Benutzer, die über ein E-Mail-Konto für Geschäftsbenutzer oder Heimanwender (z. B. Outlook, Gmail usw.) verfügen, können als Gäste in Microsoft Teams teilnehmen und erhalten Vollzugriff auf Chats, Besprechungen und Dateien des Teams. Weitere Informationen finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="f5227-p107">**Guest access** in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see [Guest access in Microsoft Teams](guest-access.md).</span></span>

### <a name="teams-settings"></a><span data-ttu-id="f5227-136">„Teams settings“ (Microsoft Teams-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="f5227-136">Teams settings</span></span>

<span data-ttu-id="f5227-137">Unter **Teams settings** (Microsoft Teams-Einstellungen) können Sie E-Mail-Integration, Cloudspeicheroptionen, Interoperabilität mit Skype for Business und Geräte einrichten.</span><span class="sxs-lookup"><span data-stu-id="f5227-137">In **Teams settings**, you can set up email integration, cloud storage options, Skype for Business interoperability, and devices.</span></span>

#### <a name="email-integration"></a><span data-ttu-id="f5227-138">E-Mail-Integration</span><span class="sxs-lookup"><span data-stu-id="f5227-138">Email integration</span></span>

<span data-ttu-id="f5227-p108">Aktivieren Sie diese Funktion, damit Benutzer über die Kanal-E-Mail-Adresse eine E-Mail an einen Kanal in Microsoft Teams senden können. Benutzer können dies für jeden Kanal tun, der zu einem Team gehört, dessen Besitzer sie sind. Außerdem können Benutzer E-Mails an jeden Kanal in einem Team senden, in dem das Hinzufügen von Connectors für Teammitglieder aktiviert ist. Stellen Sie zum Aktivieren der E-Mail-Integration sicher, dass für **Allow users to send emails to a channel email address** (Zulassen, dass Benutzer E-Mails an eine Kanal-E-Mail-Adresse senden) die Option **Ein** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f5227-p108">Turn on this feature so users can send email to a channel in Teams, using the channel email address. Users can do this for any channel belonging to a team they own. Users can also send emails to any channel in a team that has adding connectors turned on for team members. To turn on email integration, make sure that **Allow users to send emails to a channel email address** is **On**.</span></span> 

#### <a name="files"></a><span data-ttu-id="f5227-143">Dateien</span><span class="sxs-lookup"><span data-stu-id="f5227-143">Files</span></span>

<span data-ttu-id="f5227-144">Hier können Sie die Dateifreigabe und Optionen für Cloudspeicherdateien aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5227-144">Here you can turn on or turn off file sharing and cloud file storage options.</span></span> 

<span data-ttu-id="f5227-p109">Benutzer können Dateien aus Cloudspeicherdiensten in Microsoft Teams-Kanäle und -Chats hochladen und dort freigeben. Zu den Cloudspeicheroptionen in Microsoft Teams gehören zurzeit ShareFile, Dropbox, Box und Google Drive. Aktivieren Sie die Option für die Cloudspeicheranbieter, die Ihre Organisation verwenden möchte.</span><span class="sxs-lookup"><span data-stu-id="f5227-p109">Users can upload and share files from cloud storage services in Teams channels and chats. Cloud storage options in Teams currently include ShareFile, Dropbox, Box, and Google Drive. Turn on the switch for the cloud storage providers that your organization wants to use.</span></span>

#### <a name="organization"></a><span data-ttu-id="f5227-148">Organisation</span><span class="sxs-lookup"><span data-stu-id="f5227-148">Organization</span></span>

<span data-ttu-id="f5227-p110">Hier können Sie die Registerkarte **Organisation** aktivieren, auf der das detaillierte Organigramm für die Organisation des Benutzers angezeigt wird. Weitere Informationen finden Sie unter [Verwenden der Registerkarte „Organisation“ in Microsoft Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span><span class="sxs-lookup"><span data-stu-id="f5227-p110">Here you can turn on the **Organization** tab, which shows the detailed organizational chart for the user’s organization. For more information, see [Use the organization tab in Teams](https://support.office.com/article/use-the-organization-tab-in-teams-ff02568b-290a-46d6-ae7a-cda22f723894).</span></span>

#### <a name="skype-for-business-interop"></a><span data-ttu-id="f5227-151">„Skype for Business interop“ (Interoperabilität mit Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="f5227-151">Skype for Business interop</span></span>

<span data-ttu-id="f5227-p111">Verwenden Sie diese Einstellung, um Microsoft Teams-Benutzern das Chatten mit Skype for Business-Benutzern zu ermöglichen. Detaillierte Informationen zur Interoperabilität zwischen Microsoft Teams und Skype for Business finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="f5227-p111">Use this setting to let Teams users chat with Skype for Business users. For detailed information about interoperability between Teams and Skype for Business, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="devices"></a><span data-ttu-id="f5227-154">Geräte</span><span class="sxs-lookup"><span data-stu-id="f5227-154">Devices</span></span>

<span data-ttu-id="f5227-p112">Diese Einstellungen steuern das Verhalten von Ressourcenkonten für Surface Hub-Geräte, die an Microsoft Teams-Besprechungen teilnehmen. Verwenden Sie diese Einstellungen, um Authentifizierungsanforderungen zu konfigurieren, festzulegen, dass eine Inhalts-PIN erforderlich ist, und das Senden von Nachrichten durch Surface Hub-Ressourcenkonten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5227-p112">These settings control resource account behavior for Surface Hub devices attending Microsoft Teams meetings. Use these settings to configure authentication requirements, require a content PIN, and turn on Surface Hub resource accounts to send messages.</span></span>

- <span data-ttu-id="f5227-157">**Require a secondary form of authentication to access meeting content** (Für den Zugriff auf Besprechungsinhalte ist eine sekundäre Authentifizierungsmethode erforderlich): Wählen Sie die Zugriffsebene aus, über die Benutzer verfügen, wenn sie die Inhalts-PIN eingeben.</span><span class="sxs-lookup"><span data-stu-id="f5227-157">**Require a secondary form of authentication to access meeting content** – Select the level of access that users have when they enter the content PIN.</span></span>
- <span data-ttu-id="f5227-p113">**Set content PIN** (Inhalts-PIN festlegen): Legen Sie fest, dass Benutzer diese PIN eingeben müssen, damit der nicht autorisierte Zugriff auf Dokumente nicht möglich ist. Damit verhindern Sie, dass nicht autorisierte Benutzer an bevorstehenden Besprechungen teilnehmen und Anlagen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f5227-p113">**Set content PIN** – Require users to enter this PIN to prevent unauthorized access to documents. This prevents an unauthorized user from joining upcoming meetings and browsing attachments.</span></span>
- <span data-ttu-id="f5227-160">**Resource accounts can send messages** (Ressourcenkonten können Nachrichten senden): Legen Sie diese Einstellung auf **Ein** fest, um das Senden von Nachrichten über das Surface Hub-Ressourcenkonto zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="f5227-160">**Resource accounts can send messages** – Turn this setting **On** to allow messages to be sent from the Surface Hub resource account.</span></span>

#### <a name="search"></a><span data-ttu-id="f5227-161">Suche</span><span class="sxs-lookup"><span data-stu-id="f5227-161">Search</span></span>

<span data-ttu-id="f5227-p114">Die Verzeichnissuche in Microsoft Teams verwendet Exchange-Adressbuchrichtlinien, damit Organisationen virtuelle Grenzen erstellen können. Diese steuern, wie Benutzer andere Benutzer in der Organisation suchen und mit diesen kommunizieren können. Eine bereichsbezogene Verzeichnissuche eignet sich zum Beispiel in diesen Situationen:</span><span class="sxs-lookup"><span data-stu-id="f5227-p114">Microsoft Teams scoped directory search uses Exchange address book policy (APB) to allow organizations to create virtual boundaries that control how users can find and communicate with other users in their organization. You might want to use a scoped directory search in situations like these:</span></span>

- <span data-ttu-id="f5227-164">Der Mandant Ihrer Organisation enthält mehrere Unternehmen, die voneinander getrennt sein sollen.</span><span class="sxs-lookup"><span data-stu-id="f5227-164">Your organization has multiple companies within its tenant that you want to keep separate.</span></span> 
- <span data-ttu-id="f5227-165">Ihre Bildungseinrichtung möchte Chats zwischen dem Lehrpersonal und den Kursteilnehmern begrenzen.</span><span class="sxs-lookup"><span data-stu-id="f5227-165">Your school wants to limit chats between faculty and students.</span></span> 

<span data-ttu-id="f5227-166">Ändern Sie diese Einstellung in **Ein**, um die bereichsbezogene Verzeichnissuche zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5227-166">Switch this setting **On** to turn on scoped directory searches.</span></span>

### <a name="teams-upgrade"></a><span data-ttu-id="f5227-167">„Teams upgrade“ (Microsoft Teams-Upgrade)</span><span class="sxs-lookup"><span data-stu-id="f5227-167">Teams upgrade</span></span>

<span data-ttu-id="f5227-168">Mit diesen Einstellungen können Sie konfigurieren, wie die Benutzer von Skype for Business auf Microsoft Teams aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5227-168">You can use these settings to configure how your users will be upgraded from Skype for Business to Microsoft Teams.</span></span> 

#### <a name="coexistence-mode"></a><span data-ttu-id="f5227-169">Koexistenzmodus</span><span class="sxs-lookup"><span data-stu-id="f5227-169">Coexistence mode</span></span>
<span data-ttu-id="f5227-p115">Sie können einen Koexistenzmodus angeben: **Teams only** (Nur Microsoft Teams), **Inseln** (Microsoft Teams und Skype for Business werden zusammen verwendet) oder **Skype for Business only** (Nur Skype for Business). Der ausgewählte Koexistenzmodus bestimmt, wie eingehende Anrufe und Chats weitergeleitet werden und welche App die Benutzer zum Einleiten von Chats und Anrufen oder zum Planen von Besprechungen verwenden. Detaillierte Informationen zu Koexistenzmodi finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span><span class="sxs-lookup"><span data-stu-id="f5227-p115">You can specify a coexistence mode: **Teams only**, **Islands** (Teams and Skype for Business will coexist), or **Skype for Business only**. The Coexistence mode you choose determines the routing of incoming calls and chats and the app that is used by the user to initiate chats and calls or to schedule meetings. For more information about coexistence modes, go to [Understand Microsoft Teams and Skype for Business coexistence and interoperability](teams-and-skypeforbusiness-coexistence-and-interoperability.md).</span></span>

#### <a name="app-preferences"></a><span data-ttu-id="f5227-173">„App preferences“ (App-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="f5227-173">App preferences</span></span>

<span data-ttu-id="f5227-p116">Hier können Sie die App auswählen, die Benutzer für die Teilnahme an Skype for Business-Besprechungen verwenden (Skype for Business oder die [Skype-Besprechungs-App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). Diese Einstellung ist nicht von der Einstellung für den Koexistenzmodus abhängig.</span><span class="sxs-lookup"><span data-stu-id="f5227-p116">Here you can choose the app that users will use to join Skype for Business meetings (Skype for Business or the [Skype Meetings App](https://support.office.com/en-us/article/What-is-Skype-Meetings-App-Skype-for-Business-Web-App-1FF3D412-718A-4982-8FF2-A4992608CDB5)). This setting isn't dependent on the coexistence mode setting.</span></span>

## <a name="how-can-i-tell-which-features-are-available"></a><span data-ttu-id="f5227-176">Woran erkenne ich, welche Funktionen verfügbar sind?</span><span class="sxs-lookup"><span data-stu-id="f5227-176">How can I tell which features are available?</span></span>

<span data-ttu-id="f5227-p117">In der [Office 365-Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) finden Sie Informationen zu neuen Microsoft Teams-Funktionen. Weitere Informationen zu neuen und geplanten Funktionen finden Sie in Microsoft Teams auf der Seite [Neuigkeiten](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) und im [Microsoft Teams-Blog der Tech Community](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531).</span><span class="sxs-lookup"><span data-stu-id="f5227-p117">See the [Office 365 Roadmap](https://www.microsoft.com/en-us/microsoft-365/roadmap?rtc=1&filters=Microsoft%20Teams) for information about new Teams features. For more information about new and upcoming features, see the Teams [What's New](https://support.office.com/en-us/article/what-s-new-in-microsoft-teams-d7092a6d-c896-424c-b362-a472d5f105de?ui=en-US&rs=en-US&ad=US) page and the [Tech Community Microsoft Teams blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/What-s-new-in-Teams-Microsoft-Ignite-Edition/ba-p/252531) for Teams.</span></span> 

## <a name="more-information"></a><span data-ttu-id="f5227-179">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5227-179">More information</span></span>

<span data-ttu-id="f5227-180">Weitere Informationen dazu, welche Rollen Administratorfunktionen ausführen können, finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Microsoft Teams](using-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f5227-180">For information about which roles can perform admin functions, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span>
