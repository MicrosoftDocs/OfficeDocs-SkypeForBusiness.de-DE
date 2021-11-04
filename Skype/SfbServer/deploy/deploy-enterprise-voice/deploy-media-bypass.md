---
title: Bereitstellen der Medienumgehung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Umfasst Voraussetzungen und Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: f5bed4cf31158ea170b78110f3b6f5561aedb21d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769663"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Bereitstellen der Medienumgehung in Skype for Business Server
 
Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Umfasst Voraussetzungen und Prüfliste für den Bereitstellungsprozess.
  
In diesem Thema wird davon ausgegangen, dass Sie mindestens einen oder mehrere Vermittlungsserver und mindestens einen Gatewaypeer veröffentlicht und konfiguriert haben, um PSTN-Konnektivität bereitzustellen. Weitere Informationen zu diesen Aufgaben finden Sie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype for Business Server](deploy-a-mediation-server.md) und Definieren eines [Gateways im Topologie-Generator in Skype for Business Server.](define-a-gateway.md)
  
 Wenn der Peer, mit dem Sie eine Verbindung herstellen, der SBC eines SIP-Trunkinganbieters ist, stellen Sie sicher, dass der Anbieter ein qualifizierter Anbieter ist und dass der Anbieter die Medienumgehung unterstützt. Beispielsweise lassen viele SIP-Trunkinganbieter nur zu, dass ihr SBC Datenverkehr vom Vermittlungsserver empfängt. Wenn ja, darf die Umgehung für den betreffenden Trunk nicht aktiviert werden. Außerdem können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation ihre internen Netzwerk-IP-Adressen für den SIP-Trunkinganbieter offen legt.
  
> [!NOTE]
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Ip-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im [Unified Communications Open Interoperability Program – Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)aufgeführt sind. 
  
Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) bereits optional konfiguriert haben, beachten Sie, dass eine weitere erweiterte Enterprise-VoIP Funktion, beachten Sie, dass die bandbreitenreservierung, die von der Anrufsteuerung durchgeführt wird, nicht für Anrufe gilt, für die die Medienumgehung verwendet wird. Die Überprüfung, ob die Medienumgehung verwendet werden soll, wird zuerst durchgeführt, und wenn die Medienumgehung verwendet wird, wird für den Anruf keine Anrufsteuerung verwendet. Nur wenn die Medienumgehungsüberprüfung fehlschlägt, wird die Prüfung für die Anrufsteuerung durchgeführt. Die beiden Features schließen sich daher für einen bestimmten Anruf, der an das PSTN weitergeleitet wird, gegenseitig aus. Dies ist die Logik, da die Medienumgehung davon ausgeht, dass zwischen den Medienendpunkten eines Anrufs keine Bandbreiteneinschränkungen vorhanden sind. Die Medienumgehung kann nicht für Verbindungen mit eingeschränkter Bandbreite ausgeführt werden. Daher gilt einer der folgenden Punkte für einen PSTN-Anruf: a) Medien umgehen den Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf; oder b) die Anrufsteuerung wendet Bandbreitenreservierungen auf den Anruf an, und Medien werden vom Vermittlungsserver verarbeitet, der an dem Anruf beteiligt ist.
  
Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Globale Medienumgehungseinstellungen können entweder angeben, dass für Anrufe an das Telefonfestnetz immer eine Medienumgehung versucht wird, oder dass die Medienumgehung mithilfe der Zuordnung von Subnetzen zu Netzwerkstandorten und Netzwerkregionen verwendet wird – ähnlich wie bei der Anrufsteuerung, einer weiteren erweiterten VoIP-Funktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert sind, werden die Netzwerkregion, der Netzwerkstandort und die Subnetzinformationen, die für die Anrufsteuerung angegeben sind, automatisch verwendet, um zu bestimmen, ob die Medienumgehung verwendet werden soll. Dies bedeutet, dass Sie nicht angeben können, dass bei Anrufen an das Telefonfestnetz immer versucht wird, die Medienumgehung zu verwenden, wenn die Anrufsteuerung aktiviert ist.
  
> [!NOTE]
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Ip-Nebenstellenanlagen von Cisco durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im [Unified Communications Open Interoperability Program – Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)aufgeführt sind. 
  
## <a name="deployment-process-for-media-bypass"></a>Bereitstellungsprozess für die Medienumgehung

Die folgende Tabelle enthält eine Übersicht über den Bereitstellungsprozess für die Medienumgehung. 
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Trunks für die Medienumgehung  <br/> |Falls noch nicht geschehen, konfigurieren Sie einen oder mehrere Trunks für die Medienumgehung.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Globales Konfigurieren der Medienumgehung  <br/> |Konfigurieren Sie die Medienumgehung für alle Anrufe an das Telefonfestnetz oder für bestimmte Anrufe basierend auf Netzwerkstandorten und Netzwerkregionen.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen](bypass-the-mediation-server.md) <br/> [Konfigurieren der globalen Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regionsinformationen](use-site-and-region-information.md) <br/> |
|Zuordnen von Subnetzen zu Netzwerkstandorten, falls erforderlich  <br/> |Wenn Sie die Medienumgehung so konfigurieren, dass Standort- und Regionsinformationen verwendet werden, müssen Sie die Subnetze Ihrer Bereitstellung Netzwerkstandorten und -regionen zuordnen (wenn Sie dies noch nicht für ein anderes VoIP-Feature getan haben).)  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets) <br/> |
