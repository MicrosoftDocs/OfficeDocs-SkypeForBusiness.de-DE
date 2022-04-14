---
title: Ablauffunktion für Besprechungsaufzeichnungen
author: cichur
ms.author: v-cichur
ms.reviewer: ''
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Erfahren Sie mehr über das Ablauffeature für Besprechungsaufzeichnungen in Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67cbef7e6fad2c9620de17f89b8b3a4fe641368e
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853226"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Ablauffunktion für Besprechungsaufzeichnungen – Häufig gestellte Fragen

**Worin besteht die Änderung?**

Wir führen eine standardmäßige Ablaufeinstellung von 120 Tagen für *alle* neu erstellten Teams Besprechungsaufzeichnungen (TMRs) ein. Dies ist standardmäßig für alle Mandanten aktiviert, und Sie müssen es deaktivieren, wenn Sie dieses Feature nicht möchten. Das OneDrive- und SharePoint-System überwacht das Ablaufdatum, das auf allen TMRs festgelegt ist, und verschiebt tmRs automatisch an ihrem Ablaufdatum in den Papierkorb.

**Warum wird diese Änderung eingeführt?**

Wir haben Ihre Anforderungen für das Ablauffeature für Besprechungsaufzeichnungen beantwortet. Dies ist ein einfacher Housekeeping-Mechanismus, um die Speicher unübersichtlich zu reduzieren, die durch kalte TMR entsteht. Im Durchschnitt werden 99 % der TMRs nach 120 Tagen nie wiederbeobachten.

**Warum wird dies standardmäßig aktiviert sein?**

Wir glauben, dass fast alle Kunden von der reduzierten Speicherlast ihres Mandanten profitieren werden, indem Sie Aufzeichnungen entfernen, die wahrscheinlich nach 120 Tagen nie wieder angezeigt werden. Es ist unser Ziel, allen Kunden standardmäßig ein möglichst sauberes Erlebnis zu bieten.

**Wie wird das Ablaufdatum berechnet?**

Das Ablaufdatum wird als der Tag berechnet, an dem es erstellt wird, plus der Standardanzahl von Tagen, die in der Teams Richtlinie vom Administrator festgelegt wurden.

**Wie kann ein Administrator das Ablaufdatum ändern?**

Administratoren können die Standardablaufeinstellung in ihrer Teams Richtlinienkonsole bearbeiten. Diese Änderung wirkt sich ab diesem Zeitpunkt nur noch auf neu erstellte TMRs aus. Dies wirkt sich nicht auf Aufzeichnungen vor diesem Datum aus.

Administratoren können das Ablaufdatum für vorhandene TmRs nicht ändern. Dies geschieht, um die Entscheidung des Benutzers zu schützen, der besitzer des TMR ist.

**Wem wirkt sich das aus?**

Jeder, der TMRs in OneDrive oder SharePoint speichert.

**Warum sollte ich dieses Feature verwenden?**

Dieses Feature ist standardmäßig aktiviert. Um sie zu deaktivieren, ändern Sie die Standardablaufeinstellung in der Teams-Richtlinienkonsole in **"Kein Ablaufdatum**".
Sie sollten dies verwenden, um den von Teams Besprechungsdatensätzen gesteuerten Speicherverbrauch von OneDrive oder SharePoint für Die Cloud einzuschränken. Eine typische Besprechungsaufzeichnung verbraucht etwa 400 MB pro Stunde.

**Sollte ich mich auf dieses Feature verlassen, um strikte Sicherheits- und Compliance-Einhaltung zu gewährleisten?**

Nein, Sie sollten sich aus Rechtlichem Schutz nicht darauf verlassen, da Endbenutzer das Ablaufdatum aller aufzeichnungen, die sie kontrollieren, ändern können.

**Überschreibt eine Aufbewahrungs- und/oder Löschrichtlinie, die ich im Security & Compliance Center festgelegt habe, die Ablaufeinstellung Teams Besprechungsaufzeichnung?**

Ja, alle Richtlinien, die Sie im Compliance Center festgelegt haben, haben vorrang.

Zum Beispiel: 

- Wenn Sie über eine Richtlinie verfügen, die besagt, dass alle Dateien auf einer Website 100 Tage lang aufbewahrt werden müssen und die Ablaufeinstellung für eine Teams Besprechungsaufzeichnung 30 Tage beträgt, wird die Aufzeichnung für die gesamten 100 Tage aufbewahrt.
- Wenn Sie über eine Löschrichtlinie verfügen, die besagt, dass alle Teams Besprechungsaufzeichnungen nach fünf Tagen gelöscht werden und Sie über eine Ablaufeinstellung für eine Teams Besprechungsaufzeichnung von 30 Tagen verfügen, wird die Aufzeichnung nach fünf Tagen gelöscht.

**Was geschieht, wenn ein TMR abläuft?**

Am Ablaufdatum wird die Aufzeichnung in den Papierkorb verschoben, und das Ablaufdatumsfeld wird gelöscht. Wenn Sie die Aufzeichnung aus dem Papierkorb wiederherstellen, wird sie von diesem Feature nicht erneut gelöscht, da das Ablaufdatum gelöscht wurde.

**Wie werde ich über das Ablaufen einer Datei in Kenntnis gesetzt?**

- Jeder erhält eine Benachrichtigung über das Ablaufdatum in der Aufzeichnungscheckliste im Teams Chatfenster.
- Alle Benutzer mit Ansichtrechten werden 14 Tage lang vor Ablauf der Datei neben dieser ein rotes Symbol in ihrem OneDrive- oder SharePoint-Ordner sehen.
- Der Dateibesitzer erhält eine E-Mail-Benachrichtigung, wenn die Aufzeichnung abläuft, und wird zum Papierkorb geleitet, um die Aufzeichnung wiederherzustellen.

**Welche SKUs sind für dieses Feature erforderlich?**

- Alle SKUs verfügen standardmäßig über dieses Feature.

- A1-Benutzer werden standardmäßig auf einen Ablaufzeitraum von 30 Tagen festgelegt und können das Ablaufdatum nicht ändern.

**Handelt es sich bei dem Dateiablauf um ein überwachtes Ereignis, und wird es in meinen Überwachungsprotokollen aufscheinen?**

Ja, diese werden als Systemlöschereignisse im Überwachungsprotokoll angezeigt.

**Was geschieht, wenn ich möchte, dass der Administrator die volle Kontrolle über den Lebenszyklus von Besprechungsaufzeichnungen hat und Endbenutzern nicht die Möglichkeit geben möchte, das Ablaufdatum außer Kraft zu setzen?**

Wir empfehlen die Verwendung der Richtlinien zur Aufbewahrung und/oder Löschung von Sicherheit und Compliance, die als Teil der E5-Compliance-SKU verfügbar sind. Dieses Angebot ist auf die Vereinfachung im Zusammenhang mit komplexen Richtlinien und SLA-abhängigen, administrativ-rechtlichen Aspekten ausgerichtet.

Dieses Feature ist ausschließlich als einfacher Housekeeping-Mechanismus gedacht, um die Speicher clutter zu reduzieren, die durch kalte Teams Besprechungsaufzeichnungen entsteht.

**Wann wird die Datei gelöscht?**

Die Datei wird innerhalb von fünf Tagen nach dem Ablaufdatum gelöscht, obwohl dies keine strenge Garantie ist.

**Der Standardablauf beträgt 120 Tage, aber wenn ich Teams Admin Center aktiviert habe, ist dies 60 Tage. Warum?**

Die Funktionsweise der Teams Richtlinien ist, wenn eine Richtlinie im Center vom Administrator festgelegt wird, wird eine zwischengespeicherte Momentaufnahme aller Einstellungen erstellt. Wenn der Administrator ein Attribut für die Richtlinie festgelegt hat, als vorübergehend ein 60-Tage-Standard festgelegt wurde, muss er es manuell in 120 Tage ändern. Wenn sie vor dem Festlegen des Standardwerts für 120 Tage keine benutzerdefinierte Einstellung hatten, erhalten sie die 120 Tage.
