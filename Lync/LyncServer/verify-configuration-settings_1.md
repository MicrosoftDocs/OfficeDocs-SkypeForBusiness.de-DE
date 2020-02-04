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
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="89f15-102">Überprüfen der Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="89f15-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89f15-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="89f15-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="89f15-104">Nachdem Sie die Topologie zusammengeführt und das Cmdlet " **Import-CsLegacyConfiguration** " ausgeführt haben, vergewissern Sie sich, dass Ihre Office Communications Server 2007 R2-Richtlinien und-Einstellungen in lync Server 2013 importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="89f15-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="89f15-105">In der folgenden Tabelle sind die Richtlinien und Einstellungen aufgeführt, die Sie überprüfen sollten.</span><span class="sxs-lookup"><span data-stu-id="89f15-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="89f15-106">Richtlinien und Einstellungen, die nach der Migration überprüft werden sollen</span><span class="sxs-lookup"><span data-stu-id="89f15-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89f15-107">Wenn Sie diese Arbeitsauslastung verwenden:</span><span class="sxs-lookup"><span data-stu-id="89f15-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="89f15-108">Überprüfen Sie diese Richtlinien und Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="89f15-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89f15-109">Instant Messaging (im) und Konferenzen</span><span class="sxs-lookup"><span data-stu-id="89f15-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="89f15-110">Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-110">Presence policy</span></span></p>
<p><span data-ttu-id="89f15-111">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-112">Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="89f15-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="89f15-113">Einwahl-Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="89f15-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="89f15-114">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="89f15-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-115">Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="89f15-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="89f15-116">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-116">Voice policy</span></span></p>
<p><span data-ttu-id="89f15-117">VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="89f15-117">Voice routes</span></span></p>
<p><span data-ttu-id="89f15-118">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="89f15-118">Dial plans</span></span></p>
<p><span data-ttu-id="89f15-119">PSTN-Nutzungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="89f15-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="89f15-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="89f15-121">Einfache URLs </span><span class="sxs-lookup"><span data-stu-id="89f15-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-122">Externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="89f15-122">External users</span></span></p></td>
<td><p><span data-ttu-id="89f15-123">Richtlinien für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="89f15-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-124">Archiving</span><span class="sxs-lookup"><span data-stu-id="89f15-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="89f15-125">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="89f15-126">So überprüfen Sie Richtlinien und Einstellungen</span><span class="sxs-lookup"><span data-stu-id="89f15-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="89f15-127">Notieren Sie sich in Ihrer Office Communications Server 2007 R2-Umgebung die Namen von Wählplänen (vormals als Standortprofile bezeichnet), Einwahl Zugriffsnummern (Konferenzzentrale für den Zugriff auf Telefonnummern und Regionen), VoIP-Routen und die Richtlinien, die in der Liste obige Tabelle zusätzlich zu den URLs, die für Communicator Web Access verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89f15-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="89f15-128">Öffnen Sie auf dem lync Server 2013-Front-End-Server die lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="89f15-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="89f15-129">Um importierte Konferenzrichtlinien zu überprüfen, klicken Sie im linken Bereich auf **Konferenzen**, klicken Sie auf **konferenzrichtlinie**, und überprüfen Sie dann, ob alle Konferenzrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89f15-130">Die <STRONG>Besprechungs</STRONG> Richtlinie aus früheren Versionen von Office Communications Server wird jetzt als konferenzrichtlinie in lync Server 2013 bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="89f15-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="89f15-131">Darüber hinaus ist die Einstellung für <STRONG>Anonyme Teilnehmern</STRONG> aus früheren Versionen von Office Communications Server jetzt eine Einstellung in der lync Server 2013-konferenzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="89f15-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89f15-132">Wenn in Office Communications Server 2007 R2 die konferenzrichtlinie nicht auf <STRONG>pro Benutzer verwenden</STRONG>eingestellt ist, werden nur globale Richtlinieneinstellungen importiert.</span><span class="sxs-lookup"><span data-stu-id="89f15-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="89f15-133">In dieser Situation werden keine weiteren Konferenzrichtlinien importiert.</span><span class="sxs-lookup"><span data-stu-id="89f15-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89f15-134">Wenn für <STRONG>Anonyme Teilnehmer</STRONG> in Ihrer Office Communications Server 2007 R2-konferenzrichtlinie die <STRONG>Erzwingung pro Benutzer</STRONG> festgelegt ist, werden während der Migration zwei Konferenzrichtlinien erstellt: eine mit <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> auf " <STRONG>true</STRONG> " und eines mit " <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> ", das auf " <STRONG>false</STRONG>" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="89f15-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="89f15-135">Klicken Sie zum Überprüfen von importierten Wählplänen auf **VoIP-Routing**, klicken Sie auf **Wählplan**, und überprüfen Sie, ob alle Wählpläne in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89f15-136">In lync Server 2013 werden <STRONG>Standortprofile</STRONG> nun als <STRONG>Wählpläne</STRONG>bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="89f15-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="89f15-137">Um importierte VoIP-Richtlinien zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **VoIP-Richtlinie**, und überprüfen Sie dann, ob alle VoIP-Richtlinien in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="89f15-138">Wenn für die VoIP-Richtlinie nicht die <STRONG>Verwendung pro Benutzer</STRONG> in Ihrer Office Communications Server 2007 R2-Umgebung eingestellt ist, werden nur globale Richtlinieneinstellungen importiert.</span><span class="sxs-lookup"><span data-stu-id="89f15-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="89f15-139">In dieser Situation werden keine anderen VoIP-Richtlinien importiert.</span><span class="sxs-lookup"><span data-stu-id="89f15-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="89f15-140">Um importierte VoIP-Routen zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **Route**, und stellen Sie dann sicher, dass alle VoIP-Routen in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="89f15-141">Um die importierten PSTN-Nutzungseinstellungen zu überprüfen, klicken Sie auf **VoIP-Routing**, klicken Sie auf **PSTN-Nutzung**, und überprüfen Sie, ob die PSTN-Verwendungseinstellungen aus Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="89f15-142">Um importierte Richtlinien für den externen Zugriff zu überprüfen, klicken Sie auf **Föderation und externer Zugriff**, klicken Sie auf **Richtlinie für den externen Zugriff**, und überprüfen Sie, ob alle Richtlinien für den externen Zugriff in Ihrer Office Communicator 2007 R2-Umgebung in der Liste enthalten sind</span><span class="sxs-lookup"><span data-stu-id="89f15-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="89f15-143">Klicken Sie zum Überprüfen von Archivierungsrichtlinien auf **Überwachung und Archivierung**, klicken Sie auf **Archivierungsrichtlinie**, und überprüfen Sie dann, ob alle Archivierungsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung in der Liste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="89f15-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="89f15-144">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="89f15-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="89f15-145">Zum Überprüfen von Anwesenheitsrichtlinien geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="89f15-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="89f15-146">Überprüfen Sie den Namen im Parameter **Identity** , und stellen Sie sicher, dass alle Anwesenheitsrichtlinien in Ihrer Office Communications Server 2007 R2-Umgebung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="89f15-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="89f15-147">So überprüfen Sie Richtlinien und Einstellungen mithilfe von Cmdlets</span><span class="sxs-lookup"><span data-stu-id="89f15-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="89f15-148">Öffnen Sie die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="89f15-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="89f15-149">Führen Sie die Cmdlets in der folgenden Tabelle aus, um Richtlinien und Einstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="89f15-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="89f15-150">Die Syntax dieser Cmdlets ist wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="89f15-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="89f15-151">Details zu diesen Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="89f15-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89f15-152">Für diese Richtlinie oder Einstellung:</span><span class="sxs-lookup"><span data-stu-id="89f15-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="89f15-153">Verwenden Sie dieses Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="89f15-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89f15-154">Anwesenheitsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="89f15-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-156">Konferenzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="89f15-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-158">Einwahl-Zugriffsnummern</span><span class="sxs-lookup"><span data-stu-id="89f15-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="89f15-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-160">Wählpläne</span><span class="sxs-lookup"><span data-stu-id="89f15-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="89f15-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-162">VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="89f15-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-164">VoIP-Routen</span><span class="sxs-lookup"><span data-stu-id="89f15-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="89f15-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-166">PSTN-Verwendung</span><span class="sxs-lookup"><span data-stu-id="89f15-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="89f15-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-168">URLs</span><span class="sxs-lookup"><span data-stu-id="89f15-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="89f15-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89f15-170">Richtlinien für den externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="89f15-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="89f15-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89f15-172">Archivierungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="89f15-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="89f15-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="89f15-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

