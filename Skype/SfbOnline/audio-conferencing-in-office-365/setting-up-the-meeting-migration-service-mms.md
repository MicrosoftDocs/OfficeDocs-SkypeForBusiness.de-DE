---
title: Einrichten des Meeting Migration Service (MMS)
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 031f09c0-9d2a-487a-b6db-b5d4bed6d16a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Meeting Migration Service (MMS) ist ein Skype for Business-Dienst, der im Hintergrund ausgeführt wird und Skype for Business- und Microsoft Teams-Besprechungen automatisch für die Benutzer aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.
ms.openlocfilehash: e240d9913ac543495286d8151bc0200a0f7c196d
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="setting-up-the-meeting-migration-service-mms"></a><span data-ttu-id="c1ade-104">Einrichten des Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="c1ade-104">Setting up the Meeting Migration Service (MMS)</span></span>

<span data-ttu-id="c1ade-p102">Meeting Migration Service (MMS) ist ein Skype for Business-Dienst, der im Hintergrund ausgeführt wird und Skype for Business- und Microsoft Teams-Besprechungen automatisch für die Benutzer aktualisiert. Mit MMS brauchen die Benutzer nicht mehr Meeting Migration Tool auszuführen, um ihre Skype for Business- und Microsoft Teams-Besprechungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p102">Meeting Migration Service (MMS) is a Skype for Business service that runs in the background and automatically updates Skype for Business and Microsoft Teams meetings for users. MMS is designed to eliminate the need for users to run the Meeting Migration Tool to update their Skype for Business and Microsoft Teams meetings.</span></span>
  
 <span data-ttu-id="c1ade-107">**Anforderungen**</span><span class="sxs-lookup"><span data-stu-id="c1ade-107">**Requirements**</span></span>
  
<span data-ttu-id="c1ade-108">Für MMS müssen sich die Postfächer der Besprechungsorganisatoren in Exchange Online befinden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-108">MMS requires the mailboxes of meeting organizers to be on Exchange Online.</span></span>
  
 <span data-ttu-id="c1ade-109">**Primäre Szenarien**</span><span class="sxs-lookup"><span data-stu-id="c1ade-109">**Primary scenarios**</span></span>
  
<span data-ttu-id="c1ade-110">MMS aktualisiert Skype-Besprechungen für einen Benutzer in den folgenden beiden primären Szenarien:</span><span class="sxs-lookup"><span data-stu-id="c1ade-110">MMS updates Skype meetings for a user in the following two primary scenarios:</span></span>
  
- <span data-ttu-id="c1ade-111">Der Benutzer wird von einer lokalen Skype for Business Server-Instanz zu Skype for Business Online migriert.</span><span class="sxs-lookup"><span data-stu-id="c1ade-111">When the user is migrated from on-premises Skype for Business Server to Skype for Business Online.</span></span>
    
- <span data-ttu-id="c1ade-112">Ein Administrator nimmt eine Änderung an den Audiokonferenzeinstellungen des Benutzers vor, die eine Aktualisierung der Audiokonferenzinformationen dieses Benutzers erfordern würde.</span><span class="sxs-lookup"><span data-stu-id="c1ade-112">When an admin makes a change to the user's audio conferencing settings that would require updating the audio conferencing information in that user's meetings.</span></span>
    
 <span data-ttu-id="c1ade-113">**Häufige Szenarien, in denen MMS nicht verwendet werden kann**</span><span class="sxs-lookup"><span data-stu-id="c1ade-113">**Common scenarios where you can't use MMS**</span></span>
  
<span data-ttu-id="c1ade-p103">Im Folgenden werden einige häufige Szenarien vorgestellt, die auf Sie zutreffen könnten. Bei allen handelt es sich um unterstützte Szenarien für die Migration. MMS kann in diesen Szenarien allerdings nicht ausgeführt werden, und Sie müssen stattdessen das [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p103">Here are some common scenarios that may apply to you. These are all supported scenarios for migration. However, MMS won't run in these scenarios and you'll need to use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) instead.</span></span>
  
- <span data-ttu-id="c1ade-117">Die Benutzerpostfächer befinden sich auf einem lokalen Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c1ade-117">User mailboxes are on Exchange Server on-premises</span></span>
    
- <span data-ttu-id="c1ade-118">Verwenden eines Drittanbieters für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="c1ade-118">Using a third-party audio conferencing provider</span></span>
    
- <span data-ttu-id="c1ade-119">Migrieren von Benutzern von Skype for Business Online zu einem lokalen Skype-Server</span><span class="sxs-lookup"><span data-stu-id="c1ade-119">Migrating users from Skype for Business Online to on-premises Skype Server</span></span>
    
## <a name="updating-meetings-when-an-on-premises-user-is-migrated-to-skype-for-business-online"></a><span data-ttu-id="c1ade-120">Aktualisieren von Besprechungen, wenn ein lokaler Benutzer zu Skype for Business Online migriert wird</span><span class="sxs-lookup"><span data-stu-id="c1ade-120">Updating meetings when an on-premises user is migrated to Skype for Business Online</span></span>

<span data-ttu-id="c1ade-p104">Dies ist das häufigste Szenario, in dem MMS dazu beitragen kann, dass die Umstellung für Ihre Benutzer reibungslos verläuft. Wenn ein Benutzer von einer lokalen Skype for Business Server-Instanz zu Skype for Business Online migriert wird, erkennt MMS den neuen Benutzer und scannt den Kalender des Benutzers nach Skype for Business- und Microsoft Teams-Besprechungen. Alle zukünftigen Besprechungen werden mit den neuen Informationen für diesen Benutzer aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p104">This is the most common scenario where MMS can help create a smoother transition for your users. When a user is migrated from an on-premises Skype for Business Server to Skype for Business Online, MMS will detect the new user and will scan that user's calendar for Skype for Business and Microsoft Teams meetings. Any future meetings will be updated with the new information for that user.</span></span>
  
### <a name="if-youre-currently-using-skype-server-2015-for-audio-conferencing"></a><span data-ttu-id="c1ade-124">Wenn Sie zurzeit Skype Server 2015 für Audiokonferenzen verwenden</span><span class="sxs-lookup"><span data-stu-id="c1ade-124">If you're currently using Skype Server 2015 for audio conferencing</span></span>

<span data-ttu-id="c1ade-125">Es wird empfohlen, den bewährten Methoden unten zu folgen, um in diesem Szenario größtmögliche Benutzerfreundlichkeit bei Verwendung von MMS zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-125">We recommend that you follow the best practices below for the best experience with MMS in this scenario:</span></span>
  
- <span data-ttu-id="c1ade-126">Da es für MMS erforderlich ist, dass sich das Postfach des Benutzers auf Exchange Online befindet, sollten Sie, wenn Sie auch von einem lokalen Exchange Server migrieren, das Postfach des Benutzers zuerst zu Exchange Online verschieben.</span><span class="sxs-lookup"><span data-stu-id="c1ade-126">Because MMS requires the user's mailbox to be on Exchange Online, if you are also migrating from on-premises Exchange Server as well, move the user's mailbox to Exchange Online first.</span></span>
    
- <span data-ttu-id="c1ade-p105">Weisen Sie dem Benutzer die Lizenz für **Audiokonferenzen** zu, bevor Sie das `Move-CSUser`-Cmdlet zum Migrieren des Benutzers ausführen. Der Grund ist, dass MMS Besprechungen auch aktualisiert, wenn Audiokonferenzeinstellungen für einen Benutzer geändert werden. Wenn Sie die Lizenz nicht zuerst zuweisen, aktualisiert MMS alle Besprechungen erneut, nachdem Sie die Lizenz zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p105">Assign the **Audio Conferencing** license to the user before you run the `Move-CSUser` cmdlet to migrate the user. This is because MMS also updates meetings when audio conferencing settings are changed for a user. If you don't assign the license first, MMS will update all meetings again when you assign the license.</span></span>
    
### <a name="if-youre-currently-using-a-third-party-audio-conferencing-provider-acp"></a><span data-ttu-id="c1ade-130">Wenn Sie derzeit einen externen Audiokonferenzanbieter (ACP) verwenden</span><span class="sxs-lookup"><span data-stu-id="c1ade-130">If you're currently using a third-party audio conferencing provider (ACP)</span></span>

<span data-ttu-id="c1ade-p106">Im Fall eines Drittanbieter-ACP hängt es von den Audiokonferenzeinstellungen Ihrer Organisation ab, ob MMS ausgeführt wird oder nicht. Sie können wählen, die Einwahlnummern von Ihrem ACP automatisch zu ersetzen, wenn Sie einem Benutzer eine Lizenz für **Audiokonferenzen** zuweisen. Andererseits müssen Sie dies möglicherweise verhindern und die Einwahlnummern Ihres ACP beibehalten. Um die Einstellung Ihrer Organisation anzuzeigen, führen Sie den folgenden Windows PowerShell-Befehl aus, und überprüfen Sie den Wert des Parameters `AutomaticallyReplaceAcpProvider`. Wenn Sie Hilfe mit PowerShell benötigen, finden Sie weitere Informationen im Abschnitt [Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation](setting-up-the-meeting-migration-service-mms.md#WPSInfo) am Ende dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p106">With a third-party ACP, whether or not MMS runs depends on your organization's audio conferencing settings. You can choose to automatically replace the dial-in numbers from your ACP when you assign a user a **Audio Conferencing** license. On the other hand, you may need to prevent that from happening and retain the dial-in numbers from your ACP. To see your organization's setting, run the following Windows PowerShell command and check the value of the parameter `AutomaticallyReplaceAcpProvider`. If you need help with PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

- <span data-ttu-id="c1ade-p107">Wenn der Wert dieses Parameters $true lautet, wird MMS ausgeführt, wenn einem Benutzer eine Lizenz für **Audiokonferenzen** zugewiesen wird, und dessen Besprechungen werden aktualisiert. Die Einwahlnummern von Ihrem ACP werden beibehalten, bis die Lizenz für **Audiokonferenzen** zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p107">If the value of this parameter is $true, then MMS will run when a user is assigned a **Audio Conferencing** license and update their meetings. The dial-in numbers from your ACP are retained until the **Audio Conferencing** license is assigned.</span></span>
    
- <span data-ttu-id="c1ade-p108">Wenn der Wert dieses Parameters $false lautet, aktualisiert MMS die Besprechungen nicht, selbst wenn einem Benutzer eine Lizenz für **Audiokonferenzen** zugewiesen wird. Die Einwahlnummern von Ihrem ACP werden beibehalten, bis der Benutzer im Skype for Business Admin Center oder über Windows PowerShell manuell für Audiokonferenzen bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p108">If the value of this parameter is $false, then MMS won't update the meetings even if a user is assigned a **Audio Conferencing** licence. The dial-in numbers from your ACP are retained until the user is manually provisioned for audio conferencing in Skype for Business admin center or using Windows PowerShell.</span></span>
    
## <a name="updating-meetings-when-a-users-audio-conferencing-settings-change"></a><span data-ttu-id="c1ade-140">Aktualisieren von Besprechungen, wenn sich die Audiokonferenzeinstellungen eines Benutzers ändern</span><span class="sxs-lookup"><span data-stu-id="c1ade-140">Updating meetings when a user's audio conferencing settings change</span></span>

<span data-ttu-id="c1ade-141">MMS aktualisiert die vorhandenen Skype for Business- und Microsoft Teams-Besprechungen in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-141">MMS will update an existing Skype for Business and Microsoft Teams meetings in the following cases:</span></span>
  
- <span data-ttu-id="c1ade-142">Wenn Sie eine Lizenz für **Audiokonferenzen** zuweisen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="c1ade-142">When you assign or remove **Audio Conferencing** license.</span></span>
    
- <span data-ttu-id="c1ade-143">Wenn Sie Audiokonferenzen aktivieren oder deaktivieren</span><span class="sxs-lookup"><span data-stu-id="c1ade-143">When you enable or disable audio conferencing.</span></span>
    
- <span data-ttu-id="c1ade-144">Wenn Sie die Konferenzkennung eines Benutzers, der für die Verwendung öffentlicher Besprechungen konfiguriert ist, ändern oder zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="c1ade-144">When you change or reset the Conference ID for a user configured to use public meetings.</span></span>
    
- <span data-ttu-id="c1ade-145">Wenn Sie den Benutzer zu einer neuen Audiokonferenzbrücke verschieben</span><span class="sxs-lookup"><span data-stu-id="c1ade-145">When you move the user to a new audio conferencing bridge.</span></span>
    
- <span data-ttu-id="c1ade-p109">Wenn die Zuweisung einer Telefonnummer zu einer Audiokonferenzbrücke aufgehoben wird. Dies ist ein komplexes Szenario, für das zusätzliche Schritte erforderlich sind. Weitere Informationen finden Sie unter [Ändern der gebührenpflichtigen oder gebührenfreien Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="c1ade-p109">When a phone number is unassigned from a audio conferencing bridge. This is a complex scenario which requires additional steps. For more information, see [Change the toll or toll free numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="c1ade-p110">MMS aktualisiert Besprechungen nur, wenn Sie die Microsoft-Brücke verwenden. Wenn Sie einen Drittanbieter für Audiokonferenzen verwenden, müssen die Benutzer ihre Besprechungen manuell aktualisieren. In diesem Fall können Sie [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p110">MMS only updates meetings when you're using the Microsoft bridge. If you are using a third-party audio conferencing provider, the users will need to update their meetings manually. In this case, you can use the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047).</span></span> 
  
<span data-ttu-id="c1ade-p111">Nicht alle Änderungen an den Audiokonferenzeinstellungen eines Benutzers lösen MMS aus. Insbesondere die folgenden beiden Änderungen führen nicht dazu, dass MMS Besprechungen aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="c1ade-p111">Not all changes to a user's audio conferencing settings trigger MMS. Specifically, the following two changes won't result in MMS updating meetings:</span></span>
  
- <span data-ttu-id="c1ade-154">Ändern der SIP-Adresse für den Besprechungsorganisator (entweder des SIP-Benutzernamens oder der SIP-Domäne)</span><span class="sxs-lookup"><span data-stu-id="c1ade-154">When you change the SIP address for the meeting organizer (either their SIP user name or their SIP domain)</span></span>
    
- <span data-ttu-id="c1ade-155">Ändern der Besprechungs-URL Ihrer Organisation anhand des Befehls [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442).</span><span class="sxs-lookup"><span data-stu-id="c1ade-155">When you change your organization's meeting URL using the [Update-CsTenantMeetingUrl](https://go.microsoft.com/fwlink/p/?linkid=836442) command.</span></span>
    
## <a name="what-happens-when-mms-updates-meetings"></a><span data-ttu-id="c1ade-156">Was geschieht, wenn MMS Besprechungen aktualisiert?</span><span class="sxs-lookup"><span data-stu-id="c1ade-156">What happens when MMS updates meetings?</span></span>

<span data-ttu-id="c1ade-157">Wenn MMS feststellt, dass die Besprechungen eines Benutzers aktualisiert werden müssen, werden folgende Schritte ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="c1ade-157">When MMS detects that a user's meetings need to be updated, it will do the following:</span></span>
  
1. <span data-ttu-id="c1ade-158">Identifizieren aller Skype for Business- und Microsoft Teams-Besprechungen, die der Benutzer in der Zukunft geplant hat</span><span class="sxs-lookup"><span data-stu-id="c1ade-158">Identify all Skype for Business and Microsoft Teams meetings the user has scheduled in the future</span></span>
    
  - <span data-ttu-id="c1ade-159">Alle Skype for Business- oder Microsoft Teams-Besprechungen, die vor der Ausführung von MMS stattfanden, werden übersprungen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-159">Any Skype for Business or Microsoft Teams meetings that occurred prior to when MMS runs are skipped</span></span>
    
  - <span data-ttu-id="c1ade-160">Nur die Besprechungen, deren Organisator der Benutzer ist, werden aktualisiert</span><span class="sxs-lookup"><span data-stu-id="c1ade-160">Only the meetings where the user is the organizer are updated</span></span>
    
2. <span data-ttu-id="c1ade-161">Ersetzen des Informationsblocks für Onlinebesprechungen in den Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="c1ade-161">Replace the online meeting information block in the meeting details</span></span>
    
3. <span data-ttu-id="c1ade-162">Senden von Aktualisierungen an alle Besprechungsempfänger im Namen des Besprechungsorganisators</span><span class="sxs-lookup"><span data-stu-id="c1ade-162">Send updates to all meeting recipients on behalf of the meeting organizer</span></span>
    
 <span data-ttu-id="c1ade-163">**Wie lange dauert die Ausführung von MMS?**</span><span class="sxs-lookup"><span data-stu-id="c1ade-163">**How long will it take for MMS to run?**</span></span>
  
<span data-ttu-id="c1ade-p112">Wie lange es dauert, bis MMS die Besprechungen migriert hat, hängt davon ab, wie viele Benutzer betroffen sind und wie viele Skype for Business- oder Microsoft Teams-Besprechungen die einzelnen Benutzer insgesamt in ihren Kalendern haben. Die Ausführung dauert mindestens zehn Minuten. Große Migrationen können bis zu zwölf Stunden dauern; die meisten Migrationen sollten aber innerhalb von einer Stunde abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p112">The amount of time it take for MMS to migrate meetings varies depending on how many users are impacted, and the total number of Skype for Business or Microsoft Teams meetings each user has on their calendar. At a minimum, it will take 10 minutes to run. While some large migrations can take up to 12 hours, most migrations should complete within 1 hour.</span></span>
  
 <span data-ttu-id="c1ade-167">**Einschränkungen und mögliche Probleme**</span><span class="sxs-lookup"><span data-stu-id="c1ade-167">**Limitations and potential issues**</span></span>
  
- <span data-ttu-id="c1ade-p113">Es werden nur die Skype for Business- oder Microsoft Teams-Besprechungen migriert, die durch Klicken auf die Schaltfläche **Skype-Besprechung hinzufügen** in Outlook im Web oder über das Skype-Besprechungs-Add-In für Outlook geplant wurden. Wenn ein Benutzer also die Informationen einer Skype-Onlinebesprechung von einer Besprechung in eine neue Besprechung kopiert, wird diese neue Besprechung nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p113">Only the Skype for Business or Microsoft Teams meetings that were scheduled by clicking the **Add Skype meeting** button in Outlook on the Web or by using the Skype Meeting add-in for Outlook are migrated. In other words, if a user copies and pastes the Skype online meeting information from one meeting to a new meeting, that new meeting won't be updated.</span></span>
    
- <span data-ttu-id="c1ade-p114">MMS ersetzt alles im Informationsblock für die Onlinebesprechung, wenn eine Besprechung migriert wird. Wenn daher ein Benutzer diesen Block bearbeitet hat, werden seine Änderungen überschrieben. Alle Inhalte, die sich in den Besprechungsdetails außerhalb des Informationsblocks der Onlinebesprechung befinden, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p114">MMS replaces everything in the online meeting information block when a meeting is migrated. Therefore, if a user has edited that block, their changes will be overwritten. Any content they have in the meeting details outside of the online meeting information block won't be affected.</span></span>
    
     ![The meeting block that gets updated by MMS](../images/210a03ee-30c1-46f3-808f-4c2ebdaa3ea1.png)
  
- <span data-ttu-id="c1ade-p115">Besprechungsinhalte, die erstellt oder an die Besprechung angehängt wurden (Whiteboards, Umfragen usw.), bleiben nach der Ausführung von MMS nicht erhalten. Wenn Ihre Besprechungsorganisatoren im Voraus Inhalte an Besprechungen angehängt haben, müssen diese Inhalte nach der Ausführung von MMS erneut erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p115">Meeting content that was created or attached to the meeting (whiteboards, polls and so on) won't be retained after MMS runs. If your meeting organizers have attached content to the meetings in advance, the content will need to be recreated after MMS runs.</span></span>
    
- <span data-ttu-id="c1ade-p116">Der Link zu freigegebenen Besprechungsnotizen im Kalenderelement und von innerhalb der Skype-Besprechung wird ebenfalls überschrieben. Beachten Sie, dass die in OneNote gespeicherten Besprechungsnotizen selbst noch vorhanden sind; nur der Link zu den freigegebenen Notizen wird überschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p116">The link to the shared meeting notes in the calendar item and also from within the Skype meeting also will be overwritten. Note that the actual meeting notes stored in OneNote will still be there, it is only the link to the shared notes that gets overwritten.</span></span>
    
- <span data-ttu-id="c1ade-178">Besprechungen mit mehr als 250 Teilnehmern (einschließlich des Organisators) werden nicht migriert.</span><span class="sxs-lookup"><span data-stu-id="c1ade-178">Meetings with more than 250 attendees (including the organizer) won't be migrated.</span></span>
    
- <span data-ttu-id="c1ade-179">Einige Unicode-Zeichen im Text der Einladung werden möglicherweise fälschlich in eines der folgenden Sonderzeichen aktualisiert: ï, ¿, ½, �.</span><span class="sxs-lookup"><span data-stu-id="c1ade-179">Some UNICODE characters in the body of the invite may be incorrectly updated to one of the following special characters: ï, ¿, ½, �.</span></span>
    
### <a name="what-will-the-users-see-when-mms-updates-their-meetings"></a><span data-ttu-id="c1ade-180">Was sehen die Benutzer, wenn MMS ihre Besprechungen aktualisiert?</span><span class="sxs-lookup"><span data-stu-id="c1ade-180">What will the users see when MMS updates their meetings?</span></span>

<span data-ttu-id="c1ade-p117">Wie Meeting Migration Tool sendet auch MMS Besprechungsaktualisierungen im Namen der Benutzer. Das Einzige, was Ihre Benutzer daher sehen, ist eine weitere Runde Besprechungszusagebenachrichtungen für ihre Besprechungen. Das kann für die Benutzer verwirrend sein. Daher empfehlen wir, Ihre Benutzer im Voraus nicht nur über den Zeitpunkt der Migration von der lokalen Version zu Skype for Business Online zu informieren, sondern auch, wenn Sie die Audiokonferenzänderungen vornehmen, die MMS auslösen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p117">Just like the Meeting Migration Tool, MMS sends meeting updates on behalf of users. Therefore, the only thing your users will see is another round of meeting acceptance notifications for their meetings. This might be confusing for users, so we recommend that you notify your users in advance not only when you migrate them from on-premises to Skype for Business Online, but also when you make audio conferencing changes that will trigger MMS.</span></span>
  
## <a name="managing-mms"></a><span data-ttu-id="c1ade-184">Verwalten von MMS</span><span class="sxs-lookup"><span data-stu-id="c1ade-184">Managing MMS</span></span>

<span data-ttu-id="c1ade-p118">Sie müssen Windows PowerShell verwenden, um MMS zu verwalten und den Status von laufenden Migrationen zu prüfen. Bei den Informationen in diesem Abschnitt wird davon ausgegangen, dass Sie mit der Nutzung von PowerShell zur Verwaltung Ihrer Skype for Business-Organisation vertraut sind. Wenn Sie neu bei PowerShell sind, finden Sie weitere Informationen im Abschnitt [Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation](setting-up-the-meeting-migration-service-mms.md#WPSInfo) am Ende dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p118">You need to use the Windows PowerShell to manage MMS and check the status of ongoing migrations. The information in this section assumes that you're familiar with using PowerShell to manage your Skype for Business organization. If you are new PowerShell, see the [Using PowerShell to manage your Skype for Business organization](setting-up-the-meeting-migration-service-mms.md#WPSInfo) section at the end of this article.</span></span>
  
### <a name="how-do-i-check-the-status-of-meeting-migrations"></a><span data-ttu-id="c1ade-188">Wie prüfe ich den Status von Besprechungsmigrationen?</span><span class="sxs-lookup"><span data-stu-id="c1ade-188">How do I check the status of meeting migrations?</span></span>

<span data-ttu-id="c1ade-p119">Sie verwenden das  `Get-CsMeetingMigrationStatus`-Cmdlet, um den Status von Besprechungsmigrationen zu prüfen. Unten sind einige Beispiele aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p119">You use the  `Get-CsMeetingMigrationStatus` cmdlet to check the status of meeting migrations. Below are some examples.</span></span>
  
<span data-ttu-id="c1ade-191">Um einen Übersichtsstatus aller MMS-Migrationen zu erhalten, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c1ade-191">To get a summary status of all MMS migrations, run the following command:</span></span>
  
```
Get-CsMeetingMigrationStatus -SummaryOnly
```

<span data-ttu-id="c1ade-192">Damit erhalten Sie eine Übersicht in Tabellenformat aller Migrationsstatus wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c1ade-192">This will give you a tabular view of all migration states like this:</span></span>
  
<span data-ttu-id="c1ade-193">State UserCount---</span><span class="sxs-lookup"><span data-stu-id="c1ade-193">State UserCount---------------</span></span><br/> <span data-ttu-id="c1ade-194">Ausstehende 21</span><span class="sxs-lookup"><span data-stu-id="c1ade-194">Pending 21</span></span><br/><span data-ttu-id="c1ade-195">In Bearbeitung 6</span><span class="sxs-lookup"><span data-stu-id="c1ade-195">InProgress 6</span></span><br/> <span data-ttu-id="c1ade-196">Fehlerhafte 2</span><span class="sxs-lookup"><span data-stu-id="c1ade-196">Failed 2</span></span> <br/> <span data-ttu-id="c1ade-197">Erfolgreiche 131</span><span class="sxs-lookup"><span data-stu-id="c1ade-197">Succeeded 131</span></span>
> [!IMPORTANT]
> <span data-ttu-id="c1ade-p120">Wenn Sie fehlgeschlagene Migrationen sehen, ergreifen Sie die nötigen Schritte, um diese Probleme so bald wie möglich zu beheben. Die Teilnehmer können sich nicht bei den von diesen Benutzern organisierten Besprechungen einwählen, bis Sie die Probleme behoben haben. Weitere Informationen finden Sie im Abschnitt [Was tue ich, wenn ein Fehler auftritt?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting).</span><span class="sxs-lookup"><span data-stu-id="c1ade-p120">If you see any migrations that have failed, take action to resolve these issues as soon as possible. People won't be able to dial-in to the meetings organized by those users until you address these. See the [What do I do if there is an error?](setting-up-the-meeting-migration-service-mms.md#Troubleshooting) section for more information.</span></span>
  
<span data-ttu-id="c1ade-p121">Um umfassende Details aller Migrationen innerhalb eines bestimmten Zeitraums anzuzeigen, können Sie die Parameter  `StartTime` und `EndTime` verwenden. Der folgende Befehl gibt zum Beispiel alle Einzelheiten aller Migrationen zurück, die vom 1. Oktober 2016 bis zum 8. Oktober 2016 stattgefunden haben.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p121">To get full details of all migrations within a specific time period, you can use the  `StartTime` and `EndTime` parameters. For example, the following command will return full details on all migrations that occurred from October 1, 2016 to October 8, 2016.</span></span>
  
```
Get-CsMeetingMigrationStatus -StartTime "10/1/2016" -EndTime "10/8/2016"
```

<span data-ttu-id="c1ade-p122">Wenn Sie den Status der Migration für einen bestimmten Benutzer prüfen möchten, können Sie dafür den Parameter  `UserId` verwenden. Beispielsweise gibt der folgende Befehl den Status des Benutzers ashaw@contoso.com zurück:</span><span class="sxs-lookup"><span data-stu-id="c1ade-p122">You also may want to check the status of the migration for a specific user, and you can use the  `UserId` parameter for that. For example, the following command will return the status for the user ashaw@contoso.com:</span></span>
  
```
Get-CsMeetingMigrationStatus -UserId "ashaw@contoso.com"
```

### <a name="what-do-i-do-if-there-is-an-error"></a><span data-ttu-id="c1ade-205">Was tue ich, wenn ein Fehler auftritt?</span><span class="sxs-lookup"><span data-stu-id="c1ade-205">What do I do if there is an error?</span></span>
<span data-ttu-id="c1ade-206"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="c1ade-206"></span></span>

<span data-ttu-id="c1ade-207">Wenn Sie das  `Get-CsMeetingMigrationStatus`-Cmdlet ausführen, um eine Übersicht zu erhalten, und feststellen, dass Migrationen im Status Fehlervorhanden sind, müssen Sie folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-207">When you run the  `Get-CsMeetingMigrationStatus` cmdlet to get a summary view and notice that there are migrations in Failed state, here's what you need to do:</span></span>
  
1. <span data-ttu-id="c1ade-p123">Stellen Sie fest, welche Benutzer betroffen sind. Führen Sie den folgenden Befehl aus, um die Liste der betroffenen Benutzer und den spezifischen gemeldeten Fehler zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="c1ade-p123">Determine which users are affected. Run the following command to get the list of affected users, and the specific error that was reported:</span></span>
    
  ```
  Get-CsMeetingMigrationStatus | Where {$_.State -eq "Failed"} | Format-Table UserId,LastErrorMessage
  ```

2. <span data-ttu-id="c1ade-210">Führen Sie für jeden dieser Benutzer das [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) aus, um deren Besprechungen manuell zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="c1ade-210">For each of those user, run the [Meeting Migration Tool](https://go.microsoft.com/fwlink/p/?linkid=626047) to manually migrate their meetings.</span></span>
    
3. <span data-ttu-id="c1ade-211">Wenn die Migration auch mit dem Meeting Migration Tool nicht funktioniert, haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="c1ade-211">If migration still doesn't work with the Meeting Migration Tool, you have two options:</span></span>
    
  - <span data-ttu-id="c1ade-212">Weisen Sie die Benutzer an, neue Skype-Besprechungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-212">Have the users create new Skype meetings.</span></span>
    
  - <span data-ttu-id="c1ade-213">[Wenden Sie sich an den Support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span><span class="sxs-lookup"><span data-stu-id="c1ade-213">[Contact support](https://go.microsoft.com/fwlink/p/?LinkID=518322).</span></span>
    
### <a name="enabling-and-disabling-mms"></a><span data-ttu-id="c1ade-214">Aktivieren und Deaktivieren von MMS</span><span class="sxs-lookup"><span data-stu-id="c1ade-214">Enabling and disabling MMS</span></span>
<span data-ttu-id="c1ade-215"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="c1ade-215"></span></span>

<span data-ttu-id="c1ade-p124">MMS ist standardmäßig für alle Organisationen aktiviert, kann aber bei Bedarf deaktiviert werden. Wenn Sie z. B. alle Besprechungen manuell migrieren möchten oder einen Drittanbieter für Audiokonferenzen verwenden, ist die Ausführung von MMS nicht erforderlich. Sie können auch wählen, MMS vorübergehend zu deaktivieren. Beispiel: Sie nehmen größere Änderungen an den Audiokonferenzeinstellungen für Ihre Organisation vor, und MMS soll erst ausgeführt werden, wenn alle Änderungen abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p124">MMS is enabled by default for all organizations, but it can be disabled as needed. For example, if you want to manually migrate all meetings or if you use a third-party audio conferencing provider, you may not need MMS running. You may also choose to temporarily disable MMS. For example, you may be doing substantial changes to the audio conferencing settings for your organization and you don't want MMS to run until all changes are completed.</span></span>
  
<span data-ttu-id="c1ade-p125">Um zu sehen, ob MMS für Ihre Organisation aktiviert ist, führen Sie den folgenden Befehl aus, und prüfen Sie den Wert für den Parameter  `MeetingMigrationEnabled`. Wenn dieser Parameter auf $true festgelegt ist, ist MMS aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p125">To see if MMS is enabled for your organization, run the following command and check the value for the  `MeetingMigrationEnabled` parameter. If this parameter is set to$true, MMS is enabled.</span></span>
  
```
Get-CsTenantMigrationConfiguration
```

<span data-ttu-id="c1ade-222">Führen Sie zum Deaktivieren von MMS den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c1ade-222">To disable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $false
```

<span data-ttu-id="c1ade-223">Führen Sie zum Aktivieren von MMS den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c1ade-223">To enable MMS, run the following command:</span></span>
  
```
Set-CsTenantMigrationConfiguration -MeetingMigrationEnabled $true
```

### <a name="enabling-and-disabling-mms-only-for-audio-conferencing-changes"></a><span data-ttu-id="c1ade-224">Aktivieren und Deaktivieren von MMS nur für Audiokonferenzänderungen</span><span class="sxs-lookup"><span data-stu-id="c1ade-224">Enabling and disabling MMS only for audio conferencing changes</span></span>
<span data-ttu-id="c1ade-225"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="c1ade-225"></span></span>

<span data-ttu-id="c1ade-p126">Sie können MMS auch nur für Audiokonferenzänderungen deaktivieren. MMS wird nach wie vor ausgeführt, wenn ein Benutzer von der lokalen Skype for Business-Version zu Skype for Business Online migriert wird. Um den aktuellen MMS-Status für Audiokonferenzaktualisierungen zu überprüfen, führen Sie den folgenden Befehl aus, und überprüfen Sie den Wert für den Parameter  `AutomaticallyMigrateUserMeetings`. Wenn dieser Parameter auf $true festgelegt ist, ist für MMS festgelegt, dass die Benutzerbesprechungen bei Änderungen an Audiokonferenzeinstellungen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p126">You can also disable MMS only for audio conferencing changes. It will still run when a user is migrated from Skype for Business on-premises to Skype for Business Online. To check the current MMS status for audio conferencing updates, run the following command and check the value for the  `AutomaticallyMigrateUserMeetings` parameter. If this parameter is set to$true, MMS is set to update user meetings when audio conferencing settings are changed.</span></span>
  
```
Get-CsOnlineDialInConferencingTenantSettings
```

<span data-ttu-id="c1ade-230">Führen Sie zum Deaktivieren von MMS für Audiokonferenzen den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c1ade-230">To disable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallyMigrateUserMeetings $false
```

<span data-ttu-id="c1ade-231">Führen Sie zum Aktivieren von MMS für Audiokonferenzen den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c1ade-231">To enable MMS for audio conferencing, run the following command:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSettings  -AutomaticallyMigrateUserMeetings $true
```

### <a name="how-do-i-run-meeting-migration-manually-for-a-user"></a><span data-ttu-id="c1ade-232">Wie führe ich die Besprechungsmigration manuell für Benutzer aus?</span><span class="sxs-lookup"><span data-stu-id="c1ade-232">How do I run Meeting Migration manually for a user?</span></span>
<span data-ttu-id="c1ade-233"><a name="Troubleshooting"> </a></span><span class="sxs-lookup"><span data-stu-id="c1ade-233"></span></span>

<span data-ttu-id="c1ade-p127">Neben den automatischen Besprechungsmigrationen können Sie die Besprechungsmigration manuell für einen Benutzer ausführen, indem Sie das **Start-CsExMeetingMigration** -Cmdlet ausführen. Dieses Cmdlet fügt den Benutzer in der Besprechungsmigrations-Warteschlange hinzu. Meeting Migration Service liest die Benutzeranforderung und migriert die zugehörigen Besprechungen. Den Status der Besprechungsmigration können Sie mit dem **Get-CsMeetingMigrationStatus** -Cmdlet überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p127">In addition to the automatic meeting migrations, you can also run the meeting migration manually for a user by running the cmdlet **Start-CsExMeetingMigration**. This cmdlet adds the user in meeting migration queue. Meeting Migration Service will read the user request and migrate their meetings. You can check the status of meeting migration by cmdlet **Get-CsMeetingMigrationStatus**.</span></span>
  
<span data-ttu-id="c1ade-238">Hier ist ein Beispiel, in dem die Besprechungsmigration für den Benutzer ashaw@contoso.com gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="c1ade-238">Here is an example that kicks off meeting migration for the user ashaw@contoso.com:</span></span>
  
```
Start-CsExMeetingMigration -Identity ashaw@contoso.com
```

## <a name="using-powershell-to-manage-your-skype-for-business-organization"></a><span data-ttu-id="c1ade-239">Verwenden von PowerShell zum Verwalten der Skype for Business-Organisation</span><span class="sxs-lookup"><span data-stu-id="c1ade-239">Using PowerShell to manage your Skype for Business organization</span></span>
<span data-ttu-id="c1ade-240"><a name="WPSInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="c1ade-240"></span></span>

 <span data-ttu-id="c1ade-241">**Überprüfen, ob Windows PowerShell 3.0 oder höher ausgeführt wird**</span><span class="sxs-lookup"><span data-stu-id="c1ade-241">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
  
1. <span data-ttu-id="c1ade-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c1ade-242">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c1ade-243">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="c1ade-243">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="c1ade-p128">Wenn Sie nicht über Version 3.0 oder eine höhere Version verfügen, müssen Sie Updates für Windows PowerShell herunterladen und installieren. Informationen zum Herunterladen von Windows PowerShell und zum Aktualisieren auf Version 4.0 finden Sie unter [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p128">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="c1ade-p129">Sie müssen auch das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt. Dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, kann aus dem Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="c1ade-p129">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
<span data-ttu-id="c1ade-250">Weitere Informationen finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1ade-250">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
  
 <span data-ttu-id="c1ade-251">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="c1ade-251">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="c1ade-252">From the **Start Menu** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="c1ade-252">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c1ade-253">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-253">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="c1ade-254">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="c1ade-254">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  $credential = Get-Credential
  $session = New-CsOnlineSession -Credential $credential
  Import-PSSession $session
  ```
<span data-ttu-id="c1ade-255">Weitere Informationen zum Starten von Windows PowerShell finden Sie unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://technet.microsoft.com/EN-US/library/dn568015.aspx) oder[Herstellen der Verbindung zu Skype for Business Online mit Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c1ade-255">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or[Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
  
- <span data-ttu-id="c1ade-p130">In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-p130">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c1ade-259">Einführung in Windows PowerShell und Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1ade-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="c1ade-260">Warum Sie Office 365 PowerShell verwenden müssen</span><span class="sxs-lookup"><span data-stu-id="c1ade-260">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="c1ade-p131">Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c1ade-p131">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="c1ade-263">Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1ade-263">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="c1ade-264">Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1ade-264">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="c1ade-265">Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c1ade-265">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="c1ade-266">See Also</span><span class="sxs-lookup"><span data-stu-id="c1ade-266">Related topics</span></span>

[<span data-ttu-id="c1ade-267">Testen oder Erwerben von Audiokonferenzen in Office 365</span><span class="sxs-lookup"><span data-stu-id="c1ade-267">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
