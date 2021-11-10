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
ms.openlocfilehash: cfbbc8602044c0429de414b94b88d0e0e5aa8b19
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889525"
---
# <a name="meeting-recording-expiration-feature---frequently-asked-questions"></a>Ablauffunktion der Besprechungsaufzeichnung – Häufig gestellte Fragen

**Worin besteht die Änderung?**

Wir haben eine standardmäßige 60-Tage-Ablaufeinstellung für alle neu erstellten Teams (TMRs) eingeführt.  Diese Funktion ist standardmäßig für alle Mandanten aktiviert, und Sie müssen sie deaktivieren, wenn Sie dieses Feature nicht verwenden möchten. Das OneDrive und SharePoint-System überwacht das für alle TMRs festgelegte Ablaufdatum und verschiebt TMRs automatisch am Ablaufdatum in den Papierkorb.

**Warum wird diese Änderung eingeführt?**

Wir haben Ihre Anfragen zur Ablauffunktion für Besprechungsaufzeichnungen beantwortet. Dies ist ein einfacher Verwahrungsmechanismus, mit dem sich die durch eine unaufgeforderte TMR entstehende Speicher-Clutter verringert. Im Durchschnitt werden 99 % der TMRs nach 60 Tagen nie wieder angezeigt.

**Warum wird dies standardmäßig aktiviert sein?**

Wir glauben, dass fast alle Kunden von der verringerten Speicherbelegung in den Mandanten profitieren werden, wenn Aufzeichnungen entfernt werden, die wahrscheinlich nach 60 Tagen nicht mehr angesehen werden. Es ist unser Ziel, standardmäßig für alle Kunden eine möglichst klare Erfahrung zu bieten.

**Wie wird das Ablaufdatum berechnet?**

Das Ablaufdatum wird als der Tag berechnet, an dem er erstellt wird, zuzüglich der Standardanzahl, die vom Administrator in der Teams festgelegt wurde.

**Wie kann ein Administrator das Ablaufdatum ändern?**

Administratoren können die Standardmäßige Ablaufeinstellung in ihrer eigenen Teams bearbeiten. Diese Änderung wirkt sich ab diesem Zeitpunkt nur auf neu erstellte TMRs aus. Es hat keine Auswirkungen auf Aufzeichnungen vor diesem Datum.

Administratoren können das Ablaufdatum in vorhandenen TMRs nicht ändern. Dies geschieht, um die Entscheidung des Benutzers zu schützen, der die TMR besitzt.

**Welche Auswirkungen hat das?**

Jeder speichert TMRs in OneDrive oder SharePoint.

**Warum sollte ich dieses Feature verwenden?**

Dieses Feature wird standardmäßig aktiviert. Um sie zu deaktivieren, ändern Sie die Standardablaufeinstellung in der Teams-Richtlinienkonsole in **Kein Ablauf.**
Verwenden Sie diese OneDrive Informationen, um die von Teams von Besprechungsdatensätzen gesteuerten Ressourcen für Cloudspeichernutzung in SharePoint zu beschränken. Eine typische Besprechungsaufzeichnung verbraucht ca. 400 MB pro Stunde für die Aufzeichnung.

**Sollte ich dieses Feature zur strikten Einhaltung von Sicherheit und Compliance verwenden?**

Nein, Sie sollten sich aus rechtlichen Grund nicht darauf verlassen, da Endbenutzer das Ablaufdatum von Aufzeichnungen ändern können, die sie kontrollieren.

**Setzt eine aufbewahrungs- und/oder löschrichtlinie, die ich im Security & Compliance Center festgelegt habe, die Ablaufeinstellung Teams Besprechungsaufzeichnung außer Kraft?**

Ja, alle richtlinien, die Sie im Compliance Center festgelegt haben, haben die volle Priorität.

Zum Beispiel: 

- Wenn Sie über eine Richtlinie verfügen, die anberaumt, dass alle Dateien auf einer Website 100 Tage aufbewahrt werden müssen und die Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung 30 Tage beträgt, wird die Aufzeichnung für die vollen 100 Tage aufbewahrt.
- Wenn Sie über eine Löschrichtlinie verfügen, die ankst, dass alle Teams-Besprechungsaufzeichnungen nach fünf Tagen gelöscht werden, und Sie eine Ablaufeinstellung für eine Teams-Besprechungsaufzeichnung von 30 Tagen festlegen, wird die Aufzeichnung nach fünf Tagen gelöscht.

**Was geschieht, wenn eine TMR abläuft?**

Am Ablaufdatum wird die Aufzeichnung in den Papierkorb verschoben, und das Feld für das Ablaufdatum wird gelöscht. Wenn Sie die Aufzeichnung aus dem Papierkorb wiederherstellen, wird sie von diesem Feature nicht mehr gelöscht, da das Ablaufdatum gelöscht wurde.

**Wie werde ich über das Ablaufen einer Datei in Kenntnis gesetzt?**

- Jeder sieht eine Benachrichtigung über das Ablaufdatum in der Aufzeichnungscheckliste im Teams Chatfenster.
- Alle Benutzer mit Ansichtrechten werden 14 Tage lang vor Ablauf der Datei neben dieser ein rotes Symbol in ihrem OneDrive- oder SharePoint-Ordner sehen.
- Der Dateibesitzer erhält eine E-Mail-Benachrichtigung, wenn die Aufzeichnung abläuft, und wird zum Papierkorb geleitet, um die Aufzeichnung wiederhergestellt zu können.

**Welche SKUs sind für dieses Feature erforderlich?**

- Alle SKUs verfügen standardmäßig über dieses Feature.

- Für alle Benutzer wird standardmäßig ein Ablaufzeitraum von 30 Tage festgelegt, und sie können das Ablaufdatum nicht ändern.

**Handelt es sich bei dem Dateiablauf um ein überwachtes Ereignis, und wird es in meinen Überwachungsprotokollen aufscheinen?**

Ja, diese werden als Systemlöschereignisse im Überwachungsprotokoll angezeigt.

**Was muss ich tun, wenn der Administrator über Vollsteuerung des Lebenszyklus von Besprechungsaufzeichnungen verfügen soll und den Endbenutzern nicht die Möglichkeit geben möchte, das Ablaufdatum außer Kraft zu setzen?**

Es wird empfohlen, die Aufbewahrungs- und/oder Löschrichtlinien für Sicherheit und Compliance zu verwenden, die als Teil der E5-Compliance-SKU verfügbar sind. Dieses Angebot ist auf die Vereinfachung im Zusammenhang mit komplexen Richtlinien und SLA-abhängigen, administrativ-rechtlichen Aspekten ausgerichtet.

Dieses Feature ist ausschließlich als einfacher Verwahrungsmechanismus gedacht, um die Speicher unübersichtlich zu machen, die aufgrund von unübersichtlich Teams Besprechungsaufzeichnungen entsteht.

**Wann wird die Datei gelöscht?**

Die Datei wird innerhalb von fünf Tagen nach dem Ablaufdatum gelöscht, obwohl dies keine strenge Garantie ist.
