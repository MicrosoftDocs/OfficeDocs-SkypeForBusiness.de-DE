---
title: Bericht zur Verwendung von Audiokonferenzen für ausgehende Anrufe
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: fafan
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: Erfahren Sie, welche Länder und Regionen über Einwahlkonferenznummern verfügen und wie sie automatisch zugewiesen werden.
ms.openlocfilehash: 16cdae3a377d5ce87c218affc4944051f14f2631
ms.sourcegitcommit: 0967f725aad0a7b9c430b2e30a37ea333007558a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2022
ms.locfileid: "65106443"
---
# <a name="audio-conferencing-dial-out-usage-report"></a>Bericht zur Verwendung von Audiokonferenzen für ausgehende Anrufe

Der Bericht zur Verwendung von Audiokonferenzen für Ausgehende Anrufe im Teams Admin Center bietet Ihnen einen Überblick über die Nutzung und die Für den Audiokonferenz-Auswahldienst ausgegebenen Dollar. Dieser Bericht ermöglicht Es Administratoren, Daten auf Benutzerebene in Bezug auf ausgegebene Kommunikationsguthaben und verwendete Ausgehende Minuten zu nutzen. Es hilft Administratoren dabei, die künftig benötigten Kommunikationsguthaben von jedem Beliebigen Zeitpunkt aus zu ermitteln.

## <a name="view-the-audio-conferencing-dial-out-usage-report"></a>Anzeigen des Verwendungsberichts für Audiokonferenzen für ausgehende Anrufe

Wählen Sie im linken Navigationsbereich des Microsoft Teams Admin Centers  **selectAnalytics &**  **reportsUsage-Berichte** > aus. Wählen Sie auf der Registerkarte " **View-Berichte** " unter  **"Bericht**" den Bericht über die **Verwendung von Audiokonferenz-Ausgehenden aus**.

 **UnderDate range**, you can select a predefined range of 7 or 28 days, or set a custom range.

 **UnderCountry Previsioned**, select a preferred country, or select all, and then  **selectRun report**.

## <a name="report-details"></a>Berichtsdetails

Der Bericht über die Verwendung von Audiokonferenzen für Ausgehende Anrufe verfügt über drei Hauptregisterkarten, auf denen Informationen in einem Diagrammformat angezeigt werden, das auf dem Bereich basiert, der in den dropdowns darüber ausgewählt wurde:

- Auf der Registerkarte **"Kosten** " werden die Kommunikationsguthaben angezeigt, die für den ausgewählten Zeitraum aufgewendet wurden, und die nachstehende Tabelle enthält Details auf Benutzerebene.
- Auf der Registerkarte " **Minuten der Verwendung** " werden die Gesamtzahl der ausgehenden Minuten im ausgewählten Zeitraum und die unten aufgeführte Tabelle mit den Details auf Benutzerebene angezeigt.
- Auf der Registerkarte " **Ausgehende Anrufe** " wird die Gesamtzahl der Ausgehenden Anrufe über den ausgewählten Zeitraum angezeigt, und die folgende Tabelle enthält Details auf Benutzerebene.

Jeder Bericht hat ein Datum für die Generierung. Die Berichte spiegeln in der Regel eine Latenz von 24 bis 48 Stunden ab der Aktivitätszeit wider.

> [!NOTE]
> Alle ausgehenden Gesprächsminuten/Anrufe/Gutschriften werden unter dem Besprechungsorganisator gezählt. Es ist nicht unbedingt dieselbe Person, die sich auswählte.

### <a name="cost-tab"></a>Registerkarte "Kosten"

Am oberen Rand dieses Registerkartenabschnitts befindet sich ein Diagramm mit einer Linie, in der Kosteninformationen über den Datumsbereich und für das ausgewählte Land bzw. die ausgewählten Länder angezeigt werden.

Unter dem Diagramm befindet sich ein Abschnitt " **Kosten** " mit einem Preis, der die Gesamtkosten pro Anrufminuten innerhalb des ausgewählten Zeitraums darstellt.

### <a name="minutes-of-use-tab"></a>Registerkarte "Minuten der Verwendung"

Am oberen Rand dieses Registerkartenabschnitts befindet sich ein Diagramm, in dem eine Linie angezeigt wird, in der Minuten für die Verwendung über den Datumsbereich und für das ausgewählte Land bzw. die ausgewählten Länder angezeigt werden.

Unterhalb des Diagramms befindet sich ein Abschnitt " **Minuten der Verwendung** ", der die Gesamtzahl der innerhalb des ausgewählten Zeitraums verwendeten Anrufe anzeigt.

### <a name="dial-out-calls"></a>Ausgehende Anrufe

Am oberen Rand dieses Registerkartenabschnitts befindet sich ein Diagramm mit einer Linie, in der Ausgehende Anrufe über den Datumsbereich und für das ausgewählte Land bzw. die ausgewählten Länder angezeigt werden.

Unterhalb des Diagramms befindet sich ein Abschnitt " **Ausgehende Anrufe** ", in dem die Gesamtzahl der Ausgehenden Anrufe innerhalb des ausgewählten Zeitraums angezeigt wird.

## <a name="using-the-report"></a>Verwenden des Berichts

Unten auf der Seite befindet sich eine Tabelle, in der Aufschlüsselungen auf Benutzerebene mit den folgenden Überschriften angezeigt werden:

- Besprechungsorganisator
- Username
- Benutzerminuten
- Guthaben ausgegeben
- Währung

Wenn Sie nach der Verwendung für einen bestimmten Benutzer suchen müssen, befindet sich rechts über dem Bericht eine Suchleiste. Die Namen des Besprechungsorganisators sind alle auswählbaren Links, die Sie zu einem detaillierteren Nutzungsbericht für den Benutzer führen. Diese Benutzeransicht verfügt über die gleichen drei Registerkarten wie der Hauptbericht, im Diagramm oben auf der Seite werden jedoch Details für den jeweiligen Benutzer angezeigt.

Sie können jeden in dieser Tabelle angezeigten Bericht zur Offlineanalyse in eine CSV-Datei exportieren. Wählen Sie **"Zum Excel exportieren**" und dann auf der Registerkarte "**Downloads**" die Option "**Herunterladen**" aus, um den Bericht herunterzuladen, sobald er bereit ist.
