---
title: Beibehalten großer Dateien, die an eine Skype for Business-Besprechung angefügt sind
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Sie können Dateien an eine Skype for Business-Besprechung anfügen, die die Teilnehmer dann öffnen und herunterladen können. An Skype for Business-Besprechungen angefügte Dateien werden in den Postfächern aller Teilnehmer aufbewahrt, deren Postfach in einem Prozessaufbewahrungsverfahren platziert wird, eine Microsoft 365- oder Office 365-Aufbewahrungsrichtlinie angewendet wird oder die einem eDiscovery-Fall im Microsoft 365 Compliance Center zugeordnet ist. Dieser Inhalt wird in den Ordnern "Wiederherstellbare Elemente" der Teilnehmer in ihren Postfächern gespeichert.
ms.openlocfilehash: 515f8b68db04a7acfc8eab2d7c639157cdb0da8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100571"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Beibehalten großer Dateien, die an eine Skype for Business-Besprechung angefügt sind

Sie können Dateien an eine Skype for Business-Besprechung anfügen, die die Teilnehmer dann öffnen und herunterladen können. An Skype for Business-Besprechungen angefügte Dateien werden in den Postfächern aller Teilnehmer aufbewahrt, deren Postfach in einem Prozessaufbewahrungsverfahren platziert wird, eine Microsoft 365- oder Office 365-Aufbewahrungsrichtlinie angewendet wird oder die einem eDiscovery-Fall im Microsoft 365 Compliance Center zugeordnet ist. Dieser Inhalt wird in den **Ordnern "Wiederherstellbare** Elemente" der Teilnehmer in ihren Postfächern gespeichert.
  
Dateien, die in postfächern im Halteraum aufbewahrt werden, werden indiziert und können daher beim Ausführen einer Inhaltssuche im Security Compliance Center durchsucht werden, wenn das Postfach eines &amp; Teilnehmers durchsucht wird. Angefügte Dateien, die größer als 30 MB sind, werden jedoch in zwei oder mehr kleinere Dateien aufgeteilt und als komprimierte (ZIP)-Dateien gespeichert. Der  *Inhalt*  dieser kleineren Dateien wird nicht für die Suche indiziert und möglicherweise nicht in einer Inhaltssuche zurückgegeben. Die Metadaten *dieser*  Dateien (z. B. der Dateiname und der Autor) werden jedoch für die Suche indiziert und können in einer Inhaltssuche zurückgegeben werden.
  
> [!IMPORTANT]
> Die Einstellungen MaxReceiveSize und MaxSendSize für ein Exchange Online-Postfach können sich auf die Möglichkeit auswirken, große Dateien aus Skype for Business-Besprechungen zu behalten. Die Standardeinstellungen für MaxReceiveSize und MaxSendSize betragen 36 MB bzw. 35 MB. Diese Standardeinstellungen sind jedoch zu klein, um eine Beliebige Datei aus einer Skype for Business-Besprechung zu behalten, die größer als 30 MB ist. Dies liegt daran, dass Exchange Online die Base64-Codierung von Nachrichtenanlagen und anderen Binärdaten verwendet. Wenn eine Nachricht codiert ist, wird ihre Größe um ca. 33 % erhöht. Um sicherzustellen, dass große Dateien aus Skype for Business-Besprechungen beibehalten werden, empfiehlt es sich daher, den Wert für MaxReceiveSize und MaxSendSize auf 39 MB zu erhöhen (was ungefähr 33 % größer als die zuvor erläuterte Größenbeschränkung von 30 MB ist) für Benutzer, die in den Halteraum gesetzt werden. Andernfalls wird eine große Datei, die an eine Skype for Business-Besprechung angefügt ist, möglicherweise nicht beibehalten. Weitere Informationen zur Verwendung der Befehle **Set-Mailbox -MaxReceiveSize** und **Set-Mailbox -MaxSendSize** in Exchange Online PowerShell finden Sie unter [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Postfächer, die sich nicht im Halteraum befinden, haben keine Besprechungsdaten gespeichert. In einer Besprechung mit drei Personen, in der die Postfächer von zwei Teilnehmern für die Aufbewahrung gekennzeichnet sind, werden die Besprechungsdaten in den Postfächern dieser beiden Teilnehmer gespeichert, jedoch nicht im Postfach des dritten Teilnehmers, dessen Postfach nicht im Halteraum liegt.
  
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
