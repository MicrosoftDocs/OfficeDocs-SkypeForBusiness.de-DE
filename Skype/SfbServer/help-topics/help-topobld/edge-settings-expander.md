---
title: Edgeeinstellungen – Erweiterung
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
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Um die Einstellungen für einen vorhandenen Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: 5d511f3fbb3e862016ddeeeae461c65af13f9598
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633649"
---
# <a name="edge-settings-expander"></a>Edgeeinstellungen – Erweiterung

Um die Einstellungen für einen vorhandenen Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:

- Allgemeine Einstellungen

- Einstellungen für die Auswahl des nächsten Hops

- Edgeserverkonfiguration



## <a name="general-settings"></a>Allgemeine Einstellungen

Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des internen Pools des Edgeserverpools. Bearbeiten Sie den FQDN des Pools, um diese Einstellung zu ändern.

Aktivieren Sie das **Kontrollkästchen Partnerverbund für diesen Edgepool aktivieren (Port 5061),** wenn Sie einen Partnerverbund mit einem vertrauenswürdigen Partner für Lync Server 2013, Microsoft Lync Server 2010 oder Microsoft Office Communications Server 2007 R2 einrichten.

Wählen Sie **"XMPP-Partnerverbund für diesen Edgepool** aktivieren" aus, um den XMPP-Partnerverbund zu aktivieren.

Geben Sie die Portnummer für **den internen Konfigurationsreplikationsport (HTTPS)** an.

## <a name="next-hop-selection-settings"></a>Einstellungen für die Auswahl des nächsten Hops

Um den **Next-Hoppool** festzulegen oder zu ändern, den die Edgeserver für die Kommunikation mit der internen Infrastruktur verwenden, wählen Sie im Dropdownlistenfeld einen Director, Directorpool, Front-End-Server oder Front-End-Serverpool aus. Zur Auswahl werden nur Directors oder Front Ends angezeigt, die im Topologie-Generator konfiguriert wurden.

## <a name="edge-server-configuration"></a>Edgeserverkonfiguration

Um Einstellungen für die **externen Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst ermitteln, ob Sie separate IP-Adressen für SIP-Zugriff, Webkonferenzen und den Audio-/Videodienst verwenden.

Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein entsprechender DNS-Hosteintrag (A) erstellt werden.

Für jeden externen Dienst geben Sie einen FQDN und einen zugeordneten Port an. Beispielsweise würde der **SIP-Zugriff** sip.contoso.com mit einem zugeordneten Port von 5061 verwenden.

> [!IMPORTANT]
> Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig befindet sich das SIP an Port 5061/TLS, der Webkonferenz-Edgedienst an Port 444/TLS und der A/V-Konferenzserver auf Port 443/TLS. Wenn Sie Änderungen an diesen Einstellungen vornehmen, einschließlich der Verwendung separater FQDN- und IP-Adressen oder Ports, müssen Sie alle anderen Dienste aktualisieren, die auf den ursprünglich konfigurierten Werten basieren.

Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den SIP-Zugriff ändern.

> [!IMPORTANT]
> Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edgedienste finden Sie unter ["Definieren der Edgetopologie".](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)