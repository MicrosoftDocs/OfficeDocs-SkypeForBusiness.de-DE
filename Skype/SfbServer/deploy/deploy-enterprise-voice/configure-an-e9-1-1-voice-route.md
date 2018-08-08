---
title: Konfigurieren einer E9-1-1-VoIP-Route in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: Konfigurieren von E9-1-1-VoIP-Routen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 85259b6490b0f14d94d4d7c26f343d638911d909
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20988748"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a><span data-ttu-id="bf41b-103">Konfigurieren einer E9-1-1-VoIP-Route in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="bf41b-103">Configure an E9-1-1 voice route in Skype for Business Server</span></span>
 
<span data-ttu-id="bf41b-104">Konfigurieren von E9-1-1-VoIP-Routen in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="bf41b-104">Configure E9-1-1 voice routes in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="bf41b-105">Für die Bereitstellung von E9-1-1 müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf41b-105">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="bf41b-106">Ausführliche Informationen zum Erstellen von VoIP-Routen finden Sie unter [Erstellen oder ändern eine VoIP-Route in Skype für Business](create-or-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="bf41b-106">For details about creating voice routes, see [Create or modify a voice route in Skype for Business](create-or-modify-a-voice-route.md).</span></span> <span data-ttu-id="bf41b-107">Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält.</span><span class="sxs-lookup"><span data-stu-id="bf41b-107">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bf41b-108">Wenn Sie Standortinformationen in einen E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt.</span><span class="sxs-lookup"><span data-stu-id="bf41b-108">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="bf41b-109">Zu diesem Zweck festlegen Sie EnablePIDFLOSupport das Flag im Cmdlet **Set-CsTrunkConfiguration** auf True.</span><span class="sxs-lookup"><span data-stu-id="bf41b-109">To do this, set the EnablePIDFLOSupport flag on the **Set-CsTrunkConfiguration** cmdlet to True.</span></span> <span data-ttu-id="bf41b-110">Der Standardwert für „EnablePIDFLOSupport“ lautet „False“.</span><span class="sxs-lookup"><span data-stu-id="bf41b-110">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="bf41b-111">Beispiel: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` es ist nicht notwendig, den Empfang von Standortinformationen für fallback öffentlich Gateways Telephone Network (Telefonfestnetz PSTN) und Emergency Location Identification-Nummer (ELIN)-Gateways gewechselt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf41b-111">For example: `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>
  
### <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="bf41b-112">So konfigurieren Sie eine E9-1-1-VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="bf41b-112">To configure an E9-1-1 voice route</span></span>

1. <span data-ttu-id="bf41b-113">Melden Sie sich mit einem Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsVoiceAdministrator“ ist, am Computer an.</span><span class="sxs-lookup"><span data-stu-id="bf41b-113">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>
    
2.  <span data-ttu-id="bf41b-114">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="bf41b-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bf41b-115">Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf41b-115">Run the following cmdlet to create a new PSTN usage record.</span></span> 
    
    <span data-ttu-id="bf41b-116">Der Name muss dem Namen entsprechen, den Sie für die Einstellung **PSTN** in der Standortrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="bf41b-116">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="bf41b-117">Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz „Notfallverwendung“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="bf41b-117">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="bf41b-118">Weitere Informationen hierzu finden Sie unter [Konfigurieren von VoIP-Richtlinien, PSTN-verwendungsdatensätzen und VoIP-Routen in Skype für Unternehmen](voice-and-pstn.md).</span><span class="sxs-lookup"><span data-stu-id="bf41b-118">For details, see [Configure voice policies, PSTN usage records, and voice routes in Skype for Business](voice-and-pstn.md).</span></span>
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. <span data-ttu-id="bf41b-119">Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des im vorherigen Schritte erstellten PSTN-Verwendungsdatensatzes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bf41b-119">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="bf41b-120">Das Nummernmuster muss dem Nummernmuster entsprechen, das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bf41b-120">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="bf41b-121">Ein Vorzeichen "+" ist erforderlich, da Skype für Unternehmen hinzugefügt "+", um Notrufe.</span><span class="sxs-lookup"><span data-stu-id="bf41b-121">A "+" sign is needed because Skype for Business adds "+" to emergency calls.</span></span> <span data-ttu-id="bf41b-122">„Co1-pstngateway-1“ ist die Dienst-ID des SIP-Trunks für den E9-1-1-Dienstanbieter oder für das ELIN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="bf41b-122">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="bf41b-123">Im folgenden Beispiel wird für die VoIP-Route der Name „EmergencyRoute“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bf41b-123">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. <span data-ttu-id="bf41b-124">Optional können Sie sollten für SIP-Trunk-Verbindungen, führen Sie das folgende Cmdlet aus, um eine lokale Route für Anrufe erstellen, die nicht von der E9-1-1-Dienstanbieter SIP-Trunk behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="bf41b-124">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider's SIP trunk.</span></span> <span data-ttu-id="bf41b-125">Diese Route wird verwendet, wenn die Verbindung zum E9-1-1-Dienstanbieter nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bf41b-125">This route will be used if the connection to the E9-1-1 service provider is not available.</span></span> 
    
    <span data-ttu-id="bf41b-126">Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung „Local“ verfügt.</span><span class="sxs-lookup"><span data-stu-id="bf41b-126">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


