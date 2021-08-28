---
title: Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: Anweisungen zum Außerbetriebsetzen Ihrer lokalen Skype for Business Umgebung.
ms.openlocfilehash: 53ed840c89ab02eff87607f0bdffebcef94fd4e2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583389"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Wenn Ihre Organisation Teams mit einer lokalen Bereitstellung von Skype for Business Server verwendet, können Sie diese Umgebungen vollständig in die Cloud migrieren und dann ihre lokale Bereitstellung von Skype for Business Server zurückziehen. 

> [!NOTE]
> Vor der Außerbetriebnahme Ihrer lokalen Umgebung müssen Sie [die Hybridkonnektivität](configure-hybrid-connectivity.md) zwischen Ihrer lokalen Bereitstellung und Microsoft 365 konfigurieren. Nach dem Konfigurieren der Hybridkonnektivität können Sie Benutzer in die Cloud migrieren, während Sie ihre Besprechungen aus der lokalen Umgebung migrieren und alle Kontakte von Skype for Business Server zu Teams migrieren. Das Konfigurieren der Hybridkonnektivität ist ein erforderlicher Schritt, um Benutzer aus der lokalen Umgebung in die Cloud zu migrieren und die vollständige Teams Funktionalität sicherzustellen.

Führen Sie die folgenden Schritte in der folgenden Reihenfolge aus, um den Wechsel von der lokalen Umgebung in die Cloud abzuschließen und Ihre lokale Skype for Business Server Umgebung außer Betrieb zu setzen:

- **Schritt 1.** [Verschieben Sie alle erforderlichen Benutzer aus der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-users.md)

- **Schritt 2.** [Deaktivieren Sie Ihre Hybridkonfiguration.](cloud-consolidation-disabling-hybrid.md)

- **Schritt 3:** [Verschieben sie Hybridanwendungsendpunkte von der lokalen Umgebung in die Onlineumgebung.](decommission-move-on-prem-endpoints.md)

- **Schritt 4.** [Entfernen Sie Ihre lokale Skype for Business Bereitstellung.](decommission-remove-on-prem.md)

