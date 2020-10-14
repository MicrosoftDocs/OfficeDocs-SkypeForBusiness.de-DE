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
ms.openlocfilehash: 83a7a0628d76a96318081ec51a039d458ea1570f
ms.sourcegitcommit: c48a5aca37220ac6a797ac88b09cf80090b1b7df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48444231"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a><span data-ttu-id="49a77-103">Verwenden von OneDrive for Business und SharePoint oder Stream für Besprechungsaufzeichnungen</span><span class="sxs-lookup"><span data-stu-id="49a77-103">Use OneDrive for Business and SharePoint or Stream for meeting recordings</span></span>

> [!Note]
> <span data-ttu-id="49a77-104">Die Änderung von der Verwendung von Microsoft Stream zu OneDrive for Business und Microsoft SharePoint für Besprechungsaufzeichnungen ist ein Phasen orientierter Ansatz.</span><span class="sxs-lookup"><span data-stu-id="49a77-104">The change from using Microsoft Stream to OneDrive for Business and Microsoft SharePoint for meeting recordings will be a phased approach.</span></span>

|||
|---|-----------------|
|<span data-ttu-id="49a77-105">Datum</span><span class="sxs-lookup"><span data-stu-id="49a77-105">Date</span></span>|<span data-ttu-id="49a77-106">Ereignis</span><span class="sxs-lookup"><span data-stu-id="49a77-106">Event</span></span>|
|<span data-ttu-id="49a77-107">Frühes Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="49a77-107">Early Q4 CY20</span></span>|<span data-ttu-id="49a77-108">**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint, die für Opt-in oder Opt-out verfügbar sind.**</span><span class="sxs-lookup"><span data-stu-id="49a77-108">**Teams meeting recording on OneDrive for Business and SharePoint available for opt in or opt out.**</span></span><br> <span data-ttu-id="49a77-109">Mandantenadministratoren können die OneDrive for Business-und SharePoint-Einstellungen für die Team Richtlinie in PowerShell aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="49a77-109">Tenant admins can opt in  or opt out of OneDrive for Business and SharePoint setting the Teams policy in PowerShell</span></span>|
|<span data-ttu-id="49a77-110">Mid Q4 CY20</span><span class="sxs-lookup"><span data-stu-id="49a77-110">Mid Q4 CY20</span></span>|<span data-ttu-id="49a77-111">**Teams-Besprechungsaufzeichnung auf OneDrive for Business und SharePoint als Standardeinstellung für Mandanten, die sich nicht abmelden**</span><span class="sxs-lookup"><span data-stu-id="49a77-111">**Teams meeting recording on OneDrive for Business and SharePoint set as default for tenants who don't opt out**</span></span><br> <span data-ttu-id="49a77-112">Dies ist der empfohlene Pfad für die meisten Kunden.</span><span class="sxs-lookup"><span data-stu-id="49a77-112">This is the  recommended path for most customers</span></span>|
<span data-ttu-id="49a77-113">Q1 CY21</span><span class="sxs-lookup"><span data-stu-id="49a77-113">Q1 CY21</span></span>|<span data-ttu-id="49a77-114">**Speichern der Besprechungsaufzeichnung für Teams im klassischen Datenstrom nicht mehr zulässig**</span><span class="sxs-lookup"><span data-stu-id="49a77-114">**Saving Teams meeting recording to Classic Stream no longer allowed**</span></span><br><span data-ttu-id="49a77-115">Alle Mandanten speichern die Besprechungsaufzeichnung für Teams in OneDrive for Business und SharePoint.</span><span class="sxs-lookup"><span data-stu-id="49a77-115">All tenants will save Teams meeting recording to OneDrive for Business and SharePoint</span></span>|
|||

<span data-ttu-id="49a77-116">Microsoft Teams hat eine neue Methode zum Speichern von Besprechungsaufzeichnungen.</span><span class="sxs-lookup"><span data-stu-id="49a77-116">Microsoft Teams has a new method for saving meeting recordings.</span></span> <span data-ttu-id="49a77-117">Als erste Phase des Übergangs vom klassischen Microsoft-Stream auf den [neuen Datenstrom](https://docs.microsoft.com/stream/streamnew/new-stream)speichert diese Methode Aufnahmen auf Microsoft OneDrive und SharePoint in Microsoft 365 und bietet zahlreiche Vorteile.</span><span class="sxs-lookup"><span data-stu-id="49a77-117">As the first phase of a transition from classic Microsoft Stream to the [new Stream](https://docs.microsoft.com/stream/streamnew/new-stream), this method stores recordings on Microsoft OneDrive and SharePoint in Microsoft 365 and offers many benefits.</span></span>

<span data-ttu-id="49a77-118">Zu den Vorteilen der Verwendung von OneDrive for Business und SharePoint für das Speichern von Aufzeichnungen gehören:</span><span class="sxs-lookup"><span data-stu-id="49a77-118">The benefits of using OneDrive for Business and SharePoint for storing recordings include:</span></span>

- <span data-ttu-id="49a77-119">Aufbewahrungsrichtlinien für Teams-Besprechungsaufzeichnung (TMR) (S + C E5-autoaufbewahrungs Etiketten)</span><span class="sxs-lookup"><span data-stu-id="49a77-119">Retention policies for Teams meeting recording (TMR) (S+C E5 autoretention labels)</span></span>
- <span data-ttu-id="49a77-120">Profitieren Sie von OneDrive for Business und SharePoint-Informations-Governance</span><span class="sxs-lookup"><span data-stu-id="49a77-120">Benefit from OneDrive for Business and SharePoint information governance</span></span>
- <span data-ttu-id="49a77-121">Einfaches Einrichten von Berechtigungen und Freigabe</span><span class="sxs-lookup"><span data-stu-id="49a77-121">Easy to set permissions and sharing</span></span>
- <span data-ttu-id="49a77-122">Freigeben von Aufzeichnungen für Gäste (externe Benutzer) mit expliziter Freigabe</span><span class="sxs-lookup"><span data-stu-id="49a77-122">Share recordings with guests (external users) with explicit share only</span></span>
- <span data-ttu-id="49a77-123">Zugriffs Fluss anfordern</span><span class="sxs-lookup"><span data-stu-id="49a77-123">Request access flow</span></span>
- <span data-ttu-id="49a77-124">Bereitstellen von OneDrive for Business-und SharePoint-freigegebenen Links</span><span class="sxs-lookup"><span data-stu-id="49a77-124">Provide OneDrive for Business and SharePoint shared links</span></span>
- <span data-ttu-id="49a77-125">Höhere Kontingente</span><span class="sxs-lookup"><span data-stu-id="49a77-125">Increased quota</span></span>
- <span data-ttu-id="49a77-126">Besprechungsaufzeichnungen sind schneller verfügbar</span><span class="sxs-lookup"><span data-stu-id="49a77-126">Meeting  recordings are available faster</span></span>
- <span data-ttu-id="49a77-127">Support für **lokale** Mandanten</span><span class="sxs-lookup"><span data-stu-id="49a77-127">**Go local** tenant support</span></span>
- <span data-ttu-id="49a77-128">Multi-Geo-Unterstützung – Aufzeichnungen werden in einer für diesen benutzerspezifischen Region gespeichert.</span><span class="sxs-lookup"><span data-stu-id="49a77-128">Multi-geo support – recordings are stored in a region specific to that user</span></span>
- <span data-ttu-id="49a77-129">Unterstützung für Ihren eigenen Schlüssel (BYOK)</span><span class="sxs-lookup"><span data-stu-id="49a77-129">Bring your own key (BYOK) support</span></span>
- <span data-ttu-id="49a77-130">Verbesserte Transkriptions Qualität und Sprecher Zuordnung</span><span class="sxs-lookup"><span data-stu-id="49a77-130">Improved Transcript quality and speaker attribution</span></span>

<span data-ttu-id="49a77-131">Es gibt einige Einschränkungen, die berücksichtigt werden sollten:</span><span class="sxs-lookup"><span data-stu-id="49a77-131">There are some limitations to consider:</span></span>

- <span data-ttu-id="49a77-132">Es werden nur Englisch-Untertitel und-Transkripte vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="49a77-132">There will be English-only closed captions and transcripts.</span></span>
- <span data-ttu-id="49a77-133">Sie können keine Transkripte oder deren Inhalt durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="49a77-133">You won't be able to search transcripts or their content.</span></span>
- <span data-ttu-id="49a77-134">Sie können die Transkripte nicht bearbeiten, aber Sie können die Beschriftungen aus-und einschalten.</span><span class="sxs-lookup"><span data-stu-id="49a77-134">You won’t be able to edit the transcripts, but you'll be able to toggle captions off/on.</span></span>
- <span data-ttu-id="49a77-135">Sie können steuern, mit wem Sie die Aufzeichnung freigeben, aber Sie können Personen mit freigegebenen Zugriff nicht blockieren, indem Sie die Aufzeichnung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="49a77-135">You can control with whom you share the recording, but you won't be able to block people with shared access from downloading the recording.</span></span>
- <span data-ttu-id="49a77-136">Wenn die Aufzeichnung die Speicherung beendet hat, wird keine e-Mail angezeigt, aber die Aufzeichnung wird nach Abschluss des Besprechungs Chats angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49a77-136">You'll not get an email when the recording finishes saving, but the recording will appear in the meeting chat once it’s finished.</span></span> <span data-ttu-id="49a77-137">Dies geschieht viel schneller als in Stream zuvor.</span><span class="sxs-lookup"><span data-stu-id="49a77-137">This will happen much quicker than it did in Stream previously</span></span>

<span data-ttu-id="49a77-138">Schauen Sie sich die "Besprechungsaufzeichnung" an, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="49a77-138">Watch "Meeting Recording" for more information.</span></span>

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a><span data-ttu-id="49a77-139">Einrichten der Option "Besprechungsaufzeichnung" für OneDrive for Business und SharePoint</span><span class="sxs-lookup"><span data-stu-id="49a77-139">Set up the meeting recording option for OneDrive for Business and SharePoint</span></span>

1. <span data-ttu-id="49a77-140">Installieren Sie die PowerShell-Verwaltungskonsole von Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="49a77-140">Install the Skype For Business Online PowerShell admin console.</span></span>

    <span data-ttu-id="49a77-141">a.</span><span class="sxs-lookup"><span data-stu-id="49a77-141">a.</span></span> <span data-ttu-id="49a77-142">Laden Sie [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide)herunter.</span><span class="sxs-lookup"><span data-stu-id="49a77-142">Download [Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).</span></span>

    <span data-ttu-id="49a77-143">b.</span><span class="sxs-lookup"><span data-stu-id="49a77-143">b.</span></span> <span data-ttu-id="49a77-144">Folgen Sie den Anweisungen, um Sie zu installieren.</span><span class="sxs-lookup"><span data-stu-id="49a77-144">Follow the prompts to install it.</span></span>

    <span data-ttu-id="49a77-145">c.</span><span class="sxs-lookup"><span data-stu-id="49a77-145">c.</span></span> <span data-ttu-id="49a77-146">Starten Sie Ihren Computer neu.</span><span class="sxs-lookup"><span data-stu-id="49a77-146">Restart your machine.</span></span>

2. <span data-ttu-id="49a77-147">Starten von PowerShell als Administrator</span><span class="sxs-lookup"><span data-stu-id="49a77-147">Launch PowerShell as an admin</span></span>

3. <span data-ttu-id="49a77-148">Importieren Sie den SkypeOnline-Connector, und melden Sie sich als Teamadministrator an.</span><span class="sxs-lookup"><span data-stu-id="49a77-148">Import the SkypeOnline Connector and log in as a Teams admin.</span></span>

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. <span data-ttu-id="49a77-149">Verwenden Sie " [csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) ", um eine Team-Besprechungsrichtlinie für den Übergang vom Datenstrom Speicher auf ODSP einzurichten.</span><span class="sxs-lookup"><span data-stu-id="49a77-149">Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) to set a Teams Meeting Policy to transition from the Stream storage to ODSP.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a><span data-ttu-id="49a77-150">Deaktivieren von OneDrive for Business und SharePoint, um den Datenstrom weiterhin verwenden zu können</span><span class="sxs-lookup"><span data-stu-id="49a77-150">Opt out of OneDrive for Business and SharePoint to continue using Stream</span></span>

<span data-ttu-id="49a77-151">Auch wenn eine Richtlinie besagt, dass Sie auf **Stream**eingestellt ist, ist Sie möglicherweise nicht eingestellt.</span><span class="sxs-lookup"><span data-stu-id="49a77-151">Even if a policy says it's set to **Stream**, it might not be set.</span></span> <span data-ttu-id="49a77-152">In der Regel ist die Standardeinstellung **Stream**, wenn die Richtlinie nicht festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="49a77-152">Typically, if the policy isn't set, then the default setting is **Stream**.</span></span> <span data-ttu-id="49a77-153">Wenn Sie jedoch die Verwendung von SharePoint oder OneDrive deaktivieren möchten, müssen Sie die Richtlinie auf **Stream** zurücksetzen, um sicherzustellen, dass Sie die Standardeinstellung ist, wenn Sie diese neue Änderung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="49a77-153">However, with this new change, if you want to opt-out of using SharePoint or OneDrive, then you must reset the policy to **Stream** to ensure that it's the default.</span></span>

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a><span data-ttu-id="49a77-154">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="49a77-154">Frequently asked questions</span></span>

<span data-ttu-id="49a77-155">**Wo werden die Besprechungsaufzeichnungen gespeichert?**</span><span class="sxs-lookup"><span data-stu-id="49a77-155">**Where will the meeting recording be stored?**</span></span>

- <span data-ttu-id="49a77-156">Bei nicht Kanal Besprechungen wird die Aufzeichnung in einem Ordner mit dem Namen **Aufzeichnungen** gespeichert, der sich auf der obersten Ebene des OneDrive befindet, das der Person gehört, die die Besprechungsaufzeichnung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="49a77-156">For non-Channel meetings, the recording is stored in a folder named **Recordings** that is at the top level of the OneDrive that belongs to the person who started the meeting recording.</span></span> <span data-ttu-id="49a77-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="49a77-157">Example:</span></span>

  <span data-ttu-id="49a77-158"><i>Recorder-OneDrive for Business</i> / **Aufnahmen**</span><span class="sxs-lookup"><span data-stu-id="49a77-158"><i>recorder's OneDrive for Business</i>/**Recordings**</span></span>

- <span data-ttu-id="49a77-159">Bei Kanal Besprechungen wird die Aufzeichnung in der Bibliothek "Teams-Website Dokumentation" in einem Ordner mit dem Namen " **Aufzeichnungen**" gespeichert.</span><span class="sxs-lookup"><span data-stu-id="49a77-159">For Channel meetings, the recording is stored in the Teams site documentation library in a folder named **Recordings**.</span></span> <span data-ttu-id="49a77-160">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="49a77-160">Example:</span></span>

  <span data-ttu-id="49a77-161"><i>Name des Teams – Kanalname</i> / **Dokumente** / **Aufnahmen**</span><span class="sxs-lookup"><span data-stu-id="49a77-161"><i>Teams name - Channel name</i>/**Documents**/**Recordings**</span></span>

<span data-ttu-id="49a77-162">**Wie behandle ich Aufnahmen von ehemaligen Mitarbeitern?**</span><span class="sxs-lookup"><span data-stu-id="49a77-162">**How do I handle recordings from former employees?**</span></span>

<span data-ttu-id="49a77-163">Da Videos genauso wie jede andere Datei in OneDrive und SharePoint sind, folgt die Behandlung von Besitz und Aufbewahrung nach dem Verlassen eines Mitarbeiters dem normalen [OneDrive-und SharePoint-Prozess]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span><span class="sxs-lookup"><span data-stu-id="49a77-163">Since videos are just like any other file in OneDrive and SharePoint, handling ownership and retention after an employee leaves will follow the normal [OneDrive and SharePoint process]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).</span></span>

<span data-ttu-id="49a77-164">**Wer hat die Berechtigung zum Anzeigen der Besprechungsaufzeichnung?**</span><span class="sxs-lookup"><span data-stu-id="49a77-164">**Who has the permissions to view the meeting recording?**</span></span>

- <span data-ttu-id="49a77-165">Für Besprechungen ohne Kanal wird für alle Besprechungsteilnehmer, mit Ausnahme externer Benutzer, automatisch ein Link persönlich freigegeben abgerufen.</span><span class="sxs-lookup"><span data-stu-id="49a77-165">For non-Channel meetings, all meeting invitees, except for external users, will automatically get a personally shared link.</span></span> <span data-ttu-id="49a77-166">Externe Benutzer müssen explizit der freigegebenen Liste vom Besprechungsorganisator oder der Person hinzugefügt werden, die die Besprechungsaufzeichnung gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="49a77-166">External users will need to be explicitly added to the shared list by the meeting organizer or the person who started the meeting recording.</span></span>

- <span data-ttu-id="49a77-167">Bei Kanal Besprechungen werden Berechtigungen von der Liste Besitzer und Mitglieder des Kanals geerbt.</span><span class="sxs-lookup"><span data-stu-id="49a77-167">For Channel meetings, permissions are inherited from the owners and members list in the channel.</span></span>

<span data-ttu-id="49a77-168">**Wie kann ich Protokolle verwalten?**</span><span class="sxs-lookup"><span data-stu-id="49a77-168">**How can I manage transcripts?**</span></span>

<span data-ttu-id="49a77-169">Kunden, die sich für diese Vorschau entscheiden, stehen in Ihren Team-Besprechungsaufzeichnungen, die zu OneDrive und SharePoint migriert werden, keine Untertitel zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="49a77-169">Customers opting in to this preview will not have closed captions available on their Teams Meeting Recordings that are migrated to OneDrive and SharePoint.</span></span><span data-ttu-id="49a77-170">Wir arbeiten daran, Beschriftungen hinzuzufügen, beginnend mit Untertiteln in Englisch, bis zu Besprechungsaufzeichnungen im Oktober 2020.</span><span class="sxs-lookup"><span data-stu-id="49a77-170">  We're working to add captioning, beginning with closed captions in English, to meeting recordings in October 2020.</span></span>

<span data-ttu-id="49a77-171">In Teams-Besprechungsaufzeichnungen stehen Untertitel für Kunden zur Verfügung, die sich für das Zulassen von Abschriften entschieden haben, wie in [Teams Cloud-Aufzeichnungen](cloud-recording.md) beschrieben</span><span class="sxs-lookup"><span data-stu-id="49a77-171">Closed captions will be available on Teams Meeting Recordings for customers who have opted in to allow transcripts as described in [Teams cloud recordings](cloud-recording.md)</span></span>

<span data-ttu-id="49a77-172">Beschriftungen tragen dazu bei, den Betrachter aller Fähigkeiten inklusiven Inhalt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="49a77-172">Captions help create inclusive content for viewers of all abilities.</span></span> <span data-ttu-id="49a77-173">Als Besitzer können Sie Beschriftungen ausblenden, obwohl die Aufzeichnung weiterhin für Teams verfügbar ist, es sei denn, Sie löschen die Beschriftungen aus Teams.</span><span class="sxs-lookup"><span data-stu-id="49a77-173">As an owner, you can hide captions, although the transcript will still be available on Teams unless you delete the captions from Teams.</span></span> <span data-ttu-id="49a77-174">Informationen [zum Aktivieren oder Deaktivieren von Besprechungsaufzeichnungen](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="49a77-174">See [how to turn on or off meeting recordings](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)</span></span>

<span data-ttu-id="49a77-175">Untertitel werden für Teams-Besprechungsaufzeichnungen für 60 Tage ab dem Zeitpunkt, zu dem die Besprechung aufgezeichnet wird, unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49a77-175">Closed captions are supported for Teams meeting recordings for 60 days from when the meeting is recorded.</span></span>

<span data-ttu-id="49a77-176">**Auswirkungen auf das Speicherkontingent**</span><span class="sxs-lookup"><span data-stu-id="49a77-176">**How will my storage quota be impacted**</span></span>

<span data-ttu-id="49a77-177">Teams, die Dateien aufzeichnen, Leben in OneDrive for Business und SharePoint und sind in Ihrem Kontingent für diese Dienste enthalten.</span><span class="sxs-lookup"><span data-stu-id="49a77-177">Teams meeting recording files live in OneDrive for Business and SharePoint and are included in your quota for those services.</span></span> <span data-ttu-id="49a77-178">Siehe [SharePoint-Kontingent](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) und [OneDrive for Business-Kontingent] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .</span><span class="sxs-lookup"><span data-stu-id="49a77-178">See [SharePoint quota](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) and [OneDrive for Business quota] (https://docs.microsoft.com/onedrive/set-default-storage-space).</span></span>

<span data-ttu-id="49a77-179">**Wie kann ich eine Besprechungsaufzeichnung für Teams wiedergeben?**</span><span class="sxs-lookup"><span data-stu-id="49a77-179">**How can I play a Teams meeting recording?**</span></span>

<span data-ttu-id="49a77-180">Ihr Video wird auf dem Video Player von OneDrive for Business oder SharePoint wiedergegeben, je nachdem, wo Sie auf die Datei zugreifen.</span><span class="sxs-lookup"><span data-stu-id="49a77-180">Your video will play on the video player of OneDrive for Business or SharePoint depending on where you access the file.</span></span>

<span data-ttu-id="49a77-181">**Wenn Sie beabsichtigen, das Hinzufügen zu Datenstrom zu verwerfen, bleiben die vorhandenen Videos unverändert und für wie lange?**</span><span class="sxs-lookup"><span data-stu-id="49a77-181">**If you plan on deprecating adding to Stream, will existing videos stay as is and for how long?**</span></span>

<span data-ttu-id="49a77-182">Stream als Plattform wird in naher Zukunft nicht mehr als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="49a77-182">Stream as a platform won't be deprecated in the near future.</span></span> <span data-ttu-id="49a77-183">Die Videos, die aktuell in Stream vorhanden sind, bleiben dort, bis wir mit der Migration beginnen.</span><span class="sxs-lookup"><span data-stu-id="49a77-183">The videos that currently live in Stream will stay there until we start migrating.</span></span> <span data-ttu-id="49a77-184">Bei der Migration werden diese Videos ebenfalls nach ODSP migriert.</span><span class="sxs-lookup"><span data-stu-id="49a77-184">Upon migration, those videos will be migrated to ODSP as well.</span></span> <span data-ttu-id="49a77-185">Weitere Informationen finden Sie [hier](https://docs.microsoft.com/stream/streamnew/classic-migration) .</span><span class="sxs-lookup"><span data-stu-id="49a77-185">Check [here](https://docs.microsoft.com/stream/streamnew/classic-migration) for more information.</span></span>
