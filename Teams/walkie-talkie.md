---
title: Walkie Talkie-Anwendung in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: So konfigurieren Sie die Walkie Talkie-app in Microsoft Teams aus einer ITAdmin Perspektive.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9369cf56a32142d6527fcb86271d8d0fa56718ec
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043010"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="8716f-103">Walkie Talkie-app in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8716f-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="8716f-104">Die Walkie-Talkie-app in Microsoft Teams bietet eine direkte Push-to-Talk (PTT)-Kommunikation für Ihr Team und wird in Kürze in der öffentlichen Vorschau auf Android zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8716f-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and will soon be available in Public Preview on Android.</span></span> <span data-ttu-id="8716f-105">Walkie Talkie ermöglicht Benutzern die Verbindung mit Ihrem Team unter Verwendung der gleichen zugrunde liegenden Kanäle, in denen Sie Mitglied sind.</span><span class="sxs-lookup"><span data-stu-id="8716f-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="8716f-106">Nur Benutzer, die eine Verbindung mit Walkie Talkie in einem Kanal herstellen, werden Teilnehmer und können jeweils einzeln über Push-to-Talk miteinander kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8716f-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="8716f-107">Mit Walkie Talkie in Teams können First-Workers nun sicher mit einer vertrauten PTT-Erfahrung kommunizieren, ohne sperrige Radios tragen zu müssen, und Walkie Talkie funktioniert überall mit WiFi-oder Mobilfunk-Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="8716f-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="8716f-108">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="8716f-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="8716f-109">Bereitstellen von Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="8716f-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="8716f-110">Während der öffentlichen Vorschau ist Walkie Talkie nicht vorinstalliert.</span><span class="sxs-lookup"><span data-stu-id="8716f-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="8716f-111">Um dieses Feature für Benutzer in Ihrer Organisation zu aktivieren, müssen Sie Walkie Talkie der APP- [Setup Richtlinie](teams-app-setup-policies.md)hinzufügen, die   Benutzern aus dem [Team Admin Center](https://admin.teams.microsoft.com/)zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="8716f-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="8716f-112">Nach der Aktivierung wird Walkie Talkie innerhalb von 48 Stunden in der Android-App verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="8716f-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="8716f-113">Hinzufügen von Walkie Talkie zu Ihrer APP-Liste</span><span class="sxs-lookup"><span data-stu-id="8716f-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="8716f-114">Im Microsoft Teams Admin Center sollten Sie unter **Teams-App**  >  -**Setup Richtlinien**zulassen, dass **Benutzer anheften** auf **ein**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="8716f-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="8716f-115">Klicken Sie dann im Abschnitt angeheftete apps auf **+ apps hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8716f-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="Zeigt den Abschnitt angeheftete apps und die Schaltfläche apps hinzufügen zur Auswahl an.":::

<span data-ttu-id="8716f-117">Verwenden Sie im Fenster **angeheftete apps hinzufügen** , das auf der rechten Seite angezeigt wird, das Textfeld **Suchen** , um nach Walkie Talkie zu suchen.</span><span class="sxs-lookup"><span data-stu-id="8716f-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="8716f-118">Wenn Sie ein Suchergebnis haben, klicken Sie auf die Schaltfläche **Hinzufügen** rechts neben dem Namen, um es Ihrer Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8716f-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="Zeigt die Sidebar "angeheftete apps hinzufügen" mit Walkie, das in den Suchbereich eingegeben wurde, und die Walkie Talkie-app in den Suchergebnissen, wobei die Schaltfläche Hinzufügen daneben angezeigt wird.":::

<span data-ttu-id="8716f-120">Die Walkie Talkie-app sollte nun in der Liste der angehefteten apps angezeigt werden und für die Verwendung verfügbar sein, sobald Sie auf die Schaltfläche " **Speichern** " klicken.</span><span class="sxs-lookup"><span data-stu-id="8716f-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="Zeigt die Liste der angehefteten apps mit hinzugefügter Walkie Talkie-APP und die Schaltfläche Speichern unter der Liste an.":::

### <a name="network-documentation"></a><span data-ttu-id="8716f-122">Netzwerkdokumentation</span><span class="sxs-lookup"><span data-stu-id="8716f-122">Network documentation</span></span>

<span data-ttu-id="8716f-123">Walkie Talkie in Teams erfordert Internet-Konnektivität und unter den Netzwerkbedingungen sind für eine optimale Nutzung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8716f-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="8716f-124">Latenz (RTT) < 300m | Jitter < 30ms | Paketverlust < 1%</span><span class="sxs-lookup"><span data-stu-id="8716f-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="8716f-125">Wie bereits erwähnt, wird die Qualität der Echt Zeit Medien über ein IP-Netzwerk stark von der Qualität der Netzwerkkonnektivität beeinflusst, insbesondere aber von der folgenden Anzahl:</span><span class="sxs-lookup"><span data-stu-id="8716f-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="8716f-126">**Latenz** – Dies ist die Zeit, die zum Abrufen eines IP-Pakets von Punkt a zu Punkt B im Netzwerk erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8716f-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="8716f-127">Diese Verzögerung der Weitergabe im Netzwerk ist im Wesentlichen mit der physischen Entfernung zwischen den beiden Punkten und der Lichtgeschwindigkeit verknüpft. Dazu gehört auch der Mehraufwand durch die zwischen den Punkten vorhandenen Router.</span><span class="sxs-lookup"><span data-stu-id="8716f-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="8716f-128">Latenz wird als Roundtrip (Round-Trip Time, RTT) gemessen.</span><span class="sxs-lookup"><span data-stu-id="8716f-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="8716f-129">**Paketverlust** – Dies wird häufig als Prozentsatz der Pakete definiert, die in einem bestimmten Zeitfenster verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="8716f-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="8716f-130">Der Paketverlust wirkt sich direkt auf die Audioqualität aus – von kleinen, einzelnen verlorenen Paketen, die fast keine Auswirkungen haben, bis hin zu Burst Verlusten, die zu einem vollständigen Audioausschnitt führen.</span><span class="sxs-lookup"><span data-stu-id="8716f-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="8716f-131">**Jitter** – Dies ist die durchschnittliche Verzögerungs Änderung zwischen aufeinanderfolgenden Paketen.</span><span class="sxs-lookup"><span data-stu-id="8716f-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="8716f-132">Die erwartete Datennutzung von Walkie Talkie beläuft sich auf 20KB/s beim Senden oder empfangen von Audio.</span><span class="sxs-lookup"><span data-stu-id="8716f-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="8716f-133">Im Leerlauf ist die erwartete Datennutzung von Walkie Talkie vernachlässigbar.</span><span class="sxs-lookup"><span data-stu-id="8716f-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="8716f-134">Walkie-Talkie-Geräte</span><span class="sxs-lookup"><span data-stu-id="8716f-134">Walkie Talkie devices</span></span>

<span data-ttu-id="8716f-135">Mitarbeiter von First-work müssen oft Walkie-Talkie-Anrufe sprechen und empfangen, auch wenn Ihre Telefone gesperrt sind.</span><span class="sxs-lookup"><span data-stu-id="8716f-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="8716f-136">Diese Erfahrung ist durch spezielle Geräte mit einer speziellen PTT-Taste möglich.</span><span class="sxs-lookup"><span data-stu-id="8716f-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="8716f-137">Vorhandene Telefone</span><span class="sxs-lookup"><span data-stu-id="8716f-137">Existing phones</span></span>
  - <span data-ttu-id="8716f-138">Kabelgebundene Headsets ([klein Elektronik](https://www.kleinelectronics.com/))</span><span class="sxs-lookup"><span data-stu-id="8716f-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/))</span></span>
  - <span data-ttu-id="8716f-139">Drahtlose Headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span><span class="sxs-lookup"><span data-stu-id="8716f-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/))</span></span>
- <span data-ttu-id="8716f-140">Robuste Telefone</span><span class="sxs-lookup"><span data-stu-id="8716f-140">Rugged phones</span></span>
  - <span data-ttu-id="8716f-141">Samsung Galaxy XCover pro</span><span class="sxs-lookup"><span data-stu-id="8716f-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="8716f-142">[Weitere Informationen](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span><span class="sxs-lookup"><span data-stu-id="8716f-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="8716f-143">[Einrichtungsleitfaden](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span><span class="sxs-lookup"><span data-stu-id="8716f-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="8716f-144">Diese Geräte sind nicht zertifizierte Teams.</span><span class="sxs-lookup"><span data-stu-id="8716f-144">These devices are not Teams certified.</span></span> <span data-ttu-id="8716f-145">Sie wurden für die Zusammenarbeit mit Teams Walkie Talkie validiert.</span><span class="sxs-lookup"><span data-stu-id="8716f-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="8716f-146">Lizenzanforderungen</span><span class="sxs-lookup"><span data-stu-id="8716f-146">License requirements</span></span>

<span data-ttu-id="8716f-147">Walkie Talkie-APP ist in allen bezahlten Lizenzen von Teams in [Office 365-Abonnements](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)enthalten.</span><span class="sxs-lookup"><span data-stu-id="8716f-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="8716f-148">Weitere Informationen zum Abrufen von Teams finden Sie unter [wie erhalte ich Zugriff auf Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span><span class="sxs-lookup"><span data-stu-id="8716f-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="8716f-149">Bestimmte erweiterte Funktionen erfordern möglicherweise zusätzliche Lizenzierung.</span><span class="sxs-lookup"><span data-stu-id="8716f-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="8716f-150">Zum Beispiel erfordert die Integration in Samsung Galaxy XCover pro eine Knox-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="8716f-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="8716f-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8716f-151">Further information</span></span>

- <span data-ttu-id="8716f-152">ITAdmins kann die Kontrolle über die Nutzung von Walkie Talkie über APP-Richtlinien behalten.</span><span class="sxs-lookup"><span data-stu-id="8716f-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="8716f-153">Wenn Ihr erster Mitarbeiter Mobile Daten für die Kommunikation über Teams verwendet, verwendet Walkie Talkie dieselbe Methode.</span><span class="sxs-lookup"><span data-stu-id="8716f-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="8716f-154">Walkie Talkie sollte in Situationen mit niedriger Bandbreite oder in Situationen, in denen Ihr Smartphone angeschlossen ist und funktioniert, gut funktionieren.</span><span class="sxs-lookup"><span data-stu-id="8716f-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="8716f-155">Walkie Talkie funktioniert nicht, wenn überhaupt keine Konnektivität vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8716f-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="8716f-156">Weitere Informationen zur Benutzeroberfläche finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="8716f-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="8716f-157">Erste Schritte mit Teams Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="8716f-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="8716f-158">Kommunizieren mit Ihrem Team mit Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="8716f-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
