---
title: Identitäten, Bereiche und Mandanten in Skype for Business Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="d5a82-102">Identitäten, Bereiche und Mandanten in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5a82-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5a82-103">_**Letztes Änderungsstand des Themas:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="d5a82-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="d5a82-104">Viele der Windows PowerShell-Cmdlets, die zum Verwalten von Skype for Business Online verwendet werden, erfordern eine sehr genaue über das Element, das Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5a82-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="d5a82-105">Wenn Sie beispielsweise das Cmdlet " [CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) " ausführen, müssen Sie angeben, welche Benutzer Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="d5a82-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="d5a82-106">Das ist aus dem folgenden Grund sinnvoll: Die w:lvl-Elemente werden nur von Entwicklern verwendet, und nullbasierte Indizes sind für Entwickler leichter zu handhaben.</span><span class="sxs-lookup"><span data-stu-id="d5a82-106">This makes sense.</span></span> <span data-ttu-id="d5a82-107">Wenn Sie dem Cmdlet nicht explizit mitteilen, welches Benutzerkonto verwaltet werden soll, hat das Cmdlet " **CsUserAcp** " keine Ahnung, welche Audiokonferenzinformationen des Benutzers geändert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="d5a82-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="d5a82-108">Aus diesem Grund müssen Sie bei jedem Ausführen des Cmdlets " **CsUserAcp** " den Parameter "Identity" angeben, gefolgt von der Identität des zu ändernden Benutzerkontos:</span><span class="sxs-lookup"><span data-stu-id="d5a82-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="d5a82-109">Wenn der Begriff *Identity* immer auf die Identität eines Benutzerkontos Bezug genommen wird, gibt es nur wenig Anlass zur Verwirrung.</span><span class="sxs-lookup"><span data-stu-id="d5a82-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="d5a82-110">Wenn Sie mit Personen (Benutzern, Kontakten usw.) zu tun haben, bezieht sich die Identität auf die einzelnen Benutzer selbst.</span><span class="sxs-lookup"><span data-stu-id="d5a82-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="d5a82-111">Andere Elemente als Benutzerkonten weisen jedoch auch Identitäten auf.</span><span class="sxs-lookup"><span data-stu-id="d5a82-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="d5a82-112">Wenn Sie sich mit Komponenten des Skype for Business Online Diensts – Richtlinien, Konfigurationseinstellungen usw. – befassen, bedeutet der Ausdruck "Identity" etwas anderes.</span><span class="sxs-lookup"><span data-stu-id="d5a82-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="d5a82-113">Verwenden Sie beispielsweise diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="d5a82-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="d5a82-114">In diesem Fall bezieht sich die Identität "Global" auf den Bereich der Besprechungs Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="d5a82-115">*Scope* ist ein Begriff, der in Skype for Business Online (und in lync Server) zum Festlegen von Verwaltungsbereichen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d5a82-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="d5a82-116">Standardmäßig haben Richtlinien und Einstellungen immer einen globalen Bereich.</span><span class="sxs-lookup"><span data-stu-id="d5a82-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="d5a82-117">Beim ersten Einrichten Ihres Skype for Business Online-Kontos haben Sie standardmäßig eine Sammlung globaler Richtlinien und Einstellungen – globale Besprechungs Konfigurationseinstellungen, eine globale Richtlinie für den externen Zugriff, einen globalen Wählplan usw.</span><span class="sxs-lookup"><span data-stu-id="d5a82-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="d5a82-118">Diese globalen Richtlinien und Einstellungen wurden in Microsoft lync Server 2010 eingeführt, um sicherzustellen, dass alle Benutzer und alle Komponenten immer in irgendeiner Weise verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="d5a82-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="d5a82-119">Dies war in Microsoft Office Communicator 2007 R2 nicht unbedingt der Fall.</span><span class="sxs-lookup"><span data-stu-id="d5a82-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="d5a82-120">Je nachdem, wie Sie auf das System zugegriffen haben, könnten Sie möglicherweise in einem weitgehend nicht verwalteten Zustand enden (in der Regel, da Gruppenrichtlinien nicht auf Ihr Benutzerkonto angewendet werden konnten).</span><span class="sxs-lookup"><span data-stu-id="d5a82-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="d5a82-121">Im Gegensatz dazu wird in lync Server und in Skype for Business Online nichts mehr verwaltet.</span><span class="sxs-lookup"><span data-stu-id="d5a82-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="d5a82-122">Dies liegt daran, dass an Stelle von nichts anderem globale Richtlinien und Einstellungen immer erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="d5a82-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="d5a82-123">Was meinen wir mit "anstelle von irgendetwas anderem"?</span><span class="sxs-lookup"><span data-stu-id="d5a82-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="d5a82-124">Nun, im Fall von Skype for Business Online ist es möglich, Richtlinien im *Tag-Bereich*oder im Bereich der Verwaltung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="d5a82-125">Auf dem Tag-Bereich (auch bekannt als benutzerbezogener *Bereich*) erstellte Richtlinien haben Vorrang vor Richtlinien, die auf globaler Ebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5a82-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="d5a82-126">Mit anderen Worten: eine benutzerspezifische Richtlinie hat immer Vorrang vor einer globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="d5a82-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="d5a82-127">Beispielsweise können Sie zwei Richtlinien für den Zugriff durch externe Benutzer haben.</span><span class="sxs-lookup"><span data-stu-id="d5a82-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="d5a82-128">Die globale Richtlinie untersagt Benutzern die Kommunikation mit Personen, die über Konten für öffentliche Chat Anbieter (Instant Messaging) wie Windows Live verfügen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="d5a82-129">Die benutzerspezifische Richtlinie, AllowPublicIMCommunication, ermöglicht die Kommunikation mit öffentlichen Instant Messaging-Anbietern.</span><span class="sxs-lookup"><span data-stu-id="d5a82-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="d5a82-130">Möglicherweise haben Sie auch zwei Benutzer: Ken Myers und Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="d5a82-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="d5a82-131">Ken Myers wurde die benutzerspezifische Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="d5a82-132">Pilar Ackerman wurde keine benutzerspezifische Richtlinie zugewiesen. Dies bedeutet, dass Sie von der globalen Richtlinie für den externen Zugriff verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="d5a82-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="d5a82-133">In der folgenden Tabelle wird gezeigt, welcher Benutzer (falls vorhanden) mit öffentlichen Instant Messaging-Anbietern kommunizieren kann:</span><span class="sxs-lookup"><span data-stu-id="d5a82-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d5a82-134">Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="d5a82-134">Policy Settings</span></span></th>
<th><span data-ttu-id="d5a82-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="d5a82-135">Ken Myer</span></span></th>
<th><span data-ttu-id="d5a82-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="d5a82-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5a82-137">Globale Richtlinieneinstellung für öffentliche Chat Anbieter</span><span class="sxs-lookup"><span data-stu-id="d5a82-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="d5a82-138">Nein</span><span class="sxs-lookup"><span data-stu-id="d5a82-138">No</span></span></p></td>
<td><p><span data-ttu-id="d5a82-139">Nein</span><span class="sxs-lookup"><span data-stu-id="d5a82-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5a82-140">Benutzerspezifische Richtlinieneinstellung für öffentliche Chat Anbieter</span><span class="sxs-lookup"><span data-stu-id="d5a82-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="d5a82-141">Ja</span><span class="sxs-lookup"><span data-stu-id="d5a82-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5a82-142">Nein</span><span class="sxs-lookup"><span data-stu-id="d5a82-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5a82-143">Benutzer kann mit öffentlichen Instant Messaging-Anbietern kommunizieren</span><span class="sxs-lookup"><span data-stu-id="d5a82-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="d5a82-144">Ja</span><span class="sxs-lookup"><span data-stu-id="d5a82-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="d5a82-145">Nein</span><span class="sxs-lookup"><span data-stu-id="d5a82-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d5a82-146">Wie Sie sehen können, kann Ken Myers mit öffentlichen Instant Messaging-Anbietern kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d5a82-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="d5a82-147">Dies liegt daran, dass die Einstellungen in der benutzerbezogenen Richtlinie, die ihm zugewiesen ist, die Einstellungen in der globalen Richtlinie außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="d5a82-148">Pilar Ackerman kann nicht mit öffentlichen Instant Messaging-Anbietern kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d5a82-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="d5a82-149">Dies liegt daran, dass Sie von der globalen Richtlinie verwaltet wird und die globale Richtlinie solche Kommunikationen verbietet.</span><span class="sxs-lookup"><span data-stu-id="d5a82-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="d5a82-150">Benutzerspezifische Richtlinien müssen vom Microsoft-Support für Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="d5a82-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="d5a82-151">Nachdem die Richtlinien erstellt wurden, können Sie Sie Benutzern mithilfe des entsprechenden Cmdlets **Grant-CS** zuweisen (beispielsweise [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="d5a82-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="d5a82-152">Benutzerspezifische Richtlinien sind leicht zu identifizieren, da die Richtlinien Identität immer mit **dem Tagpräfix beginnt.**</span><span class="sxs-lookup"><span data-stu-id="d5a82-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="d5a82-153">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d5a82-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="d5a82-154">Das Tagpräfix wird auf die frühen Entwicklungstage von lync Server 2010 <STRONG>zurück datiert.</STRONG></span><span class="sxs-lookup"><span data-stu-id="d5a82-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="d5a82-155">In diesen Tagen wurden benutzerspezifische Richtlinien als <EM>Tag-Richtlinien</EM> bezeichnet und durch <STRONG>das Tagpräfix identifiziert.</STRONG></span><span class="sxs-lookup"><span data-stu-id="d5a82-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="d5a82-156">Diese Richtlinien werden nun genauer als benutzerspezifische <EM>Richtlinien</EM>bezeichnet, und der Transponder Bereich wird genauer als benutzerbezogener <EM>Bereich</EM>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d5a82-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="d5a82-157">Aus technischen <STRONG>Gründen wurde das Tagpräfix jedoch</STRONG> nie geändert.</span><span class="sxs-lookup"><span data-stu-id="d5a82-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="d5a82-158">Ein weiterer Schlüsselbegriff, der beim Arbeiten mit Skype for Business Online und Windows PowerShell verwendet wird, ist " *Mandant*".</span><span class="sxs-lookup"><span data-stu-id="d5a82-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="d5a82-159">Wenn Sie ein Skype for Business Online-Konto einrichten, wird Ihrer neuen Bereitstellung eine Mandanten-ID zugewiesen, bei der es sich um eine GUID (Globally Unique Identifier) wie die folgende handelt:</span><span class="sxs-lookup"><span data-stu-id="d5a82-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="d5a82-160">Bei einigen der Skype for Business Online-Cmdlets müssen Sie die Mandanten-ID eingeben, wenn Sie das Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="d5a82-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="d5a82-161">Sie müssen die Mandanten-ID auch dann eingeben, wenn Sie sich angemeldet haben und nur einen Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="d5a82-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="d5a82-162">Glücklicherweise müssen Sie die Mandanten-ID nicht merken.</span><span class="sxs-lookup"><span data-stu-id="d5a82-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="d5a82-163">Sie können Ihre Mandanten-ID jederzeit abrufen, indem Sie den folgenden Windows PowerShell-Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="d5a82-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="d5a82-164">Selbstverständlich ist das Erkennen von Dingen wie dem Unterschied zwischen dem globalen und dem benutzerbezogenen Bereich (oder dem Tag-Bereich) nur die Hälfte der Schlacht.</span><span class="sxs-lookup"><span data-stu-id="d5a82-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="d5a82-165">Es ist auch wichtig zu wissen, wann (oder sogar wenn) Sie diese Bereiche verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d5a82-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="d5a82-166">Gleiches gilt für Identitäten und den Parameter Mandanten.</span><span class="sxs-lookup"><span data-stu-id="d5a82-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="d5a82-167">In den folgenden Themen wird beschrieben, wie die verschiedenen Skype for Business Online-Cmdlets Identitäten, Bereiche und den Parameter Mandanten verwenden:</span><span class="sxs-lookup"><span data-stu-id="d5a82-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="d5a82-168">Cmdlets in Skype for Business Online, die nur den globalen Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="d5a82-169">Cmdlets in Skype for Business Online, die den globalen Bereich und den Tag-Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="d5a82-170">Cmdlets in Skype for Business Online, die eine Benutzeridentität verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="d5a82-171">Cmdlets in Skype for Business Online, die eine Benutzeridentität und den Tag-Bereich verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="d5a82-172">Cmdlets in Skype for Business Online, die den Parameter "Mandant" verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="d5a82-173">Cmdlets in Skype for Business Online, die eine Konferenzanbieter Identität verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="d5a82-174">Cmdlets in Skype for Business Online, die keinen Bereich oder eine Identität verwenden</span><span class="sxs-lookup"><span data-stu-id="d5a82-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

