---
title: 'Lync Server 2013: Planen der Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2faff08d5517809d4cfb11d00711a146accc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planen der Remoteanrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-05_

In lync Server 2013 ermöglicht die Unterstützung für Remote Anruf Steuerungs Szenarien Benutzern die Steuerung Ihrer PBX-Telefone (Private Branch Exchange) mithilfe von lync 2013 auf Ihren Desktopcomputern. In diesem Abschnitt werden die Remoteanrufsteuerungsfunktionen sowie die Anforderungen für die Bereitstellung der Remoteanrufsteuerung beschrieben.

Durch die Integration zwischen einer Nebenstellenanlage und lync Server 2013 können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, die lync 2013-Benutzeroberfläche verwenden, um Anrufe auf Ihren PBX-Telefonen auf folgende Weise zu steuern:

<div>


> [!NOTE]  
> Welche Remoteanrufsteuerungsfunktionen für den Benutzern letztendlich verfügbar sind, hängt von den Funktionen der Nebenstellenanlage ab, die zum Hosten des Nebenstellentelefons eines Benutzers verwendet wird.



</div>

  - Tätigen eines ausgehenden Anrufs

  - Beantworten eines eingehenden Anrufs

  - Beantworten eines eingehenden Anrufs mit einer Sofortnachricht
    
    <div>
    

    > [!NOTE]  
    > Das heißt, wenn die Telefonnummer des Anrufers einer Sofortnachrichtenadresse in der globalen Adressliste (GAL) Ihrer Organisation, in der lync-Kontaktliste des angerufenen oder in der Organisation eines Verbundpartners zugeordnet werden kann.

    
    </div>

  - Weiterleiten eines Anrufs

  - Weiterleiten eines eingehenden Anrufs

  - Halten von Anrufen

  - Wechseln zwischen mehreren gleichzeitigen Anrufen

  - Beantworten eines zweiten Anrufs, nachdem bereits ein Anruf entgegengenommen wurde (Anklopffunktion)

  - DTMF-Ziffern (Dial Dual-Tone Multifrequency, Mehrfrequenzverfahren)

  - Eingabe von Notizen im Fenster "Unterhaltung" in Microsoft Office OneNote

Wenn ein Benutzer für die Remoteanrufsteuerung aktiviert ist, stellt lync 2013 dem Benutzer außerdem die folgenden Anrufinformationen zur Verfügung:

  - Kennung eines Anrufers nach Namen, wenn die Telefonnummer des Anrufers in der Kontaktliste eines Benutzers mit Remoteanrufsteuerung Microsoft Office Outlook-Messaging und-Zusammenarbeitsclient, lync-Kontaktliste oder der GAL Ihrer Organisation vorhanden ist.

  - Vergangene eingehende und ausgehende Anrufe, die im Ordner "Unterhaltungsverlauf" in Outlook gespeichert sind.

  - Benachrichtigungen über verpasste Anrufe, die an den Outlook-Posteingangsordner des Benutzers gesendet werden, aber nur generiert werden, wenn lync beim Empfang des eingehenden Anrufs läuft.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Remoteanrufsteuerung und Enterprise-VoIP

Obwohl Funktionen zur Remoteanrufsteuerung von Enterprise-VoIP-Features getrennt sind und Benutzer nicht für beide aktiviert werden können, bietet Enterprise-VoIP eine Teilmenge der Features, die auch für Benutzer verfügbar sind, die für die Remoteanrufsteuerung aktiviert sind. Wenn Enterprise-VoIP bereitgestellt wird, können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, lync für den Zugriff auf die folgenden Enterprise-VoIP-Funktionen verwenden:

  - Tätigen und empfangen von Audioanrufen an einen anderen lync-Client

  - Teilnahme am Audioteil einer Konferenz, die von einem Benutzer erstellt wurde, der für Enterprise-VoIP aktiviert ist

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstellungsaufgaben für die Remoteanrufsteuerung in lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

