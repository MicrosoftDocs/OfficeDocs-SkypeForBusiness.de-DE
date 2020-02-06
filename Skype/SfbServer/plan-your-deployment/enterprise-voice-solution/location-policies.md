---
title: Planen von Standortrichtlinien für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: In diesem Thema erfahren Sie, wie Sie in Skype for Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung planen.
ms.openlocfilehash: 5064197dd8d23113d7bfeca30fd3596d5ee89c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802805"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a><span data-ttu-id="caa45-103">Planen von Standortrichtlinien für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="caa45-103">Plan location policies for Skype for Business Server</span></span>
 
<span data-ttu-id="caa45-104">In diesem Thema erfahren Sie, wie Sie in Skype for Business Server Enterprise-VoIP Standortrichtlinien für eine erweiterte Notfalldienste (E9-1-1)-Bereitstellung planen.</span><span class="sxs-lookup"><span data-stu-id="caa45-104">Read this topic to learn how to plan location policies for an enhanced emergency services (E9-1-1) deployment in Skype for Business Server Enterprise Voice.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="caa45-105">Skype for Business Server unterstützt jetzt die Konfiguration mehrerer Notrufnummern für einen Client.</span><span class="sxs-lookup"><span data-stu-id="caa45-105">Skype for Business Server now supports the configuration of multiple emergency numbers for a client.</span></span> <span data-ttu-id="caa45-106">Wenn Sie mehrere Notrufnummern konfigurieren möchten, müssen Sie die Informationen unter [Planen mehrerer Notrufnummern in Skype for Business Server](multiple-emergency-numbers.md) und [Konfigurieren mehrerer Notrufnummern in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md)befolgen.</span><span class="sxs-lookup"><span data-stu-id="caa45-106">If you want to configure multiple emergency numbers, you must follow the information in [Plan for multiple emergency numbers in Skype for Business Server](multiple-emergency-numbers.md) and [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).</span></span> 
  
<span data-ttu-id="caa45-107">Sie erstellen Standortrichtlinien mithilfe des Skype Control Panels für Unternehmen oder mithilfe des Cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="caa45-107">You create location policies by using the Skype for Business Control Panel or by using the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="caa45-108">Weitere Informationen finden Sie unter [Erstellen von Standortrichtlinien in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="caa45-108">For more information, see [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).</span></span>
  
<span data-ttu-id="caa45-109">Jede Standortrichtlinie enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="caa45-109">Each location policy contains the following information:</span></span>
  
 <span data-ttu-id="caa45-110">**Erweiterte Notfalldienste aktivieren**</span><span class="sxs-lookup"><span data-stu-id="caa45-110">**Enable Enhanced 9-1-1**</span></span>
  
<span data-ttu-id="caa45-111">Wenn dieser Wert aktiviert ist, ist der Client für erweiterte Notfalldienste (E9-1-1) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="caa45-111">When this value is enabled, the client is enabled for enhanced emergency services (E9-1-1).</span></span> <span data-ttu-id="caa45-112">Wenn ein Client registriert wird, versucht er, einen Standort vom standortinformationsdienst abzurufen, und die Standortinformationen werden als Teil eines Notrufs aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="caa45-112">When a client registers, it attempts to acquire a location from the Location Information service and will include the location information as part of an emergency call.</span></span>
  
 <span data-ttu-id="caa45-113">**Standort**</span><span class="sxs-lookup"><span data-stu-id="caa45-113">**Location**</span></span>
  
<span data-ttu-id="caa45-114">Diese Einstellung wird nur verwendet, wenn **Erweiterte Notfalldienste aktivieren** aktiviert ist. </span><span class="sxs-lookup"><span data-stu-id="caa45-114">This setting is used only when **Enable Enhanced 9-1-1** is enabled.</span></span>
  
<span data-ttu-id="caa45-115">Sie können die Einstellung **Standort** wie folgt konfigurieren, um das Clientverhalten zu definieren:   </span><span class="sxs-lookup"><span data-stu-id="caa45-115">You can configure the **Location** setting to define the client behavior as follows:</span></span>
  
- <span data-ttu-id="caa45-116">Wenn der Wert auf **Nein** festgelegt wird, bedeutet dies, dass der Benutzer nicht zur Angabe eines Standorts aufgefordert wird.</span><span class="sxs-lookup"><span data-stu-id="caa45-116">Setting the value to **No** means that the user will not be prompted for a location.</span></span>
    
- <span data-ttu-id="caa45-117">Wenn der Wert auf **Ja** festgelegt wird, bedeutet dies, dass der Benutzer zur Angabe eines Standorts aufgefordert wird; er kann die Aufforderung aber verwerfen.</span><span class="sxs-lookup"><span data-stu-id="caa45-117">Setting the value to **Yes** means that the user will be prompted for a location, but can dismiss the prompt.</span></span>
    
- <span data-ttu-id="caa45-p104">Wenn der Wert auf **Haftungsausschluss** festgelegt ist, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird. Zudem wird ihm ein Haftungsausschluss angezeigt, wenn er versucht, die Aufforderung zu verwerfen. In allen Fällen kann der Benutzer den Client weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="caa45-p104">Setting the value to **Disclaimer** means that the user will be prompted for a location and also will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client.</span></span>
    
> [!NOTE]
> <span data-ttu-id="caa45-p105">Der Haftungsausschluss wird nicht angezeigt, wenn der Benutzer vor der Aktivierung für E9-1-1 bereits manuell einen Standort eingegeben hat. Aktualisierte Versionen des Haftungsausschlusses werden Benutzern nicht angezeigt, die den Haftungsausschluss bereits angezeigt haben. </span><span class="sxs-lookup"><span data-stu-id="caa45-p105">The disclaimer text will not appear if a user manually entered a location before being enabled for E9-1-1. Updates to the disclaimer text will not be viewed by users that have already viewed the disclaimer.</span></span> 
  
 <span data-ttu-id="caa45-122">**Haftungsausschluss der erweiterten Notfalldienste**</span><span class="sxs-lookup"><span data-stu-id="caa45-122">**Enhanced Emergency Service Disclaimer**</span></span>
  
<span data-ttu-id="caa45-123">Diese Einstellung gibt den Haftungsausschluss an, der Benutzern angezeigt wird, wenn sie die Eingabeaufforderung für einen Standort verwerfen.</span><span class="sxs-lookup"><span data-stu-id="caa45-123">This setting specifies the disclaimer that users see if they dismiss the prompt for a location.</span></span> <span data-ttu-id="caa45-124">In Skype for Business Server können Sie mithilfe der ortungsrichtlinie unterschiedliche Haftungsausschlüsse für verschiedene Gebietsschemas oder verschiedene Gruppen von Benutzern festlegen.</span><span class="sxs-lookup"><span data-stu-id="caa45-124">In Skype for Business Server, you can use location policy to set different disclaimers for different locales or different sets of users.</span></span>
  
 <span data-ttu-id="caa45-125">**Notruf-Wählzeichenfolge (Notfallnummer)**</span><span class="sxs-lookup"><span data-stu-id="caa45-125">**Emergency Dial String (E9-1-1 dial number)**</span></span>
  
<span data-ttu-id="caa45-126">Diese Wählzeichenfolge (abzüglich des führenden "+", aber einschließlich einer Normalisierung, die vom Wählplan des Benutzers ausgeführt wird) bedeutet, dass ein Anruf ein Notruf ist.</span><span class="sxs-lookup"><span data-stu-id="caa45-126">This dial string (less the leading "+", but including any normalization done by the user's Dial Plan) signifies that a call is an emergency call.</span></span> <span data-ttu-id="caa45-127">Die **Notrufwählzeichenfolge** veranlasst den Client, Standort- und Rückrufinformationen mit dem Anruf zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="caa45-127">The **Emergency Dial String** causes the client to include location and callback information with the call.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa45-128">Wenn in Ihrer Organisation kein Präfix für den Zugriff auf externe Leitungen verwendet wird, müssen Sie keine entsprechende Normalisierungsregel für Wählpläne erstellen, die der 911-Zeichenfolge vor dem Senden des Anrufs an ausgehendes Routing auf einem Server mit Skype for Business Server ein "+" hinzufügt. Das "+" wird dem Skype for Business-Client automatisch als Folge der ortungsrichtlinie vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="caa45-128">If your organization does not use an external line access prefix, you do not need to create a corresponding Dial Plan normalization rule that adds a "+" to the 911 string prior to sending the call to Outbound Routing on a server running Skype for Business Server; the "+" will be automatically prepended by the Skype for Business client as a result of the location policy.</span></span> <span data-ttu-id="caa45-129">Wenn Ihre Website jedoch ein externes Zugriffs Präfix verwendet, müssen Sie der entsprechenden Wähl Plan Richtlinie eine Normalisierungsregel hinzufügen, die das Präfix für den externen Zugriff abstreift und das "+" hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="caa45-129">However, if your site uses an external access prefix, you need to add a normalization rule to the applicable Dial Plan policy that strips the external access prefix and adds the "+".</span></span> <span data-ttu-id="caa45-130">Wenn Ihr Standort beispielsweise ein Präfix für den externen Zugriff von 9 verwendet und ein Benutzer 9 911 anwählt, um einen Notruf zu tätigen, wird der Client seine Wähl Plan Richtlinie verwenden, um diese auf + 911 zu normalisieren, bevor die gewählte Nummer von den Routen im Standortprofil des Anrufers ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="caa45-130">For example, if your location uses an external access prefix of 9 and a user dials 9 911 to place an emergency call, the client will use its Dial Plan policy to normalize this to +911 before the dialed number is evaluated by the routes in the caller's location profile.</span></span> 
  
 <span data-ttu-id="caa45-131">**Notruf-Wählzeichenfolgenmasken (Notfallnummermaske)**</span><span class="sxs-lookup"><span data-stu-id="caa45-131">**Emergency Dial String Masks (E9-1-1 dial mask)**</span></span>
  
<span data-ttu-id="caa45-132">Eine durch Semikolons getrennte Liste von Wählzeichenfolgen, die in die angegebene **Notruf Zeichenfolge**übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="caa45-132">A semicolon-separated list of dial strings that is translated into the specified **Emergency Dial String**.</span></span> <span data-ttu-id="caa45-133">So können Sie beispielsweise 112 hinzufügen, die für den größten Teil Europas die Notrufnummer ist.</span><span class="sxs-lookup"><span data-stu-id="caa45-133">For example, you may want to add 112, which is the emergency service number for most of Europe.</span></span> <span data-ttu-id="caa45-134">Ein Besuch von Skype for Business-Benutzern aus Europa weiß möglicherweise nicht, dass 911 die US-Notfallnummer ist, aber Sie können 112 anrufen und dasselbe Ergebnis erzielen.</span><span class="sxs-lookup"><span data-stu-id="caa45-134">A visiting Skype for Business user from Europe may not know that 911 is the U.S. emergency number, but they can dial 112 and get the same result.</span></span> <span data-ttu-id="caa45-135">Geben Sie wie bei der Notruf Zeichenfolge keine "+" vor jeder Zahl ein, und wenn Sie die Zugriffscodes für externe Leitungen verwenden, stellen Sie sicher, dass in der Wähl Plan Richtlinie des Benutzers Normalisierungsregeln vorhanden sind, um die Zugriffscode Ziffer abzustreifen.</span><span class="sxs-lookup"><span data-stu-id="caa45-135">As with the Emergency Dial String, do not include a "+" before each number, and if you use external line access codes, be sure there are normalization rules in the user's Dial Plan policy to strip off the access code digit.</span></span>
  
 <span data-ttu-id="caa45-136">**PSTN-Verwendung**</span><span class="sxs-lookup"><span data-stu-id="caa45-136">**PSTN usage**</span></span>
  
<span data-ttu-id="caa45-137">Der Name der PSTN-Verwendung mit den Routingpfaden, die bestimmen, an welchen SIP-Trunk bzw. an welches PSTN- oder ELIN-Gateway Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="caa45-137">The name of the PSTN Usage that contains the routing paths that determine which SIP trunk, PSTN gateway, or ELIN gateway emergency calls will go to.</span></span>
  
> [!NOTE]
> <span data-ttu-id="caa45-138">Einer Standortrichtlinie kann nur eine Verwendung zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="caa45-138">Only one usage can be assigned to a location policy.</span></span> <span data-ttu-id="caa45-139">Diese PSTN-Nutzung überschreibt die PSTN-Nutzungen, die der VoIP-Richtlinie des Benutzers zugewiesen sind, gilt aber nur für Anrufe, die an die Notrufnummer oder an eine der Notruf-Zeichenfolgen Masken gestellt werden.</span><span class="sxs-lookup"><span data-stu-id="caa45-139">This PSTN Usage overrides the PSTN Usages assigned to the user's voice policy, but applies only to calls placed to the Emergency Dial String or to one of the Emergency Dial String Masks.</span></span> 
  
 <span data-ttu-id="caa45-140">**Benachrichtigungs-URI**</span><span class="sxs-lookup"><span data-stu-id="caa45-140">**Notification URI**</span></span>
  
<span data-ttu-id="caa45-p111">Gibt mindestens einen SIP-URI des Sicherheitspersonals an, das bei einem Notruf per Sofortnachricht benachrichtigt wird. Verteilergruppen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="caa45-p111">Specifies one or more SIP URIs of the security personnel who receive an instant messaging (IM) notification when an emergency call is placed. Distribution groups are supported.</span></span>
  
 <span data-ttu-id="caa45-143">**Konferenz-URI**</span><span class="sxs-lookup"><span data-stu-id="caa45-143">**Conference URI**</span></span>
  
<span data-ttu-id="caa45-144">Gibt eine DID-Nummer (Direct Inward Dialing) an (in der Regel eine Sicherheitsdesknummer), die bei einem Notruf per Konferenz zugeschaltet werden soll.  </span><span class="sxs-lookup"><span data-stu-id="caa45-144">Specifies a direct inward dialing (DID) number (typically, a security desk number) that should be conferenced in when an emergency call is placed.</span></span> 
  
 <span data-ttu-id="caa45-145">**Konferenzmodus**</span><span class="sxs-lookup"><span data-stu-id="caa45-145">**Conference Mode**</span></span>
  
<span data-ttu-id="caa45-146">Gibt an, ob bei der Zuschaltung des Konferenz-URI zum Notruf eine unidirektionale oder bidirektionale Kommunikation verwendet wird. </span><span class="sxs-lookup"><span data-stu-id="caa45-146">Specifies if the conference URI will be conferenced into the emergency call by using one-way or two-way communication.</span></span> 
  
 <span data-ttu-id="caa45-147">**Standortaktualisierungsintervall**</span><span class="sxs-lookup"><span data-stu-id="caa45-147">**Location Refresh Interval**</span></span>
  
<span data-ttu-id="caa45-148">Gibt die Zeitspanne (in Stunden) zwischen Clientanforderungen für ein Standort Update vom standortinformationsdienst an.</span><span class="sxs-lookup"><span data-stu-id="caa45-148">Specifies the amount of time (in hours) between client requests for a location update from the Location Information service.</span></span> <span data-ttu-id="caa45-149">Dieser Wert kann auf einen beliebigen Wert zwischen 1 und 12 festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="caa45-149">The value can be set to any value between 1 and 12.</span></span> <span data-ttu-id="caa45-150">Der Standardwert lautet 4.</span><span class="sxs-lookup"><span data-stu-id="caa45-150">The default value is 4.</span></span>
  

