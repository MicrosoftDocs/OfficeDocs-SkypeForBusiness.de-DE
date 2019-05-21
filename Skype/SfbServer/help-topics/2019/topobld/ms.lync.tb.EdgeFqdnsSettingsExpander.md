---
title: Einstellungen für Edgeserver-FQDNs – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Um Externe Einstellungen für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst festlegen, ob für den SIP-Zugriff (Session Initiation Protocol), den Edge-Webkonferenzdienst und den Edge-Audio/Video-Dienst separate IP-Adressen verwendet werden sollen.
ms.openlocfilehash: 5fa118ea3b1b9030c36a3c23d93b27e270ccdb09
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280515"
---
# <a name="edge-server-fqdns-settings-expander"></a>Einstellungen für Edgeserver-FQDNs – Erweiterung

Um **Externe Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst festlegen, ob für den SIP-Zugriff (Session Initiation Protocol), den Edge-Webkonferenzdienst und den Edge-Audio/Video-Dienst separate IP-Adressen verwendet werden sollen.

Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein DNS-A-Eintrag (Host) erstellt werden.

Geben Sie für jeden externen Dienst einen vollqualifizierten Domänennamen und einen zugeordneten Port an. Für den **SIP-Zugriff** müssen z. B. „sip.contoso.com“ und der Port 5061 verwendet werden.

> [!IMPORTANT]
> Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig ist für SIP der Port 5061/TLS, für den Webkonferenz-Edgedienst der Port 444/TLS und für den A/V-Konferenz-Edgedienst der Port 443/TLS festgelegt. Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den **SIP-Zugriff** ändern.

> [!IMPORTANT]
> Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edgedienste finden Sie unter [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


