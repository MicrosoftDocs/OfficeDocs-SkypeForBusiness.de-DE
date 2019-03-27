---
title: Verhindern neuer Verbindungen
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: ''
ms.openlocfilehash: bc9b4a1e7d6e17f09643ff14ac0e69261c326922
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889726"
---
# <a name="preventing-new-connections-to-skype-for-business-server-for-server-maintenance"></a>Verhindern neuer Verbindungen mit Skype für Business Server zur Serverwartung


Skype für Business Server können Sie einen Server offline schalten (z. B. Software- oder Hardwareupgrades anzuwenden) ohne Verlust des Diensts für Benutzer zu übernehmen.

Wenn Sie die Option, um zu verhindern, dass neue Verbindungen oder Anrufe auf einem Server in einem Pool angeben, wird jede neue Verbindungen und Anrufe annimmt, sobald Sie diese Option implementieren beendet. Diese neue Verbindungen und Anrufe werden über den anderen Servern im Pool weitergeleitet. Ein Server, der neue Verbindungen verhindern kann die Sitzungen auf vorhandene Verbindungen, um den Vorgang fortzusetzen, bis sie natürlich enden. Wenn Sie alle vorhandene Sitzungen beendet haben, ist der Server offline geschaltet werden bereit.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, einige Skype für Business Server-Features und Dienste hängen von DNS-Lastenausgleich, um sicherzustellen, dass es ordnungsgemäß funktioniert. Wenn Sie DNS-Lastenausgleich im Pool nicht verwenden, Verbindungen über diese Dienste möglicherweise nicht mit anderen Servern weitergeleitet während des Berichtszeitraums, dass der Server neue Verbindungen verhindern ist und daher bei der Server ist offline geschaltet einige Sitzungen und Anrufe möglicherweise unterbrochen. Die Features, die DNS-Lastenausgleich, um sicherzustellen, dass diese Option reibungsloses abhängig sind wie folgt:

  - Vermittlung

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ansageanwendung

  - Anwendung zum Parken von Anrufen

Ausführliche Informationen zu DNS-Lastenausgleich finden Sie unter [Lastenausgleich Anforderungen an den](../../plan-your-deployment/network-requirements/load-balancing.md).

Zusätzlich zu verhindern neuer Verbindungen für alle Dienste auf einem Server mit Skype für Business Server, können Sie auch neue Verbindungen für einzelne Skype für Business Server-Dienste verhindern. Diese Methode eignet sich beispielsweise in einer Situation, in denen Sie müssen einen Skype für Business Serverupdate angewendet wird, die nicht den gesamten Server heruntergefahren werden, erforderlich sind. Beachten Sie, dass wenn Sie Verbindungen für einen Dienst verhindern, wählen Sie einen Dienst aus müssen sie gruppiert und in der Windows-Liste der Dienste angezeigt. Angenommen, der Skype für Business Server Front-End-Dienst und den Daten Auflistung-Agent für Überwachung sind separate Skype für Business Server-Dienste, aber in der Liste der Windows-Dienste konsolidierte und dargestellt als die Skype für Business Server-Front-End Dienst. Sie können verhindern, dass neue Verbindungen für die Skype für Business Server-Front-End-Dienst, aber Sie können nicht verhindern, dass neue Verbindungen für diese zwei einzelne zugrunde liegenden Skype für Business Server-Dienste separat.

> [!IMPORTANT]
> Beim Festlegen eines Servers zum verhindern neuer Verbindungen, und klicken Sie dann den Server neu starten, wird standardmäßig der Server sofort neue Verbindungen akzeptieren, nachdem er beginnt. Um dies zu verhindern, legen Sie den Server für nur anhalten und Fortsetzen von manuell, bevor Sie den Server neu starten.

## <a name="to-prevent-new-connections-to-skype-for-business-server"></a>So verhindern Sie neue Verbindungen zu Skype für Business Server

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Öffnen Sie die Konsole Dienste-Snap-in: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Doppelklicken Sie in der Liste auf die Skype für Business-Windows-Dienst, dem Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im Dialogfeld Eigenschaften unter **Dienststatus: gestartet**, klicken Sie auf **Anhalten**.

5.  Optional, aber empfohlen, klicken Sie neben **Starttyp**auf **manuell**.
    
    > [!IMPORTANT]
    > Beim Festlegen eines Servers zum verhindern neuer Verbindungen, und klicken Sie dann den Server neu starten, wird standardmäßig der Server sofort neue Verbindungen akzeptieren, nachdem er beginnt. Um dies zu verhindern, legen Sie den Server für nur anhalten und Fortsetzen von manuell, bevor Sie den Server neu starten.
