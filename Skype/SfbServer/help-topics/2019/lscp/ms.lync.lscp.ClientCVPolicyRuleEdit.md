---
title: Clientversionsregel
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
ROBOTS: NOINDEX, NOFOLLOW
description: Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
ms.openlocfilehash: ab67f926f7a2e0ddc91f33bc9657d8fd4104e3a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300524"
---
# <a name="client-version-rule"></a>Clientversionsregel

Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen neuer Regeln zu einer Clientversionsrichtlinie

- Ändern der Regeln, aus denen eine vorhandene Clientversionsrichtlinie besteht

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Benutzer-Agent** Sie können einen Clienttyp aus der Liste auswählen. In der folgenden Tabelle sind die Codes der Benutzer-Agents definiert. Diese Liste enthält Legacyclient Typen, die teilweise nicht mehr unterstützt werden.

|**Clientname**|**Benutzer-Agent**|
|:-----|:-----|
|Lync 2013, lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition-Plattform  <br/> |CPE  <br/> |
|Unified Communications-Plattform  <br/> |UCCP  <br/> |
|Lync 2010-Teilnehmer  <br/> |AOC  <br/> |
|Live Meeting-Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client für Real-Time Communications  <br/> |RTC  <br/> |
|Lync 2010 für iPad  <br/> |iPadLync  <br/> |
|Lync 2010 für iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 für Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 für Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 für Android  <br/> |AndroidLync  <br/> |
|Mobilitätsdienst  <br/> |McxService  <br/> |

- **Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die Versionsnummer des Clients anzugeben.

  - **Hauptversion** Gibt die Nummer an, die der Hauptversion des Clients entspricht.

  - **Nebenversion** Gibt die Nummer an, die der Nebenversion des Clients entspricht.

  - **Erstellen** Gibt die Buildnummer an, die der Haupt-und Nebenversion des Clients entspricht.

  - **Update** Gibt die Nummer an, die der aktualisierten Version des Clients entspricht.

- **Vergleichsvorgang** Sie können den übereinstimmenden Vorgang für die Client Version angeben, die Sie in den vorherigen Schritten angegeben haben. Die folgenden Vorgänge sind verfügbar:

  - **Identisch mit**

  - **Ist nicht**

  - **Neuer als**

  - **Neuer als oder identisch mit**

  - **Älter als**

  - **Älter als oder identisch mit**

- **Aktion** Sie können die Aktion angeben, die ausgeführt werden soll, wenn die Kriterien in den vorherigen Schritten erfüllt sind. Die folgenden Aktionen sind verfügbar:

  - **Zulassen** Ermöglicht es dem Client, sich anzumelden.

  - **Zulassen und aktualisieren** Ermöglicht es dem Client, sich anzumelden und Updates vom Windows Server Update-Dienst oder Microsoft Update zu erhalten. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

    > [!NOTE]
    > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich die Benutzer das nächste Mal bei Skype for Business anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

  - **Mit URL zulassen** Ermöglicht es dem Client, sich anzumelden und eine Meldung darüber anzuzeigen, wo eine andere Client Version heruntergeladen werden soll. Sie geben die URL im Feld **URL** an.

  - **Blockieren** Verhindert, dass der Client sich anmeldet.

  - **Blockieren und aktualisieren** Verhindert, dass der Client sich anmeldet und dem Client ermöglicht, Updates vom Windows Server Update-Dienst oder Microsoft Update zu erhalten. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

  - **Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.

Details zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperabilität](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie in der Betriebsdokumentation unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx).

