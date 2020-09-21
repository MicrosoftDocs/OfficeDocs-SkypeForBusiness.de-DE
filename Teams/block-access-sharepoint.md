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
description: Informationen zum Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135929"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a><span data-ttu-id="d80b2-103">Blockieren des Zugriffs auf SharePoint für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="d80b2-103">Block access to SharePoint for specific users</span></span>

<span data-ttu-id="d80b2-104">Das Anwenden einer beliebigen Richtlinie für den bedingten Zugriff auf SharePoint in Microsoft 365 wird auch für Teams übernommen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-104">Applying any Conditional Access (CA) policy on SharePoint in Microsoft 365 is also applied to Teams.</span></span> <span data-ttu-id="d80b2-105">Einige Organisationen möchten jedoch den Zugriff auf SharePoint-Dateien blockieren (hochladen, herunterladen, anzeigen, bearbeiten, erstellen), aber ihren Mitarbeitern die Verwendung von Desktop-, Mobil-und Webclients von Teams auf nicht verwalteten Geräten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-105">However, some organizations want to block access to SharePoint files (upload, download, view, edit, create) yet allow their employees to use Teams desktop, mobile, and web clients on unmanaged devices.</span></span> <span data-ttu-id="d80b2-106">Unter den Richtlinien für die Zertifizierungsstelle würde das Blockieren von SharePoint auch dazu führen, dass Teams blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="d80b2-106">Under the CA policy rules, blocking Sharepoint would lead to blocking Teams as well.</span></span> <span data-ttu-id="d80b2-107">In diesem Artikel wird erläutert, wie Sie diese Einschränkung umgehen und ihren Mitarbeitern ermöglichen, weiterhin Teams zu verwenden, während der Zugriff auf in SharePoint gespeicherte Dateien vollständig blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="d80b2-107">This article explains how you can work around this limitation and allow your employees to continue using Teams while completely blocking access to files stored in SharePoint.</span></span>

> [!Note]
> <span data-ttu-id="d80b2-108">Das Blockieren oder Einschränken des Zugriffs auf nicht verwalteten Geräten basiert auf Azure AD-bedingten Zugriffsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="d80b2-108">Blocking or limiting access on unmanaged devices relies on Azure AD conditional access policies.</span></span> <span data-ttu-id="d80b2-109">Informationen zur [Azure AD-Lizenzierung](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="d80b2-109">Learn about [Azure AD licensing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span> <span data-ttu-id="d80b2-110">Eine Übersicht über den bedingten Zugriff in Azure AD finden Sie unter [bedingter Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span><span class="sxs-lookup"><span data-stu-id="d80b2-110">For an overview of conditional access in Azure AD, see [Conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview).</span></span> <span data-ttu-id="d80b2-111">Informationen zu empfohlenen SharePoint Online-Zugriffsrichtlinien finden Sie unter [Richtlinien Empfehlungen zum Sichern von SharePoint-Websites und-Dateien](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="d80b2-111">For info about recommended SharePoint Online access policies, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span> <span data-ttu-id="d80b2-112">Wenn Sie den Zugriff auf nicht verwalteten Geräten einschränken, müssen Benutzer auf verwalteten Geräten eine der [unterstützten Betriebssystem-und Browser Kombinationen](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition)verwenden, oder Sie haben auch eingeschränkten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="d80b2-112">If you limit access on unmanaged devices, users on managed devices must use one of the [supported OS and browser combinations](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), or they will also have limited access.</span></span>

<span data-ttu-id="d80b2-113">Sie können den Zugriff sperren oder einschränken für:</span><span class="sxs-lookup"><span data-stu-id="d80b2-113">You can block or limit access for:</span></span>

- <span data-ttu-id="d80b2-114">Benutzer in der Organisation oder nur einige Benutzer oder Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-114">Users in the organization or only some users or security groups.</span></span>

- <span data-ttu-id="d80b2-115">Alle Websites in der Organisation oder nur einige Websites.</span><span class="sxs-lookup"><span data-stu-id="d80b2-115">All sites in the organization or only some sites.</span></span>

<span data-ttu-id="d80b2-116">Wenn Access blockiert ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d80b2-116">When access is blocked, users will see an error message.</span></span> <span data-ttu-id="d80b2-117">Das Blockieren des Zugriffs hilft, Sicherheit zu gewährleisten und sichere Daten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-117">Blocking access helps provide security and protects secure data.</span></span> <span data-ttu-id="d80b2-118">Wenn Access blockiert ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d80b2-118">When access is blocked, users will see an error message.</span></span>

1. <span data-ttu-id="d80b2-119">Öffnen Sie das SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span><span class="sxs-lookup"><span data-stu-id="d80b2-119">Open the SharePoint [Admin Center](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true).</span></span>

2. <span data-ttu-id="d80b2-120">Erweitern Sie **Richtlinien**  >  **Zugriffsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="d80b2-120">Expand **Policies** > **Access Policies**.</span></span>

3. <span data-ttu-id="d80b2-121">Wählen Sie im Abschnitt **nicht verwaltete Geräte** die Option **Zugriff blockieren** aus, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d80b2-121">In the **Unmanaged Devices** section,  select **Block Access** and select **Save**.</span></span>

   ![Abschnitt "nicht verwaltete Geräte" für Richtlinien](media/no-sharepoint-access1.png)

4. <span data-ttu-id="d80b2-123">Öffnen Sie das [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) -Portal, und navigieren Sie zu den **Richtlinien für den bedingten Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="d80b2-123">Open the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) portal and navigate to **Conditional Access Policies**.</span></span>

    <span data-ttu-id="d80b2-124">Sie werden sehen, dass eine neue Richtlinie von SharePoint erstellt wurde, die mit diesem Beispiel vergleichbar ist:</span><span class="sxs-lookup"><span data-stu-id="d80b2-124">You'll see a new policy has been created by SharePoint that's similar to this example:</span></span>

    ![eine neue Richtlinie mit dem Namen use app-erzwungene Einschränkungen für den Browser Zugriff](media/no-sharepoint-access2.png)

5. <span data-ttu-id="d80b2-126">Aktualisieren Sie die Richtlinie so, dass nur bestimmte Benutzer oder eine Gruppe darauf ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="d80b2-126">Update the policy to target only specific users or a group.</span></span>

    ![das SharePoint Admin Center mit hervorgehobenem Abschnitt "Benutzer auswählen"](media/no-sharepoint-access2b.png)

  > [!Note]
> <span data-ttu-id="d80b2-128">Durch das Festlegen dieser Richtlinie wird der Zugriff auf das SharePoint-Verwaltungsportal reduziert.</span><span class="sxs-lookup"><span data-stu-id="d80b2-128">Setting this policy will cut your access to the SharePoint admin portal.</span></span> <span data-ttu-id="d80b2-129">Wir empfehlen, dass Sie die Ausschlussrichtlinie konfigurieren und die globalen und SharePoint-Administratoren auswählen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-129">We recommended that you configure the exclusion policy and select the Global and SharePoint admins.</span></span>

6. <span data-ttu-id="d80b2-130">Überprüfen, ob nur SharePoint als gezielte Cloud-App ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="d80b2-130">Verify that only SharePoint is selected as targeted Cloud App</span></span>

    ![SharePoint ist als Ziel-App ausgewählt.](media/no-sharepoint-access3.png)

7. <span data-ttu-id="d80b2-132">Aktualisieren Sie die **Bedingungen** auch, um Desktop Clients einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-132">Update **Conditions** to include desktop clients, as well.</span></span>

    ![Desktop-und Mobile Apps hervorgehoben.](media/no-sharepoint-access4.png)

8. <span data-ttu-id="d80b2-134">Sicherstellen, dass **Grant Access** aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="d80b2-134">Make sure that **Grant access** is enabled</span></span>

    ![Grant Access ist aktiviert.](media/no-sharepoint-access5.png)

9. <span data-ttu-id="d80b2-136">Stellen Sie sicher, dass die Anwendung **erzwungene Einschränkungen verwenden** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d80b2-136">Make sure **Use app enforced restrictions** is enabled.</span></span>

10. <span data-ttu-id="d80b2-137">Aktivieren Sie Ihre Richtlinie, und wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="d80b2-137">Enable your policy and select **Save**.</span></span>

    ![Die erzwungenen App-Einschränkungen sind aktiviert.](media/no-sharepoint-access6.png)

<span data-ttu-id="d80b2-139">Um Ihre Richtlinie zu testen, müssen Sie sich von jedem Client wie der Team-Desktop-App oder dem OneDrive for Business-synchronisierungsclient abmelden und sich erneut anmelden, um die Richtlinie zu sehen.</span><span class="sxs-lookup"><span data-stu-id="d80b2-139">To test your policy, you need to sign out from any client such as the Teams desktop app or the OneDrive for Business sync client and sign in again to see the policy working.</span></span> <span data-ttu-id="d80b2-140">Wenn Ihr Zugriff blockiert wurde, wird in Teams eine Meldung angezeigt, die besagt, dass das Element möglicherweise nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="d80b2-140">If your access has been blocked, you'll see a message in Teams that states the item might not exist.</span></span>

 ![Nachricht "Element nicht gefunden"](media/access-denied-sharepoint.png)

<span data-ttu-id="d80b2-142">In SharePoint erhalten Sie eine Nachricht vom Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="d80b2-142">In Sharepoint, you'll receive an access denied message.</span></span>

![Die Meldung "Zugriff verweigert".](media/blocked-access-warning.png)

## <a name="related-topics"></a><span data-ttu-id="d80b2-144">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d80b2-144">Related topics</span></span>

[<span data-ttu-id="d80b2-145">Steuern des Zugriffs auf nicht verwaltete Geräte in SharePoint</span><span class="sxs-lookup"><span data-stu-id="d80b2-145">Control access for unmanaged devices in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
