---
title: Unterstützung für die Verwendung der SEFAUtil-Funktion in PowerShell in Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: erfahren Sie, wie Sie mithilfe von PowerShell SEFAUtil-Funktionen in Skype for Business Server 2019 nach der Installation des kumulativen Updates 1 erhalten.'
ms.openlocfilehash: 91958d466a2f51b45ef933d21bfce10f5c61790d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824019"
---
# <a name="using-sefautil-functionality-via-powershell-in-skype-for-business-server-2019"></a><span data-ttu-id="5c2c6-103">Verwenden der SEFAUtil-Funktionalität über PowerShell in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5c2c6-103">Using SEFAUtil functionality via PowerShell in Skype for Business Server 2019</span></span>

<span data-ttu-id="5c2c6-104">SEFAUtil (Aktivierung der sekundären Erweiterungsfunktion) ermöglicht es Skype for Business Server-Administratoren und Helpdesk-Agents, die Einstellungen für Stellvertretung, Anrufweiterleitung und Gruppenanruf-Abholung im Auftrag eines Skype for Business Server-Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-104">SEFAUtil (Secondary Extension Feature Activation) enables Skype for Business Server administrators and helpdesk agents to configure delegate-ringing, call-forwarding, and Group Call Pickup settings on behalf of a Skype for Business Server user.</span></span> <span data-ttu-id="5c2c6-105">Darüber hinaus können Administratoren mit dem Tool die Anrufweiterleitungseinstellungen abfragen, die für bestimmte Benutzer veröffentlicht sind.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-105">This tool also allows administrators to query the call-routing settings that are published for a particular user.</span></span> <span data-ttu-id="5c2c6-106">Nachdem Sie das kumulative Update für Skype for Business Server 2019 Juli installiert haben, können die folgenden Funktionen, die derzeit nur über SEFAUtil verwaltet werden können, auch über PowerShell verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="5c2c6-106">After you install the Skype for Business Server 2019 July cumulative update, the following functionality that can currently be managed only through SEFAUtil will be also manageable through PowerShell:</span></span>

- [<span data-ttu-id="5c2c6-107">Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="5c2c6-107">Call forwarding settings</span></span>](#call-forwarding-settings)
- [<span data-ttu-id="5c2c6-108">Delegierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c2c6-108">Delegation settings</span></span>](#delegation-settings)
- [<span data-ttu-id="5c2c6-109">Team Mitglieder und Verwandte Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5c2c6-109">Team members and related settings</span></span>](#team-members-and-related-settings)

## <a name="call-forwarding-settings"></a><span data-ttu-id="5c2c6-110">Einstellungen für die Anrufweiterleitung</span><span class="sxs-lookup"><span data-stu-id="5c2c6-110">Call forwarding settings</span></span>

<span data-ttu-id="5c2c6-111">Administratoren können die Einstellungen für die Anrufweiterleitung mithilfe des folgenden Cmdlets in PowerShell ändern:</span><span class="sxs-lookup"><span data-stu-id="5c2c6-111">Administrators can change call forwarding settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserCallForwardingSettings -Identity <UserIdParameter>`

<span data-ttu-id="5c2c6-112">Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurückgegeben und auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-112">This cmdlet returns the specified user’s call forwarding settings as an object and displays the same on the screen.</span></span>

- `Set-CsUserCallForwardingSettings -Identity <UserIdParameter> [Param1 <Value>] [Param2 <Value>]…`

<span data-ttu-id="5c2c6-113">Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers geändert.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-113">This cmdlet modifies the specified user’s call forwarding settings.</span></span> <span data-ttu-id="5c2c6-114">Mit diesem Cmdlet werden die Einstellungen für die Anrufweiterleitung des angegebenen Benutzers als Objekt zurückgegeben und im Erfolgsfall auf dem Bildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-114">This cmdlet returns the specified user’s call forwarding settings as an object, and displays the same on the screen, in case of success.</span></span> <span data-ttu-id="5c2c6-115">Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-115">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToVoicemail] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -DisableForwarding  [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="5c2c6-116">Dieses Cmdlet deaktiviert die Einstellungen für die Anrufweiterleitung des Benutzers (hier werden zwei verschiedene Parameter Beispiele gezeigt).</span><span class="sxs-lookup"><span data-stu-id="5c2c6-116">This cmdlet disables the user’s call forwarding settings (we show two different parameter examples here).</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableForwarding <String> [-Delegates <PSListModifier>] [-DelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`

<span data-ttu-id="5c2c6-117">Dieses Cmdlet ändert die Einstellungen für die Anrufweiterleitung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-117">This cmdlet modifies the user’s call forwarding settings.</span></span>

- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToVoicemail]  [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>] [-Team <PSListModifier>] [-TeamDelegateRingWaitTime <TimeSpan>] [-SettingsActiveWorkHours]`
- `Set-CsUserCallForwardingSettings [-Identity] <UserIdParameter> -EnableSimulRing <String> [-UnansweredToOther <String>] [-UnansweredWaitTime <TimeSpan>] [-Delegates <PSListModifier>]  [-Team <PSListModifier>]  [-TeamDelegateRingWaitTime <TimeSpan>]  [-SettingsActiveWorkHours]`

<span data-ttu-id="5c2c6-118">Mit diesem Cmdlet werden die SimulRing-Einstellungen geändert (erneut mit zwei Parameter Beispielen: eine für unbeantwortete Voicemail und die zweite für andere nicht beantwortet).</span><span class="sxs-lookup"><span data-stu-id="5c2c6-118">This cmdlet modifies the SimulRing settings (again, with two parameter examples, one for unanswered to voicemail and the second being unanswered to other).</span></span>

## <a name="delegation-settings"></a><span data-ttu-id="5c2c6-119">Delegierungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5c2c6-119">Delegation settings</span></span>

<span data-ttu-id="5c2c6-120">Administratoren können Delegierungseinstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:</span><span class="sxs-lookup"><span data-stu-id="5c2c6-120">Administrators can change delegation settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsuserDelegates -Identity <UserIdParameter>`

<span data-ttu-id="5c2c6-121">Dieses Cmdlet gibt ein Objekt der Stell Vertretungsliste zurück und zeigt die Delegatliste des angegebenen Benutzers im Erfolgsfall an.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-121">This cmdlet returns an object of delegates list, and displays the specified user’s delegate list, in case of success.</span></span> <span data-ttu-id="5c2c6-122">Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-122">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates <PSListModifier>]`

<span data-ttu-id="5c2c6-123">Dieses Cmdlet ändert die Delegierungseinstellungen des angegebenen Benutzers, gibt ein Objekt einer Stell Vertretungsliste zurück und zeigt die Liste der Stellvertretungen im Erfolgsfall an.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-123">This cmdlet modifies the specified user’s delegation settings, returns an object of delegates list and displays the list of delegates, in case of success.</span></span> <span data-ttu-id="5c2c6-124">Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-124">In case of failure, an appropriate error message will be shown.</span></span> 

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{add=[list]}] [-Delegates @{remove=[list]}]`

<span data-ttu-id="5c2c6-125">Mit diesem Cmdlet wird eine Stellvertretung hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-125">This cmdlet adds or removes a delegate.</span></span>

- `Set-CsUserDelegates -Identity <UserIdParameter> [-Delegates @{replace=[list]}]`

<span data-ttu-id="5c2c6-126">Mit diesem Cmdlet wird eine Delegate-Liste auf bestimmte Stellvertretungen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-126">This cmdlet sets a delegate list to specific delegates.</span></span>

## <a name="team-members-and-related-settings"></a><span data-ttu-id="5c2c6-127">Team Mitglieder und Verwandte Einstellungen</span><span class="sxs-lookup"><span data-stu-id="5c2c6-127">Team members and related settings</span></span>

<span data-ttu-id="5c2c6-128">Administratoren können Teammitglieder und Verwandte Einstellungen mithilfe des folgenden Cmdlets in PowerShell ändern:</span><span class="sxs-lookup"><span data-stu-id="5c2c6-128">Administrators can change team members and related settings by using the following cmdlet in PowerShell:</span></span>

- `Get-CsUserTeamMembers -Identity <UserIdParameter>`

<span data-ttu-id="5c2c6-129">Dieses Cmdlet gibt ein Objekt zurück, das eine Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-129">This cmdlet returns an object that contains list of team members, and displays the object on screen, in case of success.</span></span> <span data-ttu-id="5c2c6-130">Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-130">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team <PSListModifier>]`

<span data-ttu-id="5c2c6-131">Dieses Cmdlet ändert die Liste der Teammitglieder des angegebenen Benutzers, gibt ein Objekt zurück, das die Liste der Teammitglieder enthält, und zeigt das Objekt im Erfolgsfall auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-131">This cmdlet modifies the specified user’s team members list, returns an object that contains the team member list and displays the object on the screen, in case of success.</span></span> <span data-ttu-id="5c2c6-132">Falls ein Fehler auftritt, wird eine entsprechende Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-132">In case of failure, an appropriate error message will be shown.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{add=[list]}] [-Team @{remove=[list]}]`

<span data-ttu-id="5c2c6-133">Mit diesem Cmdlet werden Teammitglieder hinzugefügt oder entfernt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-133">This cmdlet adds or removes team members.</span></span>

- `Set-CsUserTeamMembers -Identity <UserIdParameter> [-Team @{replace=[list]}]`

<span data-ttu-id="5c2c6-134">Dieses Cmdlet legt eine Teamliste auf bestimmte Mitglieder fest.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-134">This cmdlet sets a team list to specific members.</span></span>

## <a name="more-information"></a><span data-ttu-id="5c2c6-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5c2c6-135">More information</span></span>

<span data-ttu-id="5c2c6-136">Bei lokalen Bereitstellungen können die in diesem Feature eingeführten Cmdlets nur von Mitgliedern der folgenden Gruppen pro der unten angegebenen Zugriffsebene ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="5c2c6-136">For on-premises deployments, the cmdlets introduced in this feature can only be run by members of the following groups, per the access level specified below:</span></span>

- <span data-ttu-id="5c2c6-137">CsAdministrator – abrufen und einstellen für alle Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5c2c6-137">CsAdministrator – Get and Set for all cmdlets</span></span>
- <span data-ttu-id="5c2c6-138">CsVoiceAdministrator-abrufen und einstellen für alle Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5c2c6-138">CsVoiceAdministrator - Get and Set for all cmdlets</span></span>
- <span data-ttu-id="5c2c6-139">CsHelpDesk-Get für alle Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5c2c6-139">CsHelpDesk - Get for all cmdlets</span></span>

<span data-ttu-id="5c2c6-140">Weitere Informationen zu diesen Administratorrollen finden Sie unter [Erstellen von Administratoren für Skype for Business Server Control Panel](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span><span class="sxs-lookup"><span data-stu-id="5c2c6-140">For more information on these administrator roles, see [Create Skype for Business Server Control Panel Administrators](../SfbServer/help-topics/help-depwiz/create-skype-for-business-server-control-panel-administrators.md).</span></span> <span data-ttu-id="5c2c6-141">Der Administrator kann über direkte oder Remoteanmeldung an einem Server Computer auf diese Cmdlets zugreifen.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-141">The administrator can access these cmdlets by directly or remotely logging on to a server computer.</span></span>
<span data-ttu-id="5c2c6-142">Für eine hybridbereitstellung sollten Skype for Business-Administratoren in der Lage sein, Get und für alle Cmdlets festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-142">For a hybrid deployment, Skype for Business administrators should be able to call Get and Set for all cmdlets.</span></span> <span data-ttu-id="5c2c6-143">Weitere Informationen zur vollständigen Liste der Rollen finden Sie unter Informationen [zu Office 365-Administratorrollen](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="5c2c6-143">For more information about the full list of roles, see [About Office 365 admin roles](https://docs.microsoft.com/en-us/office365/admin/add-users/about-admin-roles)</span></span>

> [!NOTE]
> <span data-ttu-id="5c2c6-144">Die automatische Server Ermittlung muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-144">Server auto-discovery must be enabled.</span></span> <span data-ttu-id="5c2c6-145">Für die Verwendung der Cmdlets werden keine zusätzlichen Lizenzierungsanforderungen eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5c2c6-145">No additional licensing requirements will be introduced for use of the cmdlets.</span></span>
