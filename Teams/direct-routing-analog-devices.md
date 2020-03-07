---
title: Direktes Routing – Verbinden von analogen Geräten
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Lesen Sie diesen Artikel, um zu erfahren, wie Sie analoge Geräte mit dem direkten Routing von Microsoft Phone System verwenden können.
ms.openlocfilehash: 45128b8806644e4399687787bcce251ccb807d85
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558515"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="ec217-103">Verwenden von analogen Geräten mit direktem Telefon System-Routing</span><span class="sxs-lookup"><span data-stu-id="ec217-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="ec217-104">In diesem Artikel wird beschrieben, wie Sie analoge Geräte mit direktem Telefon System-Routing verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec217-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="ec217-105">Wenn Sie analoge Geräte mit Direct Routing verbinden möchten, müssen Sie einen analogen Telefonie-Adapter (ATA) verwenden, und dieser Adapter muss vom Anbieter des Certified Session Border Controller (SBC) unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="ec217-106">Wenn ein Benutzer einen Anruf von einem analogen Gerät tätigt, wird der Signal-und Medienfluss über den analogen Telefonie-Adapter (ATA) an den SBC übermittelt.</span><span class="sxs-lookup"><span data-stu-id="ec217-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="ec217-107">Der SBC sendet den Anruf an einen Microsoft Teams-Endpunkt oder an das öffentlich geschaltete Telefon Netzwerk (PSTN) basierend auf der internen Routingtabelle.</span><span class="sxs-lookup"><span data-stu-id="ec217-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="ec217-108">Wenn ein Gerät einen Anruf tätigt, hängt die Route, die es ausführt, von den für das Gerät erstellten Routing Richtlinien ab.</span><span class="sxs-lookup"><span data-stu-id="ec217-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="ec217-109">In der nachstehenden Abbildung ist das direkte Routing so konfiguriert, dass alle Teams, die die Nummern zwischen + 1425 4xx XX XX und + 1425 5xx XX XX anrufen, die rote Route (gepunktete Linie) und alle PSTN-Anrufe von und zu Nummern zwischen + 1425 4xx XX XX und einer beliebigen anderen Zahl außer  Nummernbereich + 1425 5xx XX XX müssen die blaue Route (durchgezogene Linie) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ec217-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

![Diagramm mit direkter Routing Konfiguration](media/direct-routing-analog-device.png)

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="ec217-111">Beispiel: Konfigurieren der Verwendung von analogen Geräten mit direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ec217-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="ec217-112">Wenn Sie die Verwendung von analogen Geräten mit direktem Routing konfigurieren möchten, müssen Sie den analogen Telefonie-Adapter mit dem SBC verbinden und den SBC so konfigurieren, dass er mit direktem Routing funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ec217-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="ec217-113">Dieses Beispiel führt Sie durch die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="ec217-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="ec217-114">Verbinden Sie den SBC mit Direct Routing.</span><span class="sxs-lookup"><span data-stu-id="ec217-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="ec217-115">Erstellen Sie die PSTN-Nutzung.</span><span class="sxs-lookup"><span data-stu-id="ec217-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="ec217-116">Erstellen Sie eine VoIP-Route, und ordnen Sie Sie der PSTN-Nutzung zu.</span><span class="sxs-lookup"><span data-stu-id="ec217-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="ec217-117">Weisen Sie die VoIP-Route der PSTN-Nutzung zu.</span><span class="sxs-lookup"><span data-stu-id="ec217-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="ec217-118">Aktivieren Sie den Online Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ec217-118">Enable the online user.</span></span>
6. <span data-ttu-id="ec217-119">Weisen Sie dem Benutzer die VoIP-Routen Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="ec217-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="ec217-120">Erstellen Sie eine VoIP-Route für ein analoges Gerät.</span><span class="sxs-lookup"><span data-stu-id="ec217-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="ec217-121">Informationen zum Verbinden eines ATA mit einem SBC und zum Konfigurieren des SBC finden Sie im Konfigurationshandbuch des SBC-Herstellers:</span><span class="sxs-lookup"><span data-stu-id="ec217-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>
- [<span data-ttu-id="ec217-122">AudioCodes-Konfigurationsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ec217-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)
- [<span data-ttu-id="ec217-123">Menüband-Konfigurationsdokumentation</span><span class="sxs-lookup"><span data-stu-id="ec217-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="ec217-124">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="ec217-124">Step 1.</span></span>  <span data-ttu-id="ec217-125">Verbinden des SBC mit Direct Routing</span><span class="sxs-lookup"><span data-stu-id="ec217-125">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="ec217-126">Mit dem folgenden Befehl wird die SBC-Verbindung wie folgt konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="ec217-126">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="ec217-127">FQDN SBC.contoso.com</span><span class="sxs-lookup"><span data-stu-id="ec217-127">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="ec217-128">Signalisierungs-Port 5068</span><span class="sxs-lookup"><span data-stu-id="ec217-128">Signaling port 5068</span></span>
- <span data-ttu-id="ec217-129">Medien Umgehungsmodus</span><span class="sxs-lookup"><span data-stu-id="ec217-129">Media bypass mode</span></span>
- <span data-ttu-id="ec217-130">Anrufverlaufs Informationen, die an den SBC weitergeleitet werden –</span><span class="sxs-lookup"><span data-stu-id="ec217-130">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="ec217-131">P-Asserted-Identity (Pai)-Kopfzeile wird zusammen mit dem Anruf weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="ec217-131">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="ec217-132">Schritt 2: Erstellen der PSTN-Nutzung</span><span class="sxs-lookup"><span data-stu-id="ec217-132">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="ec217-133">Der nächste Befehl erstellt eine leere PSTN-Nutzung.</span><span class="sxs-lookup"><span data-stu-id="ec217-133">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="ec217-134">Online PSTN-Nutzungen sind Zeichenfolgenwerte, die für die Anruf Autorisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-134">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="ec217-135">Eine Online-PSTN-Nutzung verknüpft eine Online-VoIP-Richtlinie mit einer Route.</span><span class="sxs-lookup"><span data-stu-id="ec217-135">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="ec217-136">In diesem Beispiel wird die Zeichenfolge "Interop" zur aktuellen Liste der verfügbaren PSTN-Nutzungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ec217-136">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="ec217-137">Schritt 3: Erstellen Sie eine VoIP-Route, und ordnen Sie Sie der PSTN-Verwendung zu:</span><span class="sxs-lookup"><span data-stu-id="ec217-137">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="ec217-138">Dieser Befehl erstellt eine neue Online-VoIP-Route mit der Identität "Analog-Interop" für den Nummernbereich + 1425 XXX XX XX.</span><span class="sxs-lookup"><span data-stu-id="ec217-138">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="ec217-139">Die VoIP-Route gilt für eine Liste von Online-Gateways SBC.contoso.com und ordnet die Route der Online-PSTN-Nutzung "Interop" zu.</span><span class="sxs-lookup"><span data-stu-id="ec217-139">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="ec217-140">Eine VoIP-Route enthält einen regulären Ausdruck, der angibt, welche Telefonnummern über eine bestimmte VoIP-Route weitergeleitet werden:</span><span class="sxs-lookup"><span data-stu-id="ec217-140">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7}])$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="ec217-141">Schritt 4: Zuweisen der VoIP-Route zur PSTN-Nutzung:</span><span class="sxs-lookup"><span data-stu-id="ec217-141">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="ec217-142">Mit diesem Befehl wird eine neue Online-VoIP-Richtlinie für einzelne Benutzer mit der Identität "AnalogInteropPolicy" erstellt.</span><span class="sxs-lookup"><span data-stu-id="ec217-142">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="ec217-143">Dieser Richtlinie wird eine einzelne Online PSTN-Nutzung zugewiesen: "Interop".</span><span class="sxs-lookup"><span data-stu-id="ec217-143">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="ec217-144">Schritt 5: Aktivieren des Online Benutzers</span><span class="sxs-lookup"><span data-stu-id="ec217-144">Step 5: Enable the online user</span></span>

<span data-ttu-id="ec217-145">Dieser Befehl ändert das Benutzerkonto mit der Identität exampleuser@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ec217-145">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="ec217-146">In diesem Fall wird das Konto geändert, um Enterprise-VoIP, die Microsoft-Implementierung von VoIP, mit aktivierter Voicemail zu aktivieren und diesem Benutzer die Nummer + 14255000000 zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="ec217-146">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="ec217-147">Dieser Befehl sollte für jeden Team Benutzer (mit Ausnahme von ATA-Geräte Benutzern) im Mandanten Mandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-147">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="ec217-148">Schritt 6: Zuweisen der VoIP-Routen Richtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="ec217-148">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="ec217-149">Mit diesem Befehl wird dem Benutzer die Richtlinie für die Online-VoIP-AnalogInteropPolicy des Benutzers mit dem Identitäts exampleuser@contoso.com zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="ec217-149">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="ec217-150">Dieser Befehl sollte für jeden Team Benutzer (mit Ausnahme von ATA-Geräte Benutzern) im Mandanten Mandanten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-150">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="ec217-151">Schritt 7: Erstellen einer VoIP-Route für ein analoges Gerät</span><span class="sxs-lookup"><span data-stu-id="ec217-151">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="ec217-152">Dieser Befehl erstellt eine Online-VoIP-Route mit der Identität "Analog-Interop" für den Nummernbereich + 1425 4xx XX XX, die für eine Liste von Online-Gateways SBC.contoso.com und mit der Online-PSTN-Nutzung "Interop" verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="ec217-152">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="ec217-153">Dieser Befehl sollte für jedes analoge Gerät mit dem entsprechenden Telefonnummernmuster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-153">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="ec217-154">Alternativ können Sie beim Konfigurieren der Online-VoIP-Route in einem der vorherigen Schritte ein geeignetes Zahlenmuster für analoge Geräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="ec217-154">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6}])$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="ec217-155">Überlegungen</span><span class="sxs-lookup"><span data-stu-id="ec217-155">Considerations</span></span>

- <span data-ttu-id="ec217-156">Sofern nicht anders angegeben, handelt es sich bei einem analogen Gerät um ein Gerät, das DTMF-Ziffern senden kann, um einen Anruf zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="ec217-156">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="ec217-157">Beispielsweise analoge Telefone, Faxgeräte und Overhead-Auslagerungsgeräte.</span><span class="sxs-lookup"><span data-stu-id="ec217-157">For example, analog phones, fax machines, and overhead pagers.</span></span>
- <span data-ttu-id="ec217-158">Analoge Telefone, die mit einem ATA verbunden sind, können von Teams nicht durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="ec217-158">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="ec217-159">Teams Benutzer müssen die Telefonnummer, die dem Gerät zugeordnet ist, manuell eingeben, um das Gerät anzurufen.</span><span class="sxs-lookup"><span data-stu-id="ec217-159">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="ec217-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec217-160">See also</span></span>

[<span data-ttu-id="ec217-161">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ec217-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="ec217-162">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="ec217-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
