---
title: Aufbewahren großer Dateien, die an eine Skype for Business Besprechung angefügt sind
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
description: Sie können Dateien an eine Skype for Business Besprechung anfügen, die die Teilnehmer dann öffnen und herunterladen können. An Skype for Business Besprechungen angefügte Dateien werden in den Postfächern jedes Teilnehmers aufbewahrt, dessen Postfach im Beweissicherungsverfahren aufbewahrt wird, eine Microsoft 365- oder Office 365 Aufbewahrungsrichtlinie angewendet wurde oder in einem Haltebereich platziert wird, der einem eDiscovery-Fall im Microsoft Purview-Complianceportal zugeordnet ist. Dieser Inhalt wird in den Ordnern "Wiederherstellbare Elemente" der Teilnehmer in ihren Postfächern gespeichert.
ms.openlocfilehash: 35792e3415d3def0b8ac45ab39e9dec65f2f7725
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922436"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Aufbewahren großer Dateien, die an eine Skype for Business Besprechung angefügt sind

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Sie können Dateien an eine Skype for Business Besprechung anfügen, die die Teilnehmer dann öffnen und herunterladen können. An Skype for Business Besprechungen angefügte Dateien werden in den Postfächern jedes Teilnehmers aufbewahrt, dessen Postfach im Beweissicherungsverfahren aufbewahrt wird, eine Microsoft 365- oder Office 365 Aufbewahrungsrichtlinie angewendet wurde oder in einem Haltebereich platziert wird, der einem eDiscovery-Fall im Microsoft Purview-Complianceportal zugeordnet ist. Dieser Inhalt wird in den Ordnern " **Wiederherstellbare Elemente** " der Teilnehmer in ihren Postfächern gespeichert.
  
Dateien, die in Postfächern im Haltebereich aufbewahrt werden, werden indiziert und können daher beim Ausführen einer Inhaltssuche im Security &amp; Compliance Center beim Durchsuchen des Postfachs eines Teilnehmers durchsucht werden. Angefügte Dateien, die größer als 30 MB sind, werden jedoch in zwei oder mehr kleinere Dateien aufgeteilt und als komprimierte Dateien (.zip) gespeichert. Der  *Inhalt*  dieser kleineren Dateien wird nicht für die Suche indiziert und möglicherweise nicht in einer Inhaltssuche zurückgegeben. Die *Metadaten*  dieser Dateien (z. B. Dateiname und Autor) werden jedoch für die Suche indiziert und möglicherweise in einer Inhaltssuche zurückgegeben.
  
> [!IMPORTANT]
> Die Einstellungen "MaxReceiveSize" und "MaxSendSize" für ein Exchange Online Postfach können sich auf die Möglichkeit auswirken, große Dateien aus Skype for Business Besprechungen aufzubewahren. Die Standardeinstellungen für MaxReceiveSize und MaxSendSize sind 36 MB bzw. 35 MB. Diese Standardeinstellungen sind jedoch zu klein, um eine Datei aus einer Skype for Business Besprechung aufzubewahren, die größer als 30 MB ist. Dies liegt daran, dass Exchange Online Base64-Codierung von Nachrichtenanlagen und anderen Binärdaten verwendet. Wenn eine Nachricht codiert wird, wird ihre Größe um ca. 33 % erhöht. Um sicherzustellen, dass große Dateien aus Skype for Business Besprechungen beibehalten werden, empfehlen wir daher, den Wert für MaxReceiveSize und MaxSendSize auf 39 MB zu erhöhen (was ungefähr 33 % größer als die zuvor erläuterte Größenbeschränkung von 30 MB ist) für Benutzer, die in den Haltebereich versetzt werden. Andernfalls wird eine große Datei, die an eine Skype for Business Besprechung angefügt ist, möglicherweise nicht beibehalten. Weitere Informationen zur Verwendung der Befehle **Set-Mailbox -MaxReceiveSize** und **Set-Mailbox -MaxSendSize** in Exchange Online PowerShell finden Sie unter [Set-Mailbox](/powershell/module/exchange/mailboxes/Set-Mailbox).
  
In Postfächern, die sich nicht im Haltebereich befinden, werden keine Besprechungsdaten gespeichert. In einer Besprechung mit drei Personen, in der die Postfächer von zwei Teilnehmern zur Aufbewahrung markiert sind, werden die Besprechungsdaten beispielsweise in den Postfächern dieser beiden Teilnehmer gespeichert, jedoch nicht im Postfach des dritten Teilnehmers, dessen Postfach nicht im Haltebereich ist.
  
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
