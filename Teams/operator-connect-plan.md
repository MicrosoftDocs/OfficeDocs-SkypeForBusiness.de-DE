---
title: Operatoren Verbinden
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
description: Weitere Informationen zu Operatoren Verbinden, z. B. Anforderungen und Planung der Bereitstellung.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694540"
---
# <a name="plan-for-operator-connect"></a>Planen von Operatoren Verbinden

>[!NOTE]
>Operatoren Verbinden derzeit nur in der **öffentlichen Vorschau verfügbar.** In der öffentlichen Vorschau können Sie anstehende Features testen und Feedback geben. Features, die in public preview enthalten sind, sind möglicherweise nicht vollständig, werden möglicherweise geändert und werden in der Office 365 Government unterstützt.

Operator Verbinden ist eine weitere Option für die Bereitstellung von PSTN-Konnektivität (Public Switched Telephone Network) mit Teams und Telefonsystem.  

In diesem Artikel werden die Vorteile und Anforderungen beschrieben und die am Operator-Programm teilnehmenden Operatoren Verbinden aufgeführt.  Wenn Sie entscheiden, Verbinden die richtige Lösung für Ihre Organisation ist, lesen Sie diesen Artikel unter Konfigurieren der [Operatoren Verbinden.](operator-connect-configure.md)  

## <a name="benefits"></a>Vorteile

Wenn Ihr Verbinden Teilnehmer am Microsoft Operator Verbinden-Programm ist, kann er den Dienst verwalten, um PSTN-Anrufe an Teams. Das Operatoren-Verbinden bietet die folgenden Vorteile:

- **Nutzen Sie vorhandene Verträge, oder suchen Sie einen neuen Operator.** Sie behalten Ihren bevorzugten Operator und Ihre Verträge bei oder wählen einen neuen aus einer Auswahl von teilnehmenden Operatoren aus, um Ihre geschäftlichen Anforderungen zu erfüllen.

- **Von Operatoren verwaltete Infrastruktur.** Ihr Operator verwaltet die PSTN-Anrufdienste und Session Border Controller (SBCs), sodass Sie beim Kauf und bei der Verwaltung von Hardware sparen können.

- **Schnellere und einfachere Bereitstellung.** Sie können schnell eine Verbindung mit Ihrem Netzbetreiber herstellen und Benutzern Telefonnummern zuweisen – alles über Teams Admin Center.

- **Verbesserte Unterstützung und Zuverlässigkeit.** Operatoren bieten Vereinbarungen zum technischen Support und Vereinbarungen zum Ebene der gemeinsamen Dienste zur Verbesserung des Supportdienstes, während durch direktes Peering, das von Azure unterstützt wird, eine 1:1-Netzwerkverbindung für eine höhere Zuverlässigkeit erstellt wird.

## <a name="requirements"></a>Anforderungen

 Operatoren Verbinden die richtige Lösung für Ihre Organisation, wenn:

- Microsoft-Anrufplan ist in Ihrem geografischen Standort nicht verfügbar.
- Ihr bevorzugter Operator ist ein Teilnehmer am Microsoft Operator Verbinden Programm.
- Sie möchten nach einem neuen Operator suchen, um das Aufrufen von in einer Teams.

Zum Aktivieren von Telefonnummernzuweisungen mit operator Verbinden, stellen Sie sicher, dass Ihre Benutzer dies sind:

- Teams Telefon lizenziert. Weitere Informationen finden Sie unter [Was ist Telefonsystem?](what-is-phone-system-in-office-365.md) und [Zuweisen Teams Add-On-Lizenzen zu Benutzern.](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- Im TeamsOnly-Modus. Weitere Informationen finden Sie unter [Verstehen Microsoft Teams und Skype for Business Koexistenz und Interoperabilität.](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="available-operators"></a>Verfügbare Operatoren

Die folgenden Operatoren sind Teilnehmer am Microsoft Operator Verbinden Programm:

| Vermittlung | Funktion | Länderabdeckung |
| --- | --- | --- |
| `BT`  | Anrufe | Belgien, Dänemark, Finnland, Frankreich, Deutschland, Irland, Italien, Luxemburg, Niederlande, Norwegen, Polen, Südafrika, Spanien, Schweden, Schweiz, Vereinigtes Königreich |
| `Intrado` | Anrufe | Belgien, Kanada, Dänemark, Frankreich, Deutschland, Irland, Luxemburg, Niederlande, Spanien, Schweden, Vereinigtes Königreich, Vereinigte Staaten  |
| `NTT`  | Anrufe | Österreich, Belgien, Brasilien, Kanada, Tschechien, Dänemark, Finnland, Frankreich, Deutschland, Irland, Italien, Luxemburg, Mexiko, Niederlande, Norwegen, Polen, Portugal, Puerto Rico, Rumänien, Südafrika, Spanien, Schweden, Schweiz, Vereinigtes Königreich, Vereinigte Staaten |
| `NuWave` | Anrufe | Österreich, Belgien, Kanada, Dänemark, Frankreich, Deutschland, Irland, Italien, Niederlande, Portugal, Spanien, Schweden, Schweiz, Vereinigtes Königreich, Vereinigte Staaten   |
| `Orange Business Services` | Anrufe | Österreich, Belgien, Tschechien, Dänemark, Finnland, Frankreich, Französisch-Guiana, Deutschland, Guadeloupe, Irland, Italien, Luxemburg, Martinique, Mayotte, Niederlande, Norwegen, Polen, Portugal, Réunion, St. Saint-Martin, Spanien, Svalbard, Schweden, Schweiz, Vereinigtes Königreich  |
| `Pure IP` | Anrufe | Australien, Österreich, Belgien, Brasilien, Bulgarien, Kanada, Chile, Kolumbien, Kroatien, Zypern, Tschechien, Dänemark, Finnland, Frankreich, Deutschland, Griechenland, Hongkong S.A.R., Irland, Italien, Japan, Litauen, Luxemburg, Malaysia, Mexiko, Niederlande, Neuseeland, Norwegen, Panama, Polen, Portugal, Puerto Rico, Rumänien, Singapur, Slowakei, Slowenien, Südafrika, Spanien, Schweden, Schweiz, Vereinigtes Königreich, VEREINIGTE Staaten  |
| `Rogers Business` | Anrufe | Kanada  |
| `TATA Communications` | Anrufe | Australien, Österreich, Belgien, Kanada, Tschechisch, Dänemark, Frankreich, Deutschland, Hongkong S.A.R., Ungarn, Irland, Italien, Malaysia, Mexiko, Niederlande, Neuseeland, Polen, Portugal, Rumänien, Singapur, Südkorea, Spanien, Schweden, Schweiz, Thailand, Vereinigtes Königreich, Vereinigte Staaten |
| `Telekom Deutschland` | Anrufe | Deutschland  |
| `Telenor` | Anrufe | Dänemark, Finnland, Norwegen, Schweden  |
| `Verizon` | Anrufe | Vereinigte Staaten |
