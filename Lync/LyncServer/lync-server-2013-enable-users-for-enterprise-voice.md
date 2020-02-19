---
title: 'Lync Server 2013: Aktivieren von Benutzern für Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for Enterprise Voice
ms:assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413011(v=OCS.15)
ms:contentKeyID: 48185800
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31b9cffef7dbb9338c1019b965fb398a0f72ed34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="d6dd7-102">Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6dd7-102">Enable users for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6dd7-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d6dd7-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d6dd7-104">Nachdem Sie Dateien für einen oder mehrere Vermittlungsserver installiert, das Routing für ausgehende Anrufe konfiguriert und optional eine oder mehrere erweiterte Enterprise-VoIP-Funktionen bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um Benutzern das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="d6dd7-104">After you install files for one or more Mediation Servers, configure outbound call routing, and optionally deploy one or more advanced Enterprise Voice features, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6dd7-105">In den folgenden Verfahren kann nur der erste mithilfe von lync Server-Systemsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-105">Of the following procedures, only the first can be performed by using Lync Server Control Panel.</span></span> <span data-ttu-id="d6dd7-106">Für die restlichen Verfahren können Sie nur lync Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-106">For the remaining procedures, you can use only Lync Server Management Shell.</span></span>



</div>

  - <span data-ttu-id="d6dd7-107">Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-107">Enable the user account for Enterprise Voice.</span></span>

  - <span data-ttu-id="d6dd7-108">Optional Weisen Sie dem Benutzerkonto eine benutzerspezifische VoIP-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-108">(Optional) Assign the user account a user-specific voice policy.</span></span>

  - <span data-ttu-id="d6dd7-109">Optional Weisen Sie dem Benutzerkonto benutzerspezifische Wähleinstellungen zu.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-109">(Optional) Assign the user account a user-specific dial plan.</span></span>

<div>

## <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="d6dd7-110">So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="d6dd7-110">To enable a user account for Enterprise Voice</span></span>

1.  <span data-ttu-id="d6dd7-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d6dd7-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d6dd7-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d6dd7-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d6dd7-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d6dd7-115">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d6dd7-116">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6.  <span data-ttu-id="d6dd7-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-117">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d6dd7-118">Klicken Sie auf der Seite **Lync Server-Benutzer bearbeiten** unter **Telefonie** auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-118">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="d6dd7-119">Klicken Sie auf **Leitungs-URI**, und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise Tel: + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="d6dd7-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>

9.  <span data-ttu-id="d6dd7-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-120">Click **Commit**.</span></span>

<span data-ttu-id="d6dd7-121">Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, müssen Sie sicherstellen, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, sei es global (standardmäßig zugewiesen) oder benutzerspezifisch.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.</span></span>

<span data-ttu-id="d6dd7-122">Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und Wähleinstellungen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-122">By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="d6dd7-123">Wenn eine VoIP-Richtlinie oder ein Wählplan auf Standortebene für den Standort vorhanden ist, auf dem das Benutzerkonto verwaltet wird, werden diese Website Richtlinien automatisch auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-123">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="d6dd7-124">Um eine VoIP-Richtlinie auf Benutzerbasis oder einen Wählplan auf einen Benutzer anzuwenden, müssen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** ausführen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-124">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="d6dd7-125">Ausführliche Informationen finden Sie in der Dokumentation zur [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d6dd7-125">For details, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

<div>

## <a name="voice-policy-assignment"></a><span data-ttu-id="d6dd7-126">Zuweisung von VoIP-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d6dd7-126">Voice Policy Assignment</span></span>

<span data-ttu-id="d6dd7-127">VoIP-Richtlinien auf globaler und Standortebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-127">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="d6dd7-128">Sie können auch VoIP-Richtlinien erstellen, die für bestimmte Benutzer oder Gruppen gelten.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-128">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="d6dd7-129">Diese benutzerspezifischen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-129">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="d6dd7-130">Wenn Sie die Richtlinie "Global" oder "Standort VoIP" für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt "Wähl Plan Zuweisung" fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-130">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to Dial Plan Assignment section later in this topic.</span></span>

<div>

## <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="d6dd7-131">So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="d6dd7-131">To assign a user-specific voice policy</span></span>

1.  <span data-ttu-id="d6dd7-132">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-132">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d6dd7-133">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-133">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d6dd7-134">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="d6dd7-134">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
        Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d6dd7-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d6dd7-135">For example:</span></span>
    
        Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
    
    <span data-ttu-id="d6dd7-136">In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **voicepolicyjapan zugewiesen**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-136">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>

<span data-ttu-id="d6dd7-137">Ausführliche Informationen zum Zuweisen einer benutzerspezifischen VoIP-Richtlinie oder zum Ausführen des **Grant-CsVoicePolicy-** Cmdlets finden Sie in der Dokumentation zur [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d6dd7-137">For details about assigning a user-specific voice policy or about running the **Grant-CsVoicePolicy** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<span id="BKMK_DialPlanAssignment"></span>

<div>

## <a name="dial-plan-assignment"></a><span data-ttu-id="d6dd7-138">Wähl Plan Zuweisung</span><span class="sxs-lookup"><span data-stu-id="d6dd7-138">Dial Plan Assignment</span></span>

<span data-ttu-id="d6dd7-139">Für den Abschluss der Benutzerkontokonfiguration für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen müssen dem Benutzer Wähleinstellungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-139">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="d6dd7-140">Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht explizit einen vorhandenen Wählplan auf der Basis eines einzelnen Benutzers zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-140">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="d6dd7-141">Wenn Sie den globalen oder den Standort Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-141">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>

<div>

## <a name="to-assign-a-dial-plan"></a><span data-ttu-id="d6dd7-142">So weisen Sie Wähleinstellungen zu</span><span class="sxs-lookup"><span data-stu-id="d6dd7-142">To assign a dial plan</span></span>

1.  <span data-ttu-id="d6dd7-143">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-143">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d6dd7-144">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="d6dd7-145">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um benutzerspezifische Wähleinstellungen zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="d6dd7-145">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
        Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
    
    <span data-ttu-id="d6dd7-146">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d6dd7-146">For example:</span></span>
    
        Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
    
    <span data-ttu-id="d6dd7-147">In diesem Beispiel wird dem Benutzer mit dem Anzeigenamen Bob Kelly der Benutzer Wähl Plan mit dem Namen **dialplanjapan zugewiesen**zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d6dd7-147">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>

<span data-ttu-id="d6dd7-148">Ausführliche Informationen zum Zuweisen eines Benutzer Wähl Plans oder zum Ausführen des **Grant-CsDialPlan-** Cmdlets finden Sie in der Dokumentation zur [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) .</span><span class="sxs-lookup"><span data-stu-id="d6dd7-148">For details about assigning a user dial plan or about running the **Grant-CsDialPlan** cmdlet, see the [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) documentation.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d6dd7-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6dd7-149">See Also</span></span>


[<span data-ttu-id="d6dd7-150">Deaktivieren eines Benutzers für Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6dd7-150">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

