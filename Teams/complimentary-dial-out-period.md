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
ms.localizationpriority: ''
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
description: Erfahren Sie mehr über den kostenlosen Zeitraum für Microsoft 365 oder Office 365 Anrufplan und Office 365 Audiokonferenzen in Microsoft Teams.
ms.openlocfilehash: fa571a355f4eb9a546c2c231e9a06f83d4374029
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619601"
---
# <a name="audio-conferencing-complimentary-dial-out-period"></a>Audiokonferenz – Zeitraum für kostenlose ausgehende Anrufe

## <a name="skype-for-business-pstn-services"></a>Festnetzdienste für Skype for Business

Kunden können Microsoft 365- oder Office 365-Anrufplan und Office 365-Audiokonferenzen wie in den Nutzungsbedingungen für Skype for Business Online-PSTN-Dienste und im Volumenlizenzvertrag des Kunden gestattet verwenden. Die Nutzungsbedingungen für PSTN-Dienste finden Sie unter [Lizenzbedingungen und Dokumentation](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=2&amp;Keyword=PSTN).
  
### <a name="end-of-complimentary-dial-out-period"></a>Ende des kostenlosen Wählzeitraums

Die Funktion für kostenloses Wählen endete am 1. Dezember 2019. Weitere Informationen finden Sie unter [Audiokonferenz-Abonnement](audio-conferencing-subscription-dial-out.md)wählen und mich zum Vorteil anrufen . 

Diese Änderung wurde für Länder, in denen das Abonnement für Audiokonferenzen verfügbar ist, nicht geändert, aber derzeit ist das Einrichten von Guthaben für Kommunikationen nicht aktiviert. Diese speziellen Länder sind Russland, Südkorea und Taiwan.

### <a name="complimentary-dial-out-period-details"></a>Einzelheiten zum Zeitraum für kostenloses Wählen

Für Kunden, die unseren Microsoft 365- oder Office 365-Audiokonferenzdienst übernehmen, bietet Microsoft einen zusätzlichen kostenlosen Vorteil für das Einwählen aus Besprechungen, die von Benutzern organisiert werden, denen bis November 2019 eine Abonnementlizenz für Microsoft 365- oder Office 365-Audiokonferenzen zugewiesen ist. Während dieses kostenlosen Zeitraums gestattet Microsoft Besprechungsorganisatoren oder autorisierten Teilnehmern gemäß Definition in den Richtlinieneinstellungen für Besprechungen, Auswahlanrufe innerhalb der Besprechung an Nicht-Premium-Telefonnummern in den Ländern und Regionen der Zone [A](audio-conferencing-zones.md)zu senden. Dieser Vorteil gilt für monatliche Abonnementlizenzen für Audiokonferenzen und wird nicht auf Lizenzen für Audiokonferenzen mit Minuten pro Minute erweitert.

Darüber hinaus gilt während des kostenlosen Wählzeitraums ein Limit von 900 Minuten:

Benutzer mit einem Lizenzverwendungsstandort (der Standort ist der Standort des Benutzers, der im Lizenzierungsbereich des Microsoft 365 Admin Center definiert ist) _in_ einem beliebigen Land _, können aus einer Konferenz in jedes der 44 Länder und Regionen der Zone [A](audio-conferencing-zones.md)wählen. Jeder Benutzer erhält 900 Minuten  pro Benutzer pro Monat in alle Länder und Regionen der [Zone A,](audio-conferencing-zones.md)die auf Mandantenebene gepoolt werden. Ein Kunde hat beispielsweise 115 Abonnementlizenzen für Audiokonferenzen erworben und hat 10 Benutzer in den USA, 100 Benutzer in Großbritannien und fünf Benutzer in Indien , die alle ihren Benutzern Lizenzen für Audiokonferenzen zugewiesen haben.

- Alle 115 Benutzer nutzen einen Pool von (115 Benutzer x 900 Min.) = 103.500 Ausgehende Minuten pro Kalendermonat, die für ausgehende Anrufe in alle Länder und Regionen der Zone [A](audio-conferencing-zones.md)verwendet werden können.

- Alle Anrufe, die die 103.500 Minuten pro Kalendermonat überschreiten, werden per Minutenabrechnung über Guthaben für Kommunikationen zu unseren veröffentlichten Tarifen an dieses Ziel abgerechnet. (Hinweis: Der Mandant muss Guthaben für Kommunikationen einrichten und dem Besprechungsorganisator die Lizenz für Guthaben für Kommunikationen zuweisen.)

- Alle ausgehenden Anrufe an Ziele, die nicht in der Liste der Länder und Regionen der Zone [A](audio-conferencing-zones.md) enthalten sind, werden mit Guthaben für Kommunikationen nach unseren veröffentlichten Tarifen an dieses Ziel abgerechnet (vorausgesetzt, der Mandant hat Guthaben für Kommunikationen eingerichtet und dem Besprechungsorganisator die Lizenz für Guthaben für Kommunikationen zugewiesen).

> [!NOTE]
> Sie können die Nutzung des Minutenpools für DFÜ-Nachrichten im Skype for Business Admin Center überwachen. Wechseln Sie Microsoft Teams & Skype Admin Center zu Ältere Portalberichte  >    >  **PSTN-Minutenpools**. Dieser kostenlose Minutenpool wird im Bericht als "Ausgehende Anrufe an Länder und Regionen in Zone A" bezeichnet.

E-Mail-Benachrichtigungen werden an alle Mandantenadministratoren eines bestimmten Kunden gesendet, wenn die Nutzung des DFÜ-Minutenpools des Mandanten 80 % und 100 % erreicht hat.

Für Ausgehende Anrufe, die pro Minute abgerechnet werden (Anrufe, die den Mandanten-Minutenpool für Ausgehende Anrufe überschreiten, oder Anrufe an Ziele, die nicht in der Liste der Länder und Regionen der Zone [A](audio-conferencing-zones.md) enthalten sind), basieren die Anrufe und die zugehörigen Tarife in erster Linie auf dem Ziel des Anrufs und nicht auf dem Land oder der Region des Organisators oder dem Teilnehmer, der den Ausgehenden Anruf initiiert hat. Beispielsweise wird ein Anruf bei einer Telefonnummer in Frankreich mit dem gleichen Tarif abgerechnet, wenn er von einem Besprechungsteilnehmer in den USA oder einem in Frankreich initiiert wird.

Weitere Informationen zu Guthaben für Kommunikationen finden Sie unter [Guthaben für Kommunikationen.](what-are-communications-credits.md)
     
## <a name="related-topics"></a>Verwandte Themen

- [Verfügbarkeit von Land und Region für Audiokonferenz und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Länder und Regionen für Audiokonferenzen](audio-conferencing-zones.md)
