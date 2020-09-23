---
title: Edgeeinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c73780cd-0033-4287-9ecd-ecf65ca61e62
description: 'Um die Einstellungen für eine vorhandene Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:'
ms.openlocfilehash: c2d4ec8e97557a584821bb82ef1d24b9bfa7a9bb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218896"
---
# <a name="edge-settings-expander"></a>Edgeeinstellungen – Erweiterung

Um die Einstellungen für eine vorhandene Edgepool mit einem oder mehreren Servern zu bearbeiten, werden die folgenden Abschnitte angezeigt:

- Allgemeine Einstellungen

- Auswahl Einstellungen für den nächsten Hop

- Edgeserver Konfiguration



## <a name="general-settings"></a>Allgemeine Einstellungen

Interner Pool vollqualifizierter Domänenname (FQDN) des Edgeserver Pools. Bearbeiten Sie den FQDN des Pools, um diese Einstellung zu ändern.

Aktivieren Sie das Kontrollkästchen Partner **Verbund für diesen Edgepool aktivieren (Port 5061)** , wenn Sie einen Verbund mit einem lync Server 2013, Microsoft lync Server 2010 oder Microsoft Office Communications Server 2007 R2 vertrauenswürdigen Partner einrichten möchten.

Wählen Sie XMPP-Partner **Verbund für diesen Edgepool aktivieren** aus, um den XMPP-Partnerverbund zu aktivieren.

Geben Sie die Portnummer für den **Port der internen Konfigurations Replikation (HTTPS)** an.

## <a name="next-hop-selection-settings"></a>Auswahl Einstellungen für den nächsten Hop

Um den Pool für den **nächsten Hop** festzulegen oder zu ändern, den die Edgeserver für die Kommunikation mit der internen Infrastruktur verwenden, wählen Sie im Dropdown-Listenfeld einen Director-, Directorpool-, Front-End-Server-oder Front-End-Server-Pool aus. Für die Auswahl werden nur Directors oder Front-Ends angezeigt, die im Topologie-Generator konfiguriert wurden.

## <a name="edge-server-configuration"></a>Edgeserver Konfiguration

Um Einstellungen für die **externen Einstellungen** für die Edgeserver zu bearbeiten oder anzugeben, müssen Sie zunächst feststellen, ob Sie separate IP-Adressen für SIP-Zugriff, Webkonferenzen und den Audio/Video-Dienst verwenden werden.

Wenn separate IP-Adressen verwendet werden sollen, aktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Für jeden Dienst muss ein entsprechender DNS-Hosteintrag (a) erstellt werden.

Für jeden der extern angerichteten Dienste geben Sie einen FQDN und einen zugeordneten Port an. Beispielsweise würde der **SIP-Zugriff** SIP.contoso.com mit einem zugeordneten Port von 5061 verwenden.

> [!IMPORTANT]
> Wenn Sie separate vollqualifizierte Domänennamen für die externen Dienste auswählen, muss jedem Dienst ein eindeutiger Portwert zugeordnet werden. Standardmäßig befindet sich das SIP auf Port 5061/TLS, der Webkonferenz-Edgedienst befindet sich auf Port 444/TLS, und der A/V-Konferenzserver befindet sich auf Port 443/TLS. Wenn Sie Änderungen an diesen Einstellungen vornehmen, einschließlich der Verwendung separater FQDN-und IP-Adressen oder Ports, müssen Sie alle anderen Dienste aktualisieren, die auf die anfänglich konfigurierten Werte angewiesen sind.

Wenn Sie festlegen, dass Ihre Organisation einen einzigen FQDN und eine einzige IP-Adresse für die externen Dienste verwendet, deaktivieren Sie das Kontrollkästchen **Separate FQDNs und IP-Adressen für Webkonferenzen und A/V aktivieren**. Bei Bedarf können Sie anschließend die Werte für den Pool-FQDN und den Port für den SIP-Zugriff**** ändern.

> [!IMPORTANT]
> Wenn Sie diese Einstellungen ändern (z. B. die Verwendung separater vollqualifizierter Domänennamen und IP-Adressen oder Ports festlegen), müssen Sie alle anderen Dienste aktualisieren, die von den ursprünglich konfigurierten Werten abhängen.

## <a name="see-also"></a>Siehe auch

Ausführliche Informationen zum Definieren und Konfigurieren der Einstellungen für die Edge-Dienste finden Sie unter [define your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


