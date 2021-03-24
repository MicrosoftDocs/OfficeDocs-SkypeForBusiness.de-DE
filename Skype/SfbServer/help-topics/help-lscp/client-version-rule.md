---
title: Clientversionsregel
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyRuleEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6e7e94c2-1475-4334-b8da-716b24a4c255
description: Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.
ms.openlocfilehash: 4c46a93e46e1e07865a466a666a450a766c6897e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103451"
---
# <a name="client-version-rule"></a>Clientversionsregel

Eine Clientversionsrichtlinie besteht aus einer Gruppe von Clientversionsregeln. Mit diesen Regeln werden die Aktionen definiert, die ausgeführt werden sollen, wenn Benutzer sich mit bestimmten Clients und Clientversionen anmelden möchten.

## <a name="tasks-you-can-perform"></a>Mögliche Aufgaben

Auf der Seite **Neue Clientversionskonfiguration erstellen** oder **Clientversionskonfiguration bearbeiten** können Sie die folgenden Aufgaben ausführen:

- Hinzufügen neuer Regeln zu einer Clientversionsrichtlinie

- Ändern der Regeln, aus denen eine vorhandene Clientversionsrichtlinie besteht

## <a name="ui-reference"></a>Referenz zur Benutzeroberfläche

In den folgenden Listen werden die Menüs, Befehle, Felder und Eigenschaften der Seite beschrieben.

- **Benutzer-Agent** Sie können einen Clienttyp aus der Liste auswählen. In der folgenden Tabelle sind die Codes der Benutzer-Agents definiert.

|**Clientname**|**Benutzer-Agent**|
|:-----|:-----|
|Lync 2013, Lync 2010, Office Communicator  <br/> |OC  <br/> |
|Lync Web App, Communicator Web Access  <br/> |CWA  <br/> |
|Lync Phone Edition, Office Communicator Phone  <br/> |OCPhone  <br/> |
|Communicator Phone Edition-Plattform  <br/> |CPE  <br/> |
|Unified Communications-Plattform  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |AOC  <br/> |
|Live Meeting-Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |LMC  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client für Real-Time Communications  <br/> |RTC  <br/> |
|Lync 2010 für iPad  <br/> |iPadLync  <br/> |
|Lync 2010 für iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 for Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 für Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 für Android  <br/> |AndroidLync  <br/> |
|Mobilitätsdienst  <br/> |McxService  <br/> |

- **Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die Clientversionsnummer anzugeben.

  - **Hauptversion** Gibt die Nummer an, die der Hauptversion des Clients entspricht.

  - **Nebenversion** Gibt die Nummer an, die der Nebenversion des Clients entspricht.

  - **Build** Gibt die Buildnummer an, die der Haupt- und Nebenversion des Clients entspricht.

  - **Update** Gibt die Nummer an, die der aktualisierten Version des Clients entspricht.

- **Vergleichsvorgang** Sie können den Abgleichsvorgang für die Clientversion angeben, die Sie in den vorherigen Schritten angegeben haben. Die folgenden Vorgänge sind verfügbar:

  - **Gleich**

  - **Ungleich**

  - **Neuer als**

  - **Neuer als oder gleich**

  - **Älter als**

  - **Älter als oder gleich**

- **Aktion** Sie können die Durchzuführende Aktion angeben, wenn die Kriterien in den vorherigen Schritten erfüllt sind. Die folgenden Aktionen sind verfügbar:

  - **Zulassen** Ermöglicht dem Client die Anmeldung.

  - **Zulassen und Aktualisieren** Ermöglicht dem Client das Anmelden und Empfangen von Updates von Windows Server Update Service oder Microsoft Update. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

    > [!NOTE]
    > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich Benutzer das nächste Mal bei Skype for Business anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

  - **Zulassen mit URL** Ermöglicht dem Client die Anmeldung und zeigt eine Meldung darüber an, wo eine andere Clientversion heruntergeladen werden soll. Sie geben die URL im Feld **URL** an.

  - **Blockieren** Verhindert, dass sich der Client anmelden kann.

  - **Blockieren und Aktualisieren** Verhindert die Anmeldung des Clients und ermöglicht dem Client den Empfang von Updates von Windows Server Update Service oder Microsoft Update. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

  - **Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in der Betriebsdokumentation.