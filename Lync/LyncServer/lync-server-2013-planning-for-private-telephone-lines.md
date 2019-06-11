---
title: 'Lync Server 2013: Planen privater Telefonleitungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for private telephone lines
ms:assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412728(v=OCS.15)
ms:contentKeyID: 48184909
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4287e4b80b146e26fe5e548c07e5df189b1960e8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-private-telephone-lines-with-lync-server-2013"></a><span data-ttu-id="4994a-102">Planen privater Telefonleitungen mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4994a-102">Planning for private telephone lines with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4994a-103">_**Letztes Änderungsdatum des Themas:** 2013-02-11_</span><span class="sxs-lookup"><span data-stu-id="4994a-103">_**Topic Last Modified:** 2013-02-11_</span></span>

<span data-ttu-id="4994a-104">Lync Server 2013 führt die Möglichkeit ein, Benutzern zusätzlich zu Ihrer primären Telefonleitung eine zweite private Telefonleitung zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="4994a-104">Lync Server 2013 introduces the ability to give users a second, private telephone line in addition to their primary telephone line.</span></span> <span data-ttu-id="4994a-105">Privatleitungen werden oft Führungskräften und anderen Mitarbeitern zugewiesen, die eine nicht gelistete Telefonnummer wünschen, unter der sie direkt erreicht werden können.</span><span class="sxs-lookup"><span data-stu-id="4994a-105">Private telephone lines are often assigned to executives and others who want an unlisted telephone number at which they can be reached directly.</span></span>

<span data-ttu-id="4994a-106">Private Telefonleitungen können nur mit der lync Server-Verwaltungsshell konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-106">Private telephone lines can only be configured with the Lync Server Management Shell.</span></span> <span data-ttu-id="4994a-107">Mit der lync Server-Systemsteuerung können keine privaten Telefonanschlüsse konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-107">You cannot configure private telephone lines with the Lync Server Control Panel.</span></span> <span data-ttu-id="4994a-108">Private Telefonleitungen sollten nur in Bereitstellungen von lync Server und nicht in gemischten Bereitstellungen konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-108">Private telephone lines should be configured only in deployments of Lync Server and not in mixed deployments.</span></span>

<div>

## <a name="characteristics-of-private-telephone-lines"></a><span data-ttu-id="4994a-109">Eigenschaften von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="4994a-109">Characteristics of Private Telephone Lines</span></span>

<span data-ttu-id="4994a-110">Auch wenn das Konzept einer zweiten, privaten Telefonleitung grundsätzlich einfach zu verstehen ist, müssen Sie die Eigenschaften von Privatleitungen kennen und wissen, inwieweit sie den primären Telefonleitungen der Benutzer gleichen bzw. sich von diesen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4994a-110">Although the concept of a second, private telephone line is fundamentally simple, it is important to understand the characteristics of private lines and the ways in which they are similar to and different from users’ primary telephone lines.</span></span>

<div>

## <a name="general-characteristics-of-private-telephone-lines"></a><span data-ttu-id="4994a-111">Allgemeine Eigenschaften von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="4994a-111">General Characteristics of Private Telephone Lines</span></span>

  - <span data-ttu-id="4994a-112">Ein Benutzer kann nur eine Privatleitung besitzen.</span><span class="sxs-lookup"><span data-stu-id="4994a-112">A user can have only one private telephone line.</span></span>

  - <span data-ttu-id="4994a-113">Ein Benutzer mit einer Privatleitung verfügt nur über ein Postfach für Voicemail und erhält Benachrichtigungen über verpasste Anrufe nur unter einer einzigen E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="4994a-113">A user with a private telephone line has only one voice mailbox and receives missed call notifications at a single email address.</span></span>

  - <span data-ttu-id="4994a-114">Ein Benutzer mit einer Privatleitung besitzt keine zweite SIP-Adresse und eine zweite, private Telefonleitung bedeutet nicht, dass ein Benutzer im Netzwerk zweimal vorhanden ist (wie eine zweite Chat-Identität).</span><span class="sxs-lookup"><span data-stu-id="4994a-114">A user with a private telephone line does not have a second SIP address, and a second, private telephone line does not give a user a second presence on the network (such as a second instant messaging identity).</span></span>

  - <span data-ttu-id="4994a-115">Privatleitungen stehen nur für lokale Bereitstellungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4994a-115">Private telephone lines are available for on-premises deployments only.</span></span> <span data-ttu-id="4994a-116">Sie sind für gehostete Bereitstellungen von lync Server nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4994a-116">They are not available with hosted deployments of Lync Server.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a><span data-ttu-id="4994a-117">Unterschiede zwischen Privatleitungen und primären Telefonleitungen</span><span class="sxs-lookup"><span data-stu-id="4994a-117">How Private Telephone Lines Differ from Primary Telephone Lines</span></span>

  - <span data-ttu-id="4994a-118">Die Rufnummern für Privatleitungen werden nicht in den Telefonverzeichnissen oder Kontaktlisten aufgeführt, die von den Active Directory-Domänendiensten abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-118">The telephone numbers for private telephone lines do not appear in the telephone directories or Contacts lists that are derived from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="4994a-119">Keine der folgenden Funktionen steht für eine Privatleitung zur Verfügung: Anrufweiterleitung, Teamanruf, Gruppenanrufannahme, Delegierung, benutzerdefinierte Anrufweiterleitung und Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="4994a-119">None of the following features are available with a private telephone line: call forwarding, team call, delegation, team ring, Group Call Pickup, and Response Group application.</span></span>

  - <span data-ttu-id="4994a-120">Anrufe an eine Privatleitung weisen einen bestimmten Rufton auf und in der Systembenachrichtigung für den Anruf wird dem Benutzer mitgeteilt, dass der Anruf auf der Privatleitung eingeht.</span><span class="sxs-lookup"><span data-stu-id="4994a-120">Calls to a private telephone line have a special ring, and the system notification for the call tells the user that the incoming call is on his or her private line.</span></span>

  - <span data-ttu-id="4994a-p104">Anrufe an die Privatleitung werden immer durchgestellt. Sie folgen keinen „Nicht stören“-Regeln.</span><span class="sxs-lookup"><span data-stu-id="4994a-p104">Calls to the private telephone line always ring through. They do not follow "do not disturb" rules.</span></span>

  - <span data-ttu-id="4994a-p105">Privatleitungen sind nur eingehend und können nicht zum Tätigen ausgehender Anrufe verwendet werden. Wenn ein Benutzer mit einer Privatleitung einen Anruf tätigt, geht der Anruf von der primären Telefonleitung des Benutzers aus. Der Benutzername oder die primäre Telefonnummer des Benutzers wird dabei nicht vor dem angerufenen Teilnehmer verborgen.</span><span class="sxs-lookup"><span data-stu-id="4994a-p105">Private telephone lines are inbound only and cannot be used to make outgoing calls. When a user with a private telephone line makes a call, the call originates from the user’s primary telephone line and does not hide the user’s name or the user’s primary telephone number from the person called.</span></span>

</div>

<div>

## <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a><span data-ttu-id="4994a-125">Gemeinsamkeiten zwischen Privatleitungen und primären Telefonleitungen</span><span class="sxs-lookup"><span data-stu-id="4994a-125">How Private Telephone Lines Are Similar to Primary Telephone Lines</span></span>

  - <span data-ttu-id="4994a-126">Nicht entgegengenommene Anrufe an eine Privatleitung werden an denselben Posteingang für Voicemail geleitet, der auch für die primäre Telefonleitung verwendet wird (falls Voicemail aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="4994a-126">Unanswered calls to a private telephone line are routed to the same voice mail inbox as for the primary telephone line (if voice mail is enabled).</span></span>

  - <span data-ttu-id="4994a-127">Das Parken von Anrufen und die Anrufannahme funktionieren bei Privatleitungen genauso wie bei der primären Telefonleitung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="4994a-127">Call park and call pickup work with private telephone lines in exactly the same manner as they do with the user’s primary telephone line.</span></span>

  - <span data-ttu-id="4994a-128">Wenn für die primäre Telefonleitung eines Benutzers gleichzeitiges Klingeln aktiviert ist, gilt dies auch für die Privatleitung.</span><span class="sxs-lookup"><span data-stu-id="4994a-128">When simultaneous ringing is enabled on a user’s primary telephone line, it is also enabled on the private telephone line.</span></span>

  - <span data-ttu-id="4994a-129">Die Rufnummer für eine Privatleitung wird im Kommunikationsdatensatz ebenso aufgezeichnet wie die Rufnummer für die primäre Telefonleitung eines Benutzers, jedoch mit dem Hinweis, dass es sich um eine private Rufnummer handelt.</span><span class="sxs-lookup"><span data-stu-id="4994a-129">The telephone number for a private telephone line is recorded in the call detail record in the same manner as the telephone number for a user’s primary telephone line, but with an indication that it is a private telephone number.</span></span>

  - <span data-ttu-id="4994a-130">Nachdem ein Benutzer einen Anruf auf einer Privatleitung angenommen hat, wird der Anruf genau wie ein Anruf auf der primären Telefonleitung des Benutzers behandelt.</span><span class="sxs-lookup"><span data-stu-id="4994a-130">After a user answers a call on a private telephone line, the call is treated the same as a call on the user’s primary telephone line.</span></span> <span data-ttu-id="4994a-131">Wenn beispielsweise ein Benutzer, der einen Anruf über eine private Telefonleitung erhält, den Anruf weiterleitet oder andere zu einem Konferenzanruf auffordert, wird der Name des Benutzers in lync 2013 angezeigt, und die Telefonnummer für die primäre Telefonleitung des Benutzers wird in der Rufnummernanzeige angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4994a-131">For example, if a user who receives a call on a private telephone line forwards the call or invites others to a conference call, the user’s name appears in Lync 2013, and the telephone number for the user’s primary telephone line appears in caller ID.</span></span>

  - <span data-ttu-id="4994a-132">Genau wie bei einer primären Telefonleitung kann ein Benutzer einen Anruf von der Privatleitung aus weiterschalten, also vor der Annahme an ein anderes Ziel umleiten, z. B. an ein Mobiltelefon oder eine private Rufnummer.</span><span class="sxs-lookup"><span data-stu-id="4994a-132">A user can deflect a call (redirect the call to another destination, such as a mobile phone or home phone, before answering) from the private telephone line in the same manner as with a primary telephone line.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4994a-133">Wenn ein Anruf auf einer Privatleitung an eine andere Rufnummer umgeleitet wird, steht die Rufnummer für die Privatleitung der alternativen Rufnummer zur Verfügung und kann in den Protokollen für die betreffende Nummer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-133">When a call to a private line is routed to an alternate telephone number, the telephone number for the private telephone line is made available to the alternate telephone number and can be displayed in the logs for that number.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4994a-134">Anrufe von einer Konferenz an die Privatleitung werden in der eingehenden Systembenachrichtigung nicht mit dem Hinweis <EM>Privatleitung</EM> markiert.</span><span class="sxs-lookup"><span data-stu-id="4994a-134">Calls from a conference to the private telephone line will not have a <EM>private-line</EM> indication in the incoming system notification.</span></span>

    
    </div>

</div>

</div>

<div>

## <a name="administering-private-telephone-lines"></a><span data-ttu-id="4994a-135">Verwalten von Privatleitungen</span><span class="sxs-lookup"><span data-stu-id="4994a-135">Administering Private Telephone Lines</span></span>

<span data-ttu-id="4994a-p107">Neben den technischen Aspekten der Erstellung und Verwaltung von Privatleitungen müssen Sie dafür Verwaltungsverfahren einrichten. Hierzu gehört die Festlegung von Richtlinien darüber, wer in der Organisation eine Privatleitung erhalten soll, die Erstellung und Verwaltung von Listen mit Personen und zugehörigen Telefonleitungen, die mögliche Erstellung eines Verzeichnisses für private Rufnummern für Führungskräfte, die Organisation einer Benutzerschulung und weitere Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="4994a-p107">In addition to the technical aspects of creating and managing private telephone lines, you will need to establish administrative procedures for them. This includes determining policies for who in the organization is eligible for a private line, creating and maintaining lists of people and their telephone lines, possibly creating a private telephone directory for executives, arranging for user training, and related tasks.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4994a-p108">Die Privatleitung wird in Active Directory als Attribut „msRTCSIP-PrivateLine“ des Benutzerobjekts gespeichert. Standardmäßig haben alle Mitglieder der Gruppe der authentifizierten Benutzer Lesezugriff auf dieses Attribut.</span><span class="sxs-lookup"><span data-stu-id="4994a-p108">The private telephone line is stored in Active Directory as an msRTCSIP-PrivateLine attribute on the user object. By default any member of the Authenticated Users group has read access to this attribute.</span></span>



</div>

<div>

## <a name="assigning-telephone-numbers"></a><span data-ttu-id="4994a-140">Zuweisen von Rufnummern</span><span class="sxs-lookup"><span data-stu-id="4994a-140">Assigning Telephone Numbers</span></span>

<span data-ttu-id="4994a-141">Konten für neue Benutzer, die private Telefonleitungen benötigen, werden auf die gleiche Weise wie Konten ohne private Telefonleitungen erstellt, und zwar mithilfe der lync Server-Systemsteuerung oder der lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="4994a-141">Accounts for new users who need private telephone lines are created in the same manner as accounts without private telephone lines, using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<span data-ttu-id="4994a-142">Verwenden Sie das Cmdlet " **CsUser** " in der lync Server-Verwaltungsshell, um einer privaten Telefonleitung für einen Benutzer eine Telefonnummer zuzuweisen, beispielsweise " **CsUser-Identity" SIP:Joe@Contoso.com "-Privatsphäre" Tel: + 14255551212 "**.</span><span class="sxs-lookup"><span data-stu-id="4994a-142">Use the **Set-CsUser** cmdlet in the Lync Server Management Shell to assign a telephone number to a private telephone line for a user, for example, **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212"**.</span></span>

<span data-ttu-id="4994a-143">Telefonnummern für private Telefonleitungen können zwischen 3 und 15 Nummern lang sein und müssen dem Präfix "Tel:" vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-143">Telephone numbers for private telephone lines can be between 3 and 15 numbers in length and must be preceded with the "TEL:" prefix.</span></span> <span data-ttu-id="4994a-144">Sie können eine beliebige Ortsvorwahl und eine beliebige Landes-/Regionsvorwahl besitzen, sofern Ihre Organisation für die betreffende Orts- und Landes-/Regionsvorwahl DID-Nummern (Direct Inward Dialing) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4994a-144">They can have any area code and any country/region code as long as your organization has direct inward dialing for that area code and country/region code.</span></span>

<span data-ttu-id="4994a-145">Details zu Cmdlets und zur lync Server-Verwaltungsshell finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="4994a-145">For details about cmdlets and Lync Server Management Shell, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="private-telephone-lines-in-mixed-deployments"></a><span data-ttu-id="4994a-146">Privatleitungen in gemischten Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="4994a-146">Private Telephone Lines in Mixed Deployments</span></span>

<span data-ttu-id="4994a-147">Private Telefonleitungen sollten nur für Bereitstellungen von lync Server konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4994a-147">Private telephone lines should be configured only for deployments of Lync Server.</span></span> <span data-ttu-id="4994a-148">Bei einer Bereitstellung, bei der sowohl lync Server-als auch Office Communications Server 2007-oder Office Communications Server 2007 R2-Server vorhanden sind, schlägt das Routing des Anrufs fehl, da der Server bei einer früheren Version versucht, eine private Telefonleitung anzurufen Führen Sie eine Reverse-Number-Suche auf einem privaten Telefonanschluss durch.</span><span class="sxs-lookup"><span data-stu-id="4994a-148">In a deployment in which there are both Lync Server and Office Communications Server 2007 or Office Communications Server 2007 R2 servers, when a user on earlier version attempts to call a private telephone line, routing of the call fails because the server cannot perform a reverse number lookup on a private telephone line.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

