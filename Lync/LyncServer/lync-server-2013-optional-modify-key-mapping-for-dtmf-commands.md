---
title: 'Lync Server 2013: (Optional) Ändern der Tastenzuordnung für DTMF-Befehle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Modify key mapping for DTMF commands
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398943(v=OCS.15)
ms:contentKeyID: 48185563
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 036092f1199ad0e361f8509b36930410685ece21
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-modify-key-mapping-for-dtmf-commands-in-lync-server-2013"></a><span data-ttu-id="e7d10-102">(Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7d10-102">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7d10-103">_**Letztes Änderungsdatum des Themas:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="e7d10-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="e7d10-104">Benutzer von Einwahlkonferenzen können auf der Telefontastatur auf Tasten drücken, um DTMF-Befehle (Dual-Tone Multi-Frequency) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="e7d10-104">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="e7d10-105">Mit DTMF-Befehlen können Benutzer, die sich bei einer Konferenz einwählen, Konferenzeinstellungen (wie Muting und Aufheben der Stummschaltung oder sperren und Entsperren der Konferenz) über die Tastatur auf dem Telefon steuern.</span><span class="sxs-lookup"><span data-stu-id="e7d10-105">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> <span data-ttu-id="e7d10-106">Sie können Cmdlets verwenden, um die für die DTMF-Befehle verwendeten Tasten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e7d10-106">You can use cmdlets to modify the keys used for the DTMF commands.</span></span> <span data-ttu-id="e7d10-107">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="e7d10-107">This step is optional.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7d10-108">Details zu diesen Cmdlets und den möglichen DTMF-Optionen finden Sie unter Dokumentation zur lync Server-Verwaltungsshell oder Befehlszeilenhilfe zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e7d10-108">For details about these cmdlets and the possible DTMF options, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>



</div>

<div>

## <a name="to-modify-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="e7d10-109">So ändern Sie die Tastenzuordnung von DTMF-Befehlen</span><span class="sxs-lookup"><span data-stu-id="e7d10-109">To modify the key mapping of DTMF commands</span></span>

1.  <span data-ttu-id="e7d10-110">Melden Sie sich bei dem Computer als Mitglied der **RTCUniversalServerAdmins** -Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="e7d10-110">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="e7d10-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="e7d10-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="e7d10-112">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="e7d10-112">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingDtmfConfiguration
    
    <span data-ttu-id="e7d10-113">Dieses Cmdlet gibt die DTMF-Einstellungen zurück, die für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7d10-113">This cmdlet returns the DTMF settings used for dial-in conferencing.</span></span>

4.  <span data-ttu-id="e7d10-114">Führen Sie das folgende Cmdlet aus, und geben Sie den zu bedruckenden Schlüssel für jede Option an, die Sie ändern möchten:</span><span class="sxs-lookup"><span data-stu-id="e7d10-114">Run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    <span data-ttu-id="e7d10-115">Mit diesem Cmdlet werden die DTMF-Einstellungen geändert, die für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7d10-115">This cmdlet modifies the DTMF settings used for dial-in conferencing.</span></span>
    
    <span data-ttu-id="e7d10-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e7d10-116">For example:</span></span>
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    <span data-ttu-id="e7d10-117">In diesem Beispiel wird die gedrückte Taste getauscht, um Ankündigungen zu aktivieren oder zu deaktivieren, und die Taste, die gedrückt wird, um alle Teilnehmer stummzuschalten und die Stummschaltung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="e7d10-117">This example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="e7d10-118">Da keine Identität angegeben wird, gelten diese Änderungen für die globalen DTMF-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7d10-118">Because no Identity is specified, these changes apply to the global DTMF settings.</span></span>

5.  <span data-ttu-id="e7d10-119">(Optional) Zum Erstellen zusätzlicher DTMF-Befehlssätze für bestimmte Standorte verwenden Sie das Cmdlet **New-CsDialinConferencingDtmfConfiguration** mit dem Identitätswert eines Standorts.</span><span class="sxs-lookup"><span data-stu-id="e7d10-119">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span> <span data-ttu-id="e7d10-120">Beim Erstellen neuer DTMF-Einstellungen für Standorte haben die Standorteinstellungen Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e7d10-120">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="e7d10-121">Ausführliche Informationen finden Sie unter Dokumentation zur lync Server-Verwaltungsshell oder Befehlszeilenhilfe zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e7d10-121">For details, see Lync Server Management Shell documentation or Lync Server Management Shell command-line Help.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

