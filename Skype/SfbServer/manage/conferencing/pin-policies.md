---
title: Verwalten von PIN-Richtlinien für einwahlkonferenzen in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 459e80bf-5791-49f8-878d-4a5178b3a210
description: 'Zusammenfassung: Informationen Sie zum Verwalten von PIN-Richtlinien für einwahlkonferenzen in Skype für Business Server.'
ms.openlocfilehash: 6e6fae1d418bbce4f3183e794cf8af5560226534
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888086"
---
# <a name="manage-pin-policies-for-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="0bc7f-103">Verwalten von PIN-Richtlinien für einwahlkonferenzen in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="0bc7f-103">Manage PIN policies for dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="0bc7f-104">**Zusammenfassung:** Informationen Sie zum Verwalten von PIN-Richtlinien für einwahlkonferenzen in Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-104">**Summary:** Learn how to manage PIN policies for dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="0bc7f-105">Skype für Business Server Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen in Ihrer Organisation kann Einwahl in Konferenzen als authentifizierte Benutzer treten eine persönliche Identifikationsnummer (PIN).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-105">Skype for Business Server users who have Active Directory Domain Services (AD DS) credentials in your organization can join dial-in conferences as authenticated users by using a personal identification number (PIN).</span></span> <span data-ttu-id="0bc7f-106">In einer PIN-Richtlinie werden die Regeln für die Funktionsweise der Einwahlkonferenz-PINs definiert.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-106">PIN policy defines the rules for how dial-in conferencing PINs work.</span></span>
  
 <span data-ttu-id="0bc7f-p102">Wenn Sie dieselbe PIN-Richtlinie für Ihre gesamte Organisation einsetzen möchten, können Sie die globale PIN-Richtlinie verwenden und nach Bedarf anpassen. In der globalen PIN-Richtlinie werden die Regeln für Einwahlkonferenz-PINs auf der Gesamtstrukturebene definiert. Die globale PIN-Richtlinie kann angepasst, aber nicht verändert werden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p102">If you want to use the same PIN policy for your entire organization, you can use the global PIN policy and modify it as needed. The global PIN policy defines the rules for dial-in conferencing PINs at the forest level. You can modify the global PIN policy, but you cannot delete it.</span></span>
  
<span data-ttu-id="0bc7f-110">Sie können eine neue PIN-Richtlinie erstellen, wenn für einen Standort oder eine bestimmte Benutzergruppe eine bestimmte Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-110">You can create a new PIN policy if you want a specific policy to apply to a site or to a certain group of users.</span></span>
  
<span data-ttu-id="0bc7f-111">Die PIN-Richtlinien gelten für Benutzer vom engsten bis hin zum weitesten Bereich.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-111">PIN policies apply to users from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="0bc7f-112">Wenn Sie einem Benutzer eine PIN-Richtlinie auf Benutzerebene zuweisen, erhalten diese Einstellungen Vorrang.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-112">If you assign a user-level PIN policy to a user, those settings take precedence.</span></span> <span data-ttu-id="0bc7f-113">Wenn Sie keine Benutzerrichtlinie zuweisen, gilt die PIN-Richtlinie auf Standortebene, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-113">If you do not assign a user policy, the site-level PIN policy applies, if it exists.</span></span> <span data-ttu-id="0bc7f-114">Gelten weder Benutzer- noch Standortrichtlinien, stellt die globale PIN-Richtlinie die Standardeinstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-114">If no user or site policies apply, global PIN policy provides the default settings.</span></span>
  
## <a name="view-information-about-pin-policies"></a><span data-ttu-id="0bc7f-115">Anzeigen von Informationen über PIN-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="0bc7f-115">View information about PIN policies</span></span>

<span data-ttu-id="0bc7f-116">Sie können Informationen zu PIN-Richtlinien mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-116">You can view information about PIN policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc7f-117">Anzeigen von Informationen zu PIN-Richtlinien mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0bc7f-117">View information about PIN policies by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0bc7f-118">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="0bc7f-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="0bc7f-119">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc7f-120">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-120">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0bc7f-121">Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-121">On the **PIN Policy** page, click the PIN policy that you want to view, click **Edit**, and then click **Show details**.</span></span>
    
### <a name="view-information-about-pin-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc7f-122">Anzeigen von Informationen zu PIN-Richtlinien mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0bc7f-122">View information about PIN policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc7f-123">Wenn Sie Informationen zu den PIN-Richtlinien anzeigen möchten, verwenden Sie das Cmdlet **Get-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-123">To view information about PIN policies, use the **Get-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="0bc7f-124">Der folgende Befehl gibt zum Beispiel Informationen über eine einzelne PIN-Richtlinie mit der Identität „site:Redmond“ zurück:</span><span class="sxs-lookup"><span data-stu-id="0bc7f-124">For example, the following command returns information about a single PIN policy with the Identity site:Redmond:</span></span>
  
```
Get-CsPinPolicy -Identity "site:Redmond"
```

<span data-ttu-id="0bc7f-125">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-125">For more information, including a complete syntax description and list of parameters, see [Get-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/get-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-the-global-pin-policy"></a><span data-ttu-id="0bc7f-126">Ändern Sie die globale PIN-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="0bc7f-126">Modify the global PIN policy</span></span>

<span data-ttu-id="0bc7f-127">Sie können die globale PIN-Richtlinie mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-127">You can modify the global PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc7f-128">Ändern der globalen einwahlkonferenzen PIN-Richtlinie mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0bc7f-128">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0bc7f-129">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="0bc7f-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="0bc7f-130">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-130">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc7f-131">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-131">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0bc7f-132">Klicken Sie auf der Seite **PIN-Richtlinie** auf **Global**, klicken Sie auf **Bearbeiten** und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-132">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0bc7f-p105">Geben Sie unter **PIN-Richtlinie bearbeiten** im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p105">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
6. <span data-ttu-id="0bc7f-p106">Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
7. <span data-ttu-id="0bc7f-138">Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-138">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
8. <span data-ttu-id="0bc7f-p107">Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
9. <span data-ttu-id="0bc7f-142">Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-142">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
10. <span data-ttu-id="0bc7f-p108">Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
11. <span data-ttu-id="0bc7f-p109">Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0bc7f-148">Aus Sicherheitsgründen empfiehlt Microsoft, die Verwendung gängiger Muster nicht zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-148">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
12. <span data-ttu-id="0bc7f-149">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-149">Click **Commit**.</span></span>
    
### <a name="modify-the-global-dial-in-conferencing-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc7f-150">Ändern der globalen einwahlkonferenzen PIN-Richtlinie mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0bc7f-150">Modify the global dial-in conferencing PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc7f-151">Um die globale Richtlinie für Einwahlkonferenz-PINs zu ändern, verwenden Sie das Cmdlet **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-151">To modify the global dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0bc7f-p110">Der folgende Befehl ändert den Wert von „MinPasswordLength“ für alle PIN-Richtlinien, die für die Organisation konfiguriert wurden. Dazu ruft der Befehl zunächst das Cmdlet **Get-CsPinPolicy** ohne Parameter auf, um eine Auflistung aller vorhandenen PIN-Richtlinien abzurufen. Diese Auflistung wird dann an das Cmdlet **Set-CsPinPolicy** weitergeleitet, das wiederum den Wert der Eigenschaft „MinPasswordLength“ für jede Richtlinie in der Auflistung ändert.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p110">The following command changes the value of the MinPasswordLength for all the PIN policies configured for use in the organization. To do this, the command first calls the **Get-CsPinPolicy** cmdlet without any parameters in order to retrieve a collection of all the existing PIN policies. That collection is then piped to the **Set-CsPinPolicy** cmdlet, which modifies the value of the MinPasswordLength property for each policy in the collection:</span></span>
  
```
Get-CsPinPolicy | Set-CsPinPolicy -MinPasswordLength 10
```

<span data-ttu-id="0bc7f-155">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-155">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="create-a-user-or-site-pin-policy"></a><span data-ttu-id="0bc7f-156">Erstellen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene</span><span class="sxs-lookup"><span data-stu-id="0bc7f-156">Create a user or site PIN policy</span></span>

<span data-ttu-id="0bc7f-157">Sie können einen Benutzer oder eine Website PIN-Richtlinie mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell erstellen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-157">You can create a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc7f-158">Erstellen Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0bc7f-158">Create a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0bc7f-159">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="0bc7f-159">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="0bc7f-160">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-160">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc7f-161">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-161">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0bc7f-162">Klicken Sie auf der Seite **PIN-Richtlinie** auf **Neu** und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0bc7f-162">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="0bc7f-p111">Klicken Sie auf **Hinzufügen**, um eine Richtlinie auf Benutzerebene zu erstellen. Geben Sie im Abschnitt **Neue PIN-Richtlinie** in **Name** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p111">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="0bc7f-p112">Klicken Sie auf **Standortrichtlinie**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie eine Richtlinie erstellen möchten. Klicken Sie in der Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p112">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="0bc7f-168">Geben Sie im Feld **Beschreibung** eine Beschreibung für die PIN-Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-168">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="0bc7f-p113">Geben Sie im Feld **PIN-Mindestlänge** die gewünschte Mindestlänge für die PIN ein oder wählen Sie sie aus. In der Standardeinstellung beträgt die Mindestlänge fünf Ziffern.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p113">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="0bc7f-p114">Aktivieren Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben**, um anzugeben, nach wie vielen erfolglosen Anmeldeversuchen ein Benutzer gesperrt wird. Wenn Sie diese Option nicht aktivieren, wird die maximale Anzahl von Anmeldeversuchen basierend auf der PIN-Länge automatisch festgelegt. In der Standardeinstellung wird die maximale Anzahl von Anmeldeversuchen automatisch festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p114">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="0bc7f-174">Wenn Sie das Kontrollkästchen **Maximale Anzahl von Anmeldeversuchen angeben** aktiviert haben, geben Sie in **Maximale Anzahl von Anmeldeversuchen** die maximale Anzahl von Anmeldeversuchen ein, die Sie zulassen möchten. Sie können auch einen Wert auswählen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-174">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="0bc7f-p115">Aktivieren Sie das Kontrollkästchen **PIN-Ablauf aktivieren**, um eine PIN-Ablaufdauer festzulegen. Wenn Sie diese Option nicht aktivieren, laufen PINs nie ab. In der Standardeinstellung ist für PINs kein Ablauf festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p115">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="0bc7f-178">Wenn Sie das Kontrollkästchen **PIN-Ablauf aktivieren** aktiviert haben, geben Sie unter **PIN-Ablauf nach (Tagen)** die Anzahl von Tagen ein, nach der PINs ablaufen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-178">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="0bc7f-p116">Geben Sie unter **PIN-Verlaufszähler** die Anzahl von PINs ein, die ein Benutzer erstellen muss, bevor eine PIN erneut verwendet werden kann. In der Standardeinstellung können Benutzer ihre PINs erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p116">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="0bc7f-p117">Aktivieren Sie das Kontrollkästchen **Allgemeine Muster zulassen**, um allgemeine Muster in PINs zuzulassen, beispielsweise aufeinanderfolgende und wiederholte Zahlen. Wenn Sie diese Option nicht aktivieren, sind nur komplexe Ziffernmuster zulässig. In der Standardeinstellung dürfen nur komplexe Ziffernmuster verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p117">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0bc7f-184">Aus Sicherheitsgründen empfiehlt Microsoft, die Verwendung gängiger Muster nicht zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-184">For security reasons, Microsoft recommends that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="0bc7f-185">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-185">Click **Commit**.</span></span>
    
### <a name="create-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc7f-186">Erstellen Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0bc7f-186">Create a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc7f-187">Verwenden Sie das Cmdlet **New-CsPinPolicy**, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-187">To create a user or site PIN policy, use the **New-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0bc7f-p118">Der folgende Befehl erstellt eine neue PIN-Richtlinie mit dem Identitätswert „site:Redmond“. Dieser Befehl enthält nur einen optionalen Parameter, „MinPasswordLength“, mit dem die Eigenschaft „MinPasswordLength“ auf 7 festgelegt wird. Alle übrigen Richtlinieneigenschaften werden mit den Standardwerten konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p118">The following command creates a new PIN policy with the Identity site:Redmond. This command includes just one optional parameter, MinPasswordLength, which is used to set the MinPasswordLength property to 7. All the remaining policy properties will be configured using the default values.</span></span>
  
```
New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 7
```

 <span data-ttu-id="0bc7f-191">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-191">For more information, including a complete syntax description and list of parameters, see [New-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/new-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="modify-a-user-or-site-pin-policy"></a><span data-ttu-id="0bc7f-192">Passen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene an</span><span class="sxs-lookup"><span data-stu-id="0bc7f-192">Modify a user or site PIN policy</span></span>

<span data-ttu-id="0bc7f-193">Sie können einen Benutzer oder eine Website PIN-Richtlinie mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell ändern.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-193">You can modify a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc7f-194">Ändern Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0bc7f-194">Modify a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0bc7f-195">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="0bc7f-195">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="0bc7f-196">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-196">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc7f-197">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-197">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0bc7f-198">Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-198">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="0bc7f-199">Ändern Sie im Abschnitt **PIN-Richtlinie bearbeiten** eine beliebige der Richtlinieneinstellungen. Hiervon ausgenommen ist der Richtlinienname, dieser kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-199">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>
    
6. <span data-ttu-id="0bc7f-200">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-200">Click **Commit**.</span></span>
    
### <a name="modify-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc7f-201">Ändern Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0bc7f-201">Modify a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc7f-202">Wenn die Richtlinie für Einwahlkonferenz-PINs geändert werden soll, verwenden Sie das Cmdlet **Set-CsPinPolicy**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-202">To modify the dial-in conferencing PIN policy, use the **Set-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0bc7f-p119">Der folgende Befehl ändert die dem Standort „Redmond“ zugewiesene PIN-Richtlinie. In diesem Fall ändert der Befehl den Wert der Eigenschaft „MinPasswordLength“ in 10. Das heißt, dass neue PINs mindestens 10 Stellen umfassen müssen:</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p119">The following command modifies the PIN policy assigned to the Redmond site. In this case, the command changes the value of the MinPasswordLength property to 10; that means that new PINs will have to contain at least 10 digits:</span></span>
  
```
Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

<span data-ttu-id="0bc7f-205">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-205">For more information, including a complete syntax description and list of parameters, see [Set-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/set-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="delete-a-user-or-site-pin-policy"></a><span data-ttu-id="0bc7f-206">Löschen Sie eine PIN-Richtlinie auf Benutzer- oder Standortebene</span><span class="sxs-lookup"><span data-stu-id="0bc7f-206">Delete a user or site PIN policy</span></span>

<span data-ttu-id="0bc7f-207">Sie können einen Benutzer oder eine Website PIN-Richtlinie mithilfe der Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell löschen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-207">You can delete a user or site PIN policy by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0bc7f-208">Löschen Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0bc7f-208">Delete a user or site PIN policy by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="0bc7f-209">Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist .</span><span class="sxs-lookup"><span data-stu-id="0bc7f-209">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2.  <span data-ttu-id="0bc7f-210">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-210">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0bc7f-211">Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und dann auf **PIN-Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-211">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="0bc7f-212">Klicken Sie auf der Seite **PIN-Richtlinie** auf die PIN-Richtlinie, die Sie ändern möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **löschen**.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-212">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Delete**.</span></span>
    
### <a name="delete-a-user-or-site-pin-policy-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0bc7f-213">Löschen Sie einen Benutzer oder eine PIN-Richtlinie-Website mithilfe von Skype für Business Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0bc7f-213">Delete a user or site PIN policy by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0bc7f-214">Verwenden Sie das Cmdlet **Remove-CsPinPolicy**, um eine PIN-Richtlinie auf Benutzer- oder Standortebene zu löschen.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-214">To delete a user or site PIN policy, use the **Remove-CsPinPolicy** cmdlet.</span></span>
  
<span data-ttu-id="0bc7f-p120">Der folgende Befehl entfernt alle PIN-Richtlinien, die auf Standortebene konfiguriert wurden. Hierzu wird das Cmdlet **Get-CsPinPolicy** mit dem Parameter „Filter“ aufgerufen, um eine Auflistung aller Richtlinien zurückzugeben, deren Identitätswert mit der Zeichenfolge „site:“ beginnt. Diese Auflistung wird dann an das Cmdlet **Remove-CsPinPolicy** weitergeleitet, das jede Richtlinie in der Auflistung löscht.</span><span class="sxs-lookup"><span data-stu-id="0bc7f-p120">The following command removes all the PIN policies that have been configured at the site scope. To do this, use the **Get-CsPinPolicy** cmdlet, along with the Filter parameter, to return a collection of all the policies that have an Identity that begins with the characters "site:". This collection is then piped to the **Remove-CsPinPolicy** cmdlet, which deletes each policy in the collection:</span></span>
  
```
Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy
```

<span data-ttu-id="0bc7f-218">Weitere Informationen sowie eine Beschreibung für die vollständige Syntax und eine Liste der Parameter finden Sie unter [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0bc7f-218">For more information, including a complete syntax description and list of parameters, see [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/remove-cspinpolicy?view=skype-ps).</span></span>
  

