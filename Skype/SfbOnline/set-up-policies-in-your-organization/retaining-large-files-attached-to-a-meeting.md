---
title: Beibehalten großer Dateien, die an eine Besprechung Skype for Business sind
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Sie können Dateien an eine Besprechung Skype for Business anfügen, die dann von den Teilnehmern geöffnet und heruntergeladen werden kann. Dateien, die an Skype for Business-Besprechungen angefügt sind, werden in den Postfächern jedes Teilnehmers aufbewahrt, dessen Postfach in das Halteverfahren für ein Rechtsstreitigkeiten gesetzt wird, auf die eine Microsoft 365- oder Office 365-Aufbewahrungsrichtlinie angewendet wird oder die im Microsoft 365 Compliance Center einem eDiscovery-Fall zugeordnet ist. Dieser Inhalt wird in den Ordnern "Wiederherstellbare Elemente" von Teilnehmern in ihren Postfächern gespeichert.
ms.openlocfilehash: 1733cb1b0111bb83bbeddf5253bd1b65b919a4a0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58581989"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Beibehalten großer Dateien, die an eine Besprechung Skype for Business sind

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Sie können Dateien an eine Besprechung Skype for Business anfügen, die dann von den Teilnehmern geöffnet und heruntergeladen werden kann. Dateien, die an Skype for Business-Besprechungen angefügt sind, werden in den Postfächern jedes Teilnehmers aufbewahrt, dessen Postfach in das Halteverfahren für ein Rechtsstreitigkeiten gesetzt wird, auf die eine Microsoft 365- oder Office 365-Aufbewahrungsrichtlinie angewendet wird oder die im Microsoft 365 Compliance Center einem eDiscovery-Fall zugeordnet ist. Dieser Inhalt wird in  den Ordnern "Wiederherstellbare Elemente" von Teilnehmern in ihren Postfächern gespeichert.
  
Dateien, die in im Haltespeicher aufbewahrten Postfächern aufbewahrt werden, werden indiziert und können daher durchsucht werden, wenn im Security Compliance Center eine Inhaltssuche ausgeführt wird, wenn das Postfach eines &amp; Teilnehmers durchsucht wird. Angefügte Dateien, die größer als 30 MB sind, werden jedoch in zwei oder mehr kleinere Dateien aufgeteilt und als komprimierte (.zip) Dateien gespeichert. Der  *Inhalt*  dieser kleineren Dateien wird nicht für die Suche indiziert und möglicherweise nicht in einer Inhaltssuche zurückgegeben. Die Metadaten *dieser*  Dateien (z. B. Dateiname und Autor) werden jedoch für die Suche indiziert und bei einer Inhaltssuche zurückgegeben.
  
> [!IMPORTANT]
> Die Einstellungen MaxReceiveSize und MaxSendSize für ein Exchange Online-Postfach können die Möglichkeit zur Aufbewahrung großer Dateien aus Skype for Business beeinträchtigen. Die Standardeinstellungen für MaxReceiveSize und MaxSendSize sind 36 MB bzw. 35 MB. Diese Standardeinstellungen sind jedoch zu klein, um eine Datei aus einer Skype for Business beibehalten zu können, die größer als 30 MB ist. Dies liegt daran, Exchange Online Base64-Codierung von Nachrichtenanlagen und anderen Binärdaten verwendet. Wenn eine Nachricht codiert ist, wird ihre Größe um ca. 33 % erhöht. Um sicherzustellen, dass große Dateien aus Skype for Business-Besprechungen beibehalten werden, empfehlen wir daher, den Wert für MaxReceiveSize und MaxSendSize für Benutzer, die in einen Halteraum platziert sind, auf 39 MB zu erhöhen (ungefähr 33 % größer als die zuvor erläuterte Größenbeschränkung von 30 MB). Andernfalls wird eine große Datei, die an eine Besprechung Skype for Business, möglicherweise nicht beibehalten. Weitere Informationen zur Verwendung der Befehle **Set-Mailbox -MaxReceiveSize** und **Set-Mailbox -MaxSendSize** in Exchange Online PowerShell finden Sie unter [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Bei Postfächern, die sich nicht im Halteraum befinden, werden keine Besprechungsdaten gespeichert. In einer Besprechung mit drei Personen, bei der die Postfächer von zwei Teilnehmern für die Aufbewahrung gekennzeichnet sind, werden die Besprechungsdaten beispielsweise in den Postfächern dieser beiden Teilnehmer gespeichert, jedoch nicht im Postfach des dritten Teilnehmers, dessen Postfach nicht im Halteraum ist.
  
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
