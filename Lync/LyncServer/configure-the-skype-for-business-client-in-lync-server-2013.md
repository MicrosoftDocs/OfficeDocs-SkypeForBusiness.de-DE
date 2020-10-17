---
title: Konfigurieren des Skype for Business Clients in lync Server 2013
description: Konfigurieren Sie den Skype for Business-Client in lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7f75ae0fa61d9048991934a0ecce7a886079961
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542971"
---
# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="59962-103">Konfigurieren der Clientumgebung mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-103">Configure the client experience with Skype for Business</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59962-104">_**Letztes Änderungsstand des Themas:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="59962-104">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="59962-105">**Zusammenfassung:** In diesem Thema wird beschrieben, wie Sie die Clientumgebung für Skype for Business Clientbenutzer in einer lync Server 2013 Umgebung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="59962-105">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="59962-106">Sie können die Clienterfahrung nur konfigurieren, wenn Sie lync Server 2013 mit dem kumulativen Update vom Dezember 2014 (5.0.8308.857) oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="59962-106">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="59962-107">Informationen zum Aktualisieren von lync Server 2013 finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="59962-107">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="59962-108">Skype for Business bietet eine neue Benutzeroberfläche, die auf der Skype Consumer-Produkterfahrung basiert.</span><span class="sxs-lookup"><span data-stu-id="59962-108">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="59962-109">Zusätzlich zu allen Funktionen von lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen.</span><span class="sxs-lookup"><span data-stu-id="59962-109">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="59962-110">Ausführliche Informationen zu den neuen Clientfunktionen finden Sie unter [lync ist jetzt Skype for Business--siehe What es New](https://go.microsoft.com/fwlink/?linkid=529022).</span><span class="sxs-lookup"><span data-stu-id="59962-110">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](https://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="59962-111">Lync Server 2013 unterstützt die neue Skype for Business-Clientumgebung sowie die lync-Clientumgebung.</span><span class="sxs-lookup"><span data-stu-id="59962-111">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="59962-112">Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen.</span><span class="sxs-lookup"><span data-stu-id="59962-112">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="59962-113">Beispielsweise können Sie die lync-Clientumgebung bereitstellen, bis Benutzer in Ihrer Organisation in der neuen Skype for Business Erfahrung voll ausgebildet sind.</span><span class="sxs-lookup"><span data-stu-id="59962-113">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="59962-114">Oder wenn Sie noch nicht alle Benutzer auf Skype for Business Server 2015 aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer die gleiche Clienterfahrung haben, bis alle auf den neuen Server aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="59962-114">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="59962-115">Wenn Ihre Organisation sowohl Skype for Business Server 2015 als auch lync Server 2013 bereitgestellt hat, unterscheidet sich die standardmäßige Clientumgebung je nach Server Versionen und Benutzeroberflächeneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="59962-115">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="59962-116">Wenn Benutzer Skype for Business zum ersten Mal starten, wird immer die Skype for Business-Benutzeroberfläche angezeigt, auch wenn Sie die lync-Benutzeroberfläche ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="59962-116">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="59962-117">Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="59962-117">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="59962-118">Weitere Informationen finden Sie unter <STRONG>First Launch Client Behavior</STRONG> weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="59962-118">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="59962-119">Die lync 2013 Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen.</span><span class="sxs-lookup"><span data-stu-id="59962-119">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="59962-120">Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013 Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Nummer 16 beginnt; Beispiel: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="59962-120">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="59962-121">Konfigurieren der Clienterfahrung</span><span class="sxs-lookup"><span data-stu-id="59962-121">Configure the client experience</span></span>

<span data-ttu-id="59962-122">Sie können die Clientumgebung angeben, in der die Benutzer in Ihrer Organisation angezeigt werden, indem Sie das Cmdlet " **CSClientPolicy** " mit dem Parameter "EnableSkypeUI" verwenden.</span><span class="sxs-lookup"><span data-stu-id="59962-122">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="59962-123">Mit dem folgenden Befehl wird die Skype for Business Clientumgebung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass Standort-oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen):</span><span class="sxs-lookup"><span data-stu-id="59962-123">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="59962-124">Der nächste Befehl wählt die lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="59962-124">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="59962-125">Der nächste Befehl wählt die Skype for Business Clientumgebung für alle Benutzer innerhalb des Standorts "Redmond" aus:</span><span class="sxs-lookup"><span data-stu-id="59962-125">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="59962-126">Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und dann die Richtlinie bestimmten Benutzern zuweisen, indem Sie das Cmdlet **Grant-CsClientPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="59962-126">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="59962-127">Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie salesclientui "erstellt, mit der die Skype for Business Clientumgebung ausgewählt wird:</span><span class="sxs-lookup"><span data-stu-id="59962-127">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="59962-128">Der nächste Befehl ordnet die Richtlinie, salesclientui ", allen Mitgliedern der Vertriebsabteilung zu:</span><span class="sxs-lookup"><span data-stu-id="59962-128">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="59962-129">Clientverhalten zuerst starten</span><span class="sxs-lookup"><span data-stu-id="59962-129">First launch client behaviors</span></span>

<span data-ttu-id="59962-130">Wenn Benutzer Skype for Business zum ersten Mal starten, wird Ihnen standardmäßig immer die Skype for Business Benutzeroberfläche angezeigt, auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie den Wert des Parameters EnableSkypeUI auf $false wie zuvor beschrieben festlegen.</span><span class="sxs-lookup"><span data-stu-id="59962-130">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="59962-131">Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="59962-131">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="59962-132">Wenn Sie die lync-Benutzeroberfläche anzeigen möchten, wenn Benutzer den Skype for Business-Client zum ersten Mal starten, führen Sie die folgenden Schritte aus, bevor der Client zum ersten Mal nach dem Aktualisieren gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="59962-132">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="59962-133">Stellen Sie sicher, dass der Wert von `EnableSkypeUI` auf $false in der Richtlinie festgelegt ist, die Sie wie zuvor beschrieben verwenden.</span><span class="sxs-lookup"><span data-stu-id="59962-133">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="59962-134">Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="59962-134">Update the system registry on the user's computer.</span></span> <span data-ttu-id="59962-135">Dies sollten Sie tun, bevor Benutzer den Skype for Business-Client zum ersten Mal starten, und Sie sollten dies nur einmal tun.</span><span class="sxs-lookup"><span data-stu-id="59962-135">You should do this before the first time users launch the Skype for Business client, and you should do this only once.</span></span> <span data-ttu-id="59962-136">Informationen zum Erstellen eines Gruppenrichtlinienobjekts zum Aktualisieren der Registrierung auf einem Computer mit Domänenbeitritt finden Sie im Abschnitt weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="59962-136">For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="59962-137">Erstellen Sie im \*\* \[ HKEY \_ aktuellen \_ Benutzer \\ Software- \\ Microsoft \\ Office- \\ lync \] \*\* -Schlüssel einen neuen **binären** Wert.</span><span class="sxs-lookup"><span data-stu-id="59962-137">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="59962-138">Der **Wertname** muss **EnableSkypeUI**sein, und die **Wertdaten** müssen auf **00 00 00 00**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="59962-138">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="59962-139">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="59962-139">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="59962-140">Die lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.</span><span class="sxs-lookup"><span data-stu-id="59962-140">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="59962-141">Steuern der Anzeige des Lernprogramms für Begrüßungsbildschirm</span><span class="sxs-lookup"><span data-stu-id="59962-141">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="59962-142">Wenn Benutzer den Skype for Business-Client öffnen, wird standardmäßig ein Begrüßungsbildschirm angezeigt, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*.</span><span class="sxs-lookup"><span data-stu-id="59962-142">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="59962-143">Sie können die Anzeige des Begrüßungsbildschirms deaktivieren, aber dennoch Benutzern den Zugriff auf das Lernprogramm gestatten, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="59962-143">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="59962-144">Erstellen Sie in der \*\* \[ HKEY- \_ aktuellen \_ Benutzer \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \] \*\* Key einen neuen **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="59962-144">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="59962-145">Der **Wertname** muss **IsBasicTutorialSeenByUser**sein, und die **Wertdaten** müssen auf **1**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="59962-145">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="59962-146">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="59962-146">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="59962-147">Deaktivieren des Client-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="59962-147">Turn off the client tutorial</span></span>

<span data-ttu-id="59962-148">Wenn Sie nicht möchten, dass Ihre Benutzer auf das Lernprogramm zugreifen können, können Sie das Client Lernprogramm mit dem folgenden Registrierungswert deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="59962-148">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="59962-149">Erstellen Sie in der \*\* \[ HKEY- \_ aktuellen \_ Benutzer \\ Software \\ Microsoft \\ Office \\ 15,0 \\ lync \] \*\* Key einen neuen **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="59962-149">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="59962-150">Der **Wertname** muss **TutorialFeatureEnabled**sein, und die **Wertdaten** müssen auf **0**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="59962-150">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="59962-151">Sie können das Lernprogramm wieder aktivieren, indem Sie den **Wert Data** auf **1**festlegen.</span><span class="sxs-lookup"><span data-stu-id="59962-151">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="59962-152">Standard Client-Benutzeroberflächen</span><span class="sxs-lookup"><span data-stu-id="59962-152">Default client experiences</span></span>

<span data-ttu-id="59962-153">Wenn Ihre Organisation sowohl Skype for Business Server 2015 als auch lync Server bereitgestellt wird, unterscheidet sich die Clientumgebung je nach Server Version und der Skype-Benutzeroberflächeneinstellung.</span><span class="sxs-lookup"><span data-stu-id="59962-153">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="59962-154">In der folgenden Tabelle ist die anfängliche Clienterfahrung basierend auf der Server Version und der Benutzeroberflächeneinstellung dargestellt:</span><span class="sxs-lookup"><span data-stu-id="59962-154">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="59962-155">Server Version</span><span class="sxs-lookup"><span data-stu-id="59962-155">Server version</span></span></p></th>
<th><p><span data-ttu-id="59962-156">EnableSkypeUI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="59962-156">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="59962-157">Client Erfahrung</span><span class="sxs-lookup"><span data-stu-id="59962-157">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59962-158">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59962-158">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="59962-159">Standard</span><span class="sxs-lookup"><span data-stu-id="59962-159">Default</span></span></p></td>
<td><p><span data-ttu-id="59962-160">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-160">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59962-161">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59962-161">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="59962-162">Richtig</span><span class="sxs-lookup"><span data-stu-id="59962-162">True</span></span></p></td>
<td><p><span data-ttu-id="59962-163">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-163">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59962-164">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59962-164">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="59962-165">False</span><span class="sxs-lookup"><span data-stu-id="59962-165">False</span></span></p></td>
<td><p><span data-ttu-id="59962-166">Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</span><span class="sxs-lookup"><span data-stu-id="59962-166">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59962-167">Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-167">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-168">Standard</span><span class="sxs-lookup"><span data-stu-id="59962-168">Default</span></span></p></td>
<td><p><span data-ttu-id="59962-169">Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</span><span class="sxs-lookup"><span data-stu-id="59962-169">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59962-170">Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-170">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-171">Richtig</span><span class="sxs-lookup"><span data-stu-id="59962-171">True</span></span></p></td>
<td><p><span data-ttu-id="59962-172">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-172">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59962-173">Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-173">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-174">False</span><span class="sxs-lookup"><span data-stu-id="59962-174">False</span></span></p></td>
<td><p><span data-ttu-id="59962-175">Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true ändern)</span><span class="sxs-lookup"><span data-stu-id="59962-175">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59962-176">Lync Server 2010 oder lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-176">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-177">Standard</span><span class="sxs-lookup"><span data-stu-id="59962-177">Default</span></span></p></td>
<td><p><span data-ttu-id="59962-178">Benutzer wurde aufgefordert, zur lync-Clientumgebung zu wechseln (Benutzer kann später nicht zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="59962-178">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59962-179">Die folgende Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für die Skype-Benutzeroberfläche ändert:</span><span class="sxs-lookup"><span data-stu-id="59962-179">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="59962-180">Server Version</span><span class="sxs-lookup"><span data-stu-id="59962-180">Server version</span></span></p></th>
<th><p><span data-ttu-id="59962-181">Einstellung der Skype-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="59962-181">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="59962-182">Client-Benutzeroberfläche = lync</span><span class="sxs-lookup"><span data-stu-id="59962-182">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="59962-183">Client UI = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-183">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59962-184">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59962-184">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="59962-185">Richtig</span><span class="sxs-lookup"><span data-stu-id="59962-185">True</span></span></p></td>
<td><p><span data-ttu-id="59962-186">Der Benutzer hat aufgefordert, zu Skype for Business zu wechseln</span><span class="sxs-lookup"><span data-stu-id="59962-186">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="59962-187">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-187">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59962-188">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="59962-188">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="59962-189">False</span><span class="sxs-lookup"><span data-stu-id="59962-189">False</span></span></p></td>
<td><p><span data-ttu-id="59962-190">Lync-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="59962-190">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="59962-191">Benutzer aufgefordert, zur lync-Benutzeroberfläche zu wechseln</span><span class="sxs-lookup"><span data-stu-id="59962-191">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59962-192">Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-192">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-193">Richtig</span><span class="sxs-lookup"><span data-stu-id="59962-193">True</span></span></p></td>
<td><p><span data-ttu-id="59962-194">Der Benutzer hat aufgefordert, zu Skype for Business zu wechseln</span><span class="sxs-lookup"><span data-stu-id="59962-194">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="59962-195">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="59962-195">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59962-196">Lync Server 2010 oder lync Server 2013 (mit korrekten Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-196">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-197">False</span><span class="sxs-lookup"><span data-stu-id="59962-197">False</span></span></p></td>
<td><p><span data-ttu-id="59962-198">Lync-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="59962-198">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="59962-199">Benutzer aufgefordert, zur lync-Benutzeroberfläche zu wechseln</span><span class="sxs-lookup"><span data-stu-id="59962-199">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59962-200">Lync Server 2010 oder lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="59962-200">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="59962-201">Standard</span><span class="sxs-lookup"><span data-stu-id="59962-201">Default</span></span></p></td>
<td><p><span data-ttu-id="59962-202">Lync-Modus (kann nicht zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="59962-202">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="59962-203">Lync-Benutzeroberfläche (kann nicht zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="59962-203">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="59962-204">Die für die Verwaltung der Konfiguration des Skype for Business Clients erforderlichen Patch-Versionen sind:</span><span class="sxs-lookup"><span data-stu-id="59962-204">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="59962-205">Lync Server 2010-Februar 2015 Kumulatives Update (4.0.7577.710) für lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="59962-205">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="59962-206">Weitere Informationen finden Sie unter [Updates für lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="59962-206">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="59962-207">Lync Server 2013-Dezember 2014 Kumulatives Update (5.0.8308.857) für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59962-207">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="59962-208">Weitere Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="59962-208">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="59962-209">Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer, der einer Domäne angehört</span><span class="sxs-lookup"><span data-stu-id="59962-209">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="59962-210">Das Registrierungsupdate zum Anzeigen der lync-Clientumgebung, wenn ein Benutzer das erste Mal den Skype for Business-Client startet, sollte nur einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="59962-210">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once.</span></span> <span data-ttu-id="59962-211">Wenn Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) zum Aktualisieren der Registrierung verwenden, müssen Sie das Objekt definieren, um einen neuen Wert zu erstellen, statt die Wertdaten zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="59962-211">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="59962-212">Wenn das Gruppenrichtlinienobjekt angewendet wird und der neue Wert nicht vorhanden ist, wird es vom GPO erstellt und die Wertdaten auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="59962-212">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="59962-213">Im folgenden Verfahren wird beschrieben, wie Sie die Registrierung so ändern, dass die lync-Clientumgebung angezeigt wird, wenn ein Benutzer das Skype for Business zum ersten Mal startet.</span><span class="sxs-lookup"><span data-stu-id="59962-213">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business.</span></span> <span data-ttu-id="59962-214">Sie können dieses Verfahren auch verwenden, um die Registrierung zu aktualisieren, um das Lernprogramm für Begrüßungsbildschirm wie zuvor beschrieben zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="59962-214">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="59962-215">**So erstellen Sie das GPO**</span><span class="sxs-lookup"><span data-stu-id="59962-215">**To create the GPO**</span></span>

1.  <span data-ttu-id="59962-216">Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="59962-216">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="59962-217">Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="59962-217">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="59962-218">Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** , und wählen Sie im Menü **neu** aus.</span><span class="sxs-lookup"><span data-stu-id="59962-218">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="59962-219">Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das GPO ein, beispielsweise **MakeLyncDefaultUI**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="59962-219">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="59962-220">Klicken Sie mit der rechten Maustaste auf das neue GPO, das Sie soeben erstellt haben, und wählen Sie dann im Menü **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="59962-220">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="59962-221">Erweitern Sie im **Gruppenrichtlinien-Verwaltungs-Editor**die Option **Benutzerkonfiguration**, erweitern Sie **Einstellungen**, erweitern Sie **Windows-Einstellungen**, und wählen Sie dann den **Registrierungs** Knoten aus.</span><span class="sxs-lookup"><span data-stu-id="59962-221">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="59962-222">Klicken Sie mit der rechten Maustaste auf den **Registrierungs** Knoten, und wählen Sie dann **Neues** \> **Registrierungselement**aus.</span><span class="sxs-lookup"><span data-stu-id="59962-222">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="59962-223">Aktualisieren Sie im Dialogfeld **neue Registrierungseigenschaften** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="59962-223">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="59962-224">Feld</span><span class="sxs-lookup"><span data-stu-id="59962-224">Field</span></span></th>
    <th><span data-ttu-id="59962-225">Auszuwählender oder einzugebender Wert</span><span class="sxs-lookup"><span data-stu-id="59962-225">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="59962-226"><strong>Aktion</strong></span><span class="sxs-lookup"><span data-stu-id="59962-226"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-227"><strong>Create</strong></span><span class="sxs-lookup"><span data-stu-id="59962-227"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="59962-228"><strong>Struktur</strong></span><span class="sxs-lookup"><span data-stu-id="59962-228"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-229">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="59962-229">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="59962-230"><strong>Schlüsselpfad</strong></span><span class="sxs-lookup"><span data-stu-id="59962-230"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-231">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="59962-231">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="59962-232"><strong>Wertname</strong></span><span class="sxs-lookup"><span data-stu-id="59962-232"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-233">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="59962-233">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="59962-234"><strong>Werttyp</strong></span><span class="sxs-lookup"><span data-stu-id="59962-234"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-235">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="59962-235">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="59962-236"><strong>Value data</strong></span><span class="sxs-lookup"><span data-stu-id="59962-236"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="59962-237">00000000</span><span class="sxs-lookup"><span data-stu-id="59962-237">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="59962-238">Klicken Sie auf **OK** , um die Änderungen zu speichern, und schließen Sie dann das GPO.</span><span class="sxs-lookup"><span data-stu-id="59962-238">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="59962-239">Als nächstes müssen Sie das erstellte GPO mit der Gruppe von Benutzern verknüpfen, denen Sie die Richtlinie zuweisen möchten, beispielsweise einer Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="59962-239">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="59962-240">**So verwenden Sie das GPO zum Zuweisen der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="59962-240">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="59962-241">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen GPO**aus.</span><span class="sxs-lookup"><span data-stu-id="59962-241">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="59962-242">Wählen Sie im Dialogfeld **GPO auswählen** das erstellte GPO aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="59962-242">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="59962-243">Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung, und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="59962-243">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="59962-244">**gpupdate/Target: Benutzer**</span><span class="sxs-lookup"><span data-stu-id="59962-244">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="59962-245">Die Meldung "Richtlinie wird aktualisiert..." wird angezeigt, während das Gruppenrichtlinienobjekt angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="59962-245">The message "Updating policy..." is displayed while the GPO is applied.</span></span> <span data-ttu-id="59962-246">Wenn der Vorgang abgeschlossen ist, wird die Meldung "Benutzerrichtlinien Aktualisierung wurde erfolgreich abgeschlossen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59962-246">When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="59962-247">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="59962-247">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="59962-248">**gpresult/r**</span><span class="sxs-lookup"><span data-stu-id="59962-248">**gpresult /r**</span></span>
    
    <span data-ttu-id="59962-249">Sie sollten "zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des erstellten Gruppenrichtlinienobjekts sehen, das unten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="59962-249">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="59962-250">Sie können auch überprüfen, ob das GPO die Registrierung auf dem Computer eines Benutzers erfolgreich aktualisiert hat, indem Sie die Registrierung untersuchen.</span><span class="sxs-lookup"><span data-stu-id="59962-250">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="59962-251">Öffnen Sie den Registrierungs-Editor, und navigieren Sie zum \*\* \[ HKEY \_ aktuellen \_ Benutzer \\ Software- \\ Microsoft \\ Office \\ lync \] \*\* -Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="59962-251">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="59962-252">Wenn das GPO die Registrierung erfolgreich aktualisiert hat, wird der Wert "EnableSkypeUI" mit dem Wert "0" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="59962-252">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

