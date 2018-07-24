---
title: Konfigurieren der Clientumgebung mit Skype für Business 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren der Clientumgebung für Skype für Geschäftsbenutzer.'
ms.openlocfilehash: 18fb67b88673dd2edfe3816d485a8cb05c84f3ae
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "21018188"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a><span data-ttu-id="2092c-103">Konfigurieren der Clientumgebung mit Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="2092c-103">Configure the client experience with Skype for Business 2015</span></span>
 
<span data-ttu-id="2092c-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Client-Erfahrung für Skype Business 2015 Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2092c-104">**Summary:** Read this topic to learn how to configure the client experience for Skype for Business 2015 users.</span></span>
  
<span data-ttu-id="2092c-105">Skype für Business 2015 bietet eine neue Benutzeroberfläche, die auf Benutzerfunktionen Product Skype basiert.</span><span class="sxs-lookup"><span data-stu-id="2092c-105">Skype for Business 2015 provides a new user experience that is based on the Skype consumer product experience.</span></span> <span data-ttu-id="2092c-106">Zusätzlich zu den Features von Lync bietet Skype für Unternehmen neue Features mit vereinfachte-Steuerelementen und Symbole vertraut.</span><span class="sxs-lookup"><span data-stu-id="2092c-106">In addition to all the features of Lync, Skype for Business provides new features with simplified controls and familiar icons.</span></span> <span data-ttu-id="2092c-107">Ausführliche Informationen zu den neuen Client gewohnt sind finden Sie unter [Erforschen Skype für Unternehmen](https://go.microsoft.com/fwlink/?LinkId=529022).</span><span class="sxs-lookup"><span data-stu-id="2092c-107">For detailed information about the new client experience, see [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).</span></span>
  
<span data-ttu-id="2092c-108">Skype für Business Server unterstützt die neue Skype für Business Clientumgebung als auch das Lync-Clientumgebung.</span><span class="sxs-lookup"><span data-stu-id="2092c-108">Skype for Business Server supports the new Skype for Business client experience as well as the Lync client experience.</span></span> <span data-ttu-id="2092c-109">Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen.</span><span class="sxs-lookup"><span data-stu-id="2092c-109">As an administrator, you can choose the preferred client experience for your users.</span></span> <span data-ttu-id="2092c-110">Sie möchten beispielsweise die Lync-Client-Erfahrung bereitstellen, bis der Benutzer in Ihrer Organisation vollständig in die neue Skype Business wünschen geschult sind.</span><span class="sxs-lookup"><span data-stu-id="2092c-110">For example, you might want to deploy the Lync client experience until users in your organization are fully trained in the new Skype for Business experience.</span></span> <span data-ttu-id="2092c-111">Oder, wenn Sie für Business Server noch nicht alle Benutzer auf Skype aktualisiert haben, sollten Sie alle Benutzer können die gleichen Clientumgebung haben, bis alle auf dem neuen Server aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2092c-111">Or, if you have not yet upgraded all users to Skype for Business Server, you might want all users to have the same client experience until all are upgraded to the new server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2092c-112">Wenn Ihre Organisation sowohl Skype für Business Server und Lync Server bereitgestellt wurde, wird der Default Clientbenutzeroberfläche je nach Server-Versionen und Benutzeroberflächeneinstellungen davon abweichen.</span><span class="sxs-lookup"><span data-stu-id="2092c-112">If your organization has both Skype for Business Server and Lync Server deployed, the default client experience will differ depending on server versions and UI settings.</span></span> <span data-ttu-id="2092c-113">Wenn Benutzer Skype für Unternehmen zum ersten Mal starten, wird immer die Skype Business-Benutzeroberfläche – angezeigt, auch wenn Sie die Lync-Clientumgebung ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="2092c-113">When users launch Skype for Business for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience.</span></span> <span data-ttu-id="2092c-114">Nach einigen Minuten werden Benutzer aufgefordert werden, auf den Lync-Modus wechseln.</span><span class="sxs-lookup"><span data-stu-id="2092c-114">After several minutes, users are asked to switch to Lync mode.</span></span> <span data-ttu-id="2092c-115">Weitere Informationen entnehmen Sie dem **Abschnitt zum Clientverhalten beim ersten Start**.</span><span class="sxs-lookup"><span data-stu-id="2092c-115">For more information, see **First launch client behavior** later in this topic.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2092c-116">Die Lync 2013-Clientumgebung ist keine Option für Skype für Business 2016 Clientversionen oder höher.</span><span class="sxs-lookup"><span data-stu-id="2092c-116">The Lync 2013 client experience is not an option for Skype for Business 2016 client versions or later.</span></span> <span data-ttu-id="2092c-117">Bevor Sie versuchen, die Clientumgebung um die Verwendung des Lync 2013-Clients konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass es nicht mit der Nummer 16 gestartet wird; Beispiel: 16.x.x.x.</span><span class="sxs-lookup"><span data-stu-id="2092c-117">Before you attempt to configure your client environment to use the Lync 2013 client, please check the client version to ensure it does not start with the number 16; for example: 16.x.x.x.</span></span> 
  
## <a name="configure-the-client-experience"></a><span data-ttu-id="2092c-118">Konfigurieren der Client-Erfahrung</span><span class="sxs-lookup"><span data-stu-id="2092c-118">Configure the client experience</span></span>

<span data-ttu-id="2092c-119">Sie können die Client-Erfahrung Ihres Unternehmens, die den Benutzern angezeigt wird, angeben, indem Sie das Cmdlet **Set-CSClientPolicy** mit dem Parameter EnableSkypeUI verwenden:</span><span class="sxs-lookup"><span data-stu-id="2092c-119">You can specify the client experience the users in your organization will see by using the **Set-CSClientPolicy** cmdlet with the EnableSkypeUI parameter:</span></span>
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

<span data-ttu-id="2092c-120">wobei sich XdsIdentity auf die globale Richtlinie oder eine benannte Standortrichtlinie bezieht.</span><span class="sxs-lookup"><span data-stu-id="2092c-120">where XdsIdentity refers to the Global policy or a named site policy.</span></span>
  
<span data-ttu-id="2092c-121">Der folgende Befehl werden die Skype Business Client wünschen für alle Benutzer in Ihrer Organisation, die von der globalen Richtlinie betroffenen markiert (Denken Sie daran, Standort oder Benutzer-spezifische Richtlinien außer Kraft setzen die globale Richtlinie):</span><span class="sxs-lookup"><span data-stu-id="2092c-121">The following command selects the Skype for Business client experience for all users in your organization affected by the Global policy (remember, site or user-specific policies override the Global policy):</span></span> 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

<span data-ttu-id="2092c-122">Der nächste Befehl wählt die Lync-Client-Erfahrung für alle Benutzer in Ihrer Organisation, die von der globalen Richtlinie betroffen:</span><span class="sxs-lookup"><span data-stu-id="2092c-122">The next command selects the Lync client experience for all users in your organization affected by the Global policy:</span></span>
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

<span data-ttu-id="2092c-123">Der nächste Befehl wählt die Skype Business Client wünschen für alle Benutzer in den Standort Redmond:</span><span class="sxs-lookup"><span data-stu-id="2092c-123">The next command selects the Skype for Business client experience for all users within the Redmond site:</span></span>
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

<span data-ttu-id="2092c-124">Wenn Sie die Clientumgebung für bestimmte Benutzer innerhalb Ihrer Organisation konfigurieren möchten, können Sie eine neue Richtlinie erstellen, mit dem Cmdlet **New-CsClientPolicy** und weisen Sie die Richtlinie auf bestimmte Benutzer mithilfe der **Grant-CsClientPolicy** Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2092c-124">If you want to configure the client experience for specific users within your organization, you can create a new user policy by using the **New-CsClientPolicy** cmdlet, and then assign the policy to specific users by using the **Grant-CsClientPolicy** cmdlet.</span></span>
  
<span data-ttu-id="2092c-125">Der folgende Befehl wird beispielsweise erstellt eine neue Clientrichtlinie SalesClientUI, die die Skype Business Client wünschen auswählt:</span><span class="sxs-lookup"><span data-stu-id="2092c-125">For example, the following command creates a new client policy, SalesClientUI, that selects the Skype for Business client experience:</span></span>
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

<span data-ttu-id="2092c-126">Der nächste Befehl weist die Richtlinie „SalesClientUI“ allen Mitgliedern der Verkaufsabteilung zu:</span><span class="sxs-lookup"><span data-stu-id="2092c-126">The next command assigns the policy, SalesClientUI, to all members of the Sales department:</span></span>
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a><span data-ttu-id="2092c-127">Verhalten beim ersten Start des Clients</span><span class="sxs-lookup"><span data-stu-id="2092c-127">First launch client behaviors</span></span>

<span data-ttu-id="2092c-128">In der Standardeinstellung Wenn Benutzer Skype für Business 2015 zum ersten Mal starten sehen immer die Skype Business-Benutzeroberfläche – sie, auch wenn Sie die Lync-Clientumgebung ausgewählt haben, durch den Wert des Parameters EnableSkypeUI auf $False festlegen, wie beschrieben zuvor.</span><span class="sxs-lookup"><span data-stu-id="2092c-128">By default, when users launch Skype for Business 2015 for the first time, they will always see the Skype for Business user interface--even if you have selected the Lync client experience by setting the value of the EnableSkypeUI parameter to $False as described previously.</span></span> <span data-ttu-id="2092c-129">Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="2092c-129">After several minutes, users will then be asked to switch to Lync mode.</span></span>
  
<span data-ttu-id="2092c-130">Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:</span><span class="sxs-lookup"><span data-stu-id="2092c-130">If you want to display the Lync user interface when users launch the Skype for Business client for the first time, follow these steps before the client is started for the first time after being updated:</span></span>
  
1. <span data-ttu-id="2092c-131">Überprüfen Sie, ob der Wert der `EnableSkypeUI` ist auf $False in der Richtlinie, die Sie verwenden, wie oben beschrieben festlegen.</span><span class="sxs-lookup"><span data-stu-id="2092c-131">Confirm that the value of  `EnableSkypeUI` is set to $False in the policy you are using as described previously.</span></span>
    
2. <span data-ttu-id="2092c-p106">Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="2092c-p106">Update the system registry on the user's computer. You should do this before the first time users launch the Skype for Business client, and you should do this only once. For information about how to create a Group Policy Object to update the registry on a domain joined computer, see the section later in the topic.</span></span>
    
    <span data-ttu-id="2092c-135">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** einen neuen **Binärwert**.</span><span class="sxs-lookup"><span data-stu-id="2092c-135">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key, create a new **Binary** value.</span></span>
    
    <span data-ttu-id="2092c-136">Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="2092c-136">The **Value name** must be **EnableSkypeUI**, and the **Value data** must be set to **00 00 00 00**.</span></span>
    
    <span data-ttu-id="2092c-137">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2092c-137">The key should look like the following:</span></span>
    
 <pre>
[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
"CanSharePptInCollab"=dword:00000001
"CanShareOneNoteInCollab"=dword:00000001
"CanAppShareInCollab"=dword:00000001
"EnableSkypeUI"=hex:00,00,00,00
</pre>

<span data-ttu-id="2092c-138">Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.</span><span class="sxs-lookup"><span data-stu-id="2092c-138">The Lync user interface will now be displayed when users launch the Skype for Business client for the first time.</span></span>
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a><span data-ttu-id="2092c-139">Steuern der Anzeige des Lernprogramms auf der Willkommensseite</span><span class="sxs-lookup"><span data-stu-id="2092c-139">Control the display of the Welcome screen tutorial</span></span>

<span data-ttu-id="2092c-140">Wenn Benutzer die Skype für Business-Client öffnen, ist das Standardverhalten Willkommen angezeigt, die *meisten Benutzer des Clientcomputers fordern 7 Tipps*enthält.</span><span class="sxs-lookup"><span data-stu-id="2092c-140">When users open the Skype for Business client, the default behavior is to display a Welcome screen that includes  *7 Quick tips most people ask for*.</span></span> <span data-ttu-id="2092c-141">Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2092c-141">You can turn off the display of the Welcome screen but still allow users to access the tutorial by adding the following Registry value on the client computer:</span></span>
  
<span data-ttu-id="2092c-p108">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2092c-p108">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **IsBasicTutorialSeenByUser**, and the **Value data** must be set to **1**.</span></span>
  
<span data-ttu-id="2092c-144">Der Schlüssel sollte wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="2092c-144">The key should look like the following:</span></span>
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a><span data-ttu-id="2092c-145">Ausschalten des Client-Lernprogramms</span><span class="sxs-lookup"><span data-stu-id="2092c-145">Turn off the client tutorial</span></span>

<span data-ttu-id="2092c-146">Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:</span><span class="sxs-lookup"><span data-stu-id="2092c-146">If you do not want your users to be able to access the tutorial, you can turn off the client tutorial with the following Registry value:</span></span>
  
<span data-ttu-id="2092c-p109">Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2092c-p109">In the **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** key, create a new **DWORD (32-bit) Value**. The **Value name** must be **TutorialFeatureEnabled**, and the **Value data** must be set to **0**.</span></span>
  
<span data-ttu-id="2092c-149">Lync</span><span class="sxs-lookup"><span data-stu-id="2092c-149">Lync</span></span>
  
```
"TutorialFeatureEnabled"=dword:00000000
```

<span data-ttu-id="2092c-150">Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.</span><span class="sxs-lookup"><span data-stu-id="2092c-150">You can turn the tutorial back on by setting the **Value data** to **1**.</span></span>
  
## <a name="default-client-behaviors"></a><span data-ttu-id="2092c-151">Standardmäßiges Client-Verhalten</span><span class="sxs-lookup"><span data-stu-id="2092c-151">Default client behaviors</span></span>

<span data-ttu-id="2092c-152">Wenn Ihre Organisation sowohl Skype für Business Server und Lync Server bereitgestellt wurde, wird die Clientumgebung je nach Server-Versionen und die Skype UI Einstellung davon abweichen.</span><span class="sxs-lookup"><span data-stu-id="2092c-152">If your organization has both Skype for Business Server and Lync Server deployed, the client experience will differ depending on server versions and the Skype UI setting.</span></span> <span data-ttu-id="2092c-153">Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Benutzeroberflächeneinstellung:</span><span class="sxs-lookup"><span data-stu-id="2092c-153">The following table shows the initial client experience based on server version and the UI setting:</span></span>
  

|<span data-ttu-id="2092c-154">**Serverversion**</span><span class="sxs-lookup"><span data-stu-id="2092c-154">**Server version**</span></span>|<span data-ttu-id="2092c-155">**EnableSkypeUI-Einstellung**</span><span class="sxs-lookup"><span data-stu-id="2092c-155">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="2092c-156">**Clientumgebung**</span><span class="sxs-lookup"><span data-stu-id="2092c-156">**Client experience**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2092c-157">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2092c-157">Skype for Business Server</span></span> |<span data-ttu-id="2092c-158">Standard</span><span class="sxs-lookup"><span data-stu-id="2092c-158">Default</span></span>  <br/> |<span data-ttu-id="2092c-159">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2092c-159">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2092c-160">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2092c-160">Skype for Business Server</span></span>  |<span data-ttu-id="2092c-161">True</span><span class="sxs-lookup"><span data-stu-id="2092c-161">True</span></span>  <br/> |<span data-ttu-id="2092c-162">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2092c-162">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2092c-163">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2092c-163">Skype for Business Server</span></span>  |<span data-ttu-id="2092c-164">False</span><span class="sxs-lookup"><span data-stu-id="2092c-164">False</span></span>  <br/> |<span data-ttu-id="2092c-165">Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="2092c-165">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2092c-166">Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-166">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2092c-167">Standard</span><span class="sxs-lookup"><span data-stu-id="2092c-167">Default</span></span>  <br/> |<span data-ttu-id="2092c-168">Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="2092c-168">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2092c-169">Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-169">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2092c-170">True</span><span class="sxs-lookup"><span data-stu-id="2092c-170">True</span></span>  <br/> |<span data-ttu-id="2092c-171">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2092c-171">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2092c-172">Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-172">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2092c-173">False</span><span class="sxs-lookup"><span data-stu-id="2092c-173">False</span></span>  <br/> |<span data-ttu-id="2092c-174">Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)</span><span class="sxs-lookup"><span data-stu-id="2092c-174">User asked to switch to Lync mode (user can switch to Skype for Business later if you change the UI setting to $true)</span></span>  <br/> |
|<span data-ttu-id="2092c-175">Lync Server 2010 oder Lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-175">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="2092c-176">Standard</span><span class="sxs-lookup"><span data-stu-id="2092c-176">Default</span></span>  <br/> |<span data-ttu-id="2092c-177">Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann keine wechseln Sie zu Skype für Unternehmen weiter unten)</span><span class="sxs-lookup"><span data-stu-id="2092c-177">User asked to switch to Lync mode (user cannot switch to Skype for Business later)</span></span>  <br/> |
   
<span data-ttu-id="2092c-178">Die folgende Tabelle zeigt die Clientumgebung, wenn der Administrator die ursprüngliche Einstellung für die Erfahrung Skype UI ändert:</span><span class="sxs-lookup"><span data-stu-id="2092c-178">The next table shows the client experience when the administrator changes the initial setting for the Skype UI experience:</span></span>
  

|<span data-ttu-id="2092c-179">**Serverversion**</span><span class="sxs-lookup"><span data-stu-id="2092c-179">**Server version**</span></span>|<span data-ttu-id="2092c-180">**EnableSkypeUI-Einstellung**</span><span class="sxs-lookup"><span data-stu-id="2092c-180">**EnableSkypeUI setting**</span></span>|<span data-ttu-id="2092c-181">**Client-Benutzeroberfläche = Lync**</span><span class="sxs-lookup"><span data-stu-id="2092c-181">**Client UI = Lync**</span></span>|<span data-ttu-id="2092c-182">**Client-Benutzeroberfläche = Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="2092c-182">**Client UI = Skype for Business**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2092c-183">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2092c-183">Skype for Business Server</span></span> |<span data-ttu-id="2092c-184">True</span><span class="sxs-lookup"><span data-stu-id="2092c-184">True</span></span>  <br/> |<span data-ttu-id="2092c-185">Benutzer aufgefordert werden, wechseln Sie zu Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2092c-185">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="2092c-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2092c-186">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2092c-187">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2092c-187">Skype for Business Server</span></span> |<span data-ttu-id="2092c-188">False</span><span class="sxs-lookup"><span data-stu-id="2092c-188">False</span></span>  <br/> |<span data-ttu-id="2092c-189">Lync-Modus</span><span class="sxs-lookup"><span data-stu-id="2092c-189">Lync mode</span></span>  <br/> |<span data-ttu-id="2092c-190">Benutzer aufgefordert werden, auf den Lync-Modus wechseln</span><span class="sxs-lookup"><span data-stu-id="2092c-190">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="2092c-191">Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-191">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2092c-192">True</span><span class="sxs-lookup"><span data-stu-id="2092c-192">True</span></span>  <br/> |<span data-ttu-id="2092c-193">Benutzer aufgefordert werden, wechseln Sie zu Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2092c-193">User asked to switch to Skype for Business</span></span>  <br/> |<span data-ttu-id="2092c-194">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2092c-194">Skype for Business</span></span>  <br/> |
|<span data-ttu-id="2092c-195">Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-195">Lync Server 2010 or Lync Server 2013 (with correct patches)</span></span>  <br/> |<span data-ttu-id="2092c-196">False</span><span class="sxs-lookup"><span data-stu-id="2092c-196">False</span></span>  <br/> |<span data-ttu-id="2092c-197">Lync-Modus</span><span class="sxs-lookup"><span data-stu-id="2092c-197">Lync mode</span></span>  <br/> |<span data-ttu-id="2092c-198">Benutzer aufgefordert werden, auf den Lync-Modus wechseln</span><span class="sxs-lookup"><span data-stu-id="2092c-198">User asked to switch to Lync mode</span></span>  <br/> |
|<span data-ttu-id="2092c-199">Lync Server 2010 oder Lync Server 2013 (ohne Patches)</span><span class="sxs-lookup"><span data-stu-id="2092c-199">Lync Server 2010 or Lync Server 2013 (without patches)</span></span>  <br/> |<span data-ttu-id="2092c-200">Standard</span><span class="sxs-lookup"><span data-stu-id="2092c-200">Default</span></span>  <br/> |<span data-ttu-id="2092c-201">Lync-Modus (kann nicht wechseln zu Skype für Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="2092c-201">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |<span data-ttu-id="2092c-202">Lync-Modus (kann nicht wechseln zu Skype für Unternehmen)</span><span class="sxs-lookup"><span data-stu-id="2092c-202">Lync mode (cannot switch to Skype for Business)</span></span>  <br/> |
   
<span data-ttu-id="2092c-203">Die Patch-Versionen erforderlich, um die Konfiguration der Skype für Business Client verwalten sind:</span><span class="sxs-lookup"><span data-stu-id="2092c-203">The patch versions required to manage the configuration of the Skype for Business client are:</span></span>
  
- <span data-ttu-id="2092c-204">Lync Server 2010 – Februar 2015 Kumulatives Update (4.0.7577.710) für Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2092c-204">Lync Server 2010 - February 2015 Cumulative Update (4.0.7577.710) for Lync Server 2010.</span></span> <span data-ttu-id="2092c-205">Informationen finden Sie unter [Updates für Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span><span class="sxs-lookup"><span data-stu-id="2092c-205">For information, see [Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)</span></span>
    
- <span data-ttu-id="2092c-206">Lync Server 2013 – Dezember 2014 Kumulatives Update (5.0.8308.857) für Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2092c-206">Lync Server 2013 - December 2014 Cumulative Update (5.0.8308.857) for Lync Server 2013.</span></span> <span data-ttu-id="2092c-207">Informationen finden Sie unter [Updates für Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span><span class="sxs-lookup"><span data-stu-id="2092c-207">For information, see [Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).</span></span>
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a><span data-ttu-id="2092c-208">Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne</span><span class="sxs-lookup"><span data-stu-id="2092c-208">Create a Group Policy Object to modify the registry on a domain joined computer</span></span>

<span data-ttu-id="2092c-209">Das Update der Registrierung die Lync-Client-Erfahrung beim ersten anzeigen ein Benutzer die Skype für Business 2015 Client startet sollte nur einmal ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2092c-209">The registry update to display the Lync client experience the first time a user launches the Skype for Business 2015 client should be done only once.</span></span> <span data-ttu-id="2092c-210">Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="2092c-210">If you use a Group Policy Object (GPO) to update the registry, you need to define the object to create a new value rather than update the Value data.</span></span> <span data-ttu-id="2092c-211">Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.</span><span class="sxs-lookup"><span data-stu-id="2092c-211">When the GPO is applied, if the new value does not exist, the GPO will create it and set the Value data to 0.</span></span> 
  
<span data-ttu-id="2092c-212">Das folgende Verfahren beschreibt, wie Sie die Registrierung ändern, damit die Lync-Client-Erfahrung beim ersten angezeigt wird, die ein Benutzer die Skype für Business 2015-Client startet.</span><span class="sxs-lookup"><span data-stu-id="2092c-212">The following procedure describes how to modify the registry so that the Lync client experience is displayed the first time a user launches the Skype for Business 2015 client.</span></span> <span data-ttu-id="2092c-213">Mit diesem Verfahren können Sie auch die Registrierung aktualisieren, um das Lernprogramm der Willkommenseite zu deaktivieren (wie weiter oben beschrieben).</span><span class="sxs-lookup"><span data-stu-id="2092c-213">You can also use this procedure to update the registry to disable the Welcome screen tutorial as described earlier.</span></span>
  
### <a name="to-create-the-gpo"></a><span data-ttu-id="2092c-214">So erstellen Sie das Gruppenrichtlinienobjekt</span><span class="sxs-lookup"><span data-stu-id="2092c-214">To create the GPO</span></span>

1. <span data-ttu-id="2092c-215">Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.</span><span class="sxs-lookup"><span data-stu-id="2092c-215">Start the **Group Policy Management console**.</span></span>
    
    <span data-ttu-id="2092c-216">Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?LinkId=532759).</span><span class="sxs-lookup"><span data-stu-id="2092c-216">For information about how to use the Group Policy Management Console, see [Group Policy Management Console](https://go.microsoft.com/fwlink/?LinkId=532759).</span></span>
    
2. <span data-ttu-id="2092c-217">Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** und wählen Sie im Menü **Neu** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-217">Right-click the **Group Policy Objects** node and select **New** on the menu.</span></span>
    
3. <span data-ttu-id="2092c-218">Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das Gruppenrichtlinienobjekt (z. B.MakeLyncDefaultUI) ein und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2092c-218">In the **New GPO** dialog, enter a name for the GPO, for example,MakeLyncDefaultUI, and then click **OK**.</span></span>
    
4. <span data-ttu-id="2092c-219">Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt und wählen Sie dann im Menü **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-219">Right-click on the new GPO you just created and then select **Edit** from the menu.</span></span>
    
5. <span data-ttu-id="2092c-220">Im **Gruppenrichtlinienverwaltungs-Editor** erweitern Sie **Benutzerkonfiguration**, dann **Einstellungen** und dann **Windows-Einstellungen** und wählen Sie anschließend den Knoten **Registrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-220">In the **Group Policy Management Editor**, expand **User Configuration**, expand **Preferences**, expand **Windows Settings**, and then select the **Registry** node.</span></span>
    
6. <span data-ttu-id="2092c-221">Klicken Sie mit der rechten Maustaste auf den Knoten **Registrierung** und wählen Sie dann **Neu** > **Registrierungselement** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-221">Right-click on the **Registry** node, and then select **New** > **Registry Item**.</span></span>
    
7. <span data-ttu-id="2092c-222">Aktualisieren Sie im Dialogfeld **Neue Registrierungseigenschaften** die folgenden Angaben:</span><span class="sxs-lookup"><span data-stu-id="2092c-222">On the **New Registry Properties** dialog, update the following:</span></span>
    
   |<span data-ttu-id="2092c-223">**Feld**</span><span class="sxs-lookup"><span data-stu-id="2092c-223">**Field**</span></span>|<span data-ttu-id="2092c-224">**Auszuwählender oder einzugebender Wert**</span><span class="sxs-lookup"><span data-stu-id="2092c-224">**Value to select or enter**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="2092c-225">**Aktion**</span><span class="sxs-lookup"><span data-stu-id="2092c-225">**Action**</span></span> <br/> |<span data-ttu-id="2092c-226">**Erstellen**</span><span class="sxs-lookup"><span data-stu-id="2092c-226">**Create**</span></span> <br/> |
   |<span data-ttu-id="2092c-227">**Struktur**</span><span class="sxs-lookup"><span data-stu-id="2092c-227">**Hive**</span></span> <br/> | <span data-ttu-id="2092c-228">HKEY_CURRENT_USER</span><span class="sxs-lookup"><span data-stu-id="2092c-228">HKEY_CURRENT_USER</span></span> <br/> |
   |<span data-ttu-id="2092c-229">**Schlüsselpfad**</span><span class="sxs-lookup"><span data-stu-id="2092c-229">**Key Path**</span></span> <br/> |<span data-ttu-id="2092c-230">Software\Microsoft\Office\Lync</span><span class="sxs-lookup"><span data-stu-id="2092c-230">Software\Microsoft\Office\Lync</span></span>  <br/> |
   |<span data-ttu-id="2092c-231">**Wertname**</span><span class="sxs-lookup"><span data-stu-id="2092c-231">**Value name**</span></span> <br/> |<span data-ttu-id="2092c-232">EnableSkypeUI</span><span class="sxs-lookup"><span data-stu-id="2092c-232">EnableSkypeUI</span></span>  <br/> |
   |<span data-ttu-id="2092c-233">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="2092c-233">**Value type**</span></span> <br/> |<span data-ttu-id="2092c-234">REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="2092c-234">REG_BINARY</span></span>  <br/> |
   |<span data-ttu-id="2092c-235">**Wertdaten**</span><span class="sxs-lookup"><span data-stu-id="2092c-235">**Value data**</span></span> <br/> |<span data-ttu-id="2092c-236">00000000</span><span class="sxs-lookup"><span data-stu-id="2092c-236">00000000</span></span>  <br/> |
   
8. <span data-ttu-id="2092c-237">Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.</span><span class="sxs-lookup"><span data-stu-id="2092c-237">Click **OK** to save your changes, and then close the GPO.</span></span>
    
<span data-ttu-id="2092c-238">Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="2092c-238">Next, you'll need to link the GPO you created to the group of users that you want to assign the policy to, such as an OU.</span></span>
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a><span data-ttu-id="2092c-239">So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="2092c-239">To use the GPO to assign the policy</span></span>

1. <span data-ttu-id="2092c-240">Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-240">In the Group Policy Management Console, right-click on the OU you want to assign the policy to, and then select **Link to an existing GPO**.</span></span>
    
2. <span data-ttu-id="2092c-241">Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2092c-241">On the **Select GPO** dialog, select the GPO you created, and then select **OK**.</span></span>
    
3. <span data-ttu-id="2092c-242">Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2092c-242">On the target user's computer, open a command prompt and type the following command:</span></span>
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. <span data-ttu-id="2092c-243">Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="2092c-243">At the command prompt, type the following command:</span></span>
    
    <span data-ttu-id="2092c-244">**gpresult /r**</span><span class="sxs-lookup"><span data-stu-id="2092c-244">**gpresult /r**</span></span>
    
    <span data-ttu-id="2092c-245">Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte“ mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2092c-245">You should see "Assigned Group Policy Objects" with the name of the GPO you created displayed below.</span></span>
    
<span data-ttu-id="2092c-p115">Sie können auch überprüfen, ob das Gruppenrichtlinienobjekt die Registrierung auf dem Computer eines Benutzers ordnungsgemäß aktualisiert hat, indem Sie die Registrierung untersuchen. Öffnen Sie den Registrierungs-Editor und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Wenn das Gruppenrichtlinienobjekt die Registrierung aktualisiert hat, wird der Wert „EnableSkypeUI“ mit dem Wert „0“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2092c-p115">You can also verify that the GPO has successfully updated the registry on a user's computer by examining the registry. Open Registry Editor and navigate to the **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** key. If the GPO successfully updated the registry you will see a value named EnableSkypeUI with a value of 0.</span></span>
  

