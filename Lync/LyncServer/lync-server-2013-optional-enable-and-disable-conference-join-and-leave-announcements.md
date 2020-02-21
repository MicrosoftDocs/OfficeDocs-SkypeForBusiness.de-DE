---
title: Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5007ec14ad197afb2cfb8d2c73baa41ed144a4e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="0413f-102">Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0413f-102">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0413f-103">_**Letztes Änderungsstand des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="0413f-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="0413f-104">Wenn Einwahlbenutzer einer Konferenz beitreten oder diese verlassen, können die Konferenzankündigungsanwendung Ihren Eingang oder ihren Ausgang ankündigen, indem Sie einen Signalton abgeben oder ihre Namen sagen.</span><span class="sxs-lookup"><span data-stu-id="0413f-104">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="0413f-105">Sie können die Funktionsweise von Ankündigungen ändern, indem Sie Cmdlets ausführen.</span><span class="sxs-lookup"><span data-stu-id="0413f-105">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="0413f-106">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="0413f-106">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="0413f-107">So ändern Sie das Verhalten der Konferenz Mitgliedschaft und Abwesenheits Ankündigung</span><span class="sxs-lookup"><span data-stu-id="0413f-107">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="0413f-108">Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="0413f-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="0413f-109">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="0413f-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0413f-110">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="0413f-110">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="0413f-111">Dieses Cmdlet ruft Informationen darüber ab, ob Teilnehmer ihren Namen aufzeichnen müssen, wenn Sie einer Konferenz beitreten, und wie lync Server reagiert, wenn Teilnehmer einer Einwahlkonferenz beitreten oder diese verlassen.</span><span class="sxs-lookup"><span data-stu-id="0413f-111">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="0413f-112">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="0413f-112">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="0413f-113">**EnableNameRecording**   legt fest, ob anonyme Teilnehmer aufgefordert werden, Ihren Namen vor dem Betreten der Konferenz aufzuzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0413f-113">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="0413f-114">Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, Ihren Namen anzugeben, wenn Sie einer Konferenz beitreten.</span><span class="sxs-lookup"><span data-stu-id="0413f-114">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="0413f-115">(Authentifizierte Teilnehmer notieren ihren Namen nicht, da stattdessen Ihr Anzeigename verwendet wird.)</span><span class="sxs-lookup"><span data-stu-id="0413f-115">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="0413f-116">**EntryExitAnnouncementsEnabledByDefault**   gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="0413f-116">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="0413f-117">Der Standardwert ist "$false", was bedeutet, dass es standardmäßig keine Ankündigungen gibt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen.</span><span class="sxs-lookup"><span data-stu-id="0413f-117">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="0413f-118">Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0413f-118">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="0413f-119">**EntryExitAnnouncementsType**   gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz Beitritt oder diese verlässt, für die Ankündigungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="0413f-119">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="0413f-120">Der Standardwert ist "UseNames", was bedeutet, dass eine Ansage ähnlich der folgenden vorliegt: "Ken Myers hat der Konferenz beigetreten, wenn Ankündigungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="0413f-120">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="0413f-121">Sie können diese Einstellungen auf globaler Ebene oder auf Standortebene konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0413f-121">You can configure these settings at the global scope or at the site scope.</span></span> <span data-ttu-id="0413f-122">Auf Standortebene konfigurierte Einstellungen haben Vorrang vor den auf globaler Ebene konfigurierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0413f-122">Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="0413f-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0413f-123">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="0413f-124">In diesem Beispiel werden die Einstellungen auf Standortebene für Redmond konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0413f-124">In this example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="0413f-125">Ankündigungen sind aktiviert, aber die Teilnehmer werden nicht aufgefordert, Ihren Namen zu sagen, wenn Sie an einer Konferenz teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="0413f-125">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="0413f-126">Ein Signalton wird abgespielt, wenn Teilnehmer eine Konferenz betreten oder verlassen.</span><span class="sxs-lookup"><span data-stu-id="0413f-126">A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

