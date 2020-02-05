---
title: Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in ihrer hybridbereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie den Partnerverbund für einen Audiokonferenz-Anbieter in Skype for Business Online konfigurieren.'
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726885"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="e50e8-103">Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in ihrer hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="e50e8-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="e50e8-104">**Zusammenfassung:** Informationen zum Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="e50e8-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="e50e8-105">Wenn Sie einen Audiokonferenz-Anbieter (ACP) in ihrer hybridbereitstellung (lokal mit Online) verwenden möchten, müssen Sie den Verbund zwischen Ihrer lokalen Bereitstellung und dem ACP-Partner als zulässigen Partner Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e50e8-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="e50e8-106">Sie können den Verbund durch Hinzufügen der AKP-Partnerdomäne und des Edge-Servers (Dies kann auch als Zugriffs Proxy bezeichnet werden) zur Liste der Verbunddomänen für Ihre lokale Bereitstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e50e8-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="e50e8-107">Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="e50e8-108">Weitere Informationen erhalten Sie von Ihrem ACP-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e50e8-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="e50e8-109">Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e50e8-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="e50e8-110">**Hinzufügen der ACP-Domäne und Edgeserver als zugelassene Verbunddomäne**</span><span class="sxs-lookup"><span data-stu-id="e50e8-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="e50e8-111">Wenn Sie die ACP-Domäne als zulässigen Partner Server (zugelassene Verbunddomäne) hinzufügen möchten, führen Sie die Schritte unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)aus.</span><span class="sxs-lookup"><span data-stu-id="e50e8-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="e50e8-112">Fügen Sie für die Edgeserver den FQDN des Edgeserver des AKP-Partners hinzu.</span><span class="sxs-lookup"><span data-stu-id="e50e8-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="e50e8-113">Möglicherweise müssen Sie sich an ihren AKP-Partner wenden, um den FQDN für Ihre Edgeserver zu erhalten, die auch von Ihrem ACP als Zugriffs Proxy bezeichnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e50e8-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="e50e8-114">**Bereitstellen des FQDN des Edgeserver Pools für den AKP-Partner**</span><span class="sxs-lookup"><span data-stu-id="e50e8-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="e50e8-115">Der AKP-Partner muss den Verbund so konfigurieren, dass die lokale Domäne als zulässiger Partner Server hinzugefügt wird, indem der FQDN des Edgeserver Pools als zugelassene Verbunddomäne hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="e50e8-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


