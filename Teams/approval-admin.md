---
title: Genehmigungen Verfügbarkeit von Anwendungen in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aravin
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie mehr über die Verfügbarkeit von Genehmigungs Anwendungen in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4326408b7e27aa19af8e6c404d7275d26ba90969
ms.sourcegitcommit: d73d732591944b899a9366f79b4ea97f4a7f2260
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "49675179"
---
# <a name="teams-approvals-app-availability"></a><span data-ttu-id="48edf-103">Verfügbarkeit der APP für Teams-Genehmigungen</span><span class="sxs-lookup"><span data-stu-id="48edf-103">Teams Approvals app availability</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="48edf-104">Die Genehmigungs-APP ist als persönliche App für alle Microsoft Teams-Benutzer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48edf-104">The Approvals app is available as a personal app for all Microsoft Teams users.</span></span>
<span data-ttu-id="48edf-105">Die app "Genehmigungen" bietet eine einfache Möglichkeit, um Überwachungs-, Konformitäts-, Rechenschafts-und Workflows sowohl strukturierten als auch unstrukturierten Genehmigungen in Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="48edf-105">The Approvals app provides a simple way to bring auditing, compliance, accountability, and workflows to both structured and unstructured Approvals in Teams.</span></span>

 ![zeigt die app "Genehmigungen"](media/approvals-selection.png)

<span data-ttu-id="48edf-107">Benutzer können die Genehmigungs-App anheften, um Sie in der Menüleiste zu speichern.</span><span class="sxs-lookup"><span data-stu-id="48edf-107">Users can pin the Approvals app to save it to the menu bar.</span></span>

 ![zeigt die app "Genehmigungen" mit der Option "Pin" an](media/approvalApp-pin.png)

<span data-ttu-id="48edf-109">Mit der ersten Genehmigung, die Sie über die Genehmigungs-App erstellt haben, wird die Bereitstellung der Genehmigungslösung in der Standardumgebung für gemeinsame Datendienste (Common Data Service, CDs) ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="48edf-109">The first approval created from the Approvals app will trigger the provisioning of the Approval Solution in the default Common Data Service (CDS) environment.</span></span> <span data-ttu-id="48edf-110">Genehmigungen, die aus der Genehmigungs-App erstellt wurden, werden in der Standard-CD-Umgebung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="48edf-110">Approvals created from the Approvals app will be stored in the default CDS environment.</span></span>

<span data-ttu-id="48edf-111">In diesem Artikel werden die Anforderungen und Rollen der Genehmigungs-App beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48edf-111">This article describes the Approvals app requirements and roles.</span></span>

## <a name="required-permissions-and-licenses"></a><span data-ttu-id="48edf-112">Erforderliche Berechtigungen und Lizenzen</span><span class="sxs-lookup"><span data-stu-id="48edf-112">Required permissions and licenses</span></span>

<span data-ttu-id="48edf-113">Wenn Sie die Genehmigungs-App verwenden möchten, benötigen Sie die Berechtigung für die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="48edf-113">To use the Approvals app, you need permission for the following items:</span></span>

- <span data-ttu-id="48edf-114">Berechtigungen zum Erstellen einer Microsoft CDs-Datenbank</span><span class="sxs-lookup"><span data-stu-id="48edf-114">Permissions to create a Microsoft CDS database.</span></span>

- <span data-ttu-id="48edf-115">Ein Konto auf [Flow.Microsoft.com](https://flow.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="48edf-115">An account on [flow.microsoft.com](https://flow.microsoft.com/)</span></span>

- <span data-ttu-id="48edf-116">Administrator Rolle in der Zielumgebung.</span><span class="sxs-lookup"><span data-stu-id="48edf-116">Administrator Role in the target environment.</span></span>

- <span data-ttu-id="48edf-117">Lizenz für [Power Automation](https://docs.microsoft.com/power-automate/get-started-approvals), Office 365 oder Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="48edf-117">License for a [Power Automate](https://docs.microsoft.com/power-automate/get-started-approvals), an Office 365, or a Dynamics 365.</span></span>

## <a name="storage-with-cds"></a><span data-ttu-id="48edf-118">Speicher mit CDs</span><span class="sxs-lookup"><span data-stu-id="48edf-118">Storage with CDS</span></span>

<span data-ttu-id="48edf-119">Das gemeinsame Datenmodell (CDM) ist die Sprache für freigegebene Daten, die von Geschäfts-und Analyseanwendungen in den CDs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48edf-119">The Common Data Model (CDM) is the shared data language used by business and analytical applications in the CDS.</span></span> <span data-ttu-id="48edf-120">Es besteht aus einer Reihe von standardisierten, erweiterbaren Datenschemas, die von Microsoft und unseren Partnern veröffentlicht wurden und die Konsistenz von Daten und deren Bedeutung für Anwendungen und Geschäftsprozesse ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="48edf-120">It consists of a set of a standardized, extensible data schemas published by Microsoft and our partners that enables consistency of data and its meaning across applications and business processes.</span></span> <span data-ttu-id="48edf-121">Weitere Informationen zum [allgemeinen Datenmodell der Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span><span class="sxs-lookup"><span data-stu-id="48edf-121">Learn more about the [Common Data Model of the Microsoft Power Platform](https://docs.microsoft.com/power-automate/get-started-approvals).</span></span>

<span data-ttu-id="48edf-122">Weitere Informationen zum [Genehmigungsworkflow](https://docs.microsoft.com/power-automate/modern-approvals).</span><span class="sxs-lookup"><span data-stu-id="48edf-122">Learn more about the [Approval workflow](https://docs.microsoft.com/power-automate/modern-approvals).</span></span>

## <a name="approvals-teams-app-permissions"></a><span data-ttu-id="48edf-123">Genehmigungen Teams-App-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="48edf-123">Approvals Teams app permissions</span></span>

<span data-ttu-id="48edf-124">Mit der Genehmigungs Teams-App können Sie auf die folgenden Features zugreifen:</span><span class="sxs-lookup"><span data-stu-id="48edf-124">The Approvals Teams app lets you access the following features:</span></span>

- <span data-ttu-id="48edf-125">Empfangen von Nachrichten und Daten, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="48edf-125">Receive messages and data that you provide to it.</span></span>

- <span data-ttu-id="48edf-126">Senden Sie Nachrichten und Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="48edf-126">Send you messages and notifications.</span></span>

- <span data-ttu-id="48edf-127">Rendern Sie persönliche apps und Dialogfelder ohne einen vom Team bereitgestellten Header.</span><span class="sxs-lookup"><span data-stu-id="48edf-127">Render personal apps and dialogs without a Teams-provided header.</span></span>

- <span data-ttu-id="48edf-128">Greifen Sie auf Ihre Profilinformationen wie Name, e-Mail-Adresse, Firmenname und bevorzugte Sprache zu.</span><span class="sxs-lookup"><span data-stu-id="48edf-128">Access your profile information such as your name, email address, company name, and preferred language.</span></span>

- <span data-ttu-id="48edf-129">Empfangen von Nachrichten und Daten, die Teammitglieder in einem Kanal bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="48edf-129">Receive messages and data that team members provide to it in a channel.</span></span>

- <span data-ttu-id="48edf-130">Senden Sie Nachrichten und Benachrichtigungen in einem Kanal.</span><span class="sxs-lookup"><span data-stu-id="48edf-130">Send messages and notifications in a channel.</span></span>

- <span data-ttu-id="48edf-131">Zugriff auf die Informationen Ihres Teams:</span><span class="sxs-lookup"><span data-stu-id="48edf-131">Access your team's information:</span></span>
  - <span data-ttu-id="48edf-132">Teamname</span><span class="sxs-lookup"><span data-stu-id="48edf-132">team name</span></span>
  - <span data-ttu-id="48edf-133">Kanalliste</span><span class="sxs-lookup"><span data-stu-id="48edf-133">channel list</span></span>
  - <span data-ttu-id="48edf-134">Dienstplan (Namen und e-Mail-Adressen des Teammitglieds).</span><span class="sxs-lookup"><span data-stu-id="48edf-134">roster (team member's names and email addresses).</span></span>

- <span data-ttu-id="48edf-135">Verwenden Sie die Informationen des Teams, um sich mit Ihnen in Verbindung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="48edf-135">Use the team's information to contact them.</span></span>

## <a name="disable-the-approvals-app"></a><span data-ttu-id="48edf-136">Deaktivieren der Genehmigungs-App</span><span class="sxs-lookup"><span data-stu-id="48edf-136">Disable the Approvals app</span></span>

<span data-ttu-id="48edf-137">Standardmäßig ist die APP Genehmigungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="48edf-137">The Approvals app is available by default.</span></span> <span data-ttu-id="48edf-138">Sie können die APP im Team Admin Center deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="48edf-138">You can disable the app in the Teams admin center.</span></span>

  1. <span data-ttu-id="48edf-139">Anmelden beim Team Admin Center.</span><span class="sxs-lookup"><span data-stu-id="48edf-139">Sign in to the Teams admin center.</span></span>

  2. <span data-ttu-id="48edf-140">Erweitern Sie **Teams-apps** , und wählen Sie **apps verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="48edf-140">Expand **Teams apps** and select **Manage apps**.</span></span>

  3. <span data-ttu-id="48edf-141">Suchen Sie nach der APP Genehmigungen.</span><span class="sxs-lookup"><span data-stu-id="48edf-141">Search for the Approvals app.</span></span>

![zeigt die Admin Center-Navigation mit Teams-apps > hervorgehobene apps verwalten](media/manage-approval-apps.png)

  4. <span data-ttu-id="48edf-143">Wählen Sie Genehmigungen aus.</span><span class="sxs-lookup"><span data-stu-id="48edf-143">Select Approvals.</span></span>

  5. <span data-ttu-id="48edf-144">Wählen Sie die Umschaltfläche aus, um die APP für Ihre Organisation zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="48edf-144">Select the toggle to disable the app for your organization.</span></span>

![zeigt die Details für die Genehmigungs-APP an.](media/approvals-details.png)

## <a name="retention-policy"></a><span data-ttu-id="48edf-146">Aufbewahrungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="48edf-146">Retention policy</span></span>

<span data-ttu-id="48edf-147">Genehmigungen, die aus der Genehmigungs-App erstellt wurden, werden in der Standard-CD-Umgebung gespeichert, die derzeit keine Sicherungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="48edf-147">Approvals created from the Approvals App are stored in the default CDS environment, which doesn’t support backups at this time.</span></span> <span data-ttu-id="48edf-148">Weitere Informationen zum [Sichern und Wiederherstellen von Umgebungen – Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span><span class="sxs-lookup"><span data-stu-id="48edf-148">Learn more about how to [Back up and restore environments - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/backup-restore-environments).</span></span>

## <a name="auditing"></a><span data-ttu-id="48edf-149">Überwachung</span><span class="sxs-lookup"><span data-stu-id="48edf-149">Auditing</span></span>

<span data-ttu-id="48edf-150">Die Genehmigungs-App protokolliert Überwachungsereignisse im Microsoft 365 Security and Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="48edf-150">The Approvals App logs audit events within the Microsoft 365 Security and Compliance Center.</span></span> <span data-ttu-id="48edf-151">Sie können das Überwachungsprotokoll anzeigen.</span><span class="sxs-lookup"><span data-stu-id="48edf-151">You can view the audit log.</span></span>

1. <span data-ttu-id="48edf-152">Wechseln Sie zur M365-Kompatibilitätswebsite.</span><span class="sxs-lookup"><span data-stu-id="48edf-152">Go to the M365 Compliance Site.</span></span>

2. <span data-ttu-id="48edf-153">Wählen Sie den Abschnitt **Audit** aus.</span><span class="sxs-lookup"><span data-stu-id="48edf-153">Select the **Audit** section.</span></span>

3. <span data-ttu-id="48edf-154">Suchen Sie nach Aktivitäten unter **Microsoft Teams-Genehmigungsaktivitäten**.</span><span class="sxs-lookup"><span data-stu-id="48edf-154">Search for activities under **Microsoft Teams approvals activities**.</span></span>

<span data-ttu-id="48edf-155">Sie können nach den folgenden Aktivitäten suchen:</span><span class="sxs-lookup"><span data-stu-id="48edf-155">You can search for the following activities:</span></span>

- <span data-ttu-id="48edf-156">Neue Genehmigungsanfrage erstellen</span><span class="sxs-lookup"><span data-stu-id="48edf-156">Create new approval request</span></span>

- <span data-ttu-id="48edf-157">Details zur Genehmigungsanforderung anzeigen</span><span class="sxs-lookup"><span data-stu-id="48edf-157">View approval request details</span></span>

- <span data-ttu-id="48edf-158">Genehmigte Genehmigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="48edf-158">Approved approval request</span></span>

- <span data-ttu-id="48edf-159">Abgelehnte Genehmigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="48edf-159">Rejected approval request</span></span>

- <span data-ttu-id="48edf-160">Genehmigungsanforderung abgebrochen</span><span class="sxs-lookup"><span data-stu-id="48edf-160">Canceled approval request</span></span>

- <span data-ttu-id="48edf-161">Freigegebene Genehmigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="48edf-161">Shared approval request</span></span>

- <span data-ttu-id="48edf-162">Datei, die an die Genehmigungsanforderung angefügt ist</span><span class="sxs-lookup"><span data-stu-id="48edf-162">File attached to approval request</span></span>

- <span data-ttu-id="48edf-163">Erneut zugewiesene Genehmigungsanforderung</span><span class="sxs-lookup"><span data-stu-id="48edf-163">Reassigned approval request</span></span>

- <span data-ttu-id="48edf-164">E-Signatur zur Genehmigungsanfrage hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="48edf-164">Added e-signature to approval request</span></span>

<span data-ttu-id="48edf-165">Für den Zugriff auf weitere Überwachungs Genehmigungen in Flow aktivieren und konfigurieren Sie die Überwachung in der Standardumgebung für die Genehmigung, Genehmigungsanforderung und Genehmigungs Antwort für primäre Genehmigungs Entitäten.</span><span class="sxs-lookup"><span data-stu-id="48edf-165">For access to more auditing approvals within Flow, enable and configure auditing in the default environment for the primary approval entities Approval, Approval Request, and Approval Response.</span></span> <span data-ttu-id="48edf-166">Erstellen, aktualisieren und Löschen von Vorgängen sind Überwachungs Bare Ereignisse für Genehmigungs Einträge.</span><span class="sxs-lookup"><span data-stu-id="48edf-166">Create, update, and delete operations are auditable events for Approval records.</span></span> <span data-ttu-id="48edf-167">Weitere Informationen zu [Überwachungsdaten und Benutzeraktivitäten für Sicherheit und Compliance – Power Platform \| Microsoft docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span><span class="sxs-lookup"><span data-stu-id="48edf-167">Learn more about [Audit data and user activity for security and compliance - Power Platform \| Microsoft Docs](https://docs.microsoft.com/power-platform/admin/audit-data-user-activity).</span></span>

<span data-ttu-id="48edf-168">Die Überwachung kann im [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US)weiter angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="48edf-168">Auditing can be customized further in the [Microsoft 365 Security and Compliance Center](https://support.office.com/article/go-to-the-office-365-security-compliance-center-7e696a40-b86b-4a20-afcc-559218b7b1b8?ui=en-US&rs=en-US&ad=US).</span></span>

1. <span data-ttu-id="48edf-169">Wenn Sie die vorkonfigurierten Berichte verwenden möchten, müssen Sie sich bei Office 365-Sicherheit und-Compliance anmelden.</span><span class="sxs-lookup"><span data-stu-id="48edf-169">To use the preconfigured reports, sign in to Office 365 Security and Compliance.</span></span>

2. <span data-ttu-id="48edf-170">Wählen Sie **& Untersuchung suchen** aus.</span><span class="sxs-lookup"><span data-stu-id="48edf-170">Select **Search & investigation**.</span></span>

3. <span data-ttu-id="48edf-171">Durchsuchen Sie das Überwachungsprotokoll, und wählen Sie die Registerkarte **Dynamik 365 Aktivitäten** aus.</span><span class="sxs-lookup"><span data-stu-id="48edf-171">Search the Audit log and select the **Dynamics 365 activities** tab.</span></span>

<span data-ttu-id="48edf-172">Weitere Informationen zu [Microsoft Dataverse und modellgesteuerte apps-Aktivitätsprotokollierung – Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span><span class="sxs-lookup"><span data-stu-id="48edf-172">Learn more about [Microsoft Dataverse and model-driven apps activity logging - Power Platform](https://docs.microsoft.com/power-platform/admin/enable-use-comprehensive-auditing).</span></span>

## <a name="security"></a><span data-ttu-id="48edf-173">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="48edf-173">Security</span></span>

<span data-ttu-id="48edf-174">In der App "Teams-Genehmigung" können Benutzer neue Genehmigungen erstellen und Genehmigungen anzeigen, die Sie gesendet und empfangen haben.</span><span class="sxs-lookup"><span data-stu-id="48edf-174">From the Teams Approval App, users have access to create new Approvals and view Approvals that they have sent and received.</span></span> <span data-ttu-id="48edf-175">Benutzer haben keinen Zugriff auf Genehmigungen, die von anderen Personen erstellt wurden, es sei denn, Sie sind entweder ein Responder oder ein Betrachter der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="48edf-175">Users won't have access to Approvals that are created by others unless they're either a responder or a viewer of the request.</span></span>

> [!Note]
> <span data-ttu-id="48edf-176">Ein Benutzer erhält eine Anzeige Rolle einer Anforderung, wenn er Teil des Chats oder Kanals ist, in dem die Genehmigung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="48edf-176">A user will be given a viewer role of a request if they are part of the chat or channel where the approval was created.</span></span> <span data-ttu-id="48edf-177">Sie verfügen nicht über die Möglichkeit, die Anforderung zu ergreifen, wenn diese Rolle bei der Erstellung der Genehmigung nicht angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="48edf-177">They won't have the ability to take action on the request if they weren't given that role when the approval was created.</span></span>
