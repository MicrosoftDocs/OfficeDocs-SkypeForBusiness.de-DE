---
title: Verwalten von Teilnahme-und Abwesenheits Ankündigungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server Konferenz Anmeldungen verwalten und Ankündigungen hinterlassen.'
ms.openlocfilehash: 3d9a14e36dfe6b8df51e5ee91dd329ce34452cda
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283795"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="b13ba-103">Verwalten von Teilnahme-und Abwesenheits Ankündigungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b13ba-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="b13ba-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzteilnahme verwalten und Ankündigungen hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="b13ba-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="b13ba-105">Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder Sie verlassen, kann die APP für Konferenz Ankündigungen deren ein-oder Ausstieg ankündigen, indem Sie einen Ton abspielen oder ihre Namen sagen.</span><span class="sxs-lookup"><span data-stu-id="b13ba-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="b13ba-106">Sie können die Funktionsweise von Ankündigungen mithilfe der Skype for Business Server-Verwaltungsshell und des Cmdlets " **Satz-CsDialinConferencing** " mit den folgenden Parametern ändern:</span><span class="sxs-lookup"><span data-stu-id="b13ba-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="b13ba-p102">EnableNameRecording – Legt fest, ob anonyme Teilnehmer vor dem Beitreten einer Konferenz dazu aufgefordert werden, ihren Namen aufzuzeichnen. Der Standardwert lautet „$true“. Dies bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen zu sagen, wenn sie einer Konferenz beitreten möchten. (Authentifizierte Teilnehmer müssen ihren Namen nicht aufzeichnen, da stattdessen ihr Anzeigename verwendet wird.)</span><span class="sxs-lookup"><span data-stu-id="b13ba-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="b13ba-p103">EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert lautet „$false“. Dies bedeutet, dass standardmäßig keine Ankündigung erfolgt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="b13ba-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="b13ba-p104">EntryExitAnnouncementsType – Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz, für die die Ankündigungsfunktion aktiviert ist, beitritt oder diese verlässt. Der Standardwert lautet „UseNames“. Dies bedeutet, dass eine Ankündigung ähnlich dieser erfolgt: „Jonas Baar ist der Konferenz beigetreten.“</span><span class="sxs-lookup"><span data-stu-id="b13ba-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="b13ba-p105">Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="b13ba-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="b13ba-117">So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="b13ba-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="b13ba-118">Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.</span><span class="sxs-lookup"><span data-stu-id="b13ba-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="b13ba-119">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b13ba-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b13ba-120">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="b13ba-120">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="b13ba-121">Mit diesem Cmdlet werden Informationen darüber abgerufen, ob Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen und wie Skype for Business Server antwortet, wenn Teilnehmer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.</span><span class="sxs-lookup"><span data-stu-id="b13ba-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="b13ba-122">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="b13ba-122">Run the following at the command prompt:</span></span>
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="b13ba-p106">Im folgenden Beispiel sind die Einstellungen auf Standortebene für Redmond konfiguriert. Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten. Wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, wird ein Ton abgespielt.</span><span class="sxs-lookup"><span data-stu-id="b13ba-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="b13ba-126">Weitere Informationen, einschließlich Syntax und einer vollständigen Liste der Parameter, finden Sie unter [CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b13ba-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

