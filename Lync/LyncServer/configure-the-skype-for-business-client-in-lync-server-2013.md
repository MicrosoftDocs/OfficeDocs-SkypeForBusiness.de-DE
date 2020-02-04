---
title: Konfigurieren des Skype for Business-Clients in lync Server 2013
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
ms.openlocfilehash: 1e1aa407fbb1d7d8a006698d30545165352386b1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a><span data-ttu-id="ea90c-102">Konfigurieren der Clientumgebung mit Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-102">Configure the client experience with Skype for Business</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea90c-103">_**Letztes Änderungsdatum des Themas:** 2015-09-17_</span><span class="sxs-lookup"><span data-stu-id="ea90c-103">_**Topic Last Modified:** 2015-09-17_</span></span>

<span data-ttu-id="ea90c-104">**Zusammenfassung:** In diesem Thema wird beschrieben, wie Sie die Clientumgebung für Skype for Business-Clientbenutzer in einer lync Server 2013-Umgebung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ea90c-104">**Summary:** This topic describes how to configure the client experience for Skype for Business client users in a Lync Server 2013 environment.</span></span> <span data-ttu-id="ea90c-105">Sie können die Clientumgebung nur konfigurieren, wenn Sie lync Server 2013 mit dem kumulativen Update vom Dezember 2014 (5.0.8308.857) oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-105">You can configure the client experience only if you are running Lync Server 2013 with the December 2014 Cumulative Update (5.0.8308.857) or later installed.</span></span> <span data-ttu-id="ea90c-106">Informationen zum Aktualisieren von lync Server 2013 finden Sie unter [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span><span class="sxs-lookup"><span data-stu-id="ea90c-106">For information about updating Lync Server 2013, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).</span></span>

<span data-ttu-id="ea90c-107">Skype for Business bietet eine neue Benutzererfahrung, die auf der Skype Consumer-Produkterfahrung basiert.</span><span class="sxs-lookup"><span data-stu-id="ea90c-107">Skype for Business provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="ea90c-108">Neben allen Funktionen von lync bietet Skype for Business neue Funktionen mit vereinfachten Steuerelementen und vertrauten Symbolen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-108">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="ea90c-109">Detaillierte Informationen zur neuen Clientumgebung finden Sie unter [lync ist jetzt Skype for Business – sehen Sie, was es neues](http://go.microsoft.com/fwlink/?linkid=529022)gibt.</span><span class="sxs-lookup"><span data-stu-id="ea90c-109">For detailed information about the new client experience, see [Lync is now Skype for Business -- see what's new](http://go.microsoft.com/fwlink/?linkid=529022).</span></span>

<span data-ttu-id="ea90c-110">Lync Server 2013 unterstützt die neue Skype for Business-Clientumgebung sowie die lync-Clientumgebung.</span><span class="sxs-lookup"><span data-stu-id="ea90c-110">Lync Server 2013 supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="ea90c-111">Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-111">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="ea90c-112">So können Sie beispielsweise die lync-Clientumgebung so lange bereitstellen, bis die Benutzer in Ihrer Organisation in der neuen Skype for Business-Benutzeroberfläche umfassend geschult sind.</span><span class="sxs-lookup"><span data-stu-id="ea90c-112">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="ea90c-113">Wenn Sie noch nicht alle Benutzer auf Skype for Business Server 2015 aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer die gleiche Clientumgebung haben, bis alle auf den neuen Server aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ea90c-113">Or, if you have not yet upgraded all users to Skype for Business Server 2015, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea90c-114">Wenn in Ihrer Organisation Skype for Business Server 2015 und lync Server 2013 bereitgestellt sind, unterscheidet sich die standardmäßige Clientumgebung je nach Server Versionen und UI-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-114">If your organization has both Skype for Business Server 2015 and Lync Server 2013 deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="ea90c-115">Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Benutzeroberfläche ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ea90c-115">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync user interface.</span></span> <span data-ttu-id="ea90c-116">Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ea90c-116">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="ea90c-117">Weitere Informationen entnehmen Sie dem <STRONG>Abschnitt zum Clientverhalten beim ersten Start</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ea90c-117">For more information, see <STRONG>First launch client behavior</STRONG> later in this topic.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ea90c-118">Die lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-118">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions.</span></span> <span data-ttu-id="ea90c-119">Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013-Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Zahl 16 beginnt; Beispiel: 16. x.x.x.</span><span class="sxs-lookup"><span data-stu-id="ea90c-119">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span>



</div>

<div>

## <a name="configure-the-client-experience"></a><span data-ttu-id="ea90c-120">Configure the client experience</span><span class="sxs-lookup"><span data-stu-id="ea90c-120">Configure the client experience</span></span>

<span data-ttu-id="ea90c-121">Sie können die Clientumgebung angeben, die die Benutzer in Ihrer Organisation sehen, indem Sie das Cmdlet " **Satz-CSClientPolicy** " mit dem EnableSkypeUI-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea90c-121">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter.</span></span> <span data-ttu-id="ea90c-122">Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass Website-oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen):</span><span class="sxs-lookup"><span data-stu-id="ea90c-122">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

<span data-ttu-id="ea90c-123">Der nächste Befehl wählt die lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="ea90c-123">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

<span data-ttu-id="ea90c-124">Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer auf der Website "Redmond" ausgewählt:</span><span class="sxs-lookup"><span data-stu-id="ea90c-124">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

<span data-ttu-id="ea90c-125">Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und dann die Richtlinie bestimmten Benutzern zuweisen, indem Sie das Cmdlet **Grant-CsClientPolicy** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ea90c-125">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>

<span data-ttu-id="ea90c-126">Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie, SalesClientUI, erstellt, die die Skype for Business-Clientumgebung auswählt:</span><span class="sxs-lookup"><span data-stu-id="ea90c-126">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

<span data-ttu-id="ea90c-127">Der nächste Befehl weist die Richtlinie „SalesClientUI“ allen Mitgliedern der Verkaufsabteilung zu:</span><span class="sxs-lookup"><span data-stu-id="ea90c-127">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="ea90c-128">Verhalten beim ersten Start des Clients</span><span class="sxs-lookup"><span data-stu-id="ea90c-128">First launch client behaviors</span></span>

<span data-ttu-id="ea90c-129">Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie standardmäßig immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie den Wert des EnableSkypeUI-Parameters auf $false festlegen, wie zuvor beschrieben .</span><span class="sxs-lookup"><span data-stu-id="ea90c-129">By default, when users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="ea90c-130">Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="ea90c-130">After several minutes, users will then be asked to switch to Lync mode.</span></span>

<span data-ttu-id="ea90c-131">Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="ea90c-131">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>

1.  <span data-ttu-id="ea90c-132">Vergewissern Sie sich, dass `EnableSkypeUI` der Wert von in der von Ihnen verwendeten Richtlinie auf $false festgesetzt ist, wie zuvor beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ea90c-132">Confirm that the value of `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>

2.  <span data-ttu-id="ea90c-p108">Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="ea90c-p108">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="ea90c-136">Erstellen Sie \*\* \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\] Microsoft Office lync\*\* -Schlüssel einen neuen **Binärwert** .</span><span class="sxs-lookup"><span data-stu-id="ea90c-136">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="ea90c-137">Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="ea90c-137">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="ea90c-138">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ea90c-138">The key should look like the following:</span></span>
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

<span data-ttu-id="ea90c-139">Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.</span><span class="sxs-lookup"><span data-stu-id="ea90c-139">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="ea90c-140">Steuern der Anzeige des Lernprogramms auf der Willkommenseite</span><span class="sxs-lookup"><span data-stu-id="ea90c-140">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="ea90c-141">Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten darin, einen Begrüßungsbildschirm anzuzeigen, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*.</span><span class="sxs-lookup"><span data-stu-id="ea90c-141">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="ea90c-142">Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ea90c-142">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>

<span data-ttu-id="ea90c-143">Erstellen Sie \*\* \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\\Microsoft\] Office 15,0 lync\*\* -Schlüssel einen neuen **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="ea90c-143">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="ea90c-144">Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="ea90c-144">The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>

<span data-ttu-id="ea90c-145">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ea90c-145">The key should look like the following:</span></span>

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="ea90c-146">Ausschalten des Client-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="ea90c-146">Turn off the client tutorial</span></span>

<span data-ttu-id="ea90c-147">Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:</span><span class="sxs-lookup"><span data-stu-id="ea90c-147">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>

<span data-ttu-id="ea90c-148">Erstellen Sie \*\* \[im\_HKEY\_-\\aktuellen\\Benutzer\\Software\\-\\Microsoft\] Office 15,0 lync\*\* -Schlüssel einen neuen **DWORD-Wert (32-Bit)**.</span><span class="sxs-lookup"><span data-stu-id="ea90c-148">In the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\]** key, create a new **DWORD (32-bit) Value**.</span></span> <span data-ttu-id="ea90c-149">Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="ea90c-149">The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>

    "TutorialFeatureEnabled"=dword:00000000

<span data-ttu-id="ea90c-150">Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.</span><span class="sxs-lookup"><span data-stu-id="ea90c-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>

</div>

</div>

<div>

## <a name="default-client-experiences"></a><span data-ttu-id="ea90c-151">Standard-Client Erlebnisse</span><span class="sxs-lookup"><span data-stu-id="ea90c-151">Default client experiences</span></span>

<span data-ttu-id="ea90c-152">Wenn in Ihrer Organisation sowohl Skype for Business Server 2015 als auch lync Server bereitgestellt werden, unterscheidet sich die Clientumgebung je nach Server Version und der Skype-Benutzeroberflächeneinstellung.</span><span class="sxs-lookup"><span data-stu-id="ea90c-152">If your organization has both Skype for Business Server 2015 and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="ea90c-153">Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Benutzeroberflächeneinstellung:</span><span class="sxs-lookup"><span data-stu-id="ea90c-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ea90c-154">Serverversion</span><span class="sxs-lookup"><span data-stu-id="ea90c-154">Server version</span></span></p></th>
<th><p><span data-ttu-id="ea90c-155">EnableSkypeUI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="ea90c-155">EnableSkypeUI setting</span></span></p></th>
<th><p><span data-ttu-id="ea90c-156">Client-Erfahrung</span><span class="sxs-lookup"><span data-stu-id="ea90c-156">Client experience</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-157">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea90c-157">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="ea90c-158">Standard</span><span class="sxs-lookup"><span data-stu-id="ea90c-158">Default</span></span></p></td>
<td><p><span data-ttu-id="ea90c-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-159">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea90c-160">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea90c-160">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="ea90c-161">Wahr</span><span class="sxs-lookup"><span data-stu-id="ea90c-161">True</span></span></p></td>
<td><p><span data-ttu-id="ea90c-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-162">Skype for Business</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-163">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea90c-163">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="ea90c-164">Falsch</span><span class="sxs-lookup"><span data-stu-id="ea90c-164">False</span></span></p></td>
<td><p><span data-ttu-id="ea90c-165">Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="ea90c-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea90c-166">Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-167">Standard</span><span class="sxs-lookup"><span data-stu-id="ea90c-167">Default</span></span></p></td>
<td><p><span data-ttu-id="ea90c-168">Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="ea90c-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-169">Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-170">Wahr</span><span class="sxs-lookup"><span data-stu-id="ea90c-170">True</span></span></p></td>
<td><p><span data-ttu-id="ea90c-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-171">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea90c-172">Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-173">Falsch</span><span class="sxs-lookup"><span data-stu-id="ea90c-173">False</span></span></p></td>
<td><p><span data-ttu-id="ea90c-174">Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="ea90c-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-175">Lync Server 2010 oder lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-176">Standard</span><span class="sxs-lookup"><span data-stu-id="ea90c-176">Default</span></span></p></td>
<td><p><span data-ttu-id="ea90c-177">Der Benutzer hat gebeten, zur lync-Clientumgebung zu wechseln (der Benutzer kann später nicht mehr zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="ea90c-177">User asked to switch to Lync client experience (user cannot switch to Skype for Business later)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ea90c-178">Die nächste Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für das Skype-UI-Erlebnis ändert:</span><span class="sxs-lookup"><span data-stu-id="ea90c-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="ea90c-179">Serverversion</span><span class="sxs-lookup"><span data-stu-id="ea90c-179">Server version</span></span></p></th>
<th><p><span data-ttu-id="ea90c-180">Skype-UI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="ea90c-180">Skype UI setting</span></span></p></th>
<th><p><span data-ttu-id="ea90c-181">Client-UI = lync</span><span class="sxs-lookup"><span data-stu-id="ea90c-181">Client UI = Lync</span></span></p></th>
<th><p><span data-ttu-id="ea90c-182">Client-Benutzeroberfläche = Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-182">Client UI = Skype for Business</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-183">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea90c-183">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="ea90c-184">Wahr</span><span class="sxs-lookup"><span data-stu-id="ea90c-184">True</span></span></p></td>
<td><p><span data-ttu-id="ea90c-185">Benutzer hat gebeten, zu Skype for Business zu wechseln</span><span class="sxs-lookup"><span data-stu-id="ea90c-185">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="ea90c-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-186">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea90c-187">Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea90c-187">Skype for Business Server 2015</span></span></p></td>
<td><p><span data-ttu-id="ea90c-188">Falsch</span><span class="sxs-lookup"><span data-stu-id="ea90c-188">False</span></span></p></td>
<td><p><span data-ttu-id="ea90c-189">Lync-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="ea90c-189">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="ea90c-190">Benutzer hat gebeten, zur lync-Benutzeroberfläche zu wechseln</span><span class="sxs-lookup"><span data-stu-id="ea90c-190">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-191">Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-192">Wahr</span><span class="sxs-lookup"><span data-stu-id="ea90c-192">True</span></span></p></td>
<td><p><span data-ttu-id="ea90c-193">Benutzer hat gebeten, zu Skype for Business zu wechseln</span><span class="sxs-lookup"><span data-stu-id="ea90c-193">User asked to switch to Skype for Business</span></span></p></td>
<td><p><span data-ttu-id="ea90c-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ea90c-194">Skype for Business</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea90c-195">Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-196">Falsch</span><span class="sxs-lookup"><span data-stu-id="ea90c-196">False</span></span></p></td>
<td><p><span data-ttu-id="ea90c-197">Lync-Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="ea90c-197">Lync UI</span></span></p></td>
<td><p><span data-ttu-id="ea90c-198">Benutzer hat gebeten, zur lync-Benutzeroberfläche zu wechseln</span><span class="sxs-lookup"><span data-stu-id="ea90c-198">User asked to switch to Lync UI</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea90c-199">Lync Server 2010 oder lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="ea90c-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-200">Standard</span><span class="sxs-lookup"><span data-stu-id="ea90c-200">Default</span></span></p></td>
<td><p><span data-ttu-id="ea90c-201">Lync-Modus (kann nicht zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="ea90c-201">Lync mode (cannot switch to Skype for Business)</span></span></p></td>
<td><p><span data-ttu-id="ea90c-202">Lync-Benutzeroberfläche (kann nicht zu Skype for Business wechseln)</span><span class="sxs-lookup"><span data-stu-id="ea90c-202">Lync UI (cannot switch to Skype for Business)</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ea90c-203">Die für die Verwaltung der Konfiguration des Skype for Business-Clients erforderlichen Patch-Versionen sind:</span><span class="sxs-lookup"><span data-stu-id="ea90c-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>

  - <span data-ttu-id="ea90c-204">Lync Server 2010-Februar 2015 Kumulatives Update (4.0.7577.710) für lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="ea90c-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="ea90c-205">Informationen finden Sie unter [Updates für lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span><span class="sxs-lookup"><span data-stu-id="ea90c-205">For information, see [Updates for Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)</span></span>

  - <span data-ttu-id="ea90c-206">Lync Server 2013-Dezember 2014 Kumulatives Update (5.0.8308.857) für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea90c-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="ea90c-207">Informationen finden Sie unter [Updates für lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span><span class="sxs-lookup"><span data-stu-id="ea90c-207">For information, see [Updates for Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).</span></span>

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="ea90c-208">Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="ea90c-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="ea90c-p115">Die Aktualisierung der Registrierung zur Anzeige der Lync-Clientumgebung beim ersten Start des Skype for Business-Clients durch einen Benutzer sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.</span><span class="sxs-lookup"><span data-stu-id="ea90c-p115">The registry update to display the Lync client experience the first time a user launches the Skype for Business client should be done only once. If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data. When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span>

<span data-ttu-id="ea90c-p116">Das nachstehende Verfahren beschreibt, wie die Registrierung geändert werden kann, damit die Lync-Clientumgebung beim ersten Start von Skype for Business auf dem Computer des Benutzers angezeigt wird. Sie haben damit auch die Möglichkeit, die Registrierung für die Deaktivierung des Lernprogramms auf der Willkommensseite zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ea90c-p116">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business. You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>

<span data-ttu-id="ea90c-214">**So erstellen Sie das Gruppenrichtlinienobjekt**</span><span class="sxs-lookup"><span data-stu-id="ea90c-214">**To create the GPO**</span></span>

1.  <span data-ttu-id="ea90c-215">Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="ea90c-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="ea90c-216">Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](http://go.microsoft.com/fwlink/?linkid=532759).</span><span class="sxs-lookup"><span data-stu-id="ea90c-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](http://go.microsoft.com/fwlink/?linkid=532759).</span></span>

2.  <span data-ttu-id="ea90c-217">Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** und wählen Sie im Menü **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>

3.  <span data-ttu-id="ea90c-218">Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das Gruppenrichtlinienobjekt (z. B. **MakeLyncDefaultUI**) ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea90c-218">In the **New GPO** dialog, enter a name for the GPO, for example, **MakeLyncDefaultUI**, and then click **OK**.</span></span>

4.  <span data-ttu-id="ea90c-219">Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt und wählen Sie dann im Menü **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>

5.  <span data-ttu-id="ea90c-220">Im **Gruppenrichtlinienverwaltungs-Editor** erweitern Sie **Benutzerkonfiguration**, dann **Einstellungen** und dann **Windows-Einstellungen** und wählen Sie anschließend den Knoten **Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>

6.  <span data-ttu-id="ea90c-221">Klicken Sie mit der rechten Maustaste auf den **Registrierungs** Knoten, und wählen Sie dann **Neues** \> **Registrierungselement**aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-221">Right-click on the **Registry** node, and then select **New** \> **Registry Item**.</span></span>

7.  <span data-ttu-id="ea90c-222">Aktualisieren Sie im Dialogfeld **Neue Registrierungseigenschaften** die folgenden Angaben:</span><span class="sxs-lookup"><span data-stu-id="ea90c-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ea90c-223">Feld</span><span class="sxs-lookup"><span data-stu-id="ea90c-223">Field</span></span></th>
    <th><span data-ttu-id="ea90c-224">Auszuwählender oder einzugebender Wert</span><span class="sxs-lookup"><span data-stu-id="ea90c-224">Value to select or enter</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="ea90c-225"><strong>Aktion</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-225"><strong>Action</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-226"><strong>Erstellen</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-226"><strong>Create</strong></span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ea90c-227"><strong>Struktur</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-227"><strong>Hive</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="ea90c-228">HKEY_CURRENT_USER</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ea90c-229"><strong>Schlüsselpfad</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-229"><strong>Key Path</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="ea90c-230">Software\Microsoft\Office\Lync</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ea90c-231"><strong>Wertname</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-231"><strong>Value name</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="ea90c-232">EnableSkypeUI</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="ea90c-233"><strong>Werttyp</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-233"><strong>Value type</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="ea90c-234">REG_BINARY</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="ea90c-235"><strong>Wertdaten</strong></span><span class="sxs-lookup"><span data-stu-id="ea90c-235"><strong>Value data</strong></span></span></p></td>
    <td><p><span data-ttu-id="ea90c-236">00000000</span><span class="sxs-lookup"><span data-stu-id="ea90c-236">00000000</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="ea90c-237">Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="ea90c-237">Click **OK** to save your changes, and then close the GPO.</span></span>

<span data-ttu-id="ea90c-238">Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="ea90c-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>

<span data-ttu-id="ea90c-239">**So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie**</span><span class="sxs-lookup"><span data-stu-id="ea90c-239">**To use the GPO to assign the policy**</span></span>

1.  <span data-ttu-id="ea90c-240">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>

2.  <span data-ttu-id="ea90c-241">Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ea90c-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>

3.  <span data-ttu-id="ea90c-242">Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="ea90c-242">On the target user's computer, open a command prompt and type the following command:</span></span>
    
    <span data-ttu-id="ea90c-243">**gpupdate /target:user**</span><span class="sxs-lookup"><span data-stu-id="ea90c-243">**gpupdate /target:user**</span></span>
    
    <span data-ttu-id="ea90c-p117">Die Meldung „Richtlinie wird aktualisiert..." wird angezeigt, während das GPO angewendet wird. Wenn der Vorgang abgeschlossen ist, erscheint die Meldung „Die Aktualisierung der Benutzerrichtlinie wurde abgeschlossen".</span><span class="sxs-lookup"><span data-stu-id="ea90c-p117">The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.</span></span>

4.  <span data-ttu-id="ea90c-246">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="ea90c-246">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="ea90c-247">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="ea90c-247">**gpresult /r**</span></span>
    
    <span data-ttu-id="ea90c-248">Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ea90c-248">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>

<span data-ttu-id="ea90c-249">Um festzustellen, ob das GPO die Registrierung auf dem Computer des Benutzers erfolgreich aktualisiert hat, überprüfen Sie die Registrierung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="ea90c-249">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry.</span></span> <span data-ttu-id="ea90c-250">Öffnen Sie den \*\* \[\_Registrierungs-Editor, und navigieren\_Sie\\zum\\HKEY\\-\\aktuellen\] Benutzer Software-Microsoft Office lync\*\* -Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ea90c-250">Open Registry Editor and navigate to the **\[HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\Lync\]** key.</span></span> <span data-ttu-id="ea90c-251">Wenn das GPO die Registrierung erfolgreich aktualisiert hat, erscheint unter „EnableSkypeUI" der Wert „0".</span><span class="sxs-lookup"><span data-stu-id="ea90c-251">If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

