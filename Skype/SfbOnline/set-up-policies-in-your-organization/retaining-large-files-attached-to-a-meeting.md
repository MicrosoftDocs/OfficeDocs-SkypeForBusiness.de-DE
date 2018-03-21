---
title: "Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen. Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center. Dieser Inhalt wird zum Umschalten wiederherstellbare Elemente Ordner in ihren Postfächern gespeichert."
ms.openlocfilehash: 59e1470d36aac988b1e0ff6ee40ebc1fb61967ed
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2018
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist

Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen. Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center. Dieser Inhalt wird zum Umschalten **Wiederherstellbare Elemente** Ordner in ihren Postfächern gespeichert.
  
Dateien, die in Postfächern in der Warteschleife beibehalten werden indiziert sind und können daher durchsucht werden, bei der Ausführung einer Inhaltssuche in das Wertpapier &amp; Compliance Center bei der Suche eines Teilnehmers Postfach. Allerdings angefügte Dateien, die größer als 39 MB sind mindestens zwei kleineren Dateien aufgeteilt werden und als komprimierte ZIP-Dateien gespeichert. Der *Inhalt* dieser kleineren Dateien ist nicht für die Suche indiziert und möglicherweise nicht in einer Inhalts-Suche zurückgegeben werden. Die *Metadaten* des diese Dateien (beispielsweise den Dateinamen und den Autor) wird für die Suche indiziert und möglicherweise in eine Inhaltssuche zurückgegeben werden.
  
> [!NOTE]
> Wenn das Postfach voll ist, oder den Administrator des Mandanten MaxSendSize konfiguriert um kleiner als 39 MB sein, hochgeladen Datei, die Daten nicht in allen aufbewahrt werden sollen. Der Standardwert MaxSendSize ist 150 MB, aber Mandanten-Admins können MaxSendSize liegend so klein wie 1 MB konfigurieren. 
  
Postfächer, die nicht in der Warteschleife sind haben keine Besprechungsdaten gespeichert. Halten beispielsweise in einer Besprechung drei Personen in der die Postfächer der beiden Teilnehmer für die Beibehaltung markiert sind, auf die Postfächer von diese beiden Teilnehmer die Besprechungsdaten gespeichert werden, aber nicht an das Postfach von der dritte Teilnehmer, dessen Postfach nicht auf.
  
## <a name="related-topics"></a>See Also
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Datenblöcke Point-Datei übertragen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  