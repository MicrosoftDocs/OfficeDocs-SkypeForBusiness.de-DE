---
title: Einstellungen für Edgeserver-FQDNs – Erweiterung
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Um externe Einstellungen für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst ermitteln, ob Sie separate IP-Adressen für den SIP-Zugriff (Session Initiation Protocol), den Webkonferenz-Edgedienst und den Audio-/Video-Edgedienst verwenden.
ms.openlocfilehash: da54236226c69b3020413bfb05aa515f26a8641b18457e7c6f7cf9e2689611a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307146"
---
# <a name="edge-server-fqdns-settings-expander"></a>Einstellungen für Edgeserver-FQDNs – Erweiterung

Um externe **Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst ermitteln, ob Sie separate IP-Adressen für den SIP-Zugriff (Session Initiation Protocol), den Webkonferenz-Edgedienst und den Audio-/Video-Edgedienst verwenden.

Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein DNS-A-Eintrag (Host) erstellt werden.

Für jeden externen Dienst geben Sie einen vollqualifizierten Domänennamen und einen zugeordneten Port an. Für den **SIP-Zugriff** muss z. B. "sip.contoso.com" und der Port 5061 verwendet werden.

> [!IMPORTANT]
> Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig ist für SIP der Port 5061/TLS, für den Webkonferenz-Edgedienst der Port 444/TLS und für den A/V-Konferenz-Edgedienst der Port 443/TLS festgelegt. Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den SIP-Zugriff ändern.

> [!IMPORTANT]
> Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edgedienste finden Sie unter [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).