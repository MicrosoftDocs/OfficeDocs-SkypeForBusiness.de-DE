---
title: 'Lync Server 2013: Erstellen von ortungsrichtlinien'
description: 'Lync Server 2013: Erstellen von ortungsrichtlinien.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create location policies
ms:assetid: f1878194-c756-4794-8fa1-15dd2118b4b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413006(v=OCS.15)
ms:contentKeyID: 48185794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 464ea9893890ab6185f180434e2dad13818123d1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562261"
---
# <a name="create-location-policies-in-lync-server-2013"></a><span data-ttu-id="45d08-103">Erstellen von ortungsrichtlinien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45d08-103">Create location policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45d08-104">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="45d08-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="45d08-105">Lync Server verwendet eine ortungsrichtlinie, um lync-Clients während der Clientregistrierung für E9-1-1 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="45d08-105">Lync Server uses a location policy to enable Lync clients for E9-1-1 during client registration.</span></span> <span data-ttu-id="45d08-106">Eine ortungsrichtlinie enthält die Einstellungen, mit denen die Implementierung von E9-1-1 definiert wird.</span><span class="sxs-lookup"><span data-stu-id="45d08-106">A location policy contains the settings that define how E9-1-1 will be implemented.</span></span>

<span data-ttu-id="45d08-107">Sie können die globale ortungsrichtlinie bearbeiten und neue getaggte ortungsrichtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="45d08-107">You can edit the global location policy and create new tagged location policies.</span></span> <span data-ttu-id="45d08-108">Ein Client erhält eine globale Richtlinie, wenn er sich nicht in einem Subnetz mit einer zugeordneten ortungsrichtlinie befindet oder wenn dem Client keine Standortrichtlinie direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="45d08-108">A client obtains a global policy when it is not located within a subnet with an associated location policy, or when the client has not been directly assigned a location policy.</span></span> <span data-ttu-id="45d08-109">Markierte Richtlinien werden Subnetzen oder Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="45d08-109">Tagged policies are assigned to subnets or users.</span></span>

<span data-ttu-id="45d08-110">Um eine ortungsrichtlinie zu erstellen, müssen Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist oder Mitglied der Administratorrolle CsVoiceAdministrator ist oder gleichwertige Administratorrechte und-Berechtigungen aufweist.</span><span class="sxs-lookup"><span data-stu-id="45d08-110">To create a location policy, you must use an account that is a member of the RTCUniversalServerAdmins group, or is a member of the CsVoiceAdministrator administrative role, or has equivalent administrator rights and permissions.</span></span>

<span data-ttu-id="45d08-111">Eine vollständige Beschreibung der Standortrichtlinien finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="45d08-111">For a complete description of Location policies, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span> <span data-ttu-id="45d08-112">Cmdlets in diesem Verfahren verwenden eine ortungsrichtlinie, die mit den folgenden Werten definiert ist:</span><span class="sxs-lookup"><span data-stu-id="45d08-112">Cmdlets in this procedure use a location policy defined using the following values:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="45d08-113">Element</span><span class="sxs-lookup"><span data-stu-id="45d08-113">Element</span></span></th>
<th><span data-ttu-id="45d08-114">Wert</span><span class="sxs-lookup"><span data-stu-id="45d08-114">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="45d08-115">EnhancedEmergencyServicesEnabled</span><span class="sxs-lookup"><span data-stu-id="45d08-115">EnhancedEmergencyServicesEnabled</span></span></p></td>
<td><p><span data-ttu-id="45d08-116"><strong>True</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-116"><strong>True</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d08-117">LocationRequired</span><span class="sxs-lookup"><span data-stu-id="45d08-117">LocationRequired</span></span></p></td>
<td><p><span data-ttu-id="45d08-118"><strong>Haftungsausschluss</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-118"><strong>Disclaimer</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d08-119">EnhancedEmergencyServiceDisclaimer</span><span class="sxs-lookup"><span data-stu-id="45d08-119">EnhancedEmergencyServiceDisclaimer</span></span></p></td>
<td><p><span data-ttu-id="45d08-120">Für Ihre Unternehmensrichtlinie müssen Sie einen Standort festlegen.</span><span class="sxs-lookup"><span data-stu-id="45d08-120">Your company policy requires you to set a location.</span></span> <span data-ttu-id="45d08-121">Wenn Sie keinen Standort festlegen, können Sie von Notfalldiensten nicht in Notfällen gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="45d08-121">If you do not set a location, emergency services will not be able to locate you in an emergency.</span></span> <span data-ttu-id="45d08-122">Legen Sie einen Speicherort fest.</span><span class="sxs-lookup"><span data-stu-id="45d08-122">Please set a location.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d08-123">UseLocationForE911Only</span><span class="sxs-lookup"><span data-stu-id="45d08-123">UseLocationForE911Only</span></span></p></td>
<td><p><span data-ttu-id="45d08-124"><strong>False</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-124"><strong>False</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d08-125">PstnUsage</span><span class="sxs-lookup"><span data-stu-id="45d08-125">PstnUsage</span></span></p></td>
<td><p><span data-ttu-id="45d08-126"><strong>EmergencyUsage</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-126"><strong>EmergencyUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d08-127">EmergencyDialString</span><span class="sxs-lookup"><span data-stu-id="45d08-127">EmergencyDialString</span></span></p></td>
<td><p><span data-ttu-id="45d08-128"><strong>911</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-128"><strong>911</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d08-129">EmergencyDialMask</span><span class="sxs-lookup"><span data-stu-id="45d08-129">EmergencyDialMask</span></span></p></td>
<td><p><span data-ttu-id="45d08-130"><strong>112</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-130"><strong>112</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d08-131">NotificationUri</span><span class="sxs-lookup"><span data-stu-id="45d08-131">NotificationUri</span></span></p></td>
<td><p><span data-ttu-id="45d08-132"><strong>sip:security@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-132"><strong>sip:security@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d08-133">ConferenceUri</span><span class="sxs-lookup"><span data-stu-id="45d08-133">ConferenceUri</span></span></p></td>
<td><p><span data-ttu-id="45d08-134"><strong>sip:+14255550123@litwareinc.com</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-134"><strong>sip:+14255550123@litwareinc.com</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="45d08-135">ConferenceMode</span><span class="sxs-lookup"><span data-stu-id="45d08-135">ConferenceMode</span></span></p></td>
<td><p><span data-ttu-id="45d08-136"><strong>TwoWay</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-136"><strong>twoway</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="45d08-137">LocationRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="45d08-137">LocationRefreshInterval</span></span></p></td>
<td><p><span data-ttu-id="45d08-138"><strong>2</strong></span><span class="sxs-lookup"><span data-stu-id="45d08-138"><strong>2</strong></span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="45d08-139">Ausführliche Informationen zum Arbeiten mit Standortrichtlinien finden Sie in der lync Server-Verwaltungsshell Dokumentation für die folgenden Cmdlets:</span><span class="sxs-lookup"><span data-stu-id="45d08-139">For details about working with location policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="45d08-140">New-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="45d08-140">New-CsLocationPolicy</span></span>

  - <span data-ttu-id="45d08-141">Get-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="45d08-141">Get-CsLocationPolicy</span></span>

  - <span data-ttu-id="45d08-142">Set-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="45d08-142">Set-CsLocationPolicy</span></span>

  - <span data-ttu-id="45d08-143">Remove-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="45d08-143">Remove-CsLocationPolicy</span></span>

  - <span data-ttu-id="45d08-144">Grant-CsLocationPolicy</span><span class="sxs-lookup"><span data-stu-id="45d08-144">Grant-CsLocationPolicy</span></span>

<div>

## <a name="to-create-location-policies"></a><span data-ttu-id="45d08-145">So erstellen Sie Standortrichtlinien</span><span class="sxs-lookup"><span data-stu-id="45d08-145">To create location policies</span></span>

1.  <span data-ttu-id="45d08-146">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="45d08-146">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="45d08-147">CsLocationPolicy schlägt fehl, wenn die Einstellung für <STRONG>PstnUsage</STRONG> nicht bereits in der globalen Liste der PstnUsages.</span><span class="sxs-lookup"><span data-stu-id="45d08-147">CsLocationPolicy will fail if the setting for <STRONG>PstnUsage</STRONG> is not already in the Global list of PstnUsages.</span></span>

    
    </div>

2.  <span data-ttu-id="45d08-148">Führen Sie optional das folgende Cmdlet aus, um die globale ortungsrichtlinie zu bearbeiten:</span><span class="sxs-lookup"><span data-stu-id="45d08-148">Optionally, run the following cmdlet to edit the global Location Policy:</span></span>
    
        Set-CsLocationPolicy -Identity Global -EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -PstnUsage "emergencyUsage" -EmergencyDialString "911" -ConferenceMode "twoway" -ConferenceUri "sip:+14255550123@litwareinc.com" -EmergencyDialMask "112" NotificationUri "sip:security@litwareinc.com" -UseLocationForE911Only $true -LocationRefreshInterval 2

3.  <span data-ttu-id="45d08-149">Führen Sie die folgenden Schritte aus, um eine getaggte ortungsrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45d08-149">Run the following to create a tagged Location Policy.</span></span>
    
        New-CsLocationPolicy -Identity Tag:Redmond - EnhancedEmergencyServicesEnabled $true -LocationRequired "disclaimer" -EnhancedEmergencyServiceDisclaimer "Your company policy requires you to set a location. If you do not set a location emergency services will not be able to locate you in an emergency. Please set a location." -UseLocationForE911Only $false -PstnUsage "EmergencyUsage" -EmergencyDialString "911" -EmergencyDialMask "112" -NotificationUri "sip:security@litwareinc.com" -ConferenceUri "sip:+14255550123@litwareinc.com" -ConferenceMode "twoway" -LocationRefreshInterval 2

4.  <span data-ttu-id="45d08-150">Führen Sie das folgende Cmdlet aus, um die in Schritt 3 erstellte getagged-ortungsrichtlinie auf eine Benutzerrichtlinie anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="45d08-150">Run the following cmdlet to apply the tagged Location Policy created in step 3 to a user policy.</span></span>
    
        (Get-CsUser | where { $_.Name -match "UserName" }) | Grant-CsLocationPolicy -PolicyName Redmond

</div>

</div>

<span> </span>

</div>

</div>

</div>

