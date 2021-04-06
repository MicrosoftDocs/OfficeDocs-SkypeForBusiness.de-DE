---
title: Außerbetriebsetzen Ihrer lokalen Skype for Business-Umgebung
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
ms.openlocfilehash: 7f5109661fc7d29d83172489dd987b96cb7e87fd
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593884"
---
# <a name="decommission-your-on-premises-skype-for-business-environment"></a>Außerbetriebsetzen Ihrer lokalen Skype for Business-Umgebung

Wenn Ihre Organisation Teams oder Skype for Business Online mit einer lokalen Bereitstellung von Skype for Business Server verwendet, können Sie diese Umgebungen vollständig in die Cloud migrieren und dann Ihre lokale Bereitstellung von Skype for Business Server zurückziehen. 

> [!NOTE]
> Vor dem Außerbetriebsetzen Ihrer lokalen Umgebung müssen Sie die [Hybridkonnektivität](configure-hybrid-connectivity.md) zwischen Ihrer lokalen Bereitstellung und Microsoft 365 konfigurieren. Nach dem Konfigurieren der Hybridkonnektivität können Sie Benutzer in die Cloud migrieren, während sie ihre Besprechungen von lokalen Besprechungen migrieren und kontakte von Skype for Business Server zu Teams migrieren. Das Konfigurieren der Hybridkonnektivität ist ein erforderlicher Schritt zum Migrieren von Benutzern von der lokalen in die Cloud und zum Sicherstellen der vollständigen Funktionalität von Teams.

Zum Abschließen des Wechsels von der lokalen in die Cloud und zum Außerbetriebsetzen Ihrer lokalen Skype for Business Server-Umgebung müssen Sie die folgenden Schritte in der folgenden Reihenfolge ausführen:

- **Schritt 1.** [Verschieben Sie alle erforderlichen Benutzer und Anwendungsendpunkte von lokal in online.](decommission-move-on-prem-users.md)

- **Schritt 2.** [Deaktivieren Sie Die Hybridkonfiguration](cloud-consolidation-disabling-hybrid.md).

- **Schritt 3.** [Entfernen Sie Ihre lokale Skype for Business-Bereitstellung.](decommission-remove-on-prem.md)

