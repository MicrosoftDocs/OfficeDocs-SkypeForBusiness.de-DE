---
title: 'Lync Server 2013: Aktivieren von Benutzern für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d94b2ad348bc1d086716deed2beef0dcfbe78e2b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="064d3-102">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064d3-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="064d3-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="064d3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="064d3-104">Nachdem Sie Dateien für einen oder mehrere Vermittlungsserver installiert, das Routing für ausgehende Anrufe konfiguriert und optional mindestens eine erweiterte Enterprise-VoIP-Funktion bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um einem Benutzer das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="064d3-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="064d3-105">Von den folgenden Verfahren kann nur die erste mithilfe der lync Server-Systemsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="064d3-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="064d3-106">Für die restlichen Verfahren können Sie nur die lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="064d3-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="064d3-107">Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="064d3-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="064d3-108">(Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="064d3-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="064d3-109">(Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="064d3-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="064d3-110">So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="064d3-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="064d3-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="064d3-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="064d3-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="064d3-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="064d3-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="064d3-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="064d3-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="064d3-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="064d3-115">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="064d3-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="064d3-116">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="064d3-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="064d3-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="064d3-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="064d3-118">Klicken Sie auf der Seite **lync Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="064d3-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="064d3-119">Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="064d3-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="064d3-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="064d3-120">Click **Commit**.</span></span>

<span data-ttu-id="064d3-121">Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, stellen Sie sicher, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, egal ob Global (standardmäßig zugewiesen) oder benutzerspezifisch.</span><span class="sxs-lookup"><span data-stu-id="064d3-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="064d3-122">Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="064d3-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="064d3-123">Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="064d3-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="064d3-124">Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="064d3-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="064d3-125">Ausführliche Informationen finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="064d3-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="064d3-126">Zuweisen einer VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="064d3-126">Voice Policy Assignment</span></span>

<span data-ttu-id="064d3-127">VoIP-Richtlinien auf globaler und Websiteebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="064d3-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="064d3-128">Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten.</span><span class="sxs-lookup"><span data-stu-id="064d3-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="064d3-129">Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="064d3-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="064d3-130">Wenn Sie die Global-oder Website-VoIP-Richtlinie für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt "Wähl Plan Zuweisung" auswählen.</span><span class="sxs-lookup"><span data-stu-id="064d3-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="064d3-131">So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="064d3-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="064d3-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="064d3-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="064d3-133">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="064d3-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="064d3-134">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="064d3-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="064d3-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="064d3-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="064d3-136">In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="064d3-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="064d3-137">Details zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie oder zum Ausführen des Cmdlets **Grant-CsVoicePolicy** finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="064d3-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="064d3-138">Zuweisen eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="064d3-138">Dial Plan Assignment</span></span>

<span data-ttu-id="064d3-139">Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="064d3-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="064d3-140">Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen.</span><span class="sxs-lookup"><span data-stu-id="064d3-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="064d3-141">Wenn Sie den Global-oder Website Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="064d3-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="064d3-142">So weisen Sie einen Wählplan zu</span><span class="sxs-lookup"><span data-stu-id="064d3-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="064d3-143">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="064d3-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="064d3-144">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="064d3-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="064d3-145">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einen benutzerspezifischen Wählplan zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="064d3-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="064d3-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="064d3-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="064d3-147">In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly den Benutzer Wählplan mit dem Namen **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="064d3-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="064d3-148">Details zum Zuweisen von Benutzer Wählplänen oder zum Ausführen des Cmdlets **Grant-CsDialPlan** finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="064d3-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="064d3-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="064d3-149">See Also</span></span>


[<span data-ttu-id="064d3-150">Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="064d3-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

