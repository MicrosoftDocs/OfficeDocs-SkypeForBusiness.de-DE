---
title: Konfigurieren eines Partnerverbunds für einen Audiokonferenzanbieter in Ihrer Hybridbereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 'Zusammenfassung: Erfahren Sie, wie Sie den Partnerverbund für einen Audiokonferenzanbieter in Skype for Business Online konfigurieren.'
ms.openlocfilehash: 25bd691186d5d37dc272b420e68bb71a7d181de1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597889"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Konfigurieren eines Partnerverbunds für einen Audiokonferenzanbieter in Ihrer Hybridbereitstellung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**Zusammenfassung:** Erfahren Sie, wie Sie den Partnerverbund für einen Audiokonferenzanbieter in Skype for Business Online konfigurieren.

Wenn Sie einen Audiokonferenzanbieter (ACP) in Ihrer Hybridbereitstellung (lokal mit Online) verwenden möchten, müssen Sie den Partnerverbund zwischen Ihrer lokalen Bereitstellung und dem ACP-Partner als zulässigen Partnerserver konfigurieren. Sie können den Partnerverbund konfigurieren, indem Sie die ACP-Partnerdomäne und den Edgeserver (dies kann auch als Zugriffsproxy bezeichnet werden) zur Liste der Partnerdomänen für Ihre lokale Bereitstellung hinzufügen. Ihr ACP-Partner muss dann den FQDN Ihres lokalen Edgeserverpools zur Liste der zulässigen Partnerdomänen hinzufügen. Wenden Sie sich an Ihren ACP-Anbieter, um weitere Informationen zu erhalten. Ihr ACP-Partner muss dann den FQDN Ihres lokalen Edgeserverpools zur Liste der zulässigen Partnerdomänen hinzufügen.

- **Hinzufügen der ACP-Domäne und des Edgeservers als zulässige Verbunddomäne**

    Um die ACP-Domäne als zulässigen Partnerserver (zugelassene Verbunddomäne) hinzuzufügen, führen Sie die Schritte unter Konfigurieren der [Unterstützung für zulässige externe Domänen aus.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains) Fügen Sie für den Edgeserver den FQDN des Edgeservers des ACP-Partners hinzu. Möglicherweise müssen Sie sich an Ihren ACP-Partner wenden, um den FQDN für den Edgeserver zu erhalten, der auch von Ihrem ACP als Zugriffsproxy bezeichnet werden kann.

- **Bereitstellen des FQDN Ihres Edgeserverpools an den ACP-Partner**

    Der ACP-Partner muss einen Partnerverbund konfigurieren, um Ihre lokale Domäne als zulässigen Partnerserver hinzuzufügen, indem der FQDN Ihres Edgeserverpools als zulässige Verbunddomäne hinzugefügt wird.