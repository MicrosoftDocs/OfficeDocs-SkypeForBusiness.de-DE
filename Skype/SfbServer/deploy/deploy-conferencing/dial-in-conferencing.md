---
title: Konfigurieren von Einwahlkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 7c62ef5ec984fe89033aa4813bca9674979c1c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298235"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="f4ad7-103">Konfigurieren von Einwahlkonferenzen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f4ad7-103">Configure dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="f4ad7-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Einwahlkonferenzen in Skype for Business Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-104">**Summary:** Read this topic to learn how to configure dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="f4ad7-105">Nachdem Sie eine Topologie erstellt haben, die die Konferenz Arbeitsauslastung und ausgewählte Einwahlkonferenzen umfasst, müssen Sie zusätzliche Schritte ausführen, um Einwahlkonferenzen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-105">After you have created a topology that includes the conferencing workload and selected dial-in conferencing, you must perform additional steps to configure dial-in conferencing.</span></span> <span data-ttu-id="f4ad7-106">Bevor Sie dieses Thema lesen, stellen Sie sicher, dass Sie den [Plan für Einwahlkonferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware-und Softwareanforderungen für Konferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md)und das [Bereitstellungs Flussdiagramm und die Checkliste für Einwahlkonferenzen](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-106">Before you read this topic, be sure you have read [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [Hardware and software requirements for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), and the [Deployment flowchart and checklist for dial-in conferencing](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing).</span></span> 
  
<span data-ttu-id="f4ad7-107">Zum Konfigurieren von Einwahlkonferenzen müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-107">To configure dial-in conferencing, you must perform the following tasks:</span></span>
  
- [<span data-ttu-id="f4ad7-108">Configure dial plans</span><span class="sxs-lookup"><span data-stu-id="f4ad7-108">Configure dial plans</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [<span data-ttu-id="f4ad7-109">Configure dial-in conferencing regions</span><span class="sxs-lookup"><span data-stu-id="f4ad7-109">Configure dial-in conferencing regions</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [<span data-ttu-id="f4ad7-110">Configure dial-in access numbers</span><span class="sxs-lookup"><span data-stu-id="f4ad7-110">Configure dial-in access numbers</span></span>](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [<span data-ttu-id="f4ad7-111">Configure conferencing policies</span><span class="sxs-lookup"><span data-stu-id="f4ad7-111">Configure conferencing policies</span></span>](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [<span data-ttu-id="f4ad7-112">Assign a Line URI to a user account</span><span class="sxs-lookup"><span data-stu-id="f4ad7-112">Assign a Line URI to a user account</span></span>](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
<span data-ttu-id="f4ad7-113">Zusätzlich können Sie die folgenden optionalen Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-113">In addition, you may perform the following optional tasks.</span></span> <span data-ttu-id="f4ad7-114">Weitere Informationen zu diesen optionalen Aufgaben finden Sie unter [Verwalten von Einwahlkonferenzen in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-114">For more information about these optional tasks, see [Manage dial-in conferencing in Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).</span></span>
  
- <span data-ttu-id="f4ad7-115">Verwalten von PIN-Richtlinien für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="f4ad7-115">Manage PIN policies for dial-in conferencing</span></span>
    
- <span data-ttu-id="f4ad7-116">Verwalten der Tastenzuordnung für DTMF-Befehle</span><span class="sxs-lookup"><span data-stu-id="f4ad7-116">Manage key mapping for DTMF commands</span></span>
    
- <span data-ttu-id="f4ad7-117">Erstellen von Konferenzverzeichnissen</span><span class="sxs-lookup"><span data-stu-id="f4ad7-117">Create conference directories</span></span>
    
- <span data-ttu-id="f4ad7-118">Verwalten der Ankündigungen beim Beitreten oder Verlassen einer Konferenz</span><span class="sxs-lookup"><span data-stu-id="f4ad7-118">Manage conference join and leave announcements</span></span>
    
- <span data-ttu-id="f4ad7-119">Testen der Einwahlkonferenzeinstellungen</span><span class="sxs-lookup"><span data-stu-id="f4ad7-119">Test dial-in conferencing settings</span></span>
    
- <span data-ttu-id="f4ad7-120">Senden einer Begrüßungs-E-Mail an die Einwahlbenutzer</span><span class="sxs-lookup"><span data-stu-id="f4ad7-120">Send welcome mail to dial-in users</span></span>
    
## <a name="configure-dial-plans"></a><span data-ttu-id="f4ad7-121">Konfigurieren von Wähleinstellungen</span><span class="sxs-lookup"><span data-stu-id="f4ad7-121">Configure dial plans</span></span>
<span data-ttu-id="f4ad7-122"><a name="BKMK_ConfigureDialPlans"> </a></span><span class="sxs-lookup"><span data-stu-id="f4ad7-122"></span></span>

<span data-ttu-id="f4ad7-123">Bei der Bereitstellung von Einwahlkonferenzen müssen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-123">When you deploy dial-in conferencing, you need to create or modify one or more dial plans for routing dial-in access phone numbers.</span></span> <span data-ttu-id="f4ad7-124">Darüber hinaus müssen Sie sicherstellen, dass jeder Wählplan mindestens eine Normalisierungsregel enthält – eine Regel, die Telefonerweiterungen in vollständige Telefonnummern im E. 164-Format umwandelt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-124">You must also make sure that each dial plan contains at least one normalization rule--a rule that converts telephone extensions into complete phone numbers in E.164 format.</span></span> 
  
<span data-ttu-id="f4ad7-p104">Benutzer von Einwahlkonferenzen nehmen an Konferenzen als authentifizierte Unternehmensbenutzer teil, indem sie ihre PIN und die Telefonnummer eingeben. Sie benötigen eine Normalisierungsregel zum Konvertieren von Durchwahlen in vollständige Rufnummern, damit Benutzer bei Eingabe einer Durchwahl authentifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p104">Users of dial-in conferencing join conferences as authenticated enterprise users by entering their personal identification number (PIN) and their phone number. You need a normalization rule to convert extensions into complete phone numbers so that users can be authenticated when they enter just a telephone extension.</span></span>
  
<span data-ttu-id="f4ad7-127">So richten Sie Wähleinstellungen für Einwahlkonferenzen ein:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-127">To set up dial plans for dial-in conferencing:</span></span>
  
- <span data-ttu-id="f4ad7-128">Unabhängig davon, ob Sie Enterprise-VoIP bereitstellen oder nicht, fügen Sie zu den Wähleinstellungen eine Region für Einwahlkonferenzen hinzu und stellen Sie sicher, dass Ihre Einwahlnummern einwandfrei von einer Normalisierungsregel umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-128">Whether or not you deploy Enterprise Voice, modify the global dial plan to add a dial-in conferencing region and to make sure that a normalization rule accurately converts your dial-in access numbers.</span></span> <span data-ttu-id="f4ad7-129">Ausführliche Anweisungen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-129">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="f4ad7-130">Wenn Sie Enterprise-VoIP nicht bereitstellen, erstellen Sie Wählpläne für Ihre Einwahlnummern.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-130">If you did not deploy Enterprise Voice, create dial plans for your dial-in conferencing access numbers.</span></span> <span data-ttu-id="f4ad7-131">Fügen Sie auf jeden Fall eine Region für Einwahlkonferenzen hinzu.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-131">Be sure to include a dial-in conferencing region.</span></span> <span data-ttu-id="f4ad7-132">Ausführliche Anweisungen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-132">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
- <span data-ttu-id="f4ad7-133">Wenn Sie Enterprise-VoIP bereitgestellt haben, ändern Sie Enterprise-sprach Wählpläne nach Bedarf, um Regionen einzubeziehen und geeignete Normalisierungsregeln für Einwahl Zugriffsnummern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-133">If you deployed Enterprise Voice, modify Enterprise Voice dial plans as necessary to include regions and use appropriate normalization rules for dial-in access numbers.</span></span> <span data-ttu-id="f4ad7-134">Sie können auch dedizierte Wählpläne erstellen, die nur für Einwahl Zugriffsnummern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-134">You can also create dedicated dial plans that are used only for dial-in access numbers.</span></span> <span data-ttu-id="f4ad7-135">Ausführliche Anweisungen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-135">For detailed instructions, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
    
<span data-ttu-id="f4ad7-136">Details zum Erstellen von Normalisierungsregeln finden Sie unter [erstellen oder Ändern einer Normalisierungsregel in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-136">For details about creating normalization rules, see [Create or modify a normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).</span></span>
  
## <a name="configure-dial-in-conferencing-regions"></a><span data-ttu-id="f4ad7-137">Konfigurieren von Einwahlkonferenzregionen</span><span class="sxs-lookup"><span data-stu-id="f4ad7-137">Configure dial-in conferencing regions</span></span>
<span data-ttu-id="f4ad7-138"><a name="BKMK_ConfigureDialInRegions"> </a></span><span class="sxs-lookup"><span data-stu-id="f4ad7-138"></span></span>

<span data-ttu-id="f4ad7-p108">Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Die Einwahlkonferenzregion ordnet den Einwahlkonferenznummern die entsprechenden Wähleinstellungen zu. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p108">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. The dial-in conferencing region associates dial-in conferencing access numbers with the appropriate dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span> 
  
<span data-ttu-id="f4ad7-142">Da es wichtig ist, eine Region für alle Wähleinstellungen anzugeben, wird empfohlen, das Vorhandensein von Konferenzregionen für alle Wähleinstellungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-142">Because it important to specify a region for all dial plans, we recommend that you verify that all dial plans have conferencing regions.</span></span> 
  
<span data-ttu-id="f4ad7-143">Verwenden Sie das Cmdlet **Get-CsDialPlan**, um zu überprüfen, ob die Region für alle Wählpläne für Einwahlkonferenzen festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-143">To verify whether the region is set for all dial-in conferencing dial plans, use the **Get-CsDialPlan** cmdlet.</span></span> <span data-ttu-id="f4ad7-144">Wenn die Region in bestimmten Wählplänen nicht vorhanden ist, können Sie die Region über das Cmdlet **Set-CsDialPlan** festlegen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-144">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="f4ad7-145">Sie können die Region auch in vorhandenen Wählplänen mit der Skype for Business Server-Systemsteuerung aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-145">You can also use Skype for Business Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="f4ad7-146">Ausführliche Informationen zur Verwendung der Skype for Business Server-Systemsteuerung finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-146">For details about using Skype for Business Server Control Panel, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="f4ad7-147">So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde</span><span class="sxs-lookup"><span data-stu-id="f4ad7-147">To verify whether dial plans have the region property set</span></span>

1. <span data-ttu-id="f4ad7-148">Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-148">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="f4ad7-149">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-149">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4ad7-150">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-150">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   <span data-ttu-id="f4ad7-151">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-151">For example:</span></span>
    
   ```
   Get-CsDialPlan
   ```

   <span data-ttu-id="f4ad7-152">In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-152">In this example, all the dial plans configured for your organization are returned.</span></span>
    
4. <span data-ttu-id="f4ad7-153">Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-153">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> 
    
<span data-ttu-id="f4ad7-154">Weitere Informationen finden Sie unter [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-154">For more information, see [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).</span></span>
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="f4ad7-155">So legen Sie die Region für einen Satz mit Wähleinstellungen fest</span><span class="sxs-lookup"><span data-stu-id="f4ad7-155">To set the region property for a dial plan</span></span>

1. <span data-ttu-id="f4ad7-156">Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-156">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>
    
2. <span data-ttu-id="f4ad7-157">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f4ad7-158">Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-158">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   <span data-ttu-id="f4ad7-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-159">For example:</span></span>
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   <span data-ttu-id="f4ad7-160">In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-160">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> 
    
<span data-ttu-id="f4ad7-161">Weitere Informationen finden Sie unter [Satz-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-161">For more information, see [Set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).</span></span>
  
## <a name="configure-dial-in-access-numbers"></a><span data-ttu-id="f4ad7-162">Konfigurieren von Zugriffsnummern für die Einwahl</span><span class="sxs-lookup"><span data-stu-id="f4ad7-162">Configure dial-in access numbers</span></span>
<span data-ttu-id="f4ad7-163"><a name="BKMK_ConfigureDialInAccessNumbers"> </a></span><span class="sxs-lookup"><span data-stu-id="f4ad7-163"></span></span>

<span data-ttu-id="f4ad7-164">Beim Bereitstellen von Einwahlkonferenzen müssen Sie Telefonnummern einrichten, die Benutzer aus dem Telefonfestnetz (Public Switched Telephone Network, PSTN) wählen können, um am Audioteil einer Konferenz teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-164">When you deploy dial-in conferencing, you need to set up phone numbers that users can dial from the public switched telephone network (PSTN) to join the audio portion of conferences.</span></span> <span data-ttu-id="f4ad7-165">Diese Zugriffsnummern für die Einwahl werden in Besprechungseinladungen und auf der Webseite mit den Einstellungen für Einwahlkonferenzen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-165">These dial-in access numbers appear in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
  
<span data-ttu-id="f4ad7-166">Vor dem Erstellen von Zugriffsnummern für die Einwahl müssen Sie zunächst die Regionen Ihrer Einwahlkonferenzen planen und anschließend Wählpläne für die Regionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-166">Before you can create dial-in access numbers, you must first plan your dial-in conferencing regions and then configure dial plans with the regions.</span></span> <span data-ttu-id="f4ad7-167">Details zu Regionen finden Sie unter [Planen von Einwahlkonferenzen in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-167">For details about regions, see [Plan for dial-in conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md).</span></span> <span data-ttu-id="f4ad7-168">Details zum Konfigurieren von Wählplänen für Einwahlkonferenzen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-168">For details about configuring dial plans for dial-in conferencing, see [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4ad7-p112">Sie können eine neue Zugriffsnummer erst dann für Einwahlkonferenzen verwenden, wenn die Replikation der Active Directory-Domänendienste (AD DS) für diese Zugriffsnummer abgeschlossen ist. Die Replikation kann mehrere Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p112">You cannot use a new dial-in access number until Active Directory Domain Services (AD DS) replication of that access number is complete. Replication can take several hours to complete.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f4ad7-171">Nach dem Erstellen von Zugriffsnummern für die Einwahl können Sie den Anzeigenamen für die Active Directory-Kontaktobjekte modifizieren, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-171">After you create dial-in access numbers, you can modify the display name for the Active Directory contact objects so that users can more easily identify the correct access number.</span></span> <span data-ttu-id="f4ad7-172">Wenn Sie den Anzeigenamen ändern möchten, verwenden Sie das Cmdlet " [Satz-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) ".</span><span class="sxs-lookup"><span data-stu-id="f4ad7-172">To modify the display name, use the [Set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="f4ad7-173">Active Directory-Objekte sollten nicht manuell geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-173">You should not modify Active Directory objects manually.</span></span>
  
### <a name="to-create-a-dial-in-access-number"></a><span data-ttu-id="f4ad7-174">So erstellen Sie eine Einwahlnummer</span><span class="sxs-lookup"><span data-stu-id="f4ad7-174">To create a dial-in access number</span></span>

1. <span data-ttu-id="f4ad7-175">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-175">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f4ad7-176">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-176">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ad7-177">Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Einwahlnummer**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-177">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>
    
4. <span data-ttu-id="f4ad7-178">Führen Sie auf der Seite **Einwahlnummer** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-178">On the **Dial-in Access Number** page, do one of the following:</span></span>
    
   - <span data-ttu-id="f4ad7-179">Klicken Sie auf **Neu**, um **Neue Einwahlnummer** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-179">Click **New** to open **New Dial-in Access Number**.</span></span>
    
   - <span data-ttu-id="f4ad7-180">Klicken Sie auf eine der Einwahlnummern in der Liste, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-180">Click one of the dial-in access numbers in the list, click **Edit**, and then click **Show details**.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f4ad7-p114">Die Suche nach den Inhalten einer Spalte in der Liste der Zugriffsnummern für die Einwahl über das Suchfeld führt möglicherweise nicht zu den erwarteten Ergebnissen. Sortieren Sie die Liste stattdessen nach der gewünschten Spalte, um nach der Zugriffsnummer für die Einwahl zu suchen, die Sie anzeigen oder ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p114">Using the search field to search for the contents of a column in the list of dial-in access numbers may not yield the results you expect. Instead, sort the list by the column of interest to identify the dial-in access number you want to view or change.</span></span> 
  
5. <span data-ttu-id="f4ad7-p115">Geben Sie im Feld **Anzeigenummer** die Telefonnummer ein, die PSTN-Telefonbenutzer (Public Switched Telephone Network, Telefonfestnetz) wählen, um an einer Konferenz teilzunehmen. Diese Nummer wird in Besprechungseinladungen und auf der Webseite mit den Einstellungen für die Einwahlkonferenz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p115">In **Display number**, type the phone number that public switched telephone network (PSTN) phone users dial to join a conference. This number is displayed in meeting invitations and on the Dial-in Conferencing Settings webpage.</span></span>
    
6. <span data-ttu-id="f4ad7-185">Geben Sie in **Anzeigename** eine Beschreibung für die Zugriffsnummer für die Einwahl ein.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-185">In **Display name**, type a description for the dial-in access number.</span></span> <span data-ttu-id="f4ad7-186">Dies ist der Name, der der Einwahl Zugriffsnummer in den Suchergebnissen von Skype for Business zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-186">This is the name that is associated with the dial-in access number in Skype for Business search results.</span></span> <span data-ttu-id="f4ad7-187">Der Name wird im Client angezeigt, wenn ein Benutzer die Einwahlnummer wählt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-187">This name is displayed in the client when a user calls the access number.</span></span> 
    
7. <span data-ttu-id="f4ad7-p117">Geben Sie im Feld **Anschluss-URI** die E.164-Nummer der Zugriffsnummer für die Einwahl im TEL-URI-Format ein, einschließlich des +-Symbols vor der Nummer und ohne Leerzeichen. Beispiel: tel:+14255550200.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p117">In **Line URI**, type the E.164 number of the dial-in access number in TEL URI format, including the + symbol before the number and excluding spaces. For example, tel:+14255550200.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4ad7-190">Dieser Anschluss-URI kann nicht für eine andere Einwahlnummer für Einwahlkonferenzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-190">The same Line URI cannot be reused by another dial-in conferencing access number.</span></span> 
  
8. <span data-ttu-id="f4ad7-191">Führen Sie unter **SIP-URI** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f4ad7-191">In **SIP URI**, do the following:</span></span>
    
   - <span data-ttu-id="f4ad7-192">Geben Sie in das Textfeld einen eindeutigen SIP-URI für diese Zugriffsnummer für Einwahlkonferenzen ein.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-192">In the text box, type a unique SIP URI for this dial-in conferencing access number.</span></span> <span data-ttu-id="f4ad7-193">Dieser SIP-URI wird an verschiedenen Speicherorten angezeigt, einschließlich, aber nicht ausschließlich, von Benachrichtigungsnachrichten und früheren Versionen von lync-Clients.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-193">This SIP URI is displayed in various locations including, but not limited to, call notification messages and previous versions of Lync clients.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="f4ad7-p119">Dieser SIP-URI kann nicht für eine andere Zugriffsnummer für Einwahlkonferenzen verwendet werden. Der SIP-URI kann nach der Erstellung der Zugriffsnummer nicht geändert werden. Die einzige Möglichkeit zum Ändern des SIP-URI besteht darin, die Zugriffsnummer zu löschen und neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p119">The same SIP URI cannot be reused by another dial-in conferencing access number. The SIP URI cannot be modified after the access number is created. The only way to change the SIP URI is to delete and recreate the access number.</span></span> 
  
   - <span data-ttu-id="f4ad7-197">Klicken Sie im Dropdown-Listenfeld auf die Domäne der Conferencing Attendant-Anwendung, die diese Einwahl Zugriffsnummer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-197">In the drop-down list box, click the domain of the Conferencing Attendant application that supports this dial-in access number.</span></span>
    
9. <span data-ttu-id="f4ad7-198">Klicken Sie unter **Pool** auf den Pool, der die Instanz der Konferenzzentrale ausführt, die diese Einwahlnummer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-198">In **Pool**, click the pool that is running the instance of Conferencing Attendant that supports this dial-in access number.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4ad7-199">Wenn der Pool nach dem Erstellen der Zugriffsnummer geändert werden muss, müssen Sie das Cmdlet [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) verwenden oder die Zugriffsnummer löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-199">If you need to change the pool after you create the access number, you must use the [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) cmdlet or delete and recreate the access number.</span></span>
  
10. <span data-ttu-id="f4ad7-200">Klicken Sie unter **Primäre Sprache** auf die Sprache, in der Ansagen für diese Einwahlnummer wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-200">In **Primary language**, click the language in which prompts are played for this dial-in access number.</span></span> 
    
    <span data-ttu-id="f4ad7-p120">Bei der primären Sprache handelt es sich um die Sprache, die die Konferenzzentrale zum Beantworten des Anrufs verwendet. Die unterstützten Sprachen werden auf der Webseite mit den Einstellungen für die Einwahlkonferenz neben den verschiedenen Zugriffsnummern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p120">The primary language is the language that the Conferencing Attendant uses to answer the call. Supported languages are displayed alongside each access phone number on the Dial-in Conferencing Settings webpage.</span></span>
    
11. <span data-ttu-id="f4ad7-203">(Optional) Klicken Sie unter **Sekundäre Sprachen (maximal vier)** auf **Hinzufügen**, wählen Sie eine oder mehrere zusätzliche Sprachen aus, die für Anrufer dieser Zugriffsnummer für die Einwahl unterstützt werden sollen, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-203">(Optional) In **Secondary languages (maximum of four)**, click **Add**, select one or more additional languages that you want to support for callers to this dial-in access number, and then click **OK**.</span></span> 
    
    <span data-ttu-id="f4ad7-p121">Sie können für jede Zugriffsnummer für die Einwahl bis zu vier sekundäre Sprachen auswählen. Benutzer können beim Einwählen in eine Konferenz eine sekundäre Sprache auswählen, bevor sie die Konferenz-ID eingeben.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p121">You can choose up to four secondary languages for each dial-in access number. Users can select a secondary language before entering the conference ID when they dial in to a conference.</span></span>
    
12. <span data-ttu-id="f4ad7-206">Wenn Sie einen Bereich für die Einwahl Zugriffsnummer hinzufügen möchten, klicken Sie unter **zugeordnete Regionen**auf **Hinzufügen**, klicken Sie auf eine oder mehrere Regionen, die den Wählplänen für diese Einwahl Zugriffsnummer zugeordnet sind, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-206">To add a region for the dial-in access number, under **Associated regions**, click **Add**, click one or more regions that are associated with the dial plans for this dial-in access number, and then click **OK**.</span></span>
    
13. <span data-ttu-id="f4ad7-207">Zum Löschen einer Region aus der Einwahlnummer klicken Sie unter **Zugeordnete Regionen** auf die zu löschende Region und anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-207">To delete a region from the dial-in access number, under **Associated regions**, click the region you want to delete, and then click **Remove**.</span></span>
    
14. <span data-ttu-id="f4ad7-208">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-208">Click **Commit**.</span></span>
    
## <a name="configure-conferencing-policies"></a><span data-ttu-id="f4ad7-209">Konfigurieren von Konferenzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f4ad7-209">Configure conferencing policies</span></span>
<span data-ttu-id="f4ad7-210"><a name="BKMK_ConfigureConferencingPolicies"> </a></span><span class="sxs-lookup"><span data-stu-id="f4ad7-210"></span></span>

<span data-ttu-id="f4ad7-p122">Die Konferenzrichtlinie ist eine Benutzerkontoeinstellung, die die Konferenzmöglichkeiten für Teilnehmer festlegt. Sie können Konferenzrichtlinien auf Standort- oder Benutzerebene erstellen. Konferenzrichtlinieneinstellungen umfassen viele Aspekte der Konferenzplanung und -teilnahme. Mehrere Konferenzrichtlinieneinstellungen unterstützen Einwahlkonferenzen für Teilnehmer. Bei der Konfiguration von Einwahlkonferenzen sollten Sie sicherstellen, dass diese Felder für Ihre Organisation angemessen festgelegt sind, und sie bei Bedarf bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-p122">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span> 
  
<span data-ttu-id="f4ad7-216">Weitere Informationen zum Konfigurieren von Konferenzrichtlinien finden Sie unter [Verwalten von Konferenzrichtlinien in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-216">For more information about configuring conferencing policies, see [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).</span></span>
  
## <a name="assign-a-line-uri-to-a-user-account"></a><span data-ttu-id="f4ad7-217">Weisen Sie einem Benutzerkonto einen Anschluss-URI zu</span><span class="sxs-lookup"><span data-stu-id="f4ad7-217">Assign a Line URI to a user account</span></span>
<span data-ttu-id="f4ad7-218"><a name="BKMK_AssignaLineURI"> </a></span><span class="sxs-lookup"><span data-stu-id="f4ad7-218"></span></span>

<span data-ttu-id="f4ad7-219">Teilnehmer an Einwahlkonferenzen geben ihre Telefonnummer oder Durchwahl sowie eine PIN ein, um als authentifizierte Benutzer an Konferenzen teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-219">Dial-in users enter their phone number or extension and a PIN to join conferences as authenticated users.</span></span> <span data-ttu-id="f4ad7-220">Die in den Skype for Business Server-Benutzerkonten angegebene Telefon Leitungs- **URI** ist für die Authentifizierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-220">The telephony **Line URI** specified on Skype for Business Server user accounts is required for authentication.</span></span>
  
<span data-ttu-id="f4ad7-221">In diesem Thema wird beschrieben, wie Sie einem einzelnen Benutzerkonto einen **Anschluss-URI** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-221">The procedure in this topic describes how to assign a **Line URI** for a single user account.</span></span> <span data-ttu-id="f4ad7-222">Wenn Sie mehreren Benutzerkonten einen **Anschluss-URI** zuweisen möchten, können Sie ein Skript erstellen, das das Cmdlet **Set-CsUser** verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-222">If you need to assign a **Line URI** for multiple user accounts, you can create a script that uses the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="f4ad7-223">Details zur Verwendung eines Beispielskripts zum Zuweisen von **Leitungs-URI** zu mehreren Benutzerkonten finden Sie unter Zuweisen von Leitungs- [URIs zu mehreren Benutzern](https://go.microsoft.com/fwlink/p/?linkId=196945).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-223">For details about using a sample script to assign **Line URI** to multiple user accounts, see [Assign Line URIs to Multiple Users](https://go.microsoft.com/fwlink/p/?linkId=196945).</span></span>
  
1. <span data-ttu-id="f4ad7-224">Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-UserAdministrator** oder **CsAdministrator** an.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-224">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-UserAdministrator** or **CsAdministrator** role.</span></span>
    
2.  <span data-ttu-id="f4ad7-225">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-225">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f4ad7-226">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-226">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f4ad7-227">Geben Sie in das Suchfeld den Namen des Benutzers ein, den Sie für Einwahlkonferenzen konfigurieren möchten, oder klicken Sie auf **Filter hinzufügen**, um Suchfelder anzugeben und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-227">In the search field, type the name of the user you want to configure for dial-in conferencing or click **Add filter** to specify search fields, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f4ad7-228">Doppelklicken Sie auf den Benutzernamen, um das Dialogfeld **Skype for Business Server-Benutzer bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-228">Double-click the user name to open the **Edit Skype for Business Server User** dialog box.</span></span>
    
6. <span data-ttu-id="f4ad7-229">Geben Sie unter **Telefonie** in das Feld **Anschluss-URI** eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="f4ad7-229">Under **Telephony**, in the **Line URI** field, type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f4ad7-230">Sie können **Anschluss-URI** nur angeben, wenn **Telefonie** auf **Nur von PC zu PC**, **Enterprise-VoIP**, **Remoteanrufsteuerung** oder **Nur Remoteanrufsteuerung** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-230">You can specify **Line URI** only if **Telephony** is set to **PC-to-PC only**, **Enterprise Voice**, **Remote call control** or **Remote call control only**.</span></span> 
  
7. <span data-ttu-id="f4ad7-231">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f4ad7-231">Click **Commit**.</span></span>
    

