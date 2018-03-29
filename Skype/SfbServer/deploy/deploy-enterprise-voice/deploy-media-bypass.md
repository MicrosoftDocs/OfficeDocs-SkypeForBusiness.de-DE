---
title: Bereitstellen der Medienumgehung in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
description: Bereitstellen von medienumgehung in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
ms.openlocfilehash: 0a42645b9d6fbe90ed36d8b1f474187a4c522f16
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-media-bypass-in-skype-for-business-server-2015"></a>Bereitstellen der Medienumgehung in Skype for Business Server 2015
 
Bereitstellen von medienumgehung in Skype für Business Server Enterprise-VoIP. Dazu gehören die Voraussetzungen sowie die Prüfliste für den Bereitstellungsprozess.
  
In diesem Thema wird davon ausgegangen, dass Sie bereits veröffentlicht und mindestens einen oder mehrere Vermittlungsserver und mindestens ein gatewaypeer, um PSTN-Konnektivität bereitzustellen konfiguriert haben. Weitere Informationen zu Aufgaben finden Sie unter [Bereitstellen eines Vermittlungsservers im Topologie-Generator in Skype für Business Server 2015](deploy-a-mediation-server.md) und [Definieren eines Gateways im Topologie-Generator in Skype für Business Server 2015](define-a-gateway.md).
  
 Wenn es sich bei dem Peer, mit dem Sie sich verbinden, um den SBC eines SIP-Trunkinganbieters handelt, sollten Sie sich vergewissern, dass dieser ein qualifizierter Anbieter ist und die Medienumgehung unterstützt. Viele SIP-Trunkinganbieter lassen für den SBC nur den Empfang von Datenverkehr vom Vermittlungsserver zu. In diesem Fall darf die Medienumgehung für den betreffenden Trunk nicht aktiviert werden. Darüber hinaus können Sie die Medienumgehung nur aktivieren, wenn Ihre Organisation dem SIP-Trunkinganbieter ihre internen Netzwerk-IP-Adressen offenlegt.
  
> [!NOTE]
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten unterstützt und aufgeführtes Dokument Versionen [Unified Communications Open Interoperability Program – Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) – eine andere erweiterte Enterprise-VoIP-Funktion – bereits optional konfiguriert haben, beachten Sie, dass die Bandbreitenreservierung der Anrufsteuerung nicht für Anrufe gilt, für welche die Medienumgehung aktiviert ist. Bei einem Anruf wird zuerst überprüft, ob die Medienumgehung angewendet werden soll. Wenn dies der Fall ist, wird die Anrufsteuerung nicht angewendet. Nur wenn die Medienumgehung nicht aktiviert ist, wird geprüft, ob die Anrufsteuerung angewendet werden soll. Diese beiden Funktionen schließen sich für alle Anrufe, die an das PSTN weitergeleitet werden, gegenseitig aus. Dies ist ein logisches Verhalten, denn die Medienumgehung setzt voraus, dass bei einem Anruf keine Bandbreitenbeschränkungen zwischen den Medienendpunkten vorhanden sind. In Verbindungen mit eingeschränkter Bandbreite kann keine Medienumgehung stattfinden. Demzufolge trifft auf einen PSTN-Anruf nur eine der beiden folgenden Verhaltensweisen zu: a) die Medien umgehen den Vermittlungsserver und die Anrufsteuerung reserviert keine Bandbreite für den Anruf oder b) die Anrufsteuerung reserviert Bandbreite für den Anruf und die Medien werden vom betroffenen Vermittlungsserver verarbeitet.
  
Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Über globale Einstellungen für die Medienumgehung können Sie entweder angeben, dass die Medienumgehung auf Anrufe über das Telefonfestnetz immer angewendet wird oder dass die Medienumgehung auf der Grundlage von Zuordnungen von Subnetzen zu Netzwerkstandorten und Netzwerkregionen angewendet wird – ähnlich wie bei der Anrufsteuerung, einer anderen erweiterten VoIP-Funktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert wurden, werden die Informationen zu Netzwerkregionen, Netzwerkstandorten und Subnetzen, die für die Anrufsteuerung konfiguriert wurden, automatisch für Entscheidungen zur Verwendung der Medienumgehung herangezogen. Dies bedeutet, dass Sie die Medienumgehung nicht auf alle Anrufe über das Telefonfestnetz anwenden können, wenn die Anrufsteuerung aktiviert ist.
  
> [!NOTE]
> Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunkinganbieter). Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden. Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten unterstützt und aufgeführtes Dokument Versionen [Unified Communications Open Interoperability Program – Lync Server](https://go.microsoft.com/fwlink/p/?linkId=214406). 
  
## <a name="deployment-process-for-media-bypass"></a>Bereitstellungsprozess für die Medienumgehung

Die folgende Tabelle enthält eine Übersicht über den Bereitstellungsprozess für die Medienumgehung. 
  
|**Phase**|**Schritte**|**Rollen**|**Dokumentation zur Bereitstellung**|
|:-----|:-----|:-----|:-----|
|Konfigurieren von Trunks für die Medienumgehung  <br/> |Konfigurieren Sie, wenn Sie es noch nicht getan haben, einen oder mehrere Trunks für die Medienumgehung.  <br/> | Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder CsAdministrator <br/> |[Konfigurieren eines Trunks mit medienumgehung in Skype für Business Server 2015](configure-trunk-with-media-bypass.md) <br/> |
|Globales Konfigurieren der Medienumgehung  <br/> |Konfigurieren Sie die Medienumgehung entweder für alle Anrufe an das PSTN oder für bestimmte Anrufe basierend auf Netzwerkstandorten und Netzwerkregionen.  <br/> | Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder CsAdministrator <br/> |[Konfigurieren der medienumgehung in Skype für Business Server 2015 zum dauerhaften Umgehung des Vermittlungsservers](bypass-the-mediation-server.md) <br/> [Konfigurieren von globalen Einstellungen für die medienumgehung in Skype für Business Server 2015 Standorten und Regionen verwenden](use-site-and-region-information.md) <br/> |
|Gegebenenfalls Zuordnen von Subnetzen zu Netzwerkstandorten  <br/> |Wenn Sie die Medienumgehung konfigurieren, um Standort- und Regionsinformationen zu verwenden, müssen Sie die Subnetze Ihrer Bereitstellung zu Netzwerkstandorten und Regionen zuordnen (wenn das noch nicht für eine andere VoIP-Funktion geschehen ist.)  <br/> | Mitglied der Gruppe "RTCUniversalServerAdmins" oder ein Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder CsAdministrator <br/> |[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets) <br/> |
   

