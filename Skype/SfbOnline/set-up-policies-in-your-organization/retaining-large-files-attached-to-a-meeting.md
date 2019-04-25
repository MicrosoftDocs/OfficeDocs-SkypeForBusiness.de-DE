---
title: Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: brendonb, markjjo
ms.topic: article
ms.assetid: 12203a1a-4a9f-4838-88c5-3740ea16ed8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen. Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center. Dieser Inhalt wird zum Umschalten wiederherstellbare Elemente Ordner in ihren Postfächern gespeichert.
ms.openlocfilehash: f9a18aaf556427ccc1fad2700b40f40ff057be6a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237518"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Beibehaltung große Dateien, einen Skype für Business Besprechung zugeordnet ist

Sie können Dateien an einen Skype für Business-Besprechung anfügen, welche Teilnehmer können dann öffnen und herunterladen. Anlagen von Skype für Business Besprechungen werden in die Postfächer der alle Teilnehmer beibehalten, dessen Postfach beweissicherungsverfahrens platziert wird, verfügt über ein Office 365-Aufbewahrungsrichtlinie angewendet oder befindet sich in einem Haltestatus Zusammenhang mit einem eDiscovery-Fall in die Office 365-Sicherheit &amp; Compliance Center. Dieser Inhalt wird zum Umschalten **Wiederherstellbare Elemente** Ordner in ihren Postfächern gespeichert.
  
Dateien, die in Postfächern in der Warteschleife beibehalten werden indiziert sind und können daher durchsucht werden, bei der Ausführung einer Inhaltssuche in das Wertpapier &amp; Compliance Center bei der Suche eines Teilnehmers Postfach. Allerdings angefügte Dateien, die größer als 30 MB sind mindestens zwei kleineren Dateien aufgeteilt werden und als komprimierte ZIP-Dateien gespeichert. Der *Inhalt* dieser kleineren Dateien ist nicht für die Suche indiziert und möglicherweise nicht in einer Inhalts-Suche zurückgegeben werden. Jedoch die *Metadaten* des diese Dateien (beispielsweise den Dateinamen und den Autor) wird für die Suche indiziert und möglicherweise in eine Inhaltssuche zurückgegeben werden.
  
> [!IMPORTANT]
> Die MaxReceiveSize und MaxSendSize auf Einstellungen für Exchange Online-Postfach können sich auf die Möglichkeit, große Dateien von Skype für Business Besprechungen beibehalten auswirken. Die Standardeinstellungen für MaxReceiveSize und MaxSendSize werden 36 MB und 35 MB. Diese Standardeinstellungen werden jedoch jede Datei aus einer Skype für geschäftliche Besprechung beizubehalten, die größer als 30 MB ist zu klein. Dies ist, da Exchange Online arbeitet mit Base64-Codierung von e-Mail-Anlagen und andere binären Daten. Wenn eine Nachricht codiert ist, wird die Größe ungefähr 33 % erhöht. Aus diesem Grund sollten, um sicherzustellen, dass große Dateien von Skype für Business Besprechungen beibehalten werden, erhöhen Sie den Wert für MaxReceiveSize und MaxSendSize auf 39 MB (also ungefähr 33 % größer als die 30 MB groß sein, die zuvor erläutert wurde) für Benutzer, die in der Warteschleife platziert werden. Anderenfalls möglicherweise eine große Datei, einen Skype für Business Besprechung zugeordnet ist, nicht beibehalten werden. Weitere Informationen zur Verwendung der **Set-Mailbox-MaxReceiveSize** und **Set-Mailbox MaxSendSize** Befehle in Exchange Online PowerShell finden Sie unter [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Postfächer, die nicht in der Warteschleife sind haben keine Besprechungsdaten gespeichert. Halten beispielsweise in einer Besprechung drei Personen in der die Postfächer der beiden Teilnehmer für die Beibehaltung markiert sind, auf die Postfächer von diese beiden Teilnehmer die Besprechungsdaten gespeichert werden, aber nicht an das Postfach von der dritte Teilnehmer, dessen Postfach nicht auf.
  
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Datenblöcke Point-Datei übertragen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
 