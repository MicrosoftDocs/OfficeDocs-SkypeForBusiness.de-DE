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
ms.openlocfilehash: dd35979ce67f33f053e89ea941f5e911733d6f16efa2b6b6a2a10c49d2e63884
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314631"
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
|Lync 2013, Lync 2010, Office Communicator  <br/> |Oc  <br/> |
|Lync Web App, Communicator Web Access  <br/> |Cwa  <br/> |
|Lync Telefon Edition, Office Communicator Telefon  <br/> |OCPhone  <br/> |
|Communicator Phone Edition-Plattform  <br/> |Cpe  <br/> |
|Unified Communications-Plattform  <br/> |UCCP  <br/> |
|Lync 2010 Attendee  <br/> |Aoc  <br/> |
|Live Meeting-Add-In  <br/> |LiveMeetingAddins  <br/> |
|Office Live Meeting  <br/> |Lmc  <br/> |
|Windows Messenger  <br/> |WM  <br/> |
|Client für Real-Time Communications  <br/> |Rtc  <br/> |
|Lync 2010 für iPad  <br/> |iPadLync  <br/> |
|Lync 2010 für iPhone  <br/> |iPhoneLync  <br/> |
|Lync 2010 für Windows Phone  <br/> |WPLync  <br/> |
|Lync 2010 für Nokia  <br/> |NokiaLync  <br/> |
|Lync 2010 für Android  <br/> |AndroidLync  <br/> |
|Mobilitätsdienst  <br/> |McxService  <br/> |

- **Versionsnummer** Sie können die Versionsnummern für die folgenden Felder angeben oder Platzhalter verwenden, um die Clientversionsnummer anzugeben.

  - **Hauptversion** Gibt die Nummer an, die der Hauptversion des Clients entspricht.

  - **Nebenversion** Gibt die Nummer an, die der Nebenversion des Clients entspricht.

  - **Erstellen** Gibt die Buildnummer an, die der Haupt- und Nebenversion des Clients entspricht.

  - **Aktualisieren** Gibt die Nummer an, die der aktualisierten Version des Clients entspricht.

- **Vergleichsvorgang** Sie können den Abgleichsvorgang für die Clientversion angeben, die Sie in den vorherigen Schritten angegeben haben. Die folgenden Vorgänge sind verfügbar:

  - **Gleich**

  - **Ungleich**

  - **Neuer als**

  - **Neuer als oder gleich**

  - **Älter als**

  - **Älter als oder gleich**

- **Aktion** Sie können die auszuführende Aktion angeben, wenn die Kriterien in den vorherigen Schritten erfüllt sind. Die folgenden Aktionen sind verfügbar:

  - **Zulassen** Ermöglicht dem Client die Anmeldung.

  - **Zulassen und Aktualisieren** Ermöglicht dem Client, sich anzumelden und Updates von Windows Server Update Service oder Microsoft Update zu erhalten. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

    > [!NOTE]
    > Wenn Sie diese Aktion auswählen, wird eine Benachrichtigung angezeigt, wenn sich Benutzer das nächste Mal bei Skype for Business anmelden. Die Benachrichtigung weist darauf hin, dass ein Update verfügbar ist, selbst wenn etwaige Updates noch nicht in Windows Server Update Service oder Microsoft Update veröffentlicht wurden. Um Unklarheiten zu vermeiden, sollten Sie diese Aktion erst dann auswählen, wenn Updates verfügbar gemacht wurden.

  - **Zulassen mit URL** Ermöglicht es dem Client, sich anzumelden, und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden soll. Sie geben die URL im Feld **URL** an.

  - **Blockieren** Verhindert, dass sich der Client anmeldet.

  - **Blockieren und Aktualisieren** Verhindert, dass sich der Client anmeldet, und ermöglicht dem Client den Empfang von Updates von Windows Server Update Service oder Microsoft Update. Diese Aktion ist nur verfügbar, wenn der Benutzer-Agent **OC** ausgewählt ist.

  - **Mit URL blockieren**   Verhindert die Anmeldung des Clients und zeigt eine Meldung an, wo eine andere Clientversion heruntergeladen werden kann. Sie geben die URL im Feld **URL** an.

Ausführliche Informationen zur Interoperabilität zwischen Clients und Clientversionen finden Sie unter [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in der Planungsdokumentation. Ausführliche Informationen zur Verwendung von Clientversionskonfigurationen finden Sie unter [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in der Betriebsdokumentation.