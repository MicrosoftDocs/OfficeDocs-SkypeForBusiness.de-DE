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
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586618"
---
# <a name="assignments-in-teams-for-education"></a><span data-ttu-id="d1ea1-103">Aufgaben in Teams für Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="d1ea1-103">Assignments in Teams for Education</span></span>

<span data-ttu-id="d1ea1-104">Mit den Funktionen "Aufgaben" und "Noten" in "Teams für Bildung" können Pädagogen ihren Schülern Aufgaben, Arbeit oder Quizaufgaben zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-104">The Assignments and Grades features in Teams for Education allow educators to assign tasks, work, or quizzes to their students.</span></span> <span data-ttu-id="d1ea1-105">Pädagogen können Zuordnungs Zeitpläne, Anweisungen, Hinzufügen von Ressourcen zum umwandeln, benoten mit Rubriken und vieles mehr verwalten.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-105">Educators can manage assignment timelines, instructions, add resources to turn in, grade with rubrics, and more.</span></span> <span data-ttu-id="d1ea1-106">Sie können auch Kurs-und einzelne Kursteilnehmerstatus auf der Registerkarte "Noten" nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-106">They can also track class and individual student progress in the Grades tab.</span></span>

<span data-ttu-id="d1ea1-107">[Weitere Informationen zu Aufgaben und Noten in Teams für Bildung](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-107">[Learn more about Assignments and Grades in Teams for Education](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments).</span></span>

> [!Note]
> <span data-ttu-id="d1ea1-108">Details zu Teams-Aufgaben auf verschiedenen Plattformen finden Sie unter [Teams-Features nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-108">For details about Teams assignments on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d1ea1-109">Aufgaben Integrationen im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="d1ea1-109">Assignments integrations in the Microsoft Teams admin center</span></span>

<span data-ttu-id="d1ea1-110">Mithilfe der Administratoreinstellungen im Microsoft Teams Admin Center können Sie Features für Pädagogen in Ihrer Organisation und deren Schüler aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-110">Using the admin settings in the Microsoft Teams admin center, you can turn features on or off for educators within your organization and their students.</span></span> <span data-ttu-id="d1ea1-111">Die folgenden Einstellungen beziehen sich auf Aufgaben:</span><span class="sxs-lookup"><span data-stu-id="d1ea1-111">The following are settings related to Assignments:</span></span>

<span data-ttu-id="d1ea1-112"><a name="#bkemaildigest"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ea1-112"><a name="#bkemaildigest"> </a></span></span>
### <a name="weekly-guardian-email-digest"></a><span data-ttu-id="d1ea1-113">Wöchentlicher Guardian-e-Mail-Digest</span><span class="sxs-lookup"><span data-stu-id="d1ea1-113">Weekly guardian email digest</span></span>


<span data-ttu-id="d1ea1-114">Guardian-e-Mails werden an alle Wochenenden an Eltern oder Erziehungsberechtigte gesendet.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-114">Guardian emails are sent each weekend to parents or guardians.</span></span> <span data-ttu-id="d1ea1-115">Die e-Mail enthält Informationen zu Aufgaben aus der vorherigen Woche und für die kommende Woche.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-115">The email contains information about assignments from the previous week and for the upcoming week.</span></span> <span data-ttu-id="d1ea1-116">Die übergeordnete und Guardian-Synchronisierung kann mithilfe von [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync)eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-116">The Parent and Guardian Sync can be setup using [School Data Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync).</span></span>

1. <span data-ttu-id="d1ea1-117">Importieren Sie über Eltern-und Guardian-Synchronisierung in SDS die übergeordneten Kontaktinformationen.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-117">Import parent contact information via Parent and Guardian Sync in SDS.</span></span> <span data-ttu-id="d1ea1-118">Anweisungen zum Aktivieren der Synchronisierung von Eltern und Guardian finden Sie unter [Aktivieren der übergeordneten und Guardian-Synchronisierung](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-118">For instructions on how to enable Parent and Guardian Sync, see [Enabling Parent and Guardian Sync](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync).</span></span>

2. <span data-ttu-id="d1ea1-119">Aktivieren Sie die Einstellung Guardian im Microsoft Teams Admin Center, da die Einstellung standardmäßig deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-119">Turn on the Guardian Setting in the Microsoft Teams admin center, as the setting is turned off by default.</span></span> <span data-ttu-id="d1ea1-120">Damit können Lehrer eine wöchentliche Zusammenfassung senden.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-120">This will enable teachers to send out a weekly digest.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1ea1-121">Lehrer können den Digest ablehnen, indem Sie die Einstellung in Ihrem eigenen persönlichen kursteam deaktivieren (**Zuordnungseinstellungen > Eltern/Betreuer-e-Mails**).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-121">Teachers can opt-out of the digest by deselecting the setting inside their own personal class team (**Assignment Settings > Parent/Guardian Emails**).</span></span>

<span data-ttu-id="d1ea1-122">Um zu überprüfen, ob Eltern die e-Mail erhalten, müssen die folgenden drei Elemente wahr sein:</span><span class="sxs-lookup"><span data-stu-id="d1ea1-122">To verify that Parents will get the email the following three items must be true:</span></span>

 - <span data-ttu-id="d1ea1-123">E-Mail-Adresse, die dem Kursteilnehmer Profil in SDS angefügt und als _Elternteil_ oder _Erziehungsberechtigter_ markiert ist.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-123">Email address attached to the student profile in SDS and tagged as _Parent_ or _Guardian_.</span></span> <span data-ttu-id="d1ea1-124">Ausführliche Informationen finden Sie unter [übergeordnetes und Guardian-Synchronisierungsdatei Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-124">For details, see [Parent and Guardian Sync File Format](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format).</span></span>

 - <span data-ttu-id="d1ea1-125">Die Kursteilnehmer gehören mindestens einer Klasse an, in der e-Mail-Nachrichten nicht vom Lehrer in den [Zuordnungseinstellungen](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-125">Students belong to at least one class in which e-mail is not disabled by the teacher in [assignment settings](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77).</span></span>

 - <span data-ttu-id="d1ea1-126">Die e-Mails enthalten Informationen zu Aufgaben, die ein Fälligkeitsdatum in der vorherigen Woche oder in der nächsten Woche hatten.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-126">The emails will contain information about assignments that had a due date in the previous week or in the upcoming week.</span></span>

<span data-ttu-id="d1ea1-127">Die Standardeinstellung für dieses Feature ist- **aus**.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-127">Default setting for this feature is - **Off**.</span></span>


<span data-ttu-id="d1ea1-128"><a name="bkmakecode"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ea1-128"><a name="bkmakecode"> </a></span></span>
### <a name="makecode"></a><span data-ttu-id="d1ea1-129">MakeCode</span><span class="sxs-lookup"><span data-stu-id="d1ea1-129">MakeCode</span></span>
<span data-ttu-id="d1ea1-130">Microsoft MakeCode ist eine blockbasierte Codierungs Plattform, die die Computerwissenschaften für alle Kursteilnehmer zum Leben erweckt.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-130">Microsoft MakeCode is a block-based coding platform that brings computer science to life for all students.</span></span> 

<span data-ttu-id="d1ea1-131">MakeCode ist ein Microsoft-Produkt, das den Microsoft- [Nutzungsbedingungen](https://go.microsoft.com/fwlink/?LinkID=206977) und den [Datenschutz](https://go.microsoft.com/fwlink/?LinkId=521839) Richtlinien unterliegt.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-131">MakeCode is a Microsoft product that is subject to the Microsoft [terms of use](https://go.microsoft.com/fwlink/?LinkID=206977) and [privacy](https://go.microsoft.com/fwlink/?LinkId=521839) policies.</span></span>

<span data-ttu-id="d1ea1-132">Die Standardeinstellung für dieses Feature ist- **aus**.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-132">Default setting for this feature is - **Off**.</span></span>

<span data-ttu-id="d1ea1-133">Zum Aktivieren von MakeCode-Aufgaben in Teams wechseln Sie zum **Team Admin Center**, navigieren Sie zum Abschnitt **Aufgaben** , und aktivieren Sie die Option MakeCode-Umschaltfläche **auf ein**.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-133">To enable MakeCode assignments in Teams, go to the **Teams Admin Center**, navigate to the **Assignments** section, and turn the MakeCode toggle option to **On**.</span></span> <span data-ttu-id="d1ea1-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-134">Click **Save**.</span></span> <span data-ttu-id="d1ea1-135">Lassen Sie einige Stunden dauern, bis diese Einstellungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-135">Allow a few hours for these settings to take effect.</span></span>

<span data-ttu-id="d1ea1-136">Weitere Informationen zur Funktionsweise dieses Features finden Sie in dieser [Video Demonstration](https://makecode.com/blog/teams/teams-assignments).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-136">For more information on how this feature works, see this [video demonstration](https://makecode.com/blog/teams/teams-assignments).</span></span>

<span data-ttu-id="d1ea1-137">[Weitere Informationen zu MakeCode](https://aka.ms/makecode).</span><span class="sxs-lookup"><span data-stu-id="d1ea1-137">[Learn more about MakeCode](https://aka.ms/makecode).</span></span>

<span data-ttu-id="d1ea1-138"><a name="#turnitin"> </a></span><span class="sxs-lookup"><span data-stu-id="d1ea1-138"><a name="#turnitin"> </a></span></span>
### <a name="turnitin"></a><span data-ttu-id="d1ea1-139">Turnitin</span><span class="sxs-lookup"><span data-stu-id="d1ea1-139">Turnitin</span></span>

<span data-ttu-id="d1ea1-140">[Turnitin](https://www.turnitin.com/) ist ein akademischer Integritätsdienst.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-140">[Turnitin](https://www.turnitin.com/) is an academic integrity service.</span></span> <span data-ttu-id="d1ea1-141">Hierbei handelt es sich um ein Produkt oder einen Dienst eines Drittanbieters, der seinen eigenen Bedingungen und Datenschutzrichtlinien unterliegt.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-141">This is a third-party product or service that is subject to its own terms and privacy policy.</span></span> <span data-ttu-id="d1ea1-142">Sie sind für die Nutzung von Produkten und Dienstleistungen von Drittanbietern verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-142">You are responsible for your use of any third-party products and services.</span></span>

<span data-ttu-id="d1ea1-143">Die Standardeinstellung für dieses Feature ist- **aus**.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-143">Default setting for this feature is - **Off**..</span></span>

<span data-ttu-id="d1ea1-144">Zum Aktivieren von Turnitin für Ihre Organisation benötigen Sie ein Turnitin-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-144">To enable Turnitin for your organization, you will need a Turnitin subscription.</span></span> <span data-ttu-id="d1ea1-145">Anschließend können Sie die folgenden Informationen eingeben, die in ihrer Turnitin-Verwaltungskonsole zu finden sind:</span><span class="sxs-lookup"><span data-stu-id="d1ea1-145">Then you can input the following information, which can be found in your Turnitin admin console:</span></span>

  * <span data-ttu-id="d1ea1-146">**TurnitinApiKey**: Hierbei handelt es sich um eine 32-Zeichen-GUID, die in der Admin-Konsole unter Integrationen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-146">**TurnitinApiKey**: This is a 32-character GUID found in the admin console under Integrations.</span></span>
  * <span data-ttu-id="d1ea1-147">**TurnitinApiUrl**: Dies ist die HTTPS-URL Ihrer Turnitin-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-147">**TurnitinApiUrl**: This is the HTTPS URL of your Turnitin admin console.</span></span>

<span data-ttu-id="d1ea1-148">Hier sind einige Anweisungen, die Ihnen bei der Behebung dieser Informationen helfen.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-148">Here are some instructions to help you obtain this information.</span></span>

<span data-ttu-id="d1ea1-149">Die **TurnitinApiUrl** ist die Hostadresse Ihrer Admin-Konsole.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-149">The **TurnitinApiUrl** is the host address of your admin console.</span></span>
<span data-ttu-id="d1ea1-150">Beispiel `https://your-tenant-name.turnitin.com`</span><span class="sxs-lookup"><span data-stu-id="d1ea1-150">Example: `https://your-tenant-name.turnitin.com`</span></span>

<span data-ttu-id="d1ea1-151">In der Admin-Konsole können Sie eine Integration und einen API-Schlüssel erstellen, der der Integration zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-151">The admin console is where you can create an integration and an API key associated with the integration.</span></span>

<span data-ttu-id="d1ea1-152">Wählen Sie **Integrationen** aus dem Seitenmenü und dann **Integration hinzufügen** aus, und geben Sie der Integration einen Namen.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-152">Select **Integrations** from the side menu, then select **Add Integration** and give the integration a name.</span></span>

![Screenshot mit dem Hinzufügen einer neuen Integration](./educationImages/Assignments_mopo_turnitin2.png)

<span data-ttu-id="d1ea1-154">Nachdem Sie den Anweisungen folgen, wird Ihnen der **TurnitinApiKey** mitgeteilt.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-154">The **TurnitinApiKey** will be given to you after you follow the prompts.</span></span> <span data-ttu-id="d1ea1-155">Kopieren Sie den API-Schlüssel, und fügen Sie ihn in das Microsoft Teams Admin Center ein.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-155">Copy the API key and paste it into the Microsoft Teams admin center.</span></span>  <span data-ttu-id="d1ea1-156">Dies ist das einzige Mal, dass Sie den Schlüssel anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-156">This is the only time you can view the key.</span></span>

![Screenshot mit dem Kopieren des API-Schlüssels](./educationImages/Assignments_mopo_turnitin3.png)

<span data-ttu-id="d1ea1-158">Wenn Sie im Admin Center für diese Einstellung auf die Schaltfläche " **Speichern** " klicken, können diese Einstellungen einige Stunden in Kraft treten.</span><span class="sxs-lookup"><span data-stu-id="d1ea1-158">Upon clicking the **Save** button in the admin center for this setting, allow a few hours for these settings to take effect.</span></span>

