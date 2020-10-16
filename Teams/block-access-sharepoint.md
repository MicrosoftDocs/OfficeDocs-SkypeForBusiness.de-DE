---
title: Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie den Zugriff auf SharePoint für bestimmte Benutzer blockieren
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203838"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="191e6-103">Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="191e6-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="191e6-104">Eine Richtlinie für bedingten Zugriff (Conditional Access, AC) in SharePoint in Microsoft 365 wird auch auf Teams angewendet.</span><span class="sxs-lookup"><span data-stu-id="191e6-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="191e6-105">Einige Organisationen möchten jedoch den Zugriff auf SharePoint-Dateien (hochladen, herunterladen, anzeigen, bearbeiten, erstellen) blockieren, ihren Mitarbeitern allerdings dennoch den Zugriff auf Desktop-, Web- und mobile Clients in Teams erlauben.</span><span class="sxs-lookup"><span data-stu-id="191e6-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="191e6-106">Gemäß den CA-Richtlinien würde eine Blockierung von SharePoint auch zu einer Blockierung von Teams führen.</span><span class="sxs-lookup"><span data-stu-id="191e6-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="191e6-107">In diesem Artikel wird erklärt, wie Sie diese Beschränkung umgehen können, und es Ihren Mitarbeitern ermöglichen, weiterhin Teams zu nutzen, während der Zugriff auf in SharePoint gespeicherte Dateien komplett blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="191e6-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="191e6-108">Das Blockieren oder Einschränken des Zugriffs auf nicht verwalteten Geräte basiert auf den Azure AD-Richtlinien für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="191e6-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="191e6-109">Erfahren Sie mehr über die [Azure AD-Lizenzierung](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="191e6-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="191e6-110">Einen Überblick über den bedingten Zugriff in Azure AD erhalten Sie unter [Bedingter Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="191e6-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="191e6-111">Informationen zu empfohlenen Richtlinien für den SharePoint Online-Zugriff finden Sie unter [Richtlinienempfehlungen zur Sicherung von SharePoint-Websites und -Dateien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="191e6-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="191e6-112">Wenn Sie den Zugriff auf nicht verwalteten Geräten einschränken, müssen Benutzer mit verwalteten Geräten [unterstützte Betriebssysteme oder Browser-Kombinationen](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition) verwenden, oder ihr Zugriff wird eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="191e6-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="191e6-113">Sie können den Zugriff blockieren oder einschränken für:</span><span class="sxs-lookup"><span data-stu-id="191e6-113">You can block or limit access for:</span></span>

- <span data-ttu-id="191e6-114">Benutzer in der Organisation oder nur bestimmte Benutzer oder Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="191e6-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="191e6-115">Alle Websites in der Organisation oder nur bestimmte Websites.</span><span class="sxs-lookup"><span data-stu-id="191e6-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="191e6-116">Wenn der Zugriff blockiert wird, sehen die Benutzer eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="191e6-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="191e6-117">Das Blockieren des Zugriffs erhöht die Sicherheit und schützt sichere Daten.</span><span class="sxs-lookup"><span data-stu-id="191e6-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="191e6-118">Wenn der Zugriff blockiert wird, sehen die Benutzer eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="191e6-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="191e6-119">Öffnen Sie das SharePoint Admin Center.</span><span class="sxs-lookup"><span data-stu-id="191e6-119">Open the SharePoint Admin Center.</span></span>

2. <span data-ttu-id="191e6-120">Erweitern der **Richtlinien** > **Zugriffsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="191e6-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="191e6-121">Wählen Sie im Abschnitt **Nicht verwaltete Geräte\*\*\*\*Zugriff blockieren**, und wählen Sie dann **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="191e6-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![Abschnitt „Nicht verwaltete Geräte“ für Richtlinien](media/no-sharepoint-access1.png)

4. <span data-ttu-id="191e6-123">Öffnen Sie das Portal [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) und navigieren Sie zu **Richtlinien für den bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="191e6-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="191e6-124">In SharePoint wird eine neue Richtlinie erstellt, die ähnlich wie dieses Beispiel aussieht:</span><span class="sxs-lookup"><span data-stu-id="191e6-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![eine neue Richtlinie namens „Von der App erzwungene Einschränkungen für den Browser-Zugriff verwenden“](media/no-sharepoint-access2.png)

5. <span data-ttu-id="191e6-126">Aktualisieren Sie die Richtlinie, um nur bestimmte Benutzer oder eine Gruppe anzuvisieren.</span><span class="sxs-lookup"><span data-stu-id="191e6-126">Update the policy to target only specific users or a group.</span></span>

    ![das SharePoint Admin Center mit dem hervorgehobenen Abschnitt „Benutzer auswählen“.](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="191e6-128">Wenn Sie diese Richtlinie festlegen, wird Ihr Zugriff auf das SharePoint-Administratorportal eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="191e6-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="191e6-129">Wir empfehlen, dass Sie diese Ausschlussrichtlinie konfigurieren, und dann die globalen Administratoren und SharePoint-Administratoren auswählen.</span><span class="sxs-lookup"><span data-stu-id="191e6-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="191e6-130">Stellen Sie sicher, dass nur SharePoint als gezielte Cloud-App ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="191e6-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint ist als gezielte App ausgewählt.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="191e6-132">Aktualisieren Sie die **Bedingungen**, um auch Desktop-Clients einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="191e6-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![Desktop- und mobile Anwendungen hervorgehoben.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="191e6-134">Stellen Sie sicher, dass **Zugriff gewähren** aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="191e6-134">Make sure that **Grant access** is enabled</span></span>

    ![„Zugriff gewähren“ ist aktiviert.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="191e6-136">Stellen Sie sicher, dass **Von der App erzwungene Einschränkungen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="191e6-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="191e6-137">Aktivieren Sie Ihre Richtlinie und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="191e6-137">Enable your policy and select **Save**.</span></span>

    ![„Von der App erzwungene Einschränkungen“ ist aktiviert.](media/no-sharepoint-access6.png)

<span data-ttu-id="191e6-139">Um Ihre Richtlinie zu testen, müssen Sie sich von allen Clients wie der Teams-Desktop-App oder OneDrive for Business-Synchronisierungsclient abmelden und wieder anmelden, um zu sehen, ob die Richtlinie funktioniert.</span><span class="sxs-lookup"><span data-stu-id="191e6-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="191e6-140">Wenn Ihr Zugriff blockiert wurde, sehen Sie eine Nachricht in Teams, die angibt, dass das Element unter Umständen nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="191e6-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Die Nachricht „Element nicht gefunden“.](media/access-denied-sharepoint.png)

<span data-ttu-id="191e6-142">In SharePoint erhalten Sie die Fehlermeldung, dass der Zugriff verweigert wurde.</span><span class="sxs-lookup"><span data-stu-id="191e6-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Die Fehlermeldung „Zugriff verweigert“.](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="191e6-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="191e6-144">Related topics</span></span>

[<span data-ttu-id="191e6-145">Steuern des Zugriffs auf nicht verwaltete Geräten in SharePoint</span><span class="sxs-lookup"><span data-stu-id="191e6-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
