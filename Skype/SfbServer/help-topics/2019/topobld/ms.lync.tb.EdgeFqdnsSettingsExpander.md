---
title: Einstellungen für Edgeserver-FQDNs – Erweiterung
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Um externe Einstellungen für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst ermitteln, ob Sie separate IP-Adressen für den SIP-Zugriff (Session Initiation Protocol), den Webkonferenz-Edgedienst und den Audio-/Video-Edgedienst verwenden.
ms.openlocfilehash: 98169166a684cbd42b3d17cd2962024b26d59680
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769313"
---
# <a name="edge-server-fqdns-settings-expander"></a>Einstellungen für Edgeserver-FQDNs – Erweiterung

Um externe **Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst ermitteln, ob Sie separate IP-Adressen für den SIP-Zugriff (Session Initiation Protocol), den Webkonferenz-Edgedienst und den Audio-/Video-Edgedienst verwenden.

Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein DNS-A-Eintrag (Host) erstellt werden.

Für jeden externen Dienst geben Sie einen vollqualifizierten Domänennamen und einen zugeordneten Port an. Für den **SIP-Zugriff** muss z. B. "sip.contoso.com" und der Port 5061 verwendet werden.

> [!IMPORTANT]
> Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig ist für SIP der Port 5061/TLS, für den Webkonferenz-Edgedienst der Port 444/TLS und für den A/V-Konferenz-Edgedienst der Port 443/TLS festgelegt. Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den SIP-Zugriff ändern.

> [!IMPORTANT]
> Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edgedienste finden Sie unter [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).