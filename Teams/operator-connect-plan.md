---
title: Telefonieanbieter
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Erfahren Sie mehr über Telefonieanbieter, z. B. Anforderungen und Planung der Bereitstellung.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adc229264513d7ec4ca692dca1731d7390b80dc243b4571757607c1c76b7cacb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54323947"
---
# <a name="plan-for-operator-connect"></a>Plan für Telefonieanbieter

>[!NOTE]
>Telefonieanbieter ist derzeit nur in der **öffentlichen Vorschau** verfügbar. Die öffentliche Vorschau bietet Ihnen die Möglichkeit, kommende Funktionen zu testen und Feedback zu geben. Die in der öffentlichen Vorschau enthaltenen Features sind u. U. nicht vollständig, könnten geändert werden und werden in Office 365 Government Cloud nicht unterstützt.

Telefonieanbieter ist eine weitere Option für die Bereitstellung von PSTN-Konnektivität (Public Switched Telephone Network) mit Teams und dem Telefonsystem.  

Dieser Artikel beschreibt Vorteile und Anforderungen und listet die Betreiber auf, die am Telefonieanbieter-Programm teilnehmen.  Wenn Sie sich entscheiden, dass Telefonieanbieter die richtige Lösung für Ihr Unternehmen ist, lesen Sie nach dem Lesen dieses Artikels den Abschnitt [Konfigurieren von Telefonieanbieter](operator-connect-configure.md).  

## <a name="benefits"></a>Vorteile

Wenn Ihr bestehender Betreiber am Microsoft Telefonieanbieter-Programm teilnimmt, kann er den Dienst verwalten, um Festnetzanrufe in Microsoft Teams zu ermöglichen. Das Telefonieanbieter-Programm bietet die folgenden Vorteile:

- **Nutzen bestehender Verträge oder finden eines neuen Betreibers.** Sie behalten Ihren bevorzugten Betreiber und Ihre bevorzugten Verträge oder wählen einen neuen aus einer Auswahl an teilnehmenden Betreibern aus, um Ihre Geschäftsanforderungen zu erfüllen.

- **Vom Betreiber verwaltete Infrastruktur.** Ihr Betreiber verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und der Verwaltung von Hardware sparen können.

- **Schnellere, einfachere Bereitstellung.** Sie können schnell eine Verbindung zu Ihrem Betreiber herstellen und Benutzern Telefonnummern zuweisen – alles über das Teams Admin Center.

- **Verbesserte Unterstützung und Zuverlässigkeit.** Die Betreiber bieten technischen Support und gemeinsame Service-Level-Agreements, um den Support-Service zu verbessern, während direktes Peering, das von Azure unterstützt wird, eine Eins-zu-Eins-Netzwerkverbindung für erhöhte Zuverlässigkeit schafft.

## <a name="requirements"></a>Anforderungen

 Telefonieanbieter könnte die richtige Lösung für Ihr Unternehmen sein, wenn:

- Der Microsoft-Anrufplan an Ihrem geografischen Standort nicht verfügbar ist.
- Ihr bevorzugter Operator ist Teilnehmer am Microsoft Telefonieanbieter-Programm.
- Sie möchten einen neuen Operator finden, um Anrufe in Teams zu ermöglichen.

Um die Zuweisung von Telefonnummern mit Telefonieanbieter zu aktivieren, stellen Sie sicher, dass Ihre Benutzer:

- Teams-Telefon lizenziert. Weitere Informationen finden Sie unter [Was ist ein Telefonsystem? ](what-is-phone-system-in-office-365.md) und [Zuweisen von Teams-Add-On-Lizenzen zu Benutzern](teams-add-on-licensing/assign-teams-add-on-licenses.md).
- Im TeamsOnly-Modus. Um mehr zu erfahren, siehe [Grundlegendes zur Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business](teams-and-skypeforbusiness-coexistence-and-interoperability.md).

## <a name="available-operators"></a>Verfügbare Operatoren

Die folgenden Operatoren sind Teilnehmer des Microsoft Telefonieanbieter-Programms:

| Operator | Funktion | Länderabdeckung |
| --- | --- | --- |
| `BT`  | Anrufe | Belgien, Dänemark, Finnland, Frankreich, Deutschland, Irland, Italien, Luxemburg, Niederlande, Norwegen, Polen, Südafrika, Spanien, Schweden, Schweiz, Vereinigtes Königreich |
| `Intrado` | Anrufe | Belgien, Kanada, Dänemark, Frankreich, Deutschland, Irland, Luxemburg, Niederlande, Spanien, Schweden, Vereinigtes Königreich, Vereinigte Staaten  |
| `NTT`  | Anrufe | Österreich, Belgien, Brasilien, Kanada, Tschechien, Dänemark, Finnland, Frankreich, Deutschland, Irland, Italien, Luxemburg, Mexiko, Niederlande, Norwegen, Polen, Portugal, Puerto Rico, Rumänien, Südafrika, Spanien, Schweden, Schweiz, Vereinigtes Königreich, Vereinigte Staaten |
| `NuWave` | Anrufe | Österreich, Belgien, Kanada, Dänemark, Frankreich, Deutschland, Irland, Italien, Niederlande, Portugal, Spanien, Schweden, Schweiz, Großbritannien, USA   |
| `Orange Business Services` | Anrufe | Österreich, Belgien, Tschechien, Dänemark, Finnland, Frankreich, Französisch-Guayana, Deutschland, Guadeloupe, Irland, Italien, Luxemburg, Martinique, Mayotte, Niederlande, Norwegen, Polen, Portugal, Réunion, Saint Barthélemy, Saint Martin, Spanien, Svalbard, Schweden, Schweiz, Vereinigtes Königreich  |
| `Pure IP` | Anrufe | Australien, Österreich, Belgien, Brasilien, Bulgarien, Kanada, Chile, Kolumbien, Kroatien, Zypern, Tschechien, Dänemark, Finnland, Frankreich, Deutschland, Griechenland, Sonderverwaltungszone Hongkong, Irland, Italien, Japan, Litauen, Luxemburg, Malaysia, Mexiko, Niederlande, Neuseeland, Norwegen, Panama, Polen, Portugal, Puerto Rico, Rumänien, Singapur, Slowakei, Slowenien, Südafrika, Spanien, Schweden, Schweiz, Großbritannien, USA  |
| `Rogers Business` | Anrufe | Kanada  |
| `TATA Communications` | Anrufe | Australien, Österreich, Belgien, Kanada, Tschechien, Dänemark, Frankreich, Deutschland, Hongkong, Ungarn, Irland, Italien, Malaysia, Mexiko, Niederlande, Neuseeland, Polen, Portugal, Rumänien, Singapur, Südkorea, Spanien, Schweden, Schweiz, Thailand, Großbritannien, USA |
| `Telekom Deutschland` | Anrufe | Deutschland  |
| `Telenor` | Anrufe | Dänemark, Finnland, Norwegen, Schweden  |
| `Verizon` | Anrufe | Vereinigte Staaten von Amerika |
