---
title: Wie ist der Status meiner Portierungsaufträge?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie den Status Ihrer Portierungsaufträge abrufen und welche verschiedenen Aktionen Sie für diese ausführen können.
ms.collection:
- M365-voice
ms.openlocfilehash: 29b12d5ec47625a62314bf601018ef069aec4ddb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270420"
---
# <a name="whats-the-status-of-your-port-orders"></a>Wie ist der Status meiner Portierungsaufträge?

Um den Status Ihres Portierungsauftrags anzuzeigen, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu >**VoIP-Portierungsaufträge** > , und klicken Sie dann auf "**Bestellverlauf**". Jeder Portierauftragsstatus wird in der Spalte **"Status"** aufgeführt. Erfahren Sie [, wie lange das Portieren von Nummern dauert](../phone-number-calling-plans/port-order-overview.md#how-long-does-it-take-to-port-numbers) , um mehr über den Bestellvorgang zu erfahren. 

In der folgenden Tabelle sind die Status von Portreihenfolgen sowie bei Bedarf mögliche Aktionen aufgeführt.

|**Status**|**Können Sie die Bestellung anzeigen?**|**Können Sie die Bestellung bearbeiten?**|**Können Sie die Bestellung stornieren?**|**Können Sie die Bestellung löschen?**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verarbeitung** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Der Administrator hat den Auftrag erstellt, und er wurde von Microsoft empfangen.  <br/> |
|**Kontaktieren des Netzbetreibers** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Die Bestellung wurde von Microsoft empfangen und genehmigt, und wir arbeiten mit dem verlierenden Netzbetreiber zusammen, um die Genehmigung zu erhalten.  <br/> |
|**Übertragung genehmigt** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Der Auftrag wurde vom unterlegenen Beförderer angenommen, und das Datum der Auftragsverpflichtung (Firm Order Commitment, FOC) wurde festgelegt.  <br/> |
|**Übertragung ausstehend** <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Die Übertragung ist weniger als 24 Stunden entfernt, sodass die Bestellung nicht mehr bearbeitet oder storniert werden kann.  <br/> |
|**Fehler** <br/> |Nein  <br/> |Ja  <br/> |Ja  <br/> |Ja (zu diesem Zeitpunkt können Sie den Portierauftrag nicht löschen, wenn ein Fehler auftritt. Der Portierungsauftrag muss neu erstellt werden, oder Sie müssen sich an den [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md) wenden.  <br/> |Der unterlegene Beförderer wies den Auftrag zurück.  <br/> |
|**Abgeschlossen** <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Die Nummern wurden erfolgreich übertragen.  <br/> |
|**Abgebrochen** <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Der Administrator hat die Bestellung storniert.  <br/> |

Vollständige schrittweise Anleitungen finden Sie unter [Übertragen von Telefonnummern an Teams](transfer-phone-numbers-to-teams.md).

Wenn Sie Hilfe benötigen oder weitere Telefonnummern benötigen, wenden Sie sich an den [TNS Service Desk](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md).

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
