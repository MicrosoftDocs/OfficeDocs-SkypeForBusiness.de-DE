---
title: Einrichten Ihres Netzwerks für Skype-Livekonferenz
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: b29ec51ddcb672f6727f7bc43958872962245ebb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226162"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="77964-103">Einrichten Ihres Netzwerks für Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="77964-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="77964-p101">Nach der [Aktivieren von Skype-Livekonferenz](enable-skype-meeting-broadcast.md) Skype-Livekonferenz müssen Sie Ihr Netzwerk konfigurieren. Führen Sie diesen Schritt aus, wenn Sie Webinare und andere Konferenzen für Personen außerhalb Ihres Unternehmens durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="77964-p101">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network. Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="77964-106">Wenn Sie keine Erfahrungen mit der Konfiguration Ihrer Firewall haben, sollten Sie möglicherweise einen [Microsoft-Partner](https://go.microsoft.com/fwlink/?linkid=391089) für diese Aufgabe heranziehen.</span><span class="sxs-lookup"><span data-stu-id="77964-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="77964-107">Um diesen Schritt zu überspringen und stattdessen Ihrem Verbund ein anderes Unternehmen hinzuzufügen, das Sie zu Konferenzen einladen können, führen Sie die Schritte unter [Nutzern gestatten, externe Skype for Business-Nutzer zu kontaktieren](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md) aus.</span><span class="sxs-lookup"><span data-stu-id="77964-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="77964-108">Schritt 1: Einrichten von zulässigen Domänen</span><span class="sxs-lookup"><span data-stu-id="77964-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="77964-109">Verwenden Sie **eine** der folgenden Methoden, um zulässige Domänen einzurichten:</span><span class="sxs-lookup"><span data-stu-id="77964-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="77964-110">**Methode 1: Verwenden des Office 365 Admin Center**</span><span class="sxs-lookup"><span data-stu-id="77964-110">**Method 1: Use the Office 365 admin center**</span></span>

1. <span data-ttu-id="77964-111">Besuchen Sie das **Office 365 Administrationscenter** , und klicken Sie dann im linken Navigationsbereich, auf **Einstellungen** > **Services &amp; -add-ins**, und wählen Sie dann **Skype für Unternehmen**.</span><span class="sxs-lookup"><span data-stu-id="77964-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="77964-112">Klicken Sie auf der Seite **externe Freigabe** unter **Domäne Ausnahmen**wählen Sie **alle Domänen werden blockiert, es sei denn**, und geben Sie die folgenden Domänen, getrennt durch ein Komma (,):</span><span class="sxs-lookup"><span data-stu-id="77964-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="77964-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="77964-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="77964-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="77964-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="77964-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="77964-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="77964-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="77964-116">resources.lync.com</span></span>

3. <span data-ttu-id="77964-117">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77964-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="77964-118">**Methode 2: Verwenden von Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="77964-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="77964-119">Wählen Sie im **Startmenü**mit der rechten Maustaste in **Windows PowerShell** , und klicken Sie auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="77964-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="77964-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="77964-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="77964-121">Schritt 2: Hinzufügen von Skype Besprechung übertragen Domänen, URLs und IP-Adressen</span><span class="sxs-lookup"><span data-stu-id="77964-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="77964-122">Im zweiten Schritt des Setupvorgangs fügen Sie zuerst die benötigten Domänen hinzu. Anschließend fügen Sie die IP-Adressen und URLs hinzu, die erforderlich sind, damit Skype-Livekonferenz funktioniert.</span><span class="sxs-lookup"><span data-stu-id="77964-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="77964-123">**Hinzufügen der erforderlichen Skype für Business Online Endpunkt-URLs und IP-Adressen sehen, welche erforderlich sind** [hier](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span><span class="sxs-lookup"><span data-stu-id="77964-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="77964-124">Einrichten von Skype-Livekonferenz in Hybridbereitstellungen und -organisationen</span><span class="sxs-lookup"><span data-stu-id="77964-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="77964-125">Wenn Sie einen Skype für Business Online-Organisation und einer lokalen Bereitstellung von Lync Server 2010, Microsoft Lync Server 2013 und Skype für Business Server 2015 und haben Sie beide Benutzer online und lokalen, es sind weitere Schritte zur Setup aus, die Sie benötigen, führen Sie Zusätzlich zu den oben, um Ihre lokale Organisation mit Skype für Business Online kommunizieren und alle Benutzer zur Teilnahme an einer Besprechung übertragen Skype zulassen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="77964-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="77964-126">Die entsprechenden Anforderungen finden Sie unter [Konfigurieren der lokalen Bereitstellung von Skype-Livekonferenz](https://go.microsoft.com/fwlink/?LinkId=617070).</span><span class="sxs-lookup"><span data-stu-id="77964-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="77964-127">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="77964-127">Related topics</span></span>

[<span data-ttu-id="77964-128">Aktivieren von Skype-Livekonferenz</span><span class="sxs-lookup"><span data-stu-id="77964-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="77964-129">URLs und IP-Adressbereiche von Office 365</span><span class="sxs-lookup"><span data-stu-id="77964-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="77964-130">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="77964-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



