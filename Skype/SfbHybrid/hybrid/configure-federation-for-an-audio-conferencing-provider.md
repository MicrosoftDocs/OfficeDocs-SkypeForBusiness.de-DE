---
title: Konfigurieren des Verbunds für einen Audiokonferenzanbieter in Ihrer Hybridbereitstellung
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie den Verbund für einen Audiokonferenzanbieter in Skype for Business Online konfigurieren.'
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118974"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Konfigurieren des Verbunds für einen Audiokonferenzanbieter in Ihrer Hybridbereitstellung

**Zusammenfassung:** Erfahren Sie, wie Sie den Verbund für einen Audiokonferenzanbieter in Skype for Business Online konfigurieren.

Wenn Sie einen Audiokonferenzanbieter (ACP) in Ihrer Hybridbereitstellung (lokal mit Online) verwenden möchten, müssen Sie den Partnerverbund zwischen Ihrer lokalen Bereitstellung und dem ACP-Partner als zulässiger Partnerserver konfigurieren. Sie können den Partnerverbund konfigurieren, indem Sie die ACP-Partnerdomäne und den Edgeserver (dies kann auch als Zugriffsproxy bezeichnet werden) zur Liste der Verbunddomänen für Ihre lokale Bereitstellung hinzufügen. Ihr ACP-Partner muss dann den FQDN Ihres lokalen Edgeserverpools zur Liste der zulässigen Verbunddomänen hinzufügen. Wenden Sie sich an Ihren ACP-Anbieter, um weitere Informationen zu erhalten. Ihr ACP-Partner muss dann den FQDN Ihres lokalen Edgeserverpools zur Liste der zulässigen Verbunddomänen hinzufügen.

- **Hinzufügen der ACP-Domäne und des Edgeservers als zulässige Verbunddomäne**

    Führen Sie die Schritte unter Configure Support for Allowed External Domains aus, um die ACP-Domäne als zulässigen Partnerserver (zulässige [Verbunddomäne) hinzuzufügen.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains) Fügen Sie für den Edgeserver den FQDN des Edgeservers des ACP-Partners hinzu. Möglicherweise müssen Sie sich an Ihren ACP-Partner wenden, um den FQDN für den Edgeserver zu erhalten, der auch von Ihrem ACP als Zugriffsproxy bezeichnet werden kann.

- **Bereitstellen des FQDN Ihres Edgeserverpools für den ACP-Partner**

    Der ACP-Partner muss den Partnerverbund so konfigurieren, dass Seine lokale Domäne als zulässiger Partnerserver hinzugefügt wird, indem der FQDN Ihres Edgeserverpools als zulässige Verbunddomäne hinzugefügt wird.