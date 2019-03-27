---
title: Planen von privaten Telefonleitungen mit Skype für Unternehmen
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Planen von privaten Telefonleitungen (sekundären) in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 16c5b6e29041280bf92f849bd327d864c7b58e15
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878056"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a><span data-ttu-id="25c33-103">Planen von privaten Telefonleitungen mit Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="25c33-103">Plan for private telephone lines with Skype for Business</span></span>
 
<span data-ttu-id="25c33-104">Planen von privaten Telefonleitungen (sekundären) in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="25c33-104">Planning for private (secondary) telephone lines in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="25c33-105">Skype für Business Server können Sie Benutzern eine zweite private Telefonleitung neben ihren primären Telefonleitung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="25c33-105">Skype for Business Server enables you to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="25c33-106">Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="25c33-106">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>
  
<span data-ttu-id="25c33-107">Private Telefonleitungen können nur mit der Skype für Business Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="25c33-107">Private telephone lines can only be configured with the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="25c33-108">Sie können nicht privaten Telefonleitungen mit der Skype Business Server-Systemsteuerung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="25c33-108">You cannot configure private telephone lines with the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="25c33-109">Private Telefonleitungen sollte nur in Bereitstellungen von Skype für Business Server und nicht in gemischten Bereitstellungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="25c33-109">Private telephone lines should be configured only in deployments of Skype for Business Server and not in mixed deployments.</span></span>
  
## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="25c33-110">Eigenschaften von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="25c33-110">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="25c33-111">Obwohl das Konzept von einem zweiten, private Telefonleitung grundlegend einfach ist, ist es wichtig zu verstehen, die Merkmale der privaten Zeilen und die Möglichkeiten, in denen ähnlich sind, und primären Telefonleitungen Benutzer unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="25c33-111">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users' primary telephone lines.</span></span>
  
### <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="25c33-112">Allgemeine Eigenschaften von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="25c33-112">General Characteristics of Private Telephone Lines</span></span>

- <span data-ttu-id="25c33-113">Ein Benutzer kann nur eine Privatleitung besitzen.</span><span class="sxs-lookup"><span data-stu-id="25c33-113">A user can have only one private telephone line.</span></span>
    
- <span data-ttu-id="25c33-114">Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="25c33-114">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>
    
- <span data-ttu-id="25c33-115">Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Chat-Identität).</span><span class="sxs-lookup"><span data-stu-id="25c33-115">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span> 
    
- <span data-ttu-id="25c33-116">Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="25c33-116">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="25c33-117">Sie sind nicht mit gehostete Bereitstellungen von Skype für Business Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="25c33-117">They are not available with hosted deployments of Skype for Business Server.</span></span>
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="25c33-118">Unterschiede zwischen Privatleitungen und primären Telefonleitungen</span><span class="sxs-lookup"><span data-stu-id="25c33-118">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

- <span data-ttu-id="25c33-119">Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="25c33-119">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>
    
- <span data-ttu-id="25c33-120">Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="25c33-120">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>
    
- <span data-ttu-id="25c33-121">Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.</span><span class="sxs-lookup"><span data-stu-id="25c33-121">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>
    
- <span data-ttu-id="25c33-p104">Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen „Nicht stören“-Regeln.</span><span class="sxs-lookup"><span data-stu-id="25c33-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>
    
- <span data-ttu-id="25c33-124">Private Telefonleitungen sind nur eingehend und können nicht verwendet werden, um ausgehende Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="25c33-124">Private telephone lines are inbound only and cannot be used to make outgoing calls.</span></span> <span data-ttu-id="25c33-125">Wenn ein Benutzer mit einer privatleitung aufruft, wird der Anruf stammt aus der primären Telefonleitung des Benutzers und wird nicht ausgeblendet, den Namen des Benutzers oder der Benutzer primäre Telefonnummer der Person, die aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="25c33-125">When a user with a private telephone line makes a call, the call originates from the user's primary telephone line and does not hide the user's name or the user's primary telephone number from the person called.</span></span>
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="25c33-126">Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen</span><span class="sxs-lookup"><span data-stu-id="25c33-126">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

- <span data-ttu-id="25c33-127">Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="25c33-127">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>
    
- <span data-ttu-id="25c33-128">Parken Sie und die Anrufannahme funktionieren bei privatleitungen genau die gleiche Weise, wie mit der primären Telefonleitung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="25c33-128">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user's primary telephone line.</span></span>
    
- <span data-ttu-id="25c33-129">Wenn die primäre Telefonleitung eines Benutzers Gleichzeitiges Klingeln aktiviert ist, ist es auch auf die privatleitung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="25c33-129">When simultaneous ringing is enabled on a user's primary telephone line, it is also enabled on the private telephone line.</span></span>
    
- <span data-ttu-id="25c33-130">Die Telefonnummer für eine privatleitung ist die gleiche Weise wie die Telefonnummer für die primäre Telefonleitung eines Benutzers, wobei jedoch ein Hinweis darauf, dass es sich um eine private Telefonnummer ist in der Anruf Detaildatensatz eingetragen.</span><span class="sxs-lookup"><span data-stu-id="25c33-130">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user's primary telephone line, but with an indication that it is a private telephone number.</span></span>
    
- <span data-ttu-id="25c33-131">Nachdem ein Benutzer behandelt Antworten, die ein Anruf auf eine privatleitung der Anruf wird als Anruf auf primäre Telefonleitung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="25c33-131">After a user answers a call on a private telephone line, the call is treated the same as a call on the user's primary telephone line.</span></span> <span data-ttu-id="25c33-132">Beispielsweise wenn ein Benutzer einen Anruf auf eine privatleitung empfängt den Anruf leitet oder andere Personen zu einer Telefonkonferenz eingeladen, den Namen des Benutzers in Skype für Unternehmen wird angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird angezeigt, in Anrufer-ID ein.</span><span class="sxs-lookup"><span data-stu-id="25c33-132">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user's name appears in Skype for Business, and the telephone number for the user's primary telephone line appears in caller ID.</span></span>
    
- <span data-ttu-id="25c33-133">Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. an ein Mobiltelefon oder eine private Rufnummer.</span><span class="sxs-lookup"><span data-stu-id="25c33-133">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="25c33-134">Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="25c33-134">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="25c33-135">Anrufen von einer Konferenz an die privatleitung haben einen Hinweis *privatleitung* nicht in der Benachrichtigung über eingehende System.</span><span class="sxs-lookup"><span data-stu-id="25c33-135">Calls from a conference to the private telephone line will not have a  *private-line*  indication in the incoming system notification.</span></span>
  
## <a name="administering-private-telephone-lines"></a><span data-ttu-id="25c33-136">Verwalten von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="25c33-136">Administering Private Telephone Lines</span></span>

<span data-ttu-id="25c33-p107">Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="25c33-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>
  
> [!NOTE]
> <span data-ttu-id="25c33-p108">Die Privatleitung wird in Active Directory als Attribut „msRTCSIP-PrivateLine“ des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="25c33-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span> 
  
### <a name="assigning-telephone-numbers"></a><span data-ttu-id="25c33-141">Zuweisen von Rufnummern</span><span class="sxs-lookup"><span data-stu-id="25c33-141">Assigning Telephone Numbers</span></span>

 <span data-ttu-id="25c33-142">Konten für neue Benutzer, die privatleitungen benötigen, werden in die gleiche Weise wie Konten ohne privatleitungen mit Skype für Business Server-Systemsteuerung oder Skype für Business Server-Verwaltungsshell erstellt.</span><span class="sxs-lookup"><span data-stu-id="25c33-142">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Skype for Business Server Control Panel or Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="25c33-143">Verwenden Sie das **Set-CsUser** -Cmdlet in der Skype für Business Server-Verwaltungsshell eine privatleitung für einen Benutzer eine Telefonnummer zuweisen **Set-CsUser-Identity "sip:joe@contoso.com" - PrivateLine "Tel: + 14255551212"**.</span><span class="sxs-lookup"><span data-stu-id="25c33-143">Use the **Set-CsUser** cmdlet in the Skype for Business Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>
  
<span data-ttu-id="25c33-144">Telefonnummern für den privaten Telefonleitungen kann zwischen 3 bis 15 Ziffern lang sein und muss mit der "TEL:" Präfix.</span><span class="sxs-lookup"><span data-stu-id="25c33-144">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="25c33-145">Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet.</span><span class="sxs-lookup"><span data-stu-id="25c33-145">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span> 
  
<span data-ttu-id="25c33-146">Ausführliche Informationen zu Cmdlets und Skype für Business Server-Verwaltungsshell finden Sie unter der Skype Business Server-Verwaltungsshell-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="25c33-146">For details about cmdlets and Skype for Business Server Management Shell, see the Skype for Business Server Management Shell documentation.</span></span>
  
### <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="25c33-147">Privatleitungen in gemischten Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="25c33-147">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="25c33-148">Private Telefonleitungen sollte nur für die Bereitstellung von Skype für Business Server oder Lync Server 2013 konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="25c33-148">Private telephone lines should be configured only for deployments of Skype for Business Server or Lync Server 2013.</span></span> <span data-ttu-id="25c33-149">In einer Bereitstellung, in der stehen, Servern, auf denen frühere Versionen von Lync Server, wenn ein Benutzer in einer früheren Version der versucht, eine privatleitung aufrufen, fällt routing des Anrufs, da der Server eine inverssuche für eine privatleitung durchführen kann nicht aus.</span><span class="sxs-lookup"><span data-stu-id="25c33-149">In a deployment in which there are servers running earlier versions of Lync Server, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>
  

