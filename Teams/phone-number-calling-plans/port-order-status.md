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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: 'Erfahren Sie, wie Sie den Status Ihrer Portierungs Bestellungen ermitteln und welche verschiedenen Aktionen Sie ausführen können. '
ms.openlocfilehash: cfbbbea1d82cfa2f1905584740e8053e83f19ee6
ms.sourcegitcommit: 33bec766519397f898518a999d358657a413924c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583092"
---
# <a name="whats-the-status-of-your-port-orders"></a>Wie ist der Status meiner Portierungsaufträge?

Wenn Sie den Status Ihrer Portierungs Reihenfolge anzeigen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu > **VoIP** > -**Port Bestellungen**, und klicken Sie dann auf **Bestellverlauf**. Jeder Port Auftragsstatus wird in der Spalte **Status** aufgelistet.

In der folgenden Tabelle sind die Port Auftragsstatus sowie Aktionen aufgeführt, die Sie bei Bedarf ausführen können.

|**Status**|**Können Sie den Auftrag anzeigen?**|**Können Sie die Bestellung bearbeiten?**|**Können Sie die Bestellung stornieren?**|**Können Sie den Auftrag löschen?**|**Beschreibung**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Verarbeitung** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Der Administrator hat den Auftrag erstellt, der von Microsoft empfangen wurde.  <br/> |
|**Kontaktaufnahme mit dem Netzbetreiber** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Die Bestellung wurde von Microsoft eingegangen und genehmigt, und wir arbeiten mit dem verlorenen Netzbetreiber zusammen, um ihn genehmigt zu erhalten.  <br/> |
|**Übertragung genehmigt** <br/> |Ja  <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Die Bestellung wurde vom Verlust Träger akzeptiert, und das Datum der Firm Order Commitment (BAK) wurde festgesetzt.  <br/> |
|**Übertragung ausstehend** <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Die Übertragung ist weniger als 24 Stunden entfernt, sodass die Bestellung nicht mehr bearbeitet oder storniert werden kann.  <br/> |
|**Fehler** <br/> |Nein  <br/> |Ja  <br/> |Ja   <br/> |Ja (zu diesem Zeitpunkt können Sie die Portierungs Reihenfolge nicht löschen, wenn ein Fehler vorliegt. Die Portierungs Reihenfolge muss neu erstellt werden, oder Sie müssen sich an die [Hilfe des PSTN-Service-Desks](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)wenden.  <br/> |Die verlorene Fluggesellschaft hat die Bestellung abgelehnt.  <br/> |
|**Abgeschlossen** <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Nein  <br/> |Die Nummern wurden erfolgreich übertragen.  <br/> |
|**Storniert** <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |Nein  <br/> |Der Administrator hat den Auftrag storniert.  <br/> |

Eine vollständige Schritt-für-Schritt-Anleitung finden Sie unter [übertragen von Telefonnummern in Teams](transfer-phone-numbers-to-teams.md).

Wenn Sie Hilfe benötigen oder weitere Telefonnummern benötigen, wenden Sie sich an den [PSTN-Service-Desk](../manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md).

## <a name="related-topics"></a>Verwandte Themen

- [Was ist ein Portierungsauftrag?](port-order-overview.md)
- [Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Verwalten von Telefonnummern für Ihre Organisation](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Nutzungsbedingungen für Notrufe](../emergency-calling-terms-and-conditions.md)
- [Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
