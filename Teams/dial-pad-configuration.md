---
title: Konfiguration der Wähltastatur für Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
description: Hier erfahren Sie, wie Sie die Wähltastatur im Teams-Client so konfigurieren, dass Benutzer auf die PSTN-Funktionalität (Public Switched Telephone Network) zugreifen können.
ms.openlocfilehash: 44fcbb766cadaa4b31aa065fae80fdcd48c5453f
ms.sourcegitcommit: a94a267c421a78587b0dbbea5fa167aad2882e9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45012416"
---
# <a name="dial-pad-configuration"></a><span data-ttu-id="4338d-103">Wähltasten Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4338d-103">Dial pad configuration</span></span>

<span data-ttu-id="4338d-104">Im Teams-Client ermöglicht die Wähltastatur Benutzern den Zugriff auf die PSTN-Funktionalität (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="4338d-104">In the Teams client, the dial pad enables users to access Public Switched Telephone Network (PSTN) functionality.</span></span> <span data-ttu-id="4338d-105">Die Wähltasten sind für Benutzer mit einer Telefon System Lizenz verfügbar, vorausgesetzt, Sie sind ordnungsgemäß konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4338d-105">The dial pad is available for users with a Phone System license, provided they are configured properly.</span></span> <span data-ttu-id="4338d-106">Die folgenden Kriterien sind für die Anzeige der Wähltasten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="4338d-106">The following criteria are all required for the dial pad to show:</span></span>

- <span data-ttu-id="4338d-107">Der Benutzer verfügt über eine aktivierte Telefon System Lizenz ("MCOEV").</span><span class="sxs-lookup"><span data-stu-id="4338d-107">User has an enabled Phone System (“MCOEV”) license</span></span>
- <span data-ttu-id="4338d-108">Der Benutzer hat einen Microsoft-Anrufplan oder ist für die direkte Weiterleitung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4338d-108">User has Microsoft Calling Plan or is enabled for Direct Routing</span></span>
- <span data-ttu-id="4338d-109">Benutzer hat Enterprise-VoIP aktiviert</span><span class="sxs-lookup"><span data-stu-id="4338d-109">User has Enterprise Voice enabled</span></span>
- <span data-ttu-id="4338d-110">Der Nutzer ist online und nicht in Skype for Business vor Ort.</span><span class="sxs-lookup"><span data-stu-id="4338d-110">User is homed online and not in Skype for Business on premises</span></span>
- <span data-ttu-id="4338d-111">Benutzer hat eine Anrufrichtlinie für Teams aktiviert</span><span class="sxs-lookup"><span data-stu-id="4338d-111">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="4338d-112">In den folgenden Abschnitten wird beschrieben, wie Sie die Kriterien mithilfe von PowerShell überprüfen.</span><span class="sxs-lookup"><span data-stu-id="4338d-112">The following sections describe how to use PowerShell to check the criteria.</span></span> <span data-ttu-id="4338d-113">In den meisten Fällen müssen Sie sich verschiedene Eigenschaften in der Ausgabe des Cmdlets Get-CsOnlineUser ansehen.</span><span class="sxs-lookup"><span data-stu-id="4338d-113">In most cases, you need to look at various properties in the output of the Get-CsOnlineUser cmdlet.</span></span> <span data-ttu-id="4338d-114">Beispiele gehen davon aus, dass $User entweder die UPN-oder die SIP-Adresse des Benutzers ist.</span><span class="sxs-lookup"><span data-stu-id="4338d-114">Examples assume $user is either the UPN or sip address of the user.</span></span>

## <a name="user-has-an-enabled-phone-system-mcoev-license"></a><span data-ttu-id="4338d-115">Der Benutzer verfügt über eine aktivierte Telefon System Lizenz ("MCOEV").</span><span class="sxs-lookup"><span data-stu-id="4338d-115">User has an enabled Phone System (“MCOEV”) license</span></span>

<span data-ttu-id="4338d-116">Sie müssen sicherstellen, dass der zugewiesene Plan für den Benutzer das **CapabilityStatus-Attribut auf Enabled** und den **Funktionsplan auf MCOEV** (Phone System License) zeigt.</span><span class="sxs-lookup"><span data-stu-id="4338d-116">You must ensure that the assigned plan for the user shows the **CapabilityStatus attribute set to Enabled** and the **Capability Plan set to MCOEV** (Phone System license).</span></span> <span data-ttu-id="4338d-117">Möglicherweise sehen Sie MCOEV, MCOEV1 usw.</span><span class="sxs-lookup"><span data-stu-id="4338d-117">You might see MCOEV, MCOEV1, and so on.</span></span> <span data-ttu-id="4338d-118">Alle sind akzeptabel--solange der Kapazitäts Plan mit MCOEV beginnt.</span><span class="sxs-lookup"><span data-stu-id="4338d-118">All are acceptable--as long as the Capability Plan starts with MCOEV.</span></span>

<span data-ttu-id="4338d-119">Um zu überprüfen, ob die Attribute richtig festgesetzt sind, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="4338d-119">To check that the attributes are set correctly, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="4338d-120">Die Ausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4338d-120">The output will look like the following.</span></span> <span data-ttu-id="4338d-121">Sie müssen nur die Attribute **CapabilityStatus** und **Capability Plan** überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4338d-121">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```
<Plan SubscribedPlanId="2f9eda01-4630-4a5c-bdb3-cf195f22d240"  
   ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
   CapabilityStatus="Enabled"  
   AssignedTimestamp="2020-04-21T18:31:13Z" 
   ServicePlanId="4828c8ec-dc2e-4779-b502-87ac9ce28ab7" 
   xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11"> 
  <Capability> 
     <Capability Plan="MCOEV" 
     xmlns="http://schemas.microsoft.com/online/MCO/2009/01"/> 
  </Capability>
</Plan>
```


## <a name="user-has-microsoft-calling-plan-or-is-enabled-for-direct-routing"></a><span data-ttu-id="4338d-122">Der Benutzer hat einen Microsoft-Anrufplan oder ist für die direkte Weiterleitung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4338d-122">User has Microsoft Calling Plan OR is enabled for Direct Routing</span></span>

<span data-ttu-id="4338d-123">**Wenn der Benutzer Microsoft-Anrufplan hat**, müssen Sie sicherstellen, dass das **CapabilityStatus-Attribut auf Enabled festzulegen ist**und dass der **Kapazitätsplan auf MCOPSTN festgesetzt ist**.</span><span class="sxs-lookup"><span data-stu-id="4338d-123">**If the user has Microsoft Calling Plan**, you must ensure that the **CapabilityStatus attribute is set to Enabled**, and that the **Capability Plan is set to MCOPSTN**.</span></span> <span data-ttu-id="4338d-124">Möglicherweise sehen Sie MCOPSTN1, MCOPSTN2 usw.</span><span class="sxs-lookup"><span data-stu-id="4338d-124">You might see MCOPSTN1, MCOPSTN2, and so on.</span></span> <span data-ttu-id="4338d-125">Alle sind akzeptabel--solange der Kapazitäts Plan mit MCOPSTN beginnt.</span><span class="sxs-lookup"><span data-stu-id="4338d-125">All are acceptable--as long as the Capability Plan starts with MCOPSTN.</span></span>

<span data-ttu-id="4338d-126">Verwenden Sie den folgenden Befehl, um die Attribute zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4338d-126">To check the attributes, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|select AssignedPlan|fl
```

<span data-ttu-id="4338d-127">Die Ausgabe sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="4338d-127">The output will look like the following.</span></span> <span data-ttu-id="4338d-128">Sie müssen nur die Attribute **CapabilityStatus** und **Capability Plan** überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4338d-128">You only need to check the **CapabilityStatus** and the **Capability Plan** attributes:</span></span>

```  
<Plan SubscribedPlanId="71d1258e-a4e6-443f-884e-0f3d6f644bb1" 
ServiceInstance="MicrosoftCommunicationsOnline/NOAM-0M-DMT" 
CapabilityStatus="Enabled"    
AssignedTimestamp="2018-09-18T18:41:42Z" 
ServicePlanId="5a10155d-f5c1-411a-a8ec-e99aae125390" 
xmlns="http://schemas.microsoft.com/online/directoryservices/change/2008/11">
 <Capability>
    <Capability Plan="MCOPSTN2" 
    xmlns="http://schemas.microsoft.com/online/MCO/2009/01" />
 </Capability>
</Plan>
  ```

<span data-ttu-id="4338d-129">**Wenn der Benutzer für die direkte Weiterleitung aktiviert ist**, muss dem Benutzer ein ungleich NULL-Wert für OnlineVoiceRoutingPolicy zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4338d-129">**If the user is enabled for Direct Routing**, the user must be assigned a non-null value for OnlineVoiceRoutingPolicy.</span></span> <span data-ttu-id="4338d-130">Verwenden Sie zum Überprüfen des Attributs den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="4338d-130">To check the attribute, use the following command:</span></span>
  
```
Get-CsOnlineUser -Identity $user|Select OnlineVoiceRoutingPolicy 
```

<span data-ttu-id="4338d-131">Die Ausgabe sollte einen Wert ungleich NULL aufweisen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="4338d-131">The output should have a non-null value, for example:</span></span>

```
OnlineVoiceRoutingPolicy
------------------------
Test_Policy
```

## <a name="user-has-enterprise-voice-enabled"></a><span data-ttu-id="4338d-132">Benutzer hat Enterprise-VoIP aktiviert</span><span class="sxs-lookup"><span data-stu-id="4338d-132">User has Enterprise Voice enabled</span></span>

<span data-ttu-id="4338d-133">Verwenden Sie den folgenden Befehl, um zu überprüfen, ob der Benutzer Enterprise-VoIP aktiviert hat:</span><span class="sxs-lookup"><span data-stu-id="4338d-133">To check if the user has Enterprise Voice enabled, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select EnterpriseVoiceEnabled
```

<span data-ttu-id="4338d-134">Die Ausgabe sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4338d-134">The output should look like:</span></span>

```
EnterpriseVoiceEnabled
----------------------
                  True

```
 
## <a name="user-is-homed-online-and-not-in-skype-for-business-on-premises"></a><span data-ttu-id="4338d-135">Der Nutzer ist online und nicht in Skype for Business vor Ort.</span><span class="sxs-lookup"><span data-stu-id="4338d-135">User is homed online and not in Skype for Business on premises</span></span>

<span data-ttu-id="4338d-136">Um sicherzustellen, dass der Benutzer online und nicht in Skype for Business lokal gehostet wird, darf der RegistrarPool nicht NULL sein, und der Hostinganbieter muss einen Wert enthalten, der mit "sipfed. Online" beginnt.</span><span class="sxs-lookup"><span data-stu-id="4338d-136">To ensure the user is homed online and not in Skype for Business on premises, the RegistrarPool must not be null and the HostingProvider must contain a value that starts with “sipfed.online.”</span></span>  <span data-ttu-id="4338d-137">Verwenden Sie den folgenden Befehl, um die Werte zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="4338d-137">To check the values, use the following command:</span></span>

```
Get-CsOnlineUser -Identity $user|Select RegistrarPool, HostingProvider
```

<span data-ttu-id="4338d-138">Die Ausgabe sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4338d-138">The output should be similar to:</span></span>

```
RegistrarPool                 HostingProvider
-------------                 ---------------
sippoolbn10M02.infra.lync.com sipfed.online.lync.com
```

## <a name="user-has-teams-calling-policy-enabled"></a><span data-ttu-id="4338d-139">Benutzer hat eine Anrufrichtlinie für Teams aktiviert</span><span class="sxs-lookup"><span data-stu-id="4338d-139">User has Teams Calling Policy enabled</span></span>

<span data-ttu-id="4338d-140">Die effektive TeamsCallingPolicy des Benutzers muss AllowPrivateCalling auf "true" festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="4338d-140">The user’s effective TeamsCallingPolicy must have AllowPrivateCalling set to true.</span></span>  <span data-ttu-id="4338d-141">Standardmäßig erben Benutzer die globale Richtlinie, bei der AllowPrivateCallingPolicy standardmäßig auf "true" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4338d-141">By default, users inherit the global policy, which has AllowPrivateCallingPolicy set to true by default.</span></span>

<span data-ttu-id="4338d-142">Verwenden Sie den folgenden Befehl, um die TeamsCallingPolicy für einen Benutzer abzurufen und zu überprüfen, ob AllowPrivateCalling auf "true" festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="4338d-142">To get the TeamsCallingPolicy for a user and to check that AllowPrivateCalling is set to true, use the following command:</span></span>

```
if (($p=(get-csonlineuser -Identity $user).TeamsCallingPolicy) -eq $null) {Get-CsTeamsCallingPolicy -Identity global} else {get-csteamscallingpolicy -Identity $p}
```

<span data-ttu-id="4338d-143">Die Ausgabe sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="4338d-143">The output should look like:</span></span>

```
Identity                   : Global
Description                :
AllowPrivateCalling        : True
AllowWebPSTNCalling        : True
AllowVoicemail             : UserOverride
AllowCallGroups            : True
AllowDelegation            : True
AllowCallForwardingToUser  : True
AllowCallForwardingToPhone : True
PreventTollBypass          : False
BusyOnBusyEnabledType      : Disabled
MusicOnHoldEnabledType     : Enabled
``` 

## <a name="additional-notes"></a><span data-ttu-id="4338d-144">Zusätzliche Notizen</span><span class="sxs-lookup"><span data-stu-id="4338d-144">Additional notes</span></span>

-   <span data-ttu-id="4338d-145">Möglicherweise müssen Sie den Microsoft Teams-Client neu starten, nachdem Sie eine dieser Konfigurationsänderungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="4338d-145">You may need to restart the Teams client after making any of these configuration changes.</span></span>

-   <span data-ttu-id="4338d-146">Wenn Sie kürzlich eines der oben aufgeführten Kriterien aktualisiert haben, müssen Sie möglicherweise einige Stunden warten, bis der Client die neuen Einstellungen erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="4338d-146">If you recently updated any of the above criteria, you may need to wait a few hours for the client to receive the new settings.</span></span>

-   <span data-ttu-id="4338d-147">Wenn die Wähltastatur weiterhin nicht angezeigt wird, überprüfen Sie, ob ein Bereitstellungsfehler vorliegt, indem Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="4338d-147">If you still don’t see the dial pad, check if there is a provisioning error by using the following command:</span></span>

  ```
  Get-CsOnlineUser -Identity $user|Select McoValidationError
  ```

-    <span data-ttu-id="4338d-148">Wenn es mehr als 24 Stunden war und Sie immer noch Probleme haben, wenden Sie sich an den Support.</span><span class="sxs-lookup"><span data-stu-id="4338d-148">If it has been more than 24 hours and you are still seeing problems, contact Support.</span></span>


