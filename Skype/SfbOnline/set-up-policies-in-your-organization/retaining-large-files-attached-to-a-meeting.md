---
title: Beibehalten von umfangreichen Dateien, die an eine Skype for Business-Besprechung angefügt sind
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
description: Sie können Dateien an eine Skype for Business-Besprechung anfügen, die Teilnehmer dann öffnen und herunterladen können. Dateien, die an Skype for Business-Besprechungen angefügt sind, werden in den Postfächern von Teilnehmern aufbewahrt, deren Postfach in einem Rechtsstreit gehalten wird, auf die eine Office 365-Aufbewahrungsrichtlinie angewendet wurde oder die &amp; mit einem eDiscovery-Fall im Office 365 Security Compliance Center verknüpft ist. Dieser Inhalt wird in den Ordnern der Teilnehmer, die sich in ihren Postfächern befinden, gespeichert.
ms.openlocfilehash: fdd6786cb9b7e5535abee47eb1f0b538b6a22b45
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706650"
---
# <a name="retaining-large-files-attached-to-a-skype-for-business-meeting"></a>Beibehalten von umfangreichen Dateien, die an eine Skype for Business-Besprechung angefügt sind

Sie können Dateien an eine Skype for Business-Besprechung anfügen, die Teilnehmer dann öffnen und herunterladen können. Dateien, die an Skype for Business-Besprechungen angefügt sind, werden in den Postfächern von Teilnehmern aufbewahrt, deren Postfach in einem Rechtsstreit gehalten wird, auf die eine Office 365-Aufbewahrungsrichtlinie angewendet wurde oder die &amp; mit einem eDiscovery-Fall im Office 365 Security Compliance Center verknüpft ist. Dieser Inhalt wird in **den Ordnern der** Teilnehmer, die sich in ihren Postfächern befinden, gespeichert.
  
Dateien, die in Postfächern aufbewahrt werden, sind indiziert und können daher beim Ausführen einer Inhaltssuche im Security &amp; Compliance Center beim Durchsuchen des Postfachs eines Teilnehmers durchsucht werden. Angefügte Dateien, die größer als 30 MB sind, werden jedoch in zwei oder mehr kleinere Dateien aufgeteilt und als komprimierte Dateien (zip) gespeichert. Der *Inhalt* dieser kleineren Dateien ist nicht für die Suche indiziert und wird möglicherweise nicht in einer Inhaltssuche zurückgegeben. Die *Metadaten* dieser Dateien (wie Dateinamen und Autor) werden jedoch für die Suche indiziert und möglicherweise in einer Inhaltssuche zurückgegeben.
  
> [!IMPORTANT]
> Die MaxReceiveSize-und MaxSendSize-Einstellungen für ein Exchange Online-Postfach können sich auf die Möglichkeit auswirken, große Dateien von Skype for Business-Besprechungen zu speichern. Die Standardeinstellungen für MaxReceiveSize und MaxSendSize sind 36 MB bzw. 35 MB. Diese Standardeinstellungen sind jedoch zu klein, um eine Datei aus einer Skype for Business-Besprechung mit einer Größe von mehr als 30 MB beizubehalten. Dies liegt daran, dass Exchange Online die Base64-Codierung von Nachrichtenanlagen und anderen binären Daten verwendet. Beim Codieren einer Nachricht wird die Größe um etwa 33% erhöht. Um sicherzustellen, dass große Dateien von Skype for Business-Besprechungen beibehalten werden, empfehlen wir, den Wert für MaxReceiveSize und MaxSendSize auf 39 MB zu erhöhen (was ungefähr 33% größer ist als der zuvor erläuterte Grenzwert von 30 MB). für Benutzer, die in Wartestellung gesetzt werden. Andernfalls wird eine große Datei, die an eine Skype for Business-Besprechung angefügt ist, möglicherweise nicht beibehalten. Weitere Informationen zum Verwenden der Befehle " **Satz-Postfach-MaxReceiveSize** " und " **Satz-Postfach-MaxSendSize** " in Exchange Online PowerShell finden Sie unter [Einrichten des Postfachs](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Set-Mailbox).
  
Für Postfächer, die nicht gesperrt sind, werden keine Besprechungsdaten gespeichert. In einer Besprechung mit drei Personen, bei der die Postfächer von zwei Teilnehmern für die Aufbewahrung markiert sind, werden die Besprechungsdaten in den Postfächern dieser beiden Teilnehmer gespeichert, jedoch nicht in dem Postfach des dritten Teilnehmers, dessen Postfach nicht gesperrt ist.
  
## <a name="related-topics"></a>Verwandte Themen
[Erstellen von benutzerdefinierten externen Zugriffsrichtlinien](create-custom-external-access-policies.md)

[Blockieren von Punkt-zu-Punkt-Dateiübertragungen](block-point-to-point-file-transfers.md)

[Einrichten von Clientrichtlinien für Ihre Organisation](set-up-client-policies-for-your-organization.md)

[Einrichten von Konferenzrichtlinien in Ihrer Organisation](set-up-conferencing-policies-for-your-organization.md)
  
  
 