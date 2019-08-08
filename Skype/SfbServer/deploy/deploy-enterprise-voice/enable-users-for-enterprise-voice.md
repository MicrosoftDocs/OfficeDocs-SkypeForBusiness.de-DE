---
title: Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie mit Enterprise-VoIP in Skype for Business Server Anrufe tätigen und empfangen können.'
ms.openlocfilehash: cf9aab0f104582c57e745c95ae5cf8f24f07b3a5
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240331"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="f47c0-103">Aktivieren von Benutzern für Enterprise-VoIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f47c0-103">Enable users for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="f47c0-104">**Zusammenfassung:** Erfahren Sie, wie Sie in Skype for Business Server mithilfe von Enterprise-VoIP Anrufe tätigen und empfangen können.</span><span class="sxs-lookup"><span data-stu-id="f47c0-104">**Summary:** Learn how to enable users to make and receive calls by using Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="f47c0-105">Nachdem Sie Enterprise-VoIP oder-Anruf über Arbeit bereitgestellt haben, können Sie die folgenden Verfahren verwenden, um einem Benutzer das tätigen von Anrufen mithilfe von Enterprise-VoIP zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="f47c0-105">After you deploy Enterprise Voice or Call Via Work, you can use the following procedures to enable a user to make calls by using Enterprise Voice:</span></span>
  
> [!NOTE]
> <span data-ttu-id="f47c0-106">Von den folgenden Verfahren kann nur die erste mithilfe der Skype for Business Server-Systemsteuerung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f47c0-106">Of the following procedures, only the first can be performed by using Skype for Business Server Control Panel.</span></span> <span data-ttu-id="f47c0-107">Für die restlichen Verfahren können Sie nur die Skype for Business Server-Verwaltungsshell verwenden.</span><span class="sxs-lookup"><span data-stu-id="f47c0-107">For the remaining procedures, you can use only Skype for Business Server Management Shell.</span></span> 
  
- <span data-ttu-id="f47c0-108">Aktivieren Sie das Benutzerkonto für Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="f47c0-108">Enable the user account for Enterprise Voice.</span></span>
    
- <span data-ttu-id="f47c0-109">(Optional) Zuweisen einer benutzerspezifischen VoIP-Richtlinie für das Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="f47c0-109">(Optional) Assign the user account a user-specific voice policy.</span></span>
    
- <span data-ttu-id="f47c0-110">(Optional) Zuweisen eines benutzerspezifischen Satzes mit Wähleinstellungen für das Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="f47c0-110">(Optional) Assign the user account a user-specific dial plan.</span></span>
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="f47c0-111">So aktivieren Sie ein Benutzerkonto für Enterprise-VoIP</span><span class="sxs-lookup"><span data-stu-id="f47c0-111">To enable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="f47c0-112">Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Benutzer mit der Administratorrolle **CsVoiceAdministrator**, **CsServerAdministrator** oder **CsAdministrator** beim Computer an.</span><span class="sxs-lookup"><span data-stu-id="f47c0-112">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="f47c0-113">Öffnen Sie die Skype for Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="f47c0-113">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f47c0-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f47c0-115">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, das aktiviert werden soll und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-115">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f47c0-116">Klicken Sie in der Tabelle auf das Benutzerkonto, das Sie für Enterprise-VoIP aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f47c0-116">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>
    
6. <span data-ttu-id="f47c0-117">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-117">On the **Edit** menu, click **Show details**.</span></span>
    
7. <span data-ttu-id="f47c0-118">Klicken Sie auf der Seite **Skype for Business Server-Benutzer bearbeiten** unter **Telefonie**auf **Enterprise-VoIP**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-118">On the **Edit Skype for Business Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>
    
8. <span data-ttu-id="f47c0-119">Klicken Sie auf **Anschluss-URI** und geben Sie eine eindeutige, normalisierte Telefonnummer ein (beispielsweise tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="f47c0-119">Click **Line URI**, and then type a unique, normalized phone number (for example, tel:+14255550200).</span></span>
    
9. <span data-ttu-id="f47c0-120">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-120">Click **Commit**.</span></span>
    
<span data-ttu-id="f47c0-121">Um die Aktivierung eines Benutzers für Enterprise-VoIP abzuschließen, stellen Sie sicher, dass dem Benutzer eine VoIP-Richtlinie und ein Wählplan zugewiesen ist, egal ob Global (standardmäßig zugewiesen) oder benutzerspezifisch. Standardmäßig werden allen Benutzern eine globale VoIP-Richtlinie und ein Wählplan zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f47c0-121">To finish enabling a user for Enterprise Voice, be sure that the user is assigned a voice policy and a dial plan, whether global (assigned by default) or user-specific.By default, all users are assigned a global voice policy and dial plan.</span></span> <span data-ttu-id="f47c0-122">Wenn auf Standortebene eine VoIP-Richtlinie für den Standort vorhanden ist, der das Benutzerkonto verwaltet, gelten diese Standortrichtlinien automatisch für alle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f47c0-122">If a voice policy or dial plan exists at the site level for the site on which the user account is homed, those site policies will automatically apply to the user.</span></span> <span data-ttu-id="f47c0-123">Führen Sie die Cmdlets **Grant-CsVoicePolicy** und **Grant-CsDialPlan** aus, um eine benutzerspezifische VoIP-Richtlinie oder einen Wählplan für einen Benutzer anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="f47c0-123">To apply a per-user voice policy or dial plan to a user, you must run the **Grant-CsVoicePolicy** and **Grant-CsDialPlan** cmdlets.</span></span> <span data-ttu-id="f47c0-124">Ausführliche Informationen finden Sie in den folgenden Verfahren in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="f47c0-124">For details, see the following procedures in this topic.</span></span>
## <a name="voice-policy-assignment"></a><span data-ttu-id="f47c0-125">Zuweisen einer VoIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f47c0-125">Voice Policy Assignment</span></span>

<span data-ttu-id="f47c0-126">VoIP-Richtlinien auf globaler und Websiteebene werden automatisch allen Benutzerkonten zugewiesen, die für Enterprise-VoIP aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f47c0-126">Global and site-level voice policies are automatically assigned to all user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="f47c0-127">Sie können auch VoIP-Richtlinien erstellen, die für spezielle Benutzer oder Gruppen gelten.</span><span class="sxs-lookup"><span data-stu-id="f47c0-127">You can also create voice policies that apply to specific users or groups.</span></span> <span data-ttu-id="f47c0-128">Diese benutzerbezogenen Richtlinien müssen den Benutzern oder Gruppen explizit zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f47c0-128">These per-user policies must be explicitly assigned to the users or groups.</span></span> <span data-ttu-id="f47c0-129">Wenn Sie die Global-oder Website-VoIP-Richtlinie für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen und weiter unten in diesem Thema den Abschnitt " [Wähl Plan Zuweisung](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) " auswählen.</span><span class="sxs-lookup"><span data-stu-id="f47c0-129">If you want to use the global or site voice policy for all users who are enabled for Enterprise Voice, you can skip this section and continue to [Dial Plan Assignment](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) section later in this topic.</span></span>
  
### <a name="to-assign-a-user-specific-voice-policy"></a><span data-ttu-id="f47c0-130">So weisen Sie eine benutzerspezifische VoIP-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="f47c0-130">To assign a user-specific voice policy</span></span>

1. <span data-ttu-id="f47c0-131">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f47c0-131">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f47c0-132">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f47c0-133">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einem Benutzer eine vorhandene VoIP-Benutzerrichtlinie zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="f47c0-133">To assign an existing user voice policy to a user, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="f47c0-134">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f47c0-134">For example:</span></span>
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    <span data-ttu-id="f47c0-135">In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly die VoIP-Richtlinie mit dem Namen **VoicePolicyJapan**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-135">In this example, the user with the display name Bob Kelly is assigned the voice policy with the name **VoicePolicyJapan**.</span></span>
    
## <a name="dial-plan-assignment"></a><span data-ttu-id="f47c0-136">Zuweisen eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="f47c0-136">Dial Plan Assignment</span></span>
<span data-ttu-id="f47c0-137"><a name="BKMK_DialPlanAssignment"> </a></span><span class="sxs-lookup"><span data-stu-id="f47c0-137"></span></span>

<span data-ttu-id="f47c0-138">Um die Konfiguration des Benutzerkontos für Benutzer von Enterprise-VoIP oder Benutzer von Einwahlkonferenzen abzuschließen, muss dem Benutzer ein Wählplan zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="f47c0-138">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="f47c0-139">Benutzerkonten verwenden automatisch den globalen Wählplan oder, falls vorhanden, den Wählplan auf Standortebene, wenn Sie nicht jedem Benutzer explizit einen vorhandenen Wählplan zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f47c0-139">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan, when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="f47c0-140">Wenn Sie den Global-oder Website Wähl Plan für alle Benutzer verwenden möchten, die für Enterprise-VoIP aktiviert sind, können Sie diesen Abschnitt überspringen.</span><span class="sxs-lookup"><span data-stu-id="f47c0-140">If you want to use the global or site dial plan for all users who are enabled for Enterprise Voice, you can skip this section.</span></span>
  
### <a name="to-assign-a-user-specific-dial-plan"></a><span data-ttu-id="f47c0-141">Zuweisen eines benutzerspezifischen Wählplans</span><span class="sxs-lookup"><span data-stu-id="f47c0-141">To assign a user-specific dial plan</span></span>

1. <span data-ttu-id="f47c0-142">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f47c0-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f47c0-143">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-143">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="f47c0-144">Führen Sie den folgenden Befehl an der Eingabeaufforderung aus, um einen benutzerspezifischen Wählplan zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="f47c0-144">To assign a user-specific dial plan, run the following at the command prompt:</span></span>
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    <span data-ttu-id="f47c0-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f47c0-145">For example:</span></span>
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    <span data-ttu-id="f47c0-146">In diesem Beispiel erhält der Benutzer mit dem Anzeigenamen Bob Kelly den Benutzer Wählplan mit dem Namen **DialPlanJapan**.</span><span class="sxs-lookup"><span data-stu-id="f47c0-146">In this example, the user with the display name Bob Kelly is assigned the user dial plan with the name **DialPlanJapan**.</span></span>
    

