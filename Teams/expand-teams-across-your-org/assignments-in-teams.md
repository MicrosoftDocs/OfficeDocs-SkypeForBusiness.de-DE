---
title: Zuweisungen für Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: Hier erfahren Sie, wie Sie Aufgaben im Microsoft Teams Admin Center in Teams für Bildung verwalten.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3a0bf0dd0141679dc89ed1d5ecc0cfc542854c8
ms.sourcegitcommit: 3eb5820b279fc904f34ac4259deeb419e02d832a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561051"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="59fb3-103">Aufgaben in Teams für Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="59fb3-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="59fb3-104">Aufgaben sind Aufgaben oder Arbeitseinheiten, die einem Kursteilnehmer oder Teammitglied in einer Klasse im Rahmen ihrer Studie zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="59fb3-104">Assignments are tasks or units of work assigned to a student or team member in a class as part of their study.</span></span> <span data-ttu-id="59fb3-105">Sie können Aufgaben in Ihrer Team Klasse erstellen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-105">You can create assignments within your Teams class.</span></span>

<span data-ttu-id="59fb3-106">[Weitere Informationen zu Aufgaben](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="59fb3-106">[Learn more about Assignments](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="59fb3-107">Details zu Teams-Aufgaben auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="59fb3-107">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="59fb3-108">Aufgaben im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="59fb3-108">Assignments in the Microsoft Teams admin center</span></span>

<span data-ttu-id="59fb3-109">Mit den Administratoreinstellungen im Microsoft Teams Admin Center können Sie die folgenden Features aktivieren oder deaktivieren, damit Sie für Schüler und Lehrer in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-109">With the admin settings in Microsoft Teams admin center, you can turn the following features on or off to be available for students and teachers within your organization.</span></span> <span data-ttu-id="59fb3-110">Die folgenden Einstellungen beziehen sich auf Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="59fb3-110">The following are settings related to Assignments:</span></span>

<span data-ttu-id="59fb3-111"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="59fb3-111"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="59fb3-112">Wöchentlicher Guardian-e-Mail-Digest</span><span class="sxs-lookup"><span data-stu-id="59fb3-112">Weekly guardian email digest</span></span>

<span data-ttu-id="59fb3-113">Die e-Mail-Nachrichten enthalten Informationen zu den Aufgaben aus der vorherigen Woche und für die kommende Woche und werden über das Wochenende verschickt.</span><span class="sxs-lookup"><span data-stu-id="59fb3-113">The emails will contain information about assignments from the previous week and for the upcoming week, and will be sent over the weekend.</span></span> <span data-ttu-id="59fb3-114">Informationen zu den e-Mail-Inhalten finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="59fb3-114">Information about the email content can be found here.</span></span> <span data-ttu-id="59fb3-115">Die e-Mail-Nachrichten müssen von den Administratoren mithilfe von [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/)eingerichtet und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="59fb3-115">The emails need to be set up and updated by the admins by using [School Data Sync (SDS)](https://docs.microsoft.com/schooldatasync/).</span></span> <span data-ttu-id="59fb3-116">Dieses Feature füllt automatisch Kurse für Teams mit Studenten Verzeichnissen aus dem Student Information System (SIS) der Schule.</span><span class="sxs-lookup"><span data-stu-id="59fb3-116">This feature automatically populates classes for Teams with student rosters from the school's student information system (SIS).</span></span> <span data-ttu-id="59fb3-117">Die Schritte zum Aktivieren dieser Funktion sind:</span><span class="sxs-lookup"><span data-stu-id="59fb3-117">The steps to enable this feature are:</span></span>

1. <span data-ttu-id="59fb3-118">Importieren Sie über Eltern-und Guardian-Synchronisierung in SDS die übergeordneten Kontaktinformationen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-118">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="59fb3-119">Anweisungen zum Aktivieren der Synchronisierung von Eltern und Guardian finden Sie unter [Aktivieren der übergeordneten und Guardian-Synchronisierung](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="59fb3-119">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="59fb3-120">Aktivieren Sie die Einstellung Guardian im Microsoft Teams Admin Center, da die Einstellung standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="59fb3-120">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="59fb3-121">Damit können Lehrer eine wöchentliche Zusammenfassung senden.</span><span class="sxs-lookup"><span data-stu-id="59fb3-121">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="59fb3-122">Lehrer können den Digest ablehnen, indem Sie die Einstellung in Ihrem eigenen persönlichen kursteam deaktivieren (**Zuordnungseinstellungen > Eltern/Betreuer-e-Mails**).</span><span class="sxs-lookup"><span data-stu-id="59fb3-122">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="59fb3-123">Um zu überprüfen, ob Eltern die e-Mail erhalten, müssen die folgenden drei Elemente wahr sein:</span><span class="sxs-lookup"><span data-stu-id="59fb3-123">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="59fb3-124">E-Mail-Adresse, die dem Kursteilnehmer Profil in SDS angefügt und als _Elternteil_ oder _Erziehungsberechtigter_ markiert ist.</span><span class="sxs-lookup"><span data-stu-id="59fb3-124">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="59fb3-125">Ausführliche Informationen finden Sie unter [übergeordnetes und Guardian-Synchronisierungsdatei Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="59fb3-125">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="59fb3-126">Die Kursteilnehmer gehören mindestens einer Klasse an, in der e-Mail-Nachrichten nicht vom Lehrer in den [Zuordnungseinstellungen](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="59fb3-126">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="59fb3-127">Die e-Mails enthalten Informationen zu Aufgaben, die ein Fälligkeitsdatum in der vorherigen Woche oder in der nächsten Woche hatten.</span><span class="sxs-lookup"><span data-stu-id="59fb3-127">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="59fb3-128">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59fb3-128">This setting is off by default.</span></span>


<span data-ttu-id="59fb3-129"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="59fb3-129"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="59fb3-130">MakeCode</span><span class="sxs-lookup"><span data-stu-id="59fb3-130">MakeCode</span></span>
<span data-ttu-id="59fb3-131">Microsoft MakeCode ist eine blockbasierte Codierungs Plattform, die die Computerwissenschaften für alle Kursteilnehmer zum Leben erweckt.</span><span class="sxs-lookup"><span data-stu-id="59fb3-131">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="59fb3-132">MakeCode ist ein Microsoft-Produkt, das den Microsoft- [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und den [Datenschutz](https://go.microsoft.com/fwlink/?LinkId=521839) Richtlinien unterliegt.</span><span class="sxs-lookup"><span data-stu-id="59fb3-132">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="59fb3-133">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59fb3-133">This setting is off by default.</span></span> <span data-ttu-id="59fb3-134">Navigieren Sie zum Aktivieren von MakeCode-Aufgaben in Teams im **Team Admin Center** zum Abschnitt **Aufgaben** , und aktivieren Sie die Option MakeCode-Umschaltfläche **auf ein**.</span><span class="sxs-lookup"><span data-stu-id="59fb3-134">To enable MakeCode assignments in Teams, in the **Teams Admin Center**, navigate to the **Assignments** section and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="59fb3-135">Klicken Sie auf **Speichern** , und warten Sie einige Stunden, bis diese Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="59fb3-135">Click **Save** and allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="59fb3-136">Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Video Demonstration](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="59fb3-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="59fb3-137">[Weitere Informationen zu MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="59fb3-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="59fb3-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="59fb3-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="59fb3-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="59fb3-139">Turnitin</span></span>

<span data-ttu-id="59fb3-140">Turnitin ist ein Plagiat-Erkennungsdienst.</span><span class="sxs-lookup"><span data-stu-id="59fb3-140">Turnitin is a plagiarism detection service.</span></span> <span data-ttu-id="59fb3-141">Hierbei handelt es sich um ein Produkt oder einen Dienst eines Drittanbieters, der seinen eigenen Bedingungen und Datenschutzrichtlinien unterliegt.</span><span class="sxs-lookup"><span data-stu-id="59fb3-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="59fb3-142">Sie sind für die Nutzung von Produkten und Dienstleistungen von Drittanbietern verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="59fb3-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="59fb3-143">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="59fb3-143">This setting is off by default.</span></span>

<span data-ttu-id="59fb3-144">Damit Sie Turnitin für Ihre Organisation erfolgreich aktivieren können, müssen Sie bereits über ein Turnitin-Abonnement verfügen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-144">In order to successfully enable Turnitin for your organization, you will need to already have a Turnitin subscription.</span></span> <span data-ttu-id="59fb3-145">Sie müssen die folgenden zusätzlichen Informationen eingeben, die in ihrer Turnitin-Verwaltungskonsole zu finden sind:</span><span class="sxs-lookup"><span data-stu-id="59fb3-145">You will need to enter the following additional information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="59fb3-146">**TurnitinApiKey**: Hierbei handelt es sich um eine 32-Zeichen-GUID, die in der Admin-Konsole unter Integrationen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="59fb3-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="59fb3-147">**TurnitinApiUrl**: Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="59fb3-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="59fb3-148">Hier sind einige Anweisungen, die Ihnen bei der Behebung dieser Informationen helfen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="59fb3-149">Die **TurnitinApiUrl** ist die Hostadresse Ihrer Admin-Konsole.</span><span class="sxs-lookup"><span data-stu-id="59fb3-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="59fb3-150">Beispiel `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="59fb3-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="59fb3-151">In der Admin-Konsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="59fb3-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="59fb3-152">Wählen Sie **Integrationen** aus dem Seitenmenü und dann **Integration hinzufügen** aus, und geben Sie der Integration einen Namen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Screenshot mit dem Hinzufügen einer neuen Integration](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="59fb3-154">Nachdem Sie den Anweisungen folgen, wird Ihnen der **TurnitinApiKey** mitgeteilt.</span><span class="sxs-lookup"><span data-stu-id="59fb3-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="59fb3-155">Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.</span><span class="sxs-lookup"><span data-stu-id="59fb3-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="59fb3-156">Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="59fb3-156">This is the only time you can view the key.</span></span>

![Screenshot mit dem Kopieren des API-Schlüssels](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="59fb3-158">Wenn Sie im Admin Center für diese Einstellung auf die Schaltfläche " **Speichern** " klicken, können Sie diese Einstellungen einige Stunden in Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="59fb3-158">Upon clicking the **Save** button in the admin center for this setting, please allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="59fb3-159">Sind Sie bereit, die Turnitin-Integration in Teams zu verwenden?</span><span class="sxs-lookup"><span data-stu-id="59fb3-159">Ready to start using the Turnitin integration in Teams?</span></span> <span data-ttu-id="59fb3-160">Registrieren Sie sich für das [Early Access-Programm](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span><span class="sxs-lookup"><span data-stu-id="59fb3-160">Sign up for the [early access program](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration).</span></span>
