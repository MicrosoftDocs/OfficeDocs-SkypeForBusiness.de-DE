---
title: 'Lync Server 2013: Planen der Remoteanrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ede2b5d63c57864f478cb8fd9bcd4689a91ab3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a>Planen der Remoteanrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

In lync Server 2013 ermöglicht die Unterstützung von Szenarien für die Remoteanrufsteuerung, dass Benutzer Ihre PBX-Telefone (Private Branch Exchange) mithilfe von lync 2013 auf Ihren Desktopcomputern steuern können. In diesem Abschnitt werden die Features für die Remoteanrufsteuerung und die Anforderungen für die Bereitstellung der Remoteanrufsteuerung beschrieben.

Durch die Integration zwischen einer Telefonanlage und lync Server 2013 können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, die lync 2013-Benutzeroberfläche verwenden, um Anrufe auf Ihren Telefonanlagen zu steuern, und zwar wie folgt:

<div>


> [!NOTE]  
> Letztendlich bestimmen die Funktionen der Telefonanlage, die das PBX-Telefon eines Benutzers hostet, die Features für die Remoteanrufsteuerung, die für diesen Benutzer verfügbar sein werden.



</div>

  - Führen eines ausgehenden Anrufs

  - Annehmen eines eingehenden Anrufs

  - Annehmen eines eingehenden Anrufs mit einer Chatnachricht
    
    <div>
    

    > [!NOTE]  
    > Das heißt, wenn die Telefonnummer des Anrufers einer Chat Adresse in der globalen Adressliste (GAL) Ihrer Organisation, in der lync-Kontaktliste des berufenen oder in der Organisation eines Verbundpartners zugeordnet werden kann.

    
    </div>

  - Anrufdurchstellung

  - Weiterleiten eines eingehenden Anrufs

  - Anrufe in Wartestellung setzen

  - Wechseln zwischen mehreren gleichzeitigen anrufen

  - Annehmen eines zweiten Anrufs während eines Anrufs (also Anklopfen)

  - Dial Dual-Tone-mehr Frequenz (DTMF)-Ziffern

  - Geben Sie im Unterhaltungsfenster Notizen in Microsoft Office OneNote-Notizenprogramm ein.

Wenn ein Benutzer für die Remoteanrufsteuerung aktiviert ist, stellt lync 2013 dem Benutzer zudem die folgenden Anrufinformationen zur Verfügung:

  - Kennung eines Anrufers anhand des Namens, wenn die Telefonnummer des Anrufers in der Liste "Kontakte" des Microsoft Office Outlook-Messaging-und-Zusammenarbeits-Clients, der lync-Kontaktliste oder der GAL Ihrer Organisation aktiviert ist.

  - Frühere eingehende und ausgehende Anrufe, die im Ordner "Konversations Verlauf" in Outlook gespeichert sind.

  - Benachrichtigungen über verpasste Anrufe, die an den Outlook-Posteingangsordner des Benutzers gesendet werden, aber nur generiert werden, wenn lync ausgeführt wird, wenn der eingehende Anruf eingegangen ist.

<div>

## <a name="remote-call-control-and-enterprise-voice"></a>Remote Anrufsteuerung und Enterprise-VoIP

Obwohl die Features für die Remoteanrufsteuerung von den Enterprise-VoIP-Features getrennt sind und Benutzer nicht für beide Funktionen aktiviert werden können, bietet Enterprise-VoIP eine Teilmenge der Features, die auch für Benutzer verfügbar sind, die für die Remoteanrufsteuerung aktiviert sind. Wenn Enterprise-VoIP bereitgestellt wird, können Benutzer, die für die Remoteanrufsteuerung aktiviert sind, lync für den Zugriff auf die folgenden Enterprise-VoIP-Features verwenden:

  - Tätigen und empfangen von Audioanrufen an einen anderen lync-Client

  - Teilnehmen am Audioteil einer Konferenz, die von einem Benutzer erstellt wurde, der für Enterprise-VoIP aktiviert ist

</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstellungsaufgaben für die Remoteanrufsteuerung in Lync Server 2013](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

