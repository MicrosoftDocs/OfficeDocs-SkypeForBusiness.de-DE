---
title: Verwenden von OneDrive und SharePoint für Besprechungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie von Stream zu OneDrive for Business und SharePoint-Besprechungs Speicher in Microsoft Teams wechseln.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2731b5c8f9001746a180a8f63d0ffd72276c5dc1
ms.sourcegitcommit: 43e5a4aac11c20dd5a4c35b59695f309e1559e82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2020
ms.locfileid: "48346336"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="0ef42-103">Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen</span><span class="sxs-lookup"><span data-stu-id="0ef42-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="0ef42-104">Der Wechsel von Microsoft Stream zu OneDrive for Business und SharePoint für Besprechungsaufzeichnungen erfolgt schrittweise.</span><span class="sxs-lookup"><span data-stu-id="0ef42-104">The change from using Microsoft Stream to OneDrive for Business and SharePoint for meeting recordings will be a phased approach.</span></span> <span data-ttu-id="0ef42-105">Beim Start können mandantenadministratoren diese neue Workflow Option heute auswählen und beginnen, die Aufzeichnungen im Oktober 2020 automatisch auf OneDrive for Business und SharePoint zu sehen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-105">At launch, tenant admins can choose this new workflow option today and will start seeing recordings auto-upload to OneDrive for Business and SharePoint in October 2020.</span></span> <span data-ttu-id="0ef42-106">Im November müssen Sie sich abmelden, wenn Sie den Datenstrom weiterhin verwenden möchten, und einige Zeit in frühen 2021 werden wir alle Kunden dazu auffordern, OneDrive for Business und SharePoint für neue Besprechungsaufzeichnungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ef42-106">In November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

<span data-ttu-id="0ef42-107">Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-107">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="0ef42-108">Als Ausgangspunkt für den Datenstrom verwendet die Methode Microsoft OneDrive und SharePoint in Microsoft 365 und bietet zahlreiche Vorteile.</span><span class="sxs-lookup"><span data-stu-id="0ef42-108">As a departure from Stream, the method uses Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="0ef42-109">Zu den Vorteilen der Verwendung von OneDrive for Business und SharePoint für das Speichern von Aufzeichnungen gehören:</span><span class="sxs-lookup"><span data-stu-id="0ef42-109">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="0ef42-110">Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S + C E5-autoaufbewahrungs Etiketten)</span><span class="sxs-lookup"><span data-stu-id="0ef42-110">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="0ef42-111">Profitieren Sie von OneDrive for Business und SharePoint-Informations-Governance</span><span class="sxs-lookup"><span data-stu-id="0ef42-111">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="0ef42-112">Einfaches Einrichten von Berechtigungen und Freigabe</span><span class="sxs-lookup"><span data-stu-id="0ef42-112">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="0ef42-113">Freigeben von Aufzeichnungen für Gäste (externe Benutzer) mit expliziter Freigabe</span><span class="sxs-lookup"><span data-stu-id="0ef42-113">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="0ef42-114">Zugriffs Fluss anfordern</span><span class="sxs-lookup"><span data-stu-id="0ef42-114">Request access flow</span></span>
- <span data-ttu-id="0ef42-115">Bereitstellen von OneDrive for Business-und SharePoint-freigegebenen Links</span><span class="sxs-lookup"><span data-stu-id="0ef42-115">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="0ef42-116">Höhere Kontingente</span><span class="sxs-lookup"><span data-stu-id="0ef42-116">Increased quota</span></span>
- <span data-ttu-id="0ef42-117">Besprechungsaufzeichnungen sind schneller verfügbar</span><span class="sxs-lookup"><span data-stu-id="0ef42-117">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="0ef42-118">Support für **lokale** Mandanten</span><span class="sxs-lookup"><span data-stu-id="0ef42-118">**Go local** tenant support</span></span>
- <span data-ttu-id="0ef42-119">Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für diesen benutzerspezifischen Region gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0ef42-119">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="0ef42-120">Unterstützung für Ihren eigenen Schlüssel (BYOK)</span><span class="sxs-lookup"><span data-stu-id="0ef42-120">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="0ef42-121">Verbesserte Transkriptions Qualität und Sprecher Zuordnung</span><span class="sxs-lookup"><span data-stu-id="0ef42-121">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="0ef42-122">Es gibt einige Einschränkungen, die berücksichtigt werden sollten:</span><span class="sxs-lookup"><span data-stu-id="0ef42-122">There are some limitations to consider:</span></span>

- <span data-ttu-id="0ef42-123">Es werden nur Englisch-Untertitel und-Transkripte vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="0ef42-123">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="0ef42-124">Sie können keine Transkripte oder deren Inhalt durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-124">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="0ef42-125">Sie können die Transkripte nicht bearbeiten, aber Sie können die Beschriftungen aus-und einschalten.</span><span class="sxs-lookup"><span data-stu-id="0ef42-125">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="0ef42-126">Sie können steuern, mit wem Sie die Aufzeichnung freigeben, aber Sie können Personen mit freigegebenen Zugriff nicht blockieren, indem Sie die Aufzeichnung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-126">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="0ef42-127">Wenn die Aufzeichnung die Speicherung beendet hat, wird keine e-Mail angezeigt, aber die Aufzeichnung wird nach Abschluss des Besprechungs Chats angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0ef42-127">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="0ef42-128">Dies geschieht viel schneller als in Stream zuvor.</span><span class="sxs-lookup"><span data-stu-id="0ef42-128">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="0ef42-129">Schauen Sie sich die "Besprechungsaufzeichnung" an, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0ef42-129">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="0ef42-130">Einrichten der Option "Besprechungsaufzeichnung" für OneDrive for Business und SharePoint</span><span class="sxs-lookup"><span data-stu-id="0ef42-130">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="0ef42-131">Installieren Sie die PowerShell-Verwaltungskonsole von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0ef42-131">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="0ef42-132">a.</span><span class="sxs-lookup"><span data-stu-id="0ef42-132">a.</span></span> <span data-ttu-id="0ef42-133">Laden Sie [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)herunter.</span><span class="sxs-lookup"><span data-stu-id="0ef42-133">Download [Skype for Business Online Powershell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="0ef42-134">b.</span><span class="sxs-lookup"><span data-stu-id="0ef42-134">b.</span></span> <span data-ttu-id="0ef42-135">Folgen Sie den Anweisungen, um Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0ef42-135">Follow the prompts to install it.</span></span>

    <span data-ttu-id="0ef42-136">c.</span><span class="sxs-lookup"><span data-stu-id="0ef42-136">c.</span></span> <span data-ttu-id="0ef42-137">Starten Sie Ihren Computer neu.</span><span class="sxs-lookup"><span data-stu-id="0ef42-137">Restart your machine.</span></span>

2. <span data-ttu-id="0ef42-138">Starten von PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="0ef42-138">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="0ef42-139">Importieren Sie den SkypeOnline-Connector, und melden Sie sich als Teamadministrator an.</span><span class="sxs-lookup"><span data-stu-id="0ef42-139">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="0ef42-140">Verwenden Sie " [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) ", um eine Team-Besprechungsrichtlinie für den Übergang vom Datenstrom Speicher auf ODSP einzurichten.</span><span class="sxs-lookup"><span data-stu-id="0ef42-140">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="0ef42-141">Deaktivieren von OneDrive for Business und SharePoint, um den Datenstrom weiterhin verwenden zu können</span><span class="sxs-lookup"><span data-stu-id="0ef42-141">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="0ef42-142">Auch wenn eine Richtlinie besagt, dass Sie bereits auf **Stream**eingestellt ist, ist Sie möglicherweise nicht eingestellt.</span><span class="sxs-lookup"><span data-stu-id="0ef42-142">Even if a policy says it’s already set to **Stream**, it might not be set.</span></span> <span data-ttu-id="0ef42-143">Wenn Sie auf Nothing gesetzt ist, lautet der Standardwert Stream.</span><span class="sxs-lookup"><span data-stu-id="0ef42-143">If it's set to nothing, then the default is Stream.</span></span> <span data-ttu-id="0ef42-144">Wenn Sie die Deaktivierung durchführen möchten, **müssen** Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass der Datenstrom der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="0ef42-144">If you want to opt-out, you **must** reset the policy to **Stream** to ensure that Stream is the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="0ef42-145">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0ef42-145">Frequently asked questions</span></span>

<span data-ttu-id="0ef42-146">**Wo werden die Besprechungsaufzeichnungen gespeichert?**</span><span class="sxs-lookup"><span data-stu-id="0ef42-146">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="0ef42-147">Für Besprechungen ohne Kanal wird die Aufzeichnung in einem Ordner mit dem Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0ef42-147">For non-Channel meetings, the recording is stored in a folder named.</span></span> <span data-ttu-id="0ef42-148">Aufnahmen \* \*, das sich auf der obersten Ebene des OneDrive befindet, das der Person gehört, die die Besprechungsaufzeichnung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="0ef42-148">Recordings\*\* that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="0ef42-149">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ef42-149">Example:</span></span>

  <span data-ttu-id="0ef42-150"><i>Recorder-OneDrive for Business</i> / **Aufnahmen**</span><span class="sxs-lookup"><span data-stu-id="0ef42-150"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="0ef42-151">Bei Kanal Besprechungen wird die Aufzeichnung in der Bibliothek "Teams-Website Dokumentation" in einem Ordner mit dem Namen " **Aufzeichnungen**" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0ef42-151">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="0ef42-152">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0ef42-152">Example:</span></span>

  <span data-ttu-id="0ef42-153"><i>Name des Teams – Kanalname</i> / **Dokumente** / **Aufnahmen**</span><span class="sxs-lookup"><span data-stu-id="0ef42-153"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="0ef42-154">**Wer hat die Berechtigung zum Anzeigen der Besprechungsaufzeichnung?**</span><span class="sxs-lookup"><span data-stu-id="0ef42-154">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="0ef42-155">Für Besprechungen ohne Kanal wird für alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch ein Link persönlich freigegeben abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-155">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="0ef42-156">Externe Benutzer müssen explizit der freigegebenen Liste vom Besprechungsorganisator oder der Person hinzugefügt werden, die die Besprechungsaufzeichnung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="0ef42-156">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="0ef42-157">Bei Kanal Besprechungen werden Berechtigungen von der Liste Besitzer und Mitglieder des Kanals geerbt.</span><span class="sxs-lookup"><span data-stu-id="0ef42-157">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="0ef42-158">**Wie kann ich Protokolle verwalten?**</span><span class="sxs-lookup"><span data-stu-id="0ef42-158">**How can I manage transcripts?**</span></span>

<span data-ttu-id="0ef42-159">Kunden, die sich für diese Vorschau entscheiden, stehen in Ihren Team-Besprechungsaufzeichnungen, die zu OneDrive und SharePoint migriert werden, keine Untertitel zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0ef42-159">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="0ef42-160">Wir arbeiten daran, Beschriftungen hinzuzufügen, beginnend mit Untertiteln in Englisch, bis zu Besprechungsaufzeichnungen im Oktober 2020.</span><span class="sxs-lookup"><span data-stu-id="0ef42-160">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="0ef42-161">In Teams-Besprechungsaufzeichnungen stehen Untertitel für Kunden zur Verfügung, die sich für das Zulassen von Abschriften entschieden haben, wie in [Teams Cloud-Aufzeichnungen](cloud-recording.md) beschrieben</span><span class="sxs-lookup"><span data-stu-id="0ef42-161">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="0ef42-162">Beschriftungen tragen dazu bei, den Betrachter aller Fähigkeiten inklusiven Inhalt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-162">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="0ef42-163">Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Aufzeichnung weiterhin für Teams verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams.</span><span class="sxs-lookup"><span data-stu-id="0ef42-163">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="0ef42-164">Informationen [zum Aktivieren oder Deaktivieren von Besprechungsaufzeichnungen](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="0ef42-164">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="0ef42-165">Untertitel werden für Teams-Besprechungsaufzeichnungen für 60 Tage ab dem Zeitpunkt, zu dem die Besprechung aufgezeichnet wird, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0ef42-165">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="0ef42-166">**Auswirkungen auf das Speicherkontingent**</span><span class="sxs-lookup"><span data-stu-id="0ef42-166">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="0ef42-167">Teams, die Dateien aufzeichnen, Leben in OneDrive for Business und SharePoint und sind in Ihrem Kontingent für diese Dienste enthalten.</span><span class="sxs-lookup"><span data-stu-id="0ef42-167">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="0ef42-168">Siehe [SharePoint-Kontingent](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="0ef42-168">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="0ef42-169">**Wie kann ich eine Besprechungsaufzeichnung für Teams wiedergeben?**</span><span class="sxs-lookup"><span data-stu-id="0ef42-169">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="0ef42-170">Ihr Video wird auf dem Video Player von OneDrive for Business oder SharePoint wiedergegeben, je nachdem, wo Sie auf die Datei zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-170">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="0ef42-171">**Wenn Sie beabsichtigen, das Hinzufügen zu Datenstrom zu verwerfen, bleiben die vorhandenen Videos unverändert und für wie lange?**</span><span class="sxs-lookup"><span data-stu-id="0ef42-171">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="0ef42-172">Stream als Plattform wird in naher Zukunft nicht mehr als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="0ef42-172">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="0ef42-173">Die Videos, die aktuell in Stream vorhanden sind, bleiben dort, bis wir mit der Migration beginnen.</span><span class="sxs-lookup"><span data-stu-id="0ef42-173">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="0ef42-174">Bei der Migration werden diese Videos ebenfalls nach ODSP migriert.</span><span class="sxs-lookup"><span data-stu-id="0ef42-174">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="0ef42-175">Weitere Informationen finden Sie [hier](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="0ef42-175">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
