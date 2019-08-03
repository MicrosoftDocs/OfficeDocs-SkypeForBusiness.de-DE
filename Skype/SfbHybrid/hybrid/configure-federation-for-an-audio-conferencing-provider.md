---
title: Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in ihrer hybridbereitstellung
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160572"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in ihrer hybridbereitstellung

**Zusammenfassung:** Informationen zum Konfigurieren des Verbunds für einen Audiokonferenz-Anbieter in Skype for Business Online.

Wenn Sie einen Audiokonferenz-Anbieter (ACP) in ihrer hybridbereitstellung (lokal mit Online) verwenden möchten, müssen Sie den Verbund zwischen Ihrer lokalen Bereitstellung und dem ACP-Partner als zulässigen Partner Server konfigurieren. Sie können den Verbund durch Hinzufügen der AKP-Partnerdomäne und des Edge-Servers (Dies kann auch als Zugriffs Proxy bezeichnet werden) zur Liste der Verbunddomänen für Ihre lokale Bereitstellung konfigurieren. Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen. Weitere Informationen erhalten Sie von Ihrem ACP-Anbieter. Der AKP-Partner muss dann den FQDN des lokalen Edgeserver Pools der Liste zugelassene Verbunddomänen hinzufügen.

- **Hinzufügen der ACP-Domäne und Edgeserver als zugelassene Verbunddomäne**

    Wenn Sie die ACP-Domäne als zulässigen Partner Server (zugelassene Verbunddomäne) hinzufügen möchten, führen Sie die Schritte unter [Konfigurieren der Unterstützung für zugelassene externe Domänen](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)aus. Fügen Sie für die Edgeserver den FQDN des Edgeserver des AKP-Partners hinzu. Möglicherweise müssen Sie sich an ihren AKP-Partner wenden, um den FQDN für Ihre Edgeserver zu erhalten, die auch von Ihrem ACP als Zugriffs Proxy bezeichnet werden kann.

- **Bereitstellen des FQDN des Edgeserver Pools für den AKP-Partner**

    Der AKP-Partner muss den Verbund so konfigurieren, dass die lokale Domäne als zulässiger Partner Server hinzugefügt wird, indem der FQDN des Edgeserver Pools als zugelassene Verbunddomäne hinzugefügt wird.


