---
title: Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in einer hybridbereitstellung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in Skype für Business Online.'
ms.openlocfilehash: 2f89045e7d2ee3e51a6526344d2dcf2f07c0d98d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030756"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="79b4e-103">Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in einer hybridbereitstellung</span><span class="sxs-lookup"><span data-stu-id="79b4e-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="79b4e-104">**Zusammenfassung:** Informationen Sie zum Konfigurieren von Verbund für einen Anbieter von Audiokonferenzen in Skype für Business Online.</span><span class="sxs-lookup"><span data-stu-id="79b4e-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="79b4e-105">Wenn Sie ein Audio Conferencing Provider (ACP) in der hybridbereitstellung (lokal mit online) verwenden möchten, müssen Sie als eine zulässige Partnerserver Verbund zwischen der lokalen Bereitstellung und dem ACP Partner konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="79b4e-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="79b4e-106">Sie können den Verbund durch Hinzufügen der Partnerdomäne ACP und Edge-Server (Dies kann auch der Zugriffsproxy bezeichnet werden) zur Liste Partnerdomänen konfigurieren, für die lokale Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="79b4e-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="79b4e-107">Ihr ACP Partner muss den FQDN des Pools lokalen Edge-Server ihrer Liste der zulässigen Partnerdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="79b4e-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="79b4e-108">Weitere Informationen erhalten Sie bei Ihrem Anbieter ACP.</span><span class="sxs-lookup"><span data-stu-id="79b4e-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="79b4e-109">Ihr ACP Partner muss den FQDN des Pools lokalen Edge-Server ihrer Liste der zulässigen Partnerdomänen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="79b4e-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="79b4e-110">**Hinzufügen der ACP-Domäne und des Edgeservers als zugelassene Partnerverbunddomäne**</span><span class="sxs-lookup"><span data-stu-id="79b4e-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="79b4e-111">Um die ACP-Domäne als eine zulässige Partnerserver (Partnerverbunddomänen zulässig) hinzuzufügen, führen Sie die Schritte in [Konfigurieren der Unterstützung für externe Domänen zulässig](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="79b4e-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="79b4e-112">Fügen Sie den FQDN des Edge-Server des ACP Partners für den Edge-Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="79b4e-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="79b4e-113">Sie müssen sich möglicherweise an Ihren ACP-Partner wenden, um den FQDN für seinen Edgeserver zu erhalten, der von Ihrem ACP möglicherweise auch als Zugriffsproxy bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="79b4e-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="79b4e-114">**Bereitstellen von den FQDN des Pools Ihrer Edge-Server für dem ACP partner**</span><span class="sxs-lookup"><span data-stu-id="79b4e-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="79b4e-115">Der ACP-Partner muss einen Partnerverbund konfigurieren, um Ihre lokale Domäne als einen zulässigen Partnerserver hinzuzufügen, indem der FQDN Ihres Edgeserverpools als eine zugelassene Partnerverbunddomäne hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="79b4e-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


