---
title: Zeitraum für kostenlose ausgehende Anrufe
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, OscarR
ms.topic: conceptual
ms.assetid: dc6e95cd-51e8-49ca-bcd3-78dc9dae486a
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: None
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Erfahren Sie mehr über den kostenlosen Zeitraum für Abwahl von Microsoft 365- oder Office 365-Anrufplan und Office 365-Audiokonferenzen in Microsoft Teams.
ms.openlocfilehash: 0f40e35e30de5698ffcb4bf9592868685d8223ed
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918881"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Audiokonferenz – Zeitraum für kostenlose ausgehende Anrufe

## <a name="skype-for-business-pstn-services"></a>Festnetzdienste für Skype for Business

Kunden können Microsoft 365- oder Office 365-Anrufplan und Office 365-Audiokonferenzen nach den Nutzungsbedingungen für Skype for Business Online-PSTN-Dienste und dem Volumenlizenzvertrag des Kunden verwenden. Die Nutzungsbedingungen für Festnetzdienste finden Sie in den [Lizenzbedingungen und in der Dokumentation.](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN)
  
### <a name="end-of-complimentary-dial-out-period"></a>Ende des kostenlosen Wählzeitraums

Die kostenlose Funktion für das Auswählen endete am 1. Dezember 2019. Weitere Informationen finden Sie unter ["Audiokonferenz-Abonnement wählen" und "Rückruf zum Vorteil".](audio-conferencing-subscription-dial-out.md) 

Diese Änderung wurde für Länder nicht erfolgt, in denen das Abonnement für Audiokonferenzen verfügbar ist, aber wir aktivieren derzeit nicht das Einrichten von Guthaben für Kommunikationen. Diese speziellen Länder sind Russland, Südkorea und Taiwan.

### <a name="complimentary-dial-out-period-details"></a>Details des kostenlosen Wählzeitraums

Für Kunden, die unseren Microsoft 365- oder Office 365-Audiokonferenzdienst übernehmen, bietet Microsoft bis November 2019 zusätzliche kostenlose Vorteile für das Abwählen von Besprechungen, die von Benutzern organisiert werden, denen eine Lizenz für Microsoft 365- oder Office 365-Audiokonferenzen zugewiesen ist. Während dieses kostenlosen Zeitraums ermöglicht Microsoft Besprechungsorganisatoren oder autorisierten Teilnehmern gemäß Definition in den Einstellungen der Besprechungsrichtlinien, Auswählanrufe innerhalb der Besprechung an Nicht-Premium-Telefonnummern in den Ländern und Regionen der 44 Zone [A](audio-conferencing-zones.md)zu senden. Dieser Vorteil gilt für monatliche Abonnementlizenzen für Audiokonferenzen und gilt nicht für Lizenzen für Audiokonferenzen mit Minutenlizenz.

Darüber hinaus gilt während des kostenlosen Wählzeitraums ein Limit von 900 Minuten:

Benutzer mit einem Lizenzverwendungsstandort (der Standort ist der Standort des Benutzers, der im Lizenzierungsbereich des Microsoft 365 Admin Centers definiert ist) _in_ einem beliebigen Land/einer Region können aus einer Konferenz in jedes der 44 Länder und Regionen der Zone [A](audio-conferencing-zones.md)auswählen. Jeder Benutzer erhält pro Benutzer pro Monat  900 Minuten in alle Länder und Regionen der Zone [A,](audio-conferencing-zones.md)die auf Mandantenebene gepoolt werden. Ein Kunde hat z. B. 115 Abonnementlizenzen für Audiokonferenzen erworben und hat 10 Benutzer in den USA, 100 Benutzer in Großbritannien und fünf Benutzer in Indien, und das alles mit Abonnementlizenzen für Audiokonferenzen, die den Benutzern zugewiesen sind.

- Alle 115 Benutzer nutzen einen Pool von (115 Benutzer x 900 Min.) = 103.500 Anrufminuten für Konferenzen pro Kalendermonat, der für ausgehende Anrufe in alle Länder und Regionen der Zone [A verwendet werden](audio-conferencing-zones.md)kann.

- Alle Anrufe, die die 103.500 Minuten pro Kalendermonat überschreiten, werden per Minutenabrechnung über Guthaben für Kommunikationen zu den an diesem Ziel veröffentlichten Tarifen abgerechnet. (Hinweis: Der Mandant muss Guthaben für Kommunikationen einrichten und dem Besprechungsorganisator die Lizenz für Guthaben für Kommunikationen zuweisen.)

- Alle ausgehenden Anrufe an Ziele, die nicht in der Länder- und Regionsliste der Zone [A](audio-conferencing-zones.md) enthalten sind, werden mit Guthaben für Kommunikationen zu unseren veröffentlichten Tarifen an diesen Zielort abgerechnet (vorausgesetzt, der Mandant hat Guthaben für Kommunikationen eingerichtet und dem Besprechungsorganisator die Lizenz für Guthaben für Kommunikationen zugewiesen).

> [!NOTE]
> Sie können die Nutzung mit dem Minutenpool für Einwahlen im Skype for Business Admin Center überwachen. Wechseln Sie im Microsoft Teams & Skype Admin Center zu "Berichte  >  PSTN-Minutenpools"  >  **des Legacyportals.** Dieser kostenlose Minutenpool wird im Bericht mit "Ausgehende Anrufe in Länder und Regionen der Zone A" bezeichnet.

E-Mail-Benachrichtigungen werden an alle Mandantenadministratoren eines bestimmten Kunden gesendet, wenn die Nutzung des DFÜ-Minutenpools des Mandanten 80 % und 100 % erreicht hat.

Bei Ausgehendwählanrufen, die pro Minute abgerechnet werden (Anrufe, die den Minutenpool für Ausgehende Anrufe des Mandanten überschreiten, oder Anrufe an Ziele, die nicht in der Liste der Länder und Regionen der Zone [A](audio-conferencing-zones.md) enthalten sind), basieren die Anrufe und die zugehörigen Tarife in erster Linie auf dem Ziel des Anrufs und nicht auf dem Land oder der Region des Organisators oder des Teilnehmers, der den Ausgehenden Anruf initiiert. Beispielsweise wird ein Anruf bei einer Telefonnummer in Frankreich mit demselben Tarif abgerechnet, wenn er von einem Besprechungsteilnehmer in den USA oder einem in Frankreich initiiert wird.

Weitere Informationen zu Guthaben für Kommunikationen finden Sie unter [Guthaben für Kommunikationen.](what-are-communications-credits.md)
     
## <a name="related-topics"></a>Verwandte Themen

- [Verfügbarkeit von Audiokonferenzen und Anrufplänen nach Ländern und Regionen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Länder- und Regionalzonen für Audiokonferenzen](audio-conferencing-zones.md)
