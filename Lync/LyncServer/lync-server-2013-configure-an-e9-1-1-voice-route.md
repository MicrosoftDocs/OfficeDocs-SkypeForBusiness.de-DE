---
title: 'Lync Server 2013: Konfigurieren einer E9-1-1-VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0a14c540ca8d9a8655f215449d90716cf6834f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a><span data-ttu-id="9dba9-102">Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dba9-102">Configure an E9-1-1 voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dba9-103">_**Letztes Änderungsstand des Themas:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="9dba9-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="9dba9-104">Zum Bereitstellen des Notruf-Features ("E9-1-1") müssen Sie zunächst eine VoIP-Route für Notrufe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9dba9-104">To deploy E9-1-1, you first need to configure an emergency call voice route.</span></span> <span data-ttu-id="9dba9-105">Ausführliche Informationen zum Erstellen von VoIP-Routen finden Sie unter [Create a Voice Route in lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="9dba9-105">For details about creating voice routes, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span> <span data-ttu-id="9dba9-106">Sie können auch mehrere Routen definieren, zum Beispiel wenn Ihre Bereitstellung einen primären und einen sekundären SIP-Trunk enthält.</span><span class="sxs-lookup"><span data-stu-id="9dba9-106">You may define more than one route if, for example, your deployment includes a primary SIP trunk and a secondary SIP trunk.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9dba9-107">Wenn Sie Standortinformationen in einem E9-1-1-INVITE-Befehl aufnehmen möchten, müssen Sie zunächst den SIP-Trunk konfigurieren, der zum Routen von Notrufen über das Gateway eine Verbindung mit dem E9-1-1-Dienstanbieter herstellt.</span><span class="sxs-lookup"><span data-stu-id="9dba9-107">To include location information in an E9-1-1 INVITE, you need to configure the SIP trunk that connects to the E9-1-1 service provider to route emergency calls through the gateway.</span></span> <span data-ttu-id="9dba9-108">Setzen Sie zu diesem Zweck im <STRONG>Set-CsTrunkConfiguration</STRONG>-Cmdlet das Flag "EnablePIDFLOSupport" auf "True".</span><span class="sxs-lookup"><span data-stu-id="9dba9-108">To do this, set the EnablePIDFLOSupport flag on the <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet to True.</span></span> <span data-ttu-id="9dba9-109">Der Standardwert für "EnablePIDFLOSupport" lautet "False".</span><span class="sxs-lookup"><span data-stu-id="9dba9-109">The default value for EnablePIDFLOSupport is False.</span></span> <span data-ttu-id="9dba9-110">Zum Beispiel:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span><span class="sxs-lookup"><span data-stu-id="9dba9-110">For example: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE></span></span><BR><span data-ttu-id="9dba9-111">Es ist nicht erforderlich, Empfangsstandorte für Ausweich-PSTN-Gateways und -ELIN-Gateways (Emergency Location Identification Number) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9dba9-111">It is not necessary to enable receiving locations for fallback public switched telephone network (PSTN) gateways and Emergency Location Identification Number (ELIN) gateways.</span></span>



</div>

<span data-ttu-id="9dba9-112">Ausführliche Informationen zum Arbeiten mit VoIP-Routen finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9dba9-112">For details about working with voice routes, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9dba9-113">**Gruppe-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="9dba9-113">**Set-CsPstnUsage**</span></span>

  - <span data-ttu-id="9dba9-114">**Get-CsPstnUsage**</span><span class="sxs-lookup"><span data-stu-id="9dba9-114">**Get-CsPstnUsage**</span></span>

  - <span data-ttu-id="9dba9-115">**New-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="9dba9-115">**New-CsVoiceRoute**</span></span>

  - <span data-ttu-id="9dba9-116">**Get-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="9dba9-116">**Get-CsVoiceRoute**</span></span>

  - <span data-ttu-id="9dba9-117">**Gruppe-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="9dba9-117">**Set-CsVoiceRoute**</span></span>

  - <span data-ttu-id="9dba9-118">**Remove-CsVoiceRoute**</span><span class="sxs-lookup"><span data-stu-id="9dba9-118">**Remove-CsVoiceRoute**</span></span>

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a><span data-ttu-id="9dba9-119">So konfigurieren Sie eine E9-1-1-VoIP-Route</span><span class="sxs-lookup"><span data-stu-id="9dba9-119">To configure an E9-1-1 voice route</span></span>

1.  <span data-ttu-id="9dba9-120">Melden Sie sich mit einem Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsVoiceAdministrator" ist, am Computer an.</span><span class="sxs-lookup"><span data-stu-id="9dba9-120">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins groups, or a member of the CsVoiceAdministrator administrative role.</span></span>

2.  <span data-ttu-id="9dba9-121">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="9dba9-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9dba9-122">Führen Sie das folgende Cmdlet aus, um einen neuen PSTN-Verwendungsdatensatz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dba9-122">Run the following cmdlet to create a new PSTN usage record.</span></span>
    
    <span data-ttu-id="9dba9-123">Das muss der gleiche Name sein, den Sie bei der Einstellung **PSTN** in der Standortrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="9dba9-123">This must be the same name that you will use for the **PSTN** setting in the location policy.</span></span> <span data-ttu-id="9dba9-124">Obgleich Ihre Bereitstellung mehrere Telefonverwendungsdatensätze enthalten wird, fügt das folgende Beispiel der aktuellen Liste der verfügbaren PSTN-Verwendungen den Datensatz "Notfallverwendung" hinzu.</span><span class="sxs-lookup"><span data-stu-id="9dba9-124">Although your deployment will have multiple phone usage records, the following example adds "Emergency Usage" to the current list of available PSTN usages.</span></span> <span data-ttu-id="9dba9-125">Ausführliche Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen in lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="9dba9-125">For details, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  <span data-ttu-id="9dba9-126">Führen Sie das folgende Cmdlet aus, um eine neue VoIP-Route unter Verwendung des eben erstellten PSTN-Verwendungsdatensatzes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9dba9-126">Run the following cmdlet to create a new voice route by using the PSTN usage record that you created in the previous step.</span></span>
    
    <span data-ttu-id="9dba9-127">Das Nummernmuster muss das gleiche wie das in der Einstellung **Notrufwählzeichenfolge** in der Standortrichtlinie verwendete sein.</span><span class="sxs-lookup"><span data-stu-id="9dba9-127">The number pattern must be the same number pattern that is used in the **Emergency Dial String** setting in the location policy.</span></span> <span data-ttu-id="9dba9-128">Ein Pluszeichen "+" ist erforderlich, da lync "+" zu Notrufen hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="9dba9-128">A "+" sign is needed because Lync adds "+" to emergency calls.</span></span> <span data-ttu-id="9dba9-129">"Co1-pstngateway-1" ist die Dienst-ID des SIP-Trunks für den Notrufdienstanbieter oder für das ELIN-Gateway.</span><span class="sxs-lookup"><span data-stu-id="9dba9-129">"Co1-pstngateway-1" is the SIP trunk service ID for the E9-1-1 service provider or for the ELIN gateway service ID.</span></span> <span data-ttu-id="9dba9-130">Im folgenden Beispiel wird für die VoIP-Route der Name "EmergencyRoute" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="9dba9-130">The following example uses "EmergencyRoute" as the name of the voice route.</span></span>
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  <span data-ttu-id="9dba9-p105">Bei SIP-Trunk-Verbindungen wird optional die Ausführung des folgenden Cmdlets empfohlen, um eine lokale Route für Anrufe zu erstellen, die nicht über den SIP-Trunk des Anbieters für die Notrufunterstützung verarbeitet werden. Diese Route wird verwendet, wenn die Verbindung zu dem Anbieter für Notrufunterstützung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9dba9-p105">Optionally, for SIP trunk connections, we recommend that you run the following cmdlet to create a local route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available.</span></span>
    
    <span data-ttu-id="9dba9-133">Im folgenden Beispiel wird davon ausgegangen, dass der Benutzer in seiner VoIP-Richtlinie über die Verwendung "Local" verfügt.</span><span class="sxs-lookup"><span data-stu-id="9dba9-133">The following example assumes that user has "Local" usage in their voice policy.</span></span>
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

