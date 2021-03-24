---
title: Bereitstellen der Medienumgehung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Enthält die Prüfliste für voraussetzungen und den Bereitstellungsprozess.
ms.openlocfilehash: be29d86dc9e7bd627a83b41d4666eacfcb6d46a4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097081"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Bereitstellen der Medienumgehung in Skype for Business Server
 
Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Enthält die Prüfliste für voraussetzungen und den Bereitstellungsprozess.
  
In diesem Thema wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver und mindestens einen Gateway peer für die Bereitstellung von PSTN-Verbindungen veröffentlicht und konfiguriert haben. Weitere Informationen zu diesen Aufgaben finden Sie unter [Deploy a Mediation Server in Topology Builder in Skype for Business Server](deploy-a-mediation-server.md) und Define a gateway in [Topology Builder in Skype for Business Server](define-a-gateway.md).
  
 Wenn der Peer, mit dem Sie eine Verbindung herstellen, der SBC eines SIP-Trunkinganbieters ist, stellen Sie sicher, dass der Anbieter ein qualifizierter Anbieter ist und dass der Anbieter die Medienumgehung unterstützt. Viele SIP-Trunkinganbieter ermöglichen beispielsweise nur, dass ihr SBC Datenverkehr vom Vermittlungsserver erhält. Wenn ja, darf die Umgehung für den in Frage geschalteten Trunk nicht aktiviert werden. Außerdem können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation dem SIP-Trunkinganbieter die internen Netzwerk-IP-Adressen preist.
  
> [!NOTE]
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im [Unified Communications Open Interoperability Program - Lync Server aufgeführt sind.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
Wenn Sie die Anrufsteuerung (Call Admission Control, ANRUFSTEUERUNG) bereits optional konfiguriert haben Enterprise-VoIP, beachten Sie, dass die von der Anrufsteuerung durchgeführte Bandbreitenreservierung nicht für Anrufe gilt, für die die Medienumgehung verwendet wird. Die Überprüfung, ob die Medienumgehung verwendet werden soll, wird zuerst durchgeführt, und wenn die Medienumgehung verwendet wird, wird die Anrufsteuerung nicht für den Anruf verwendet. Nur wenn die Medienumgehungsprüfung fehlschlägt, wird die Überprüfung auf die Anrufsteuerung durchgeführt. Die beiden Features schließen sich daher für einen bestimmten Anruf, der an das PSTN geroutet wird, gegenseitig aus. Dies ist die Logik, da bei der Medienumgehung davon ausgegangen wird, dass bandbreiteneinschränkungen zwischen den Medienendpunkten eines Anrufs nicht vorhanden sind. Die Medienumgehung kann nicht für Verbindungen mit eingeschränkter Bandbreite ausgeführt werden. Daher gilt für einen #A0 einer der folgenden Optionen: a) Medien umgeht den Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf. oder b) die Anrufsteuerung wendet bandbreitenreservierung auf den Anruf an, und Medien werden vom Vermittlungsserver verarbeitet, der an dem Anruf beteiligt ist.
  
Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Globale Medienumgehungseinstellungen können entweder angeben, dass für Anrufe an das PSTN immer eine Medienumgehung versucht wird, oder dass die Medienumgehung mithilfe der Zuordnung von Subnetzen zu Netzwerkstandorten und Netzwerkregionen verwendet wird – ähnlich wie bei der Anrufsteuerung, einem weiteren erweiterten Sprachfeature. Wenn die Medienumgehung und die Anrufsteuerung aktiviert sind, werden die für die Anrufsteuerung angegebenen Netzwerkregions-, Netzwerkstandort- und Subnetzinformationen automatisch verwendet, wenn ermittelt wird, ob die Medienumgehung verwendet werden soll. Dies bedeutet, dass Sie nicht angeben können, dass die Medienumgehung immer für Anrufe an das PSTN versucht wird, wenn die Anrufsteuerung aktiviert ist.
  
> [!NOTE]
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur mit Produkten und Versionen unterstützt, die im [Unified Communications Open Interoperability Program - Lync Server aufgeführt sind.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md) 
  
## <a name="deployment-process-for-media-bypass"></a>Bereitstellungsprozess für medienumgehung

Die folgende Tabelle enthält eine Übersicht über den Bereitstellungsprozess der Medienumgehung. 
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Trunks für die Medienumgehung  <br/> |Wenn Sie dies noch nicht getan haben, konfigurieren Sie einen oder mehrere Trunks für die Medienumgehung.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Konfigurieren der Medienumgehung global  <br/> |Konfigurieren Sie die Medienumgehung für alle Anrufe an das PSTN oder bestimmte Anrufe basierend auf Netzwerkstandorten und Netzwerkregionen.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen](bypass-the-mediation-server.md) <br/> [Konfigurieren globaler Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Website- und Regioneninformationen](use-site-and-region-information.md) <br/> |
|Zuordnen von Subnetzen zu Netzwerkstandorten, falls erforderlich  <br/> |Wenn Sie die Medienumgehung für die Verwendung von Standort- und Regionsinformationen konfigurieren, müssen Sie die Subnetze Ihrer Bereitstellung Netzwerkstandorten und -regionen zuordnen (Falls noch nicht für ein anderes Sprachfeature.)  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets) <br/> |
