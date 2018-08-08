---
title: Planen von Standortrichtlinien für Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lesen Sie in diesem Thema erfahren, wie Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung in Skype planen.
ms.openlocfilehash: cbc4bdbf552c3839cef0701dcf3e47e4603a270e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971167"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="4df95-103">Planen von Standortrichtlinien für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="4df95-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="4df95-104">Lesen Sie in diesem Thema erfahren, wie Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung in Skype planen.</span><span class="sxs-lookup"><span data-stu-id="4df95-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4df95-105">Skype für Business Server unterstützt jetzt die Konfiguration von mehreren Notfall Zahlen für einen Client an.</span><span class="sxs-lookup"><span data-stu-id="4df95-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="4df95-106">Wenn Sie mehrere Notfall Nummern konfigurieren möchten, müssen Sie die Informationen in [mehrere Notfall Zahlen in Skype für Business Server planen](multiple-emergency-numbers.md) und [Konfigurieren von mehreren Notfall Zahlen in Skype für Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)befolgen.</span><span class="sxs-lookup"><span data-stu-id="4df95-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="4df95-107">Erstellen von ortungsrichtlinien mithilfe der Skype für die Business-Systemsteuerung oder mit dem [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4df95-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="4df95-108">Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype für Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4df95-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="4df95-109">Jede Standortrichtlinie enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="4df95-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="4df95-110">**Erweiterte Notfalldienste aktivieren**</span><span class="sxs-lookup"><span data-stu-id="4df95-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="4df95-111">Wenn dieser Wert aktiviert ist, wird der Client für erweiterte Notfalldienste (E9-1-1) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4df95-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="4df95-112">Wenn ein Client registriert, versucht, einen Speicherort aus dem Dienst Standortinformationen zu erhalten und berücksichtigt die Standortinformationen als Teil eines Notrufs.</span><span class="sxs-lookup"><span data-stu-id="4df95-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="4df95-113">**Standort**</span><span class="sxs-lookup"><span data-stu-id="4df95-113">**Location**</span></span>
  
<span data-ttu-id="4df95-114">Diese Einstellung wird nur verwendet, wenn **Erweiterte Notfalldienste aktivieren** aktiviert ist. </span><span class="sxs-lookup"><span data-stu-id="4df95-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="4df95-115">Sie können die Einstellung **Standort** wie folgt konfigurieren, um das Clientverhalten zu definieren:   </span><span class="sxs-lookup"><span data-stu-id="4df95-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="4df95-116">Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="4df95-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="4df95-117">Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen.</span><span class="sxs-lookup"><span data-stu-id="4df95-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="4df95-p104">Wenn der Wert auf **Haftungsausschluss** festgelegt ist, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird. Zudem wird ihm ein Haftungsausschluss angezeigt, wenn er versucht, die Aufforderung zu verwerfen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="4df95-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4df95-p105">Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. </span><span class="sxs-lookup"><span data-stu-id="4df95-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="4df95-122">**Haftungsausschluss der erweiterten Notfalldienste**</span><span class="sxs-lookup"><span data-stu-id="4df95-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="4df95-123">Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen.</span><span class="sxs-lookup"><span data-stu-id="4df95-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="4df95-124">In Skype für Business Server können Sie ortungsrichtlinie verwenden, um verschiedene Haftungsausschlüsse für unterschiedliche Gebietsschemas oder andere Gruppen von Benutzern festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4df95-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="4df95-125">**Notruf-Wählzeichenfolge (Notfallnummer)**</span><span class="sxs-lookup"><span data-stu-id="4df95-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="4df95-126">Diese Zeichenfolge Dial (weniger das führende Plus "+", aber einschließlich des Benutzers Dial Plan dazu Normalisierung) gibt an, dass ein Anruf ein Notruf ist.</span><span class="sxs-lookup"><span data-stu-id="4df95-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="4df95-127">Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4df95-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4df95-128">Wenn Ihre Organisation ein Präfix für den externen Zeile nicht verwendet, müssen Sie keine entsprechende Dial Plan Normalisierungsregel erstellen, die ein "+" der 911 Zeichenfolge vor dem Senden des Anrufs an das Ausgangsrouting auf einem Server mit Skype für Business Server; hinzufügt "+" wird automatisch von der Skype für Business-Client als Ergebnis der Standortrichtlinie vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4df95-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="4df95-129">Jedoch, wenn der Website ein Präfix für den externen Zugriff verwendet wird, müssen Sie eine Normalisierungsregel der betreffenden Dial Plan Richtlinie hinzuzufügen, die das Präfix für externen Zugriff entfernt und fügt die "+".</span><span class="sxs-lookup"><span data-stu-id="4df95-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="4df95-130">Beispielsweise wenn Ihres Standorts für ein Präfix für externen Zugriff von 9 verwendet wird und ein Benutzer 9 911 anwählt um ein Notruf platzieren, der Client verwendet seine Dial Plan Richtlinie dies normalisieren auf +911 vor der die gewählte Nummer durch die Routen im Standortprofil des Anrufers ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="4df95-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="4df95-131">**Notruf-Wählzeichenfolgenmasken (Notfallnummermaske)**</span><span class="sxs-lookup"><span data-stu-id="4df95-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="4df95-132">Eine durch Semikolons getrennte Liste mit Wählzeichenfolgen, die in die angegebene **Notrufwählzeichenfolge**übersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="4df95-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="4df95-133">Beispielsweise kann hinzuzufügenden 112, also die Anzahl der notrufunterstützung für die meisten Europa.</span><span class="sxs-lookup"><span data-stu-id="4df95-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="4df95-134">Eine Website besucht Skype für Geschäftsbenutzer in Europa wissen möglicherweise nicht, dass 911 die Notrufnummer US ist, aber sie können 112 einwählen und erhalten dasselbe Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="4df95-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="4df95-135">Achten Sie wie ein "+" vor jeder Zahl nicht mit der Emergency Dial Zeichenfolge einschließen, und wenn Sie externe Zeile Zugriffscodes verwenden, darauf, dass in der Richtlinie des Benutzers Dial Plan an die Ziffer Zugriffscode entfernt Normalisierungsregeln vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4df95-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="4df95-136">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="4df95-136">**PSTN usage**</span></span>
  
<span data-ttu-id="4df95-137">Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4df95-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4df95-138">Eine ortungsrichtlinie kann nur jeweils einmal zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4df95-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="4df95-139">In diesem PSTN-Verwendung überschreibt die PSTN-Verwendungen des Benutzers VoIP-Richtlinie zugewiesen, aber gilt nur für die Emergency DFÜ-Zeichenfolge oder auf eine der Emergency Dial Zeichenfolge Masken getätigte Anrufe.</span><span class="sxs-lookup"><span data-stu-id="4df95-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="4df95-140">**Benachrichtigungs-URI**</span><span class="sxs-lookup"><span data-stu-id="4df95-140">**Notification URI**</span></span>
  
<span data-ttu-id="4df95-p111">Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4df95-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="4df95-143">**Konferenz-URI**</span><span class="sxs-lookup"><span data-stu-id="4df95-143">**Conference URI**</span></span>
  
<span data-ttu-id="4df95-144">Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.  </span><span class="sxs-lookup"><span data-stu-id="4df95-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="4df95-145">**Konferenzmodus**</span><span class="sxs-lookup"><span data-stu-id="4df95-145">**Conference Mode**</span></span>
  
<span data-ttu-id="4df95-146">Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. </span><span class="sxs-lookup"><span data-stu-id="4df95-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="4df95-147">**Standortaktualisierungsintervall**</span><span class="sxs-lookup"><span data-stu-id="4df95-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="4df95-148">Gibt die Zeitdauer (in Stunden) zwischen Clientanforderungen für ein Location-Update aus dem Dienst Standortinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4df95-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="4df95-149">Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4df95-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="4df95-150">Der Standardwert lautet 4.</span><span class="sxs-lookup"><span data-stu-id="4df95-150">The default value is 4.</span></span>
  

