---
title: Buchungen-APP und virtuelle Besuche in Microsoft Teams
author: mattpennathe3rd
ms.author: v-mapenn
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
ms.reviewer: ''
description: Microsoft Teams und virtuelle Besuche mit der App "Buchungen"
ms.openlocfilehash: b00a42ab7d0b590d706b8e3218f24d13b945b731
ms.sourcegitcommit: ebdad71a8d393466e33a2fdc8606d882a6007588
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280287"
---
# <a name="bookings-app-and-virtual-visits-in-microsoft-teams"></a><span data-ttu-id="6fad8-103">Buchungen-APP und virtuelle Besuche in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6fad8-103">Bookings app and virtual visits in Microsoft Teams</span></span>

<span data-ttu-id="6fad8-104">Die app "Buchungen" in Microsoft Teams bietet eine einfache Möglichkeit zum Planen von persönlichen und virtuellen Terminen wie Gesundheits Besuche, Finanzberatungen, Interviews, Kundendienst, Unterrichtsstunden und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="6fad8-104">The Bookings app in Microsoft Teams offers a simple way to schedule in-person and virtual appointments, such as healthcare visits, financial consultations, interviews, customer support, education office hours, and much more.</span></span>

<span data-ttu-id="6fad8-105">Planer können mehrere Abteilungs-und Personal Kalender sowie die Kommunikation mit internen und externen Teilnehmern aus einer einzigen Erfahrung verwalten.</span><span class="sxs-lookup"><span data-stu-id="6fad8-105">Schedulers can manage multiple department and staff calendars, as well as communications with internal and external attendees, from a single experience.</span></span> <span data-ttu-id="6fad8-106">Die virtuellen Termine selbst werden über Microsoft Teams-Besprechungen abgehalten, die robuste Videokonferenzfunktionen bieten.</span><span class="sxs-lookup"><span data-stu-id="6fad8-106">The virtual appointments themselves are held via Microsoft Teams Meetings, which offers robust videoconferencing capabilities.</span></span>

> [!NOTE]
> <span data-ttu-id="6fad8-107">Nur Planer müssen die app "Buchungen" in Teams installieren.</span><span class="sxs-lookup"><span data-stu-id="6fad8-107">Only schedulers need to have the Bookings app installed in Teams.</span></span> <span data-ttu-id="6fad8-108">Mitarbeiter, die an virtuellen Terminen teilnehmen, benötigen die APP nicht.</span><span class="sxs-lookup"><span data-stu-id="6fad8-108">Staff conducting or participating in virtual appointments do not need the app.</span></span> <span data-ttu-id="6fad8-109">Sie können einfach an Terminen aus Ihrem Outlook-oder Teams-Kalender oder über einen Link in ihrer Buchungs Bestätigungs-e-Mail teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-109">They can simply join appointments from their Outlook or Teams calendar or from a link in their booking confirmation email.</span></span>

## <a name="prerequisites-for-using-the-bookings-app-in-teams"></a><span data-ttu-id="6fad8-110">Voraussetzungen für die Verwendung der App "Buchungen" in Teams</span><span class="sxs-lookup"><span data-stu-id="6fad8-110">Prerequisites for using the Bookings app in Teams</span></span>

- <span data-ttu-id="6fad8-111">Das Exchange-Postfach muss sich in Exchange Online befinden.</span><span class="sxs-lookup"><span data-stu-id="6fad8-111">The Exchange mailbox must be in Exchange Online.</span></span> <span data-ttu-id="6fad8-112">Lokale Exchange Server-Postfächer werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fad8-112">On-premises Exchange Server mailboxes are not supported.</span></span>

- <span data-ttu-id="6fad8-113">Microsoft-Buchungen müssen für die Organisation aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="6fad8-113">Microsoft Bookings must be turned on for the organization.</span></span>

- <span data-ttu-id="6fad8-114">Benutzer müssen über eine entsprechende Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-114">Users must have an appropriate license.</span></span> <span data-ttu-id="6fad8-115">Office 365 a3, A5, E3 und E5 sowie Microsoft 365 Business Standard, a3, A5, E3 und E5 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fad8-115">Office 365 A3, A5, E3, and E5, as well as Microsoft 365 Business Standard, A3, A5, E3, and E5 are supported.</span></span>

- <span data-ttu-id="6fad8-116">Alle Benutzer der App "Buchungen" und alle an Besprechungen teilnehmenden Mitarbeiter müssen über eine Lizenz verfügen, die die Terminplanung für Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fad8-116">All users of the Bookings app and all staff participating in meetings must have a license that supports Teams Meeting scheduling.</span></span>

- <span data-ttu-id="6fad8-117">Ihre Systeme müssen alle [Voraussetzungen für Software und Browser](hardware-requirements-for-the-teams-app.md)erfüllen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-117">Your systems must meet all [Software and browser prerequisites](hardware-requirements-for-the-teams-app.md).</span></span>

## <a name="availability-of-bookings-in-teams"></a><span data-ttu-id="6fad8-118">Verfügbarkeit von Buchungen in Teams</span><span class="sxs-lookup"><span data-stu-id="6fad8-118">Availability of Bookings in Teams</span></span>

<span data-ttu-id="6fad8-119">Die Microsoft-Buchungs-App für Teams steht auf dem Desktop und im Web zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6fad8-119">Microsoft Bookings App for Teams is available on the desktop and web.</span></span> <span data-ttu-id="6fad8-120">Sie finden Sie unter [apps in Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) und unter **Verwalten von apps** innerhalb des Admin Centers von Teams.</span><span class="sxs-lookup"><span data-stu-id="6fad8-120">It can be found under [Apps within Microsoft Teams](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=store-copy-link) and under **Manage Apps** within Teams Admin Center.</span></span>

### <a name="control-access-to-bookings-within-your-organization"></a><span data-ttu-id="6fad8-121">Steuern des Zugriffs auf Buchungen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="6fad8-121">Control access to Bookings within your organization</span></span>

<span data-ttu-id="6fad8-122">Es gibt mehrere Möglichkeiten, zu steuern, wer Zugriff auf die app "Buchungen" hat und welche Features für die app verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="6fad8-122">There are several ways to control who has access to the Bookings app and to specific features of the app.</span></span> <span data-ttu-id="6fad8-123">Informationen zum Aktivieren oder Deaktivieren von Microsoft-Buchungen im Microsoft 365 Admin Center sowie zum Erstellen einer APP-Richtlinie für Buchungen, mit der ausgewählte Benutzer Buchungen für Kalender erstellen können, finden Sie unter [Abrufen des Zugriffs auf Microsoft-Buchungen](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span><span class="sxs-lookup"><span data-stu-id="6fad8-123">To learn how to turn Microsoft Bookings on or off in the Microsoft 365 admin center, as well as how to create a Bookings app policy to allow selected users to create Bookings calendars, see [Get access to Microsoft Bookings](https://support.microsoft.com/en-us/office/get-access-to-microsoft-bookings-5382dc07-aaa5-45c9-8767-502333b214ce).</span></span> <span data-ttu-id="6fad8-124">Sie können auch erfahren, wie Sie [eine Teams-App-Richtlinie erstellen, um die Buchungen-App für ausgewählte Benutzer zu anheften](teams-app-setup-policies.md).</span><span class="sxs-lookup"><span data-stu-id="6fad8-124">You can also learn how to [Create a Teams app policy to pin the Bookings app for select users](teams-app-setup-policies.md).</span></span>

## <a name="recommended-meeting-policy-settings"></a><span data-ttu-id="6fad8-125">Empfohlene Einstellungen für Besprechungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="6fad8-125">Recommended Meeting Policy Settings</span></span>

<span data-ttu-id="6fad8-126">Erstellen Sie eine Personal Besprechungsrichtlinie, damit **alle Personen in Ihrer Organisation**automatisch zugelassen werden, um die beste Benutzerfreundlichkeit für Buchungen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-126">To enable the best experience for Bookings, create a staff meeting policy to automatically admit **Everyone in your organization**.</span></span> <span data-ttu-id="6fad8-127">Auf diese Weise können die Mitarbeiter automatisch an dem Termin teilnehmen und die Lobby-Erfahrung für externe Teilnehmer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6fad8-127">This will allow staff to join the appointment automatically and enable lobby experience for external attendees.</span></span> <span data-ttu-id="6fad8-128">Weitere Informationen finden Sie [unter Automatisches zulassen von Personen für Besprechungen](meeting-policies-in-teams.md#automatically-admit-people).</span><span class="sxs-lookup"><span data-stu-id="6fad8-128">You can learn more about [automatically admitting people to meetings](meeting-policies-in-teams.md#automatically-admit-people).</span></span>

### <a name="optional-staff-approvals-setting"></a><span data-ttu-id="6fad8-129">Optionale Einstellung für Mitarbeiter Genehmigungen</span><span class="sxs-lookup"><span data-stu-id="6fad8-129">Optional staff approvals setting</span></span>

<span data-ttu-id="6fad8-130">Als zusätzliche Privatsphäre-Einstellung können Sie festlegen, dass die Mitarbeiter sich anmelden müssen, bevor Ihre Terminplan Verfügbarkeitsinformationen durch Buchungen freigegeben werden und bevor Sie für einen Termin gebucht werden können.</span><span class="sxs-lookup"><span data-stu-id="6fad8-130">As an extra privacy setting, you can choose to require staff to opt in before their schedule availability information is shared through Bookings and before they can be booked for an appointment.</span></span>  

<span data-ttu-id="6fad8-131">Wenn Sie diese Einstellung aktivieren möchten, wechseln Sie zu den Einstellungen für **Microsoft 365 Admin Center** \> **Settings** \> **Settings**, und wählen Sie dann **Buchungen**aus.</span><span class="sxs-lookup"><span data-stu-id="6fad8-131">To enable this setting, go to **Microsoft 365 admin center** \> **Settings** \> **Settings**, then select **Bookings**.</span></span>

<span data-ttu-id="6fad8-132">Wenn diese Einstellung aktiviert ist, erhält das Personal eine e-Mail, in der Sie aufgefordert werden, die Mitgliedschaft in einem Buchungskalender zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-132">With this setting turned on, staff will receive an email in which they are asked to approve membership to a booking calendar.</span></span>  

<span data-ttu-id="6fad8-133">Dieses Feature wird nach und nach weltweit für Microsoft 365-und Office 365-Kunden eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6fad8-133">This feature is gradually being rolled out worldwide to Microsoft 365 and Office 365 customers.</span></span> <span data-ttu-id="6fad8-134">Wenn in Ihrer Umgebung noch keine Optionen zur Verfügung stehen, schauen Sie bald wieder vorbei.</span><span class="sxs-lookup"><span data-stu-id="6fad8-134">If all options are not yet available in your environment, check back soon.</span></span>

## <a name="changing-your-default-domain-when-setting-up-bookings-mailboxes"></a><span data-ttu-id="6fad8-135">Ändern ihrer Standarddomäne beim Einrichten von Buchungs Postfächern</span><span class="sxs-lookup"><span data-stu-id="6fad8-135">Changing your default domain when setting up Bookings mailboxes</span></span>

<span data-ttu-id="6fad8-136">Beim Einrichten eines Postfachs für Buchungen wird die standardmäßige e-Mail-Domäne Ihrer Microsoft 365-oder Office 365-Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fad8-136">When setting up a Bookings mailbox, the default email domain of your Microsoft 365 or Office 365 organization is used.</span></span> <span data-ttu-id="6fad8-137">Dies kann jedoch zu Problemen beim Senden von Besprechungseinladungen an externe Empfänger führen. Ihre Einladung wird möglicherweise als "Spam" gekennzeichnet und in den Junk-Ordner des Empfängers verschoben, sodass der Empfänger Ihre Einladung möglicherweise nie sehen kann.</span><span class="sxs-lookup"><span data-stu-id="6fad8-137">However, this can cause problems when sending meeting invites to external recipients; your invite might be flagged as spam and moved to the recipient’s junk folder, so the recipient might never see your invite.</span></span>

<span data-ttu-id="6fad8-138">Wir empfehlen, dass Sie vor dem Erstellen des Postfachs für Buchungen die Standarddomäne ändern.</span><span class="sxs-lookup"><span data-stu-id="6fad8-138">We recommend that you change the default domain prior to creating your Bookings mailbox.</span></span> <span data-ttu-id="6fad8-139">Informationen dazu finden Sie in den [FAQ zu Domains](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="6fad8-139">For information on how to do this, see the [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq#how-do-i-set-or-change-the-default-domain-in-office-365).</span></span>

<span data-ttu-id="6fad8-140">Wenn Sie die Standarddomäne ändern müssen, nachdem das Postfach für Buchungen bereits erstellt wurde, können Sie dies mit PowerShell tun:</span><span class="sxs-lookup"><span data-stu-id="6fad8-140">If you need to change the default domain after your Bookings mailbox has already been created, you can do so with PowerShell:</span></span>

```PowerShell
Set-Mailbox -identity business@domain.onmicrosoft.com -WindowsEmailAddress business@domain.com -EmailAddresses business@domain.com
```

<span data-ttu-id="6fad8-141">Weitere Informationen finden Sie in der PowerShell-Dokumentation für das Cmdlet " [Satz-Postfach](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) ".</span><span class="sxs-lookup"><span data-stu-id="6fad8-141">For more information, see the PowerShell documentation for the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="6fad8-142">Wenn Sie eine Exchange-Hybrid Konfiguration verwenden, empfiehlt es sich, den Nachrichtenfluss zwischen lokalen Exchange und Exchange Online beim Ändern der Standarddomäne gründlich zu testen.</span><span class="sxs-lookup"><span data-stu-id="6fad8-142">If you are using an Exchange hybrid configuration, we recommend that you thoroughly test mail flow between on-premises Exchange and Exchange Online when changing the default domain.</span></span>

## <a name="sending-feedback"></a><span data-ttu-id="6fad8-143">Senden von Feedback</span><span class="sxs-lookup"><span data-stu-id="6fad8-143">Sending feedback</span></span>

<span data-ttu-id="6fad8-144">Wir freuen uns über Ihr Feedback zu:</span><span class="sxs-lookup"><span data-stu-id="6fad8-144">We welcome your feedback on:</span></span>

  - <span data-ttu-id="6fad8-145">Benutzererfahrung oder einfache Bedienung</span><span class="sxs-lookup"><span data-stu-id="6fad8-145">User experience or ease of use</span></span>
  - <span data-ttu-id="6fad8-146">Funktionslücken oder fehlende Funktionalität</span><span class="sxs-lookup"><span data-stu-id="6fad8-146">Feature gaps or missing functionality</span></span>
  - <span data-ttu-id="6fad8-147">Bugs oder Probleme</span><span class="sxs-lookup"><span data-stu-id="6fad8-147">Bugs or issues</span></span>
  
<span data-ttu-id="6fad8-148">Um Feedback zu senden, klicken Sie auf die Schaltfläche " **Hilfe** " am unteren Rand der linken Navigationsleiste von Teams, und klicken Sie dann auf **Problem melden** für **alle** Probleme.</span><span class="sxs-lookup"><span data-stu-id="6fad8-148">To send feedback, click the **Help** button near the bottom of the Teams left navigation bar, then click **Report a Problem** for **ALL** issues.</span></span> <span data-ttu-id="6fad8-149">Bitte beachten Sie zu Beginn Ihres Feedback-Berichts, dass Sie Feedback zu "Buchungen" senden, damit wir Buchungs Probleme einfach erkennen können.</span><span class="sxs-lookup"><span data-stu-id="6fad8-149">Please note at the beginning of your feedback report that you are sending feedback about "Bookings" so we can easily identify Bookings issues.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fad8-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6fad8-150">Related topics</span></span>

[<span data-ttu-id="6fad8-151">Buchungsdokumentation für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="6fad8-151">Bookings documentation for end users</span></span>](https://support.office.com/en-us/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?ui=en-US&rs=en-US&ad=US#PickTab=Bookings)
