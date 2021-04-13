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
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Anweisungen zum Außerbetriebsetzen Ihrer lokalen Skype for Business-Umgebung.
ms.openlocfilehash: 46848c6730d37f549a8d5ee16f066fa67c789873
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656681"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Außerbetriebnahme Ihrer lokalen Skype for Business-Umgebung

Wenn Ihre Organisation Teams oder Skype for Business Online mit einer lokalen Bereitstellung von Skype for Business Server verwendet, können Sie diese Umgebungen vollständig in die Cloud migrieren und dann Ihre lokale Bereitstellung von Skype for Business Server zurückziehen. 

> [!NOTE]
> Vor dem Außerbetriebsetzen Ihrer lokalen Umgebung müssen Sie die [Hybridkonnektivität](configure-hybrid-connectivity.md) zwischen Ihrer lokalen Bereitstellung und Microsoft 365 konfigurieren. Nach dem Konfigurieren der Hybridkonnektivität können Sie Benutzer in die Cloud migrieren, während sie ihre Besprechungen von lokalen Besprechungen migrieren und kontakte von Skype for Business Server zu Teams migrieren. Das Konfigurieren der Hybridkonnektivität ist ein erforderlicher Schritt zum Migrieren von Benutzern von der lokalen in die Cloud und zum Sicherstellen der vollständigen Funktionalität von Teams.

Zum Abschließen des Wechsels von der lokalen in die Cloud und zum Außerbetriebsetzen Ihrer lokalen Skype for Business Server-Umgebung müssen Sie die folgenden Schritte in der folgenden Reihenfolge ausführen:

- **Schritt 1.** [Verschieben Sie alle erforderlichen Benutzer von lokal in online.](decommission-move-on-prem-users.md)

- **Schritt 2.** [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- **Schritt 3.** [Verschieben von Hybridanwendungsendpunkten von lokal in online](decommission-move-on-prem-endpoints.md).

- **Schritt 4.** [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)

