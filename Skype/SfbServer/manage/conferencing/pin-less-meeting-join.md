---
title: Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Zusammenfassung: Informationen zum Konfigurieren des PIN-kleiner meeting Verknüpfungsoption in Skype für Business Server.'
ms.openlocfilehash: 843ea92a331391faa47e4cbc32191312c6dfbc6b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985963"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="492dd-103">Konfigurieren der PIN-losen Besprechungsanmeldung in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="492dd-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="492dd-104">**Zusammenfassung:** Informationen zum Konfigurieren des PIN-kleiner meeting Verknüpfungsoption in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="492dd-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="492dd-105">Wenn ein Anrufer einwählen versucht, an einer Besprechung teilnehmen, platziert (Conference Auto Attendant, CAA)-Dienst den Anrufer in einen Stift Betrieb, der sich aus dem Wartebereich & #x 2014 unterscheidet. Wenn Referent noch nicht auf einen Anruf ist, und der Zugriffsnummer für Einwahl Anrufer eine PIN in leitender Position nicht eingegeben hat.</span><span class="sxs-lookup"><span data-stu-id="492dd-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="492dd-106">Die PIN-lose Besprechungsanmeldeoption ermöglicht Einwahl-Anrufern die Teilnahme an einer Besprechung ohne Eingabe einer Leiter-PIN sogar dann, wenn sie nicht als Erste zugeschaltet werden.</span><span class="sxs-lookup"><span data-stu-id="492dd-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="492dd-107">Beachten Sie Folgendes, wenn Sie diese Funktion konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="492dd-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="492dd-108">Gilt nur für private Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="492dd-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="492dd-109">PSTN-Anrufer können in privaten Besprechungen verbleiben, ohne dass authentifizierte Nutzer anwesend sind.</span><span class="sxs-lookup"><span data-stu-id="492dd-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="492dd-110">Nach der Änderung der Einstellung gilt sie für alle existierenden und neuen privaten Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="492dd-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="492dd-111">Kann entweder am Standort des Organisators oder auf globaler Ebene aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="492dd-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="492dd-112">Optionen dafür, wer die Lobby umgehen kann, können für jeden der folgenden Fälle eingestellt werden:</span><span class="sxs-lookup"><span data-stu-id="492dd-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="492dd-113">**„Jeder innerhalb meiner Organisation“ mit „Anrufer erhalten direkten Zugang“**</span><span class="sxs-lookup"><span data-stu-id="492dd-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="492dd-114">**„Alle Personen (keine Einschränkungen)“ mit „Anrufer erhalten direkten Zugang“**. (Das ist die Standardeinstellung.)</span><span class="sxs-lookup"><span data-stu-id="492dd-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="492dd-115">Wenn die Konfiguration die PIN-lose Anmeldung vorsieht, fordert der CAA-Dienst trotzdem zur Eingabe einer Leiter-PIN auf.</span><span class="sxs-lookup"><span data-stu-id="492dd-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="492dd-116">Nutzer können mit oder ohne Eingabe einer PIN an der Besprechung teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="492dd-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="492dd-117">Die Möglichkeit, geben Sie eine PIN in leitender Position beibehalten kann jedoch einen Anrufer einwählen, zur Authentifizierung als Leiter und Verwalten der Besprechung bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="492dd-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="492dd-118">Konfigurieren der PIN-losen Besprechungsanmeldung</span><span class="sxs-lookup"><span data-stu-id="492dd-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="492dd-119">Um PIN weniger Besprechungsteilnahme für Ihre Benutzer zu aktivieren, verwenden Sie das Cmdlet " [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) " wie folgt mit dem Parameter AllowAnonymousPstnActivation aus:</span><span class="sxs-lookup"><span data-stu-id="492dd-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="492dd-120">Als Beispiel ermöglicht der folgende Befehl die PIN-lose Besprechungsanmeldung für den Standort Redmond:</span><span class="sxs-lookup"><span data-stu-id="492dd-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="492dd-121">Aus Sicherheitsgründen möchten Sie unter Umständen, wenn die PIN-lose Besprechungsanmeldung aktiviert worden ist, dass anonyme Anrufer von der Einwahl ausgeschlossen werden. Stellen Sie zu diesem Zweck sicher, dass die Konferenzrichtlinie wie folgt festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="492dd-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="492dd-122">Weitere Informationen finden Sie unter [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="492dd-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

