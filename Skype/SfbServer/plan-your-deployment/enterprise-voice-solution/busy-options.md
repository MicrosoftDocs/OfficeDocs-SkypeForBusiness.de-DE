---
title: Planen der Beschäftigt-Optionen für Skype for Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informieren Sie sich über das Feature beschäftigt Optionen in Skype für Business Server.
ms.openlocfilehash: 7b71cad7eebaf2d375098abfa0891cdf6b494fe9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884786"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="36e34-103">Planen der Beschäftigt-Optionen für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="36e34-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="36e34-104">Informieren Sie sich über das Feature beschäftigt Optionen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="36e34-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="36e34-105">Wird eine neue VoIP-Richtlinie eingeführt beschäftigt Optionen in der Juli 2016 kumulative Update, mit dem Sie zum Konfigurieren eingehender Anrufe verarbeitet werden, wenn ein Benutzer ist bereits in einem Anruf oder einer Konferenz oder ein Anruf in die Warteschleife gestellt.</span><span class="sxs-lookup"><span data-stu-id="36e34-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="36e34-106">Neue oder eingehende Anrufe können mit einem Besetztzeichen abgelehnt oder an die Voicemail weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="36e34-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="36e34-107">Die Richtlinie für Beschäftigt-Optionen wird für Failover- und Notfallwiederherstellung in gepaarten Front-End-Pools und Survivable Branch Servers (SBS) unterstützt.</span><span class="sxs-lookup"><span data-stu-id="36e34-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="36e34-108">In diesem Thema werden die Funktionen der Beschäftigt-Optionen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36e34-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="36e34-109">Informationen zum Installieren und Konfigurieren von Optionen für beschäftigt finden Sie unter [Installieren und Konfigurieren von beschäftigt Optionen für Skype für Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="36e34-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="36e34-110">Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="36e34-110">Configuration options</span></span>

<span data-ttu-id="36e34-111">Wenn Beschäftigt-Optionen für die Organisation aktiviert wurden, können alle Benutzer der Organisation (sowohl Enterprise-VoIP-Benutzer als auch andere Benutzer) die folgenden Funktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="36e34-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="36e34-112">Besetzt wenn beschäftigt: Eingehende Anrufe werden mit einem Besetztzeichen abgelehnt, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="36e34-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="36e34-113">Voicemail wenn beschäftigt: Eingehende Anrufe werden an Voicemail weitergeleitet, wenn der Benutzer beschäftigt ist.</span><span class="sxs-lookup"><span data-stu-id="36e34-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="36e34-114">Die Beschäftigt-Optionen stellen Failover-Möglichkeiten bereit.</span><span class="sxs-lookup"><span data-stu-id="36e34-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="36e34-115">Wenn ein Problem auftritt, und Benutzer ein Failover auf einen anderen Front-End-Server oder in einen anderen Pool in Skype für Business Server, werden deren beschäftigt Optionen Einstellungen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="36e34-116">Unabhängig von der Konfiguration der Beschäftigt-Optionen haben Benutzer, die sich in einem Anruf oder einer Konferenz befinden bzw. einen Anruf halten, die Möglichkeit, neue Anrufe oder Konferenzen zu beginnen.  </span><span class="sxs-lookup"><span data-stu-id="36e34-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="36e34-117">Nach der Konfiguration ist die Einstellung beschäftigt Optionen für Skype für Business Anruf Geräte und Clients des Benutzers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="36e34-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="36e34-118">Auf der Grundlage der festgelegten Beschäftigt-Optionen des Benutzers ertönt bei Ablehnung oder Senden an Voicemail des Anrufs kein Klingelton auf den Anrufgeräten – einschließlich Macintosh, Windows Desktop, Mobilclients oder IP-Telefonen –, bei denen der Benutzer angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="36e34-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="36e34-119">Die Benutzer sehen Benachrichtigungen über verpasste Anrufe auf ihren Skype für Business-Clients und Geräten, und Benutzer werden informiert per e-Mail sowie.</span><span class="sxs-lookup"><span data-stu-id="36e34-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="36e34-120">Anrufer, dessen Aufruf aufgrund beschäftigt auf beschäftigt abgelehnt wurde, sieht eine Benachrichtigung in ihren Skype für Business-Client, die besagt, dass der Benutzer, den sie verwenden wollten, klicken Sie auf einen weiteren Anruf ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="36e34-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="36e34-121">Sie können das Feature beschäftigt Optionen mithilfe von Skype für Business-PowerShell-Cmdlets zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="36e34-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="36e34-122">VoIP-Richtlinie der Beschäftigt-Optionen für das Unternehmen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="36e34-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="36e34-123">„Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer im Unternehmen verwalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="36e34-124">„Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für alle Benutzer in einem bestimmten Front-End-Pool verwalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="36e34-125">„Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für eine Liste von Benutzern verwalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="36e34-126">„Besetzt wenn beschäftigt“ oder „Voicemail wenn beschäftigt“ für einen einzelnen Benutzer verwalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="36e34-127">Interoperabilität mit VoIP-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="36e34-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="36e34-128">Ausgelastet Optionen bietet Interoperabilität mit den folgenden VoIP-Anwendungen in Skype für Unternehmen:</span><span class="sxs-lookup"><span data-stu-id="36e34-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="36e34-129">Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="36e34-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="36e34-130">Für Reaktionsgruppennummern festgelegte Beschäftigt-Optionen werden vom System ignoriert; mehrere gleichzeitige Anrufe sind zulässig. </span><span class="sxs-lookup"><span data-stu-id="36e34-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="36e34-131">Die derzeitige Telefonzentralen-Weiterleitung in Reaktionsgruppen bleibt für die Agenten mit festgelegten Beschäftigt-Optionen unverändert.</span><span class="sxs-lookup"><span data-stu-id="36e34-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="36e34-132">Die von Reaktionsgruppen an die Benutzer, die Reaktionsgruppenagenten sind, eingehenden Anrufe werden nicht durch die festgelegten Beschäftigt-Optionen gedrosselt, und die derzeitige Reaktionsgruppenerfahrung bleibt beibehalten.</span><span class="sxs-lookup"><span data-stu-id="36e34-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="36e34-133">Nicht mit Reaktionsgruppen zusammenhängende Anrufe an Agenten werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="36e34-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="36e34-134">Teamanruf</span><span class="sxs-lookup"><span data-stu-id="36e34-134">Team Call</span></span>
    
  - <span data-ttu-id="36e34-135">Eingehende Anrufe für Benutzer, die für einen Teamanruf eingerichtet sind, werden priorisiert werden, um auf beschäftigt beschäftigt und Voicemail auf beschäftigt Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="36e34-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="36e34-136">Die derzeitige Teamanruferfahrung bleibt unverändert, wenn Beschäftigt-Optionen für die Benutzer festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="36e34-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="36e34-137">Nicht mit Teamanrufen zusammenhängende Anrufe diese Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="36e34-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="36e34-138">Delegierung für Chef/Verwaltung </span><span class="sxs-lookup"><span data-stu-id="36e34-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="36e34-139">Eingehende Anrufe für Benutzer, die für eine Vorgesetztenverwaltung/Delegierung entweder als Vorgesetzten oder ein Administrator eingerichtet sind Prioritäten zugewiesen beschäftigt auf beschäftigt und Voicemail auf beschäftigt Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="36e34-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="36e34-140">Die derzeitige Erfahrung bei Delegierung für Chef/Verwaltung bleibt unverändert, wenn Beschäftigt-Optionen für die Administratoren oder Chefs festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="36e34-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="36e34-141">Nicht mit der Delegierung für Chefs/Verwaltung zusammenhängende Anrufe dieser Benutzer werden entsprechend ihren festgelegten Beschäftigt-Optionen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="36e34-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="36e34-142">Funktion „Gemeinsame Leitungen“   </span><span class="sxs-lookup"><span data-stu-id="36e34-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="36e34-143">Festgelegte Beschäftigt-Optionen für Benutzerkonten, die mit der Funktion „Gemeinsame Leitungen“ eingerichtet sind, werden ignoriert. </span><span class="sxs-lookup"><span data-stu-id="36e34-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="36e34-144">Freigegebene Zeile Darstellung systemeigene beschäftigt auf beschäftigt und Voicemail zu stark ausgelastet Optionen werden stattdessen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="36e34-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="36e34-145">Anrufparkdienst </span><span class="sxs-lookup"><span data-stu-id="36e34-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="36e34-146">Geparkte Anrufe, die wegen einer Zeitüberschreitung nicht abgerufen wurden und zurückrufen, können anhand der Beschäftigt-Optionen an den Benutzer durchgestellt werden, der den Anruf geparkt hat. </span><span class="sxs-lookup"><span data-stu-id="36e34-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="36e34-147">Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="36e34-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="36e34-148">Benutzer, die sich in Telefonkonferenzen befinden, gelten als beschäftigt, und neue eingehende Anrufe werden je nach den festgelegten Beschäftigt-Optionen mit einem Besetztzeichen abgelehnt oder an Voicemail weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="36e34-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="36e34-149">Durch die Beschäftigt-Optionen wird aber nicht verhindert, dass Benutzer in Telefonkonferenzen neue Anrufe oder Konferenzen beginnen.</span><span class="sxs-lookup"><span data-stu-id="36e34-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="36e34-150">Benutzer in Konferenzen können neue Konferenzeinladungen erhalten, Peer-zu-Peer-Anrufe werden jedoch entsprechend ihren festgelegten Beschäftigt-Optionen abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="36e34-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="36e34-151">Paralleles Anrufen und Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="36e34-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="36e34-152">Die „Besetzt wenn beschäftigt“-Funktion kann nicht gemeinsam mit „Paralleles Anrufen“ und „Anrufweiterleitung“ genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="36e34-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

