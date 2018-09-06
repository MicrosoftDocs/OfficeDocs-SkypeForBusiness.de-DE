---
title: Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in einer hybridbereitstellung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in Skype für Business Online.'
ms.openlocfilehash: 8be61bdfd3d6a8cadc8ab1cea436b133e5714fdf
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "23241447"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="62286-103">Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in einer hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="62286-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="62286-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="62286-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="62286-105">Wenn Sie ein Audio Conferencing Provider (ACP) in der hybridbereitstellung (lokal mit online) verwenden möchten, müssen Sie als eine zulässige Partnerserver Verbund zwischen der lokalen Bereitstellung und dem ACP Partner konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62286-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="62286-106">Sie können den Verbund durch Hinzufügen der Partnerdomäne ACP und Edge-Server (Dies kann auch der Zugriffsproxy bezeichnet werden) zur Liste Partnerdomänen konfigurieren, für die lokale Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="62286-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="62286-107">Ihr ACP Partner muss den FQDN des Pools lokalen Edge-Server ihrer Liste der zulässigen Partnerdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62286-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="62286-108">Weitere Informationen erhalten Sie bei Ihrem Anbieter ACP.</span><span class="sxs-lookup"><span data-stu-id="62286-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="62286-109">Ihr ACP Partner muss den FQDN des Pools lokalen Edge-Server ihrer Liste der zulässigen Partnerdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="62286-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="62286-110">**Hinzufügen der ACP-Domäne und des Edgeservers als zugelassene Partnerverbunddomäne**</span><span class="sxs-lookup"><span data-stu-id="62286-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="62286-111">Um die ACP-Domäne als eine zulässige Partnerserver (Partnerverbunddomänen zulässig) hinzuzufügen, führen Sie die Schritte in [Konfigurieren der Unterstützung für externe Domänen zulässig](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="62286-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="62286-112">Fügen Sie den FQDN des Edge-Server des ACP Partners für den Edge-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="62286-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="62286-113">Sie müssen sich möglicherweise an Ihren ACP-Partner wenden, um den FQDN für seinen Edgeserver zu erhalten, der von Ihrem ACP möglicherweise auch als Zugriffsproxy bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="62286-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="62286-114">**Bereitstellen des FQDN Ihres Edgeserverpools für den ACP-Partner**</span><span class="sxs-lookup"><span data-stu-id="62286-114">**Provide the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="62286-115">Der ACP-Partner muss einen Partnerverbund konfigurieren, um Ihre lokale Domäne als einen zulässigen Partnerserver hinzuzufügen, indem der FQDN Ihres Edgeserverpools als eine zugelassene Partnerverbunddomäne hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="62286-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


