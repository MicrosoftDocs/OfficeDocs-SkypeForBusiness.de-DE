---
title: Überprüfen der Konfigurationseinstellungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f7655547ff4f3e528b3948a537bbd5e85f351ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="098b0-102">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="098b0-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="098b0-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="098b0-104">Nachdem Sie die Topologie zusammengeführt und das **Import-CsLegacyConfiguration-** Cmdlet ausgeführt haben, stellen Sie sicher, dass Ihre Office Communications Server 2007 R2-Richtlinien und-Einstellungen in lync Server 2013 importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="098b0-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="098b0-105">In der folgenden Tabelle werden die Richtlinien und Einstellungen aufgelistet, die Sie überprüfen sollten.</span><span class="sxs-lookup"><span data-stu-id="098b0-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="098b0-106">Nach der Migration zu überprüfende Richtlinien und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="098b0-107">Verwendete Arbeitslast</span><span class="sxs-lookup"><span data-stu-id="098b0-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="098b0-108">Zu überprüfende Richtlinien und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="098b0-109">Instant Messaging und Konferenzen</span><span class="sxs-lookup"><span data-stu-id="098b0-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="098b0-110">Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-110">Presence policy</span></span></p>
<p><span data-ttu-id="098b0-111">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-112">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="098b0-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="098b0-113">Zugriffsnummern für Einwahlkonferenz</span><span class="sxs-lookup"><span data-stu-id="098b0-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="098b0-114">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="098b0-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-115">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="098b0-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="098b0-116">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-116">Voice policy</span></span></p>
<p><span data-ttu-id="098b0-117">VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="098b0-117">Voice routes</span></span></p>
<p><span data-ttu-id="098b0-118">Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-118">Dial plans</span></span></p>
<p><span data-ttu-id="098b0-119">PSTN-Verwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="098b0-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="098b0-121">Einfache URLs</span><span class="sxs-lookup"><span data-stu-id="098b0-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-122">Externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="098b0-122">External users</span></span></p></td>
<td><p><span data-ttu-id="098b0-123">Richtlinien für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="098b0-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-124">Archivierung</span><span class="sxs-lookup"><span data-stu-id="098b0-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="098b0-125">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="098b0-126">So überprüfen Sie Richtlinien und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="098b0-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="098b0-127">Notieren Sie sich in Ihrer Office Communications Server 2007 R2 Umgebung die Namen von Wähleinstellungen (früher als Standortprofile bezeichnet), Einwahlnummern (Zugriffs Telefonnummern und Regionen für die Konferenzzentrale), VoIP-Routen und die Richtlinien in der Liste obige Tabelle zusätzlich zu den für Communicator-Webzugriff verwendeten URLs.</span><span class="sxs-lookup"><span data-stu-id="098b0-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="098b0-128">Öffnen Sie auf dem lync Server 2013-Front-End-Server lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="098b0-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="098b0-129">Zum Überprüfen der importierten Konferenzrichtlinien klicken Sie im linken Bereich auf **Konferenzen**, dann auf **konferenzrichtlinie**, und stellen Sie sicher, dass alle Konferenzrichtlinien in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="098b0-130">Die <STRONG>Besprechungs</STRONG> Richtlinie aus früheren Versionen von Office Communications Server wird nun in lync Server 2013 als konferenzrichtlinie bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="098b0-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="098b0-131">Darüber hinaus ist die Einstellung für <STRONG>Anonyme Teilnehmern</STRONG> aus früheren Versionen von Office Communications Server jetzt eine Einstellung in der lync Server 2013 konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="098b0-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="098b0-132">Wenn in Office Communications Server 2007 R2 die konferenzrichtlinie nicht auf die <STRONG>Verwendung pro Benutzer</STRONG>festgelegt ist, werden nur globale Richtlinieneinstellungen importiert.</span><span class="sxs-lookup"><span data-stu-id="098b0-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="098b0-133">In dieser Situation werden keine anderen Konferenzrichtlinien importiert.</span><span class="sxs-lookup"><span data-stu-id="098b0-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="098b0-134">Wenn <STRONG>Anonyme Teilnehmer</STRONG> in Ihrer Office Communications Server 2007 R2 konferenzrichtlinie auf <STRONG>erzwingen pro Benutzer</STRONG> festgelegt sind, werden während der Migration zwei Konferenzrichtlinien erstellt: eine mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> <STRONG>, und eine</STRONG> mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> , die auf <STRONG>false</STRONG>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="098b0-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="098b0-135">Zum Überprüfen von migrierten Wählplänen klicken Sie auf **VoIP-Routing** und auf **Wählplan**, und stellen Sie dann sicher, dass alle Wählpläne in Ihrer Office Communicator 2007 R2-Umgebung in der Liste aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="098b0-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="098b0-136">In lync Server 2013 werden <STRONG>Standortprofile</STRONG> jetzt als <STRONG>Wählpläne</STRONG>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="098b0-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="098b0-137">Zum Überprüfen der importierten VoIP-Richtlinien klicken Sie auf **VoIP-Routing**, dann auf **VoIP-Richtlinie**, und überprüfen Sie anschließend, ob alle VoIP-Richtlinien in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="098b0-138">Wenn für die VoIP-Richtlinie nicht die <STRONG>Verwendung pro Benutzer</STRONG> in Ihrer Office Communications Server 2007 R2 Umgebung festgelegt ist, werden nur globale Richtlinieneinstellungen importiert.</span><span class="sxs-lookup"><span data-stu-id="098b0-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="098b0-139">In dieser Situation werden keine anderen VoIP-Richtlinien importiert.</span><span class="sxs-lookup"><span data-stu-id="098b0-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="098b0-140">Zum Überprüfen von migrierten VoIP-Routen klicken Sie auf **VoIP-Routing** und dann auf **Route**, und stellen Sie sicher, dass alle VoIP-Routen in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="098b0-141">Zum Überprüfen der importierten PSTN-Verwendungseinstellungen klicken Sie auf **VoIP-Routing** und auf **PSTN-Verwendung**, und stellen Sie dann sicher, dass die PSTN-Verwendungseinstellungen aus der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="098b0-142">Zum Überprüfen der importierten Richtlinien für externen Zugriff klicken Sie auf **Partnerverbund und externer Zugriff** und auf **Externe Zugriffsrichtlinie**, und stellen Sie dann sicher, dass alle Richtlinien für externen Zugriff in der Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="098b0-143">Klicken Sie zum Überprüfen der Archivierungsrichtlinien auf **Überwachung und Archivierung**, klicken Sie auf **Archivierungsrichtlinie**, und stellen Sie dann sicher, dass alle Archivierungsrichtlinien in Ihrer Office Communications Server 2007 R2 Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="098b0-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="098b0-144">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="098b0-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="098b0-145">Geben Sie zum Überprüfen der Anwesenheitsrichtlinien an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="098b0-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="098b0-146">Stellen Sie sicher, dass alle Präsenz Richtlinien in Ihrer Office Communications Server 2007 R2 Umgebung importiert wurden, indem Sie den Namen im Parameter **Identity** betrachten.</span><span class="sxs-lookup"><span data-stu-id="098b0-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="098b0-147">So überprüfen Sie Richtlinien und Einstellungen mithilfe von Cmdlets</span><span class="sxs-lookup"><span data-stu-id="098b0-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="098b0-148">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="098b0-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="098b0-149">Führen Sie die Cmdlets in der folgenden Tabelle aus, um Richtlinien und Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="098b0-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="098b0-150">Die Syntax dieser Cmdlets entspricht dem folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="098b0-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="098b0-151">Wenn Sie ausführliche Informationen zu diesen Cmdlets benötigen, führen Sie folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="098b0-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="098b0-152">Zu überprüfende Richtlinie oder Einstellung</span><span class="sxs-lookup"><span data-stu-id="098b0-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="098b0-153">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="098b0-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="098b0-154">Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="098b0-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-156">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="098b0-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-158">Zugriffsnummern für Einwahlkonferenz</span><span class="sxs-lookup"><span data-stu-id="098b0-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="098b0-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-160">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="098b0-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="098b0-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-162">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="098b0-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-164">VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="098b0-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="098b0-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-166">PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="098b0-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="098b0-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-168">URLs</span><span class="sxs-lookup"><span data-stu-id="098b0-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="098b0-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="098b0-170">Richtlinien für externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="098b0-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="098b0-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="098b0-172">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="098b0-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="098b0-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="098b0-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

