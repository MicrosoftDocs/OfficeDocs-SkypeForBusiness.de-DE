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
description: Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Umfasst die Voraussetzungen und die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: c6820438d969ce3c802060eba9bcababc0b1315d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812445"
---
# <a name="deploy-media-bypass-in-skype-for-business-server"></a>Bereitstellen der Medienumgehung in Skype for Business Server
 
Bereitstellen der Medienumgehung in Skype for Business Server Enterprise-VoIP. Umfasst die Voraussetzungen und die Prüfliste für den Bereitstellungsprozess.
  
In diesem Thema wird davon ausgegangen, dass Sie bereits mindestens einen Vermittlungsserver und mindestens einen Gateway peer veröffentlicht und konfiguriert haben, um eine Festnetzanbindung zu ermöglichen. Weitere Informationen zu diesen Aufgaben finden Sie unter "Bereitstellen eines Vermittlungsservers im [Topologie-Generator in Skype for Business Server"](deploy-a-mediation-server.md) und "Definieren eines Gateways [im Topologie-Generator in Skype for Business Server".](define-a-gateway.md)
  
 Wenn der Peer, mit dem Sie eine Verbindung herstellen, der SBC eines SIP-Trunking-Anbieters ist, stellen Sie sicher, dass der Anbieter ein qualifizierter Anbieter ist und dass der Anbieter die Medienumgehung unterstützt. Viele SIP-Trunking-Anbieter lassen beispielsweise nur zu, dass ihr SBC Datenverkehr vom Vermittlungsserver empfangen kann. Wenn ja, darf die Umgehung für den in Frage geschalteten Trunk nicht aktiviert werden. Außerdem können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation ihre internen Netzwerk-IP-Adressen dem SIP-Trunking-Anbieter offen legt.
  
> [!NOTE]
> Die Medienumgehung kann nicht mit jedem PSTN-Gateway, IP-PBX und SBC interagieren. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur für Produkte und Versionen unterstützt, die im [Unified Communications Open Interoperability Program ( Lync Server ) aufgeführt sind.](https://go.microsoft.com/fwlink/p/?linkId=214406) 
  
Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) bereits optional konfiguriert haben, eine weitere erweiterte Enterprise-VoIP-Funktion, beachten Sie, dass die von der Anrufsteuerung durchgeführte Bandbreitenreservierung nicht für Anrufe gilt, für die die Medienumgehung verwendet wird. Die Überprüfung, ob die Medienumgehung verwendet werden soll, wird zuerst durchgeführt, und wenn die Medienumgehung verwendet wird, wird für den Anruf keine Anrufsteuerung verwendet. Nur wenn die Medienumgehung fehlschlägt, wird die Anrufsteuerung überprüft. Die beiden Funktionen schließen sich daher für einen bestimmten Anruf, der an das Telefonnetz geroutet wird, gegenseitig aus. Dies ist die Logik, da bei der Medienumgehung davon ausgegangen wird, dass zwischen den Medienendpunkten eines Anrufs keine Bandbreiteneinschränkungen bestehen. Die Medienumgehung kann nicht für Verbindungen mit eingeschränkter Bandbreite ausgeführt werden. Daher gilt eine der folgenden Optionen für einen PSTN-Anruf: a) Medien umgeht den Vermittlungsserver, und die Anrufsteuerung reserviert keine Bandbreite für den Anruf; oder b) die Anrufsteuerung wendet eine Bandbreitenreservierung auf den Anruf an, und die Medien werden vom Vermittlungsserver verarbeitet, der an dem Anruf beteiligt ist.
  
Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Die globalen Einstellungen für die Medienumgehung können entweder angeben, dass für Anrufe an das Telefonnetz immer eine Medienumgehung versucht wird, oder dass die Medienumgehung mithilfe der Zuordnung von Subnetzen zu Netzwerkstandorten und Netzwerkregionen verwendet wird – ähnlich wie bei der Anrufsteuerung, einer anderen erweiterten Sprachfunktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert sind, werden die für die Anrufsteuerung angegebenen Netzwerkregions-, Netzwerkstandort- und Subnetzinformationen automatisch verwendet, wenn ermittelt wird, ob die Medienumgehung verwendet werden soll. Dies bedeutet, dass Sie nicht angeben können, dass für Anrufe an das Telefonnetz bei aktivierter Anrufsteuerung immer eine Medienumgehung versucht wird.
  
> [!NOTE]
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBXs durchgeführt. Die Medienumgehung wird nur für Produkte und Versionen unterstützt, die im [Unified Communications Open Interoperability Program ( Lync Server ) aufgeführt sind.](https://go.microsoft.com/fwlink/p/?linkId=214406) 
  
## <a name="deployment-process-for-media-bypass"></a>Bereitstellungsprozess für die Medienumgehung

Die folgende Tabelle enthält eine Übersicht über den Bereitstellungsprozess für die Medienumgehung. 
  
|**Phase**|**Schritte**|**Rollen**|**Bereitstellungsdokumentation**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Trunks für die Medienumgehung  <br/> |Falls noch nicht geschehen, konfigurieren Sie einen oder mehrere Trunks für die Medienumgehung.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren eines Trunks mit Medienumgehung in Skype for Business Server](configure-trunk-with-media-bypass.md) <br/> |
|Globales Konfigurieren der Medienumgehung  <br/> |Konfigurieren Sie die Medienumgehung entweder für alle Anrufe an das Festnetz oder für bestimmte Anrufe basierend auf Netzwerkstandorten und Netzwerkregionen.  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Konfigurieren der Medienumgehung in Skype for Business Server, um den Vermittlungsserver immer zu umgehen](bypass-the-mediation-server.md) <br/> [Konfigurieren globaler Einstellungen für die Medienumgehung in Skype for Business Server für die Verwendung von Standort- und Regioneninformationen](use-site-and-region-information.md) <br/> |
|Zuordnen von Subnetzen zu Netzwerkstandorten bei Bedarf  <br/> |Wenn Sie die Medienumgehung für die Verwendung von Standort- und Regionsinformationen konfigurieren, müssen Sie die Subnetze Ihrer Bereitstellung Netzwerkstandorten und Regionen zuordnen (sofern noch nicht geschehen für eine andere Sprachfunktion).)  <br/> | Ein Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" <br/> |[Zuordnen eines Subnetzes zu einem Netzwerkstandort](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

