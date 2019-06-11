---
title: Bereitstellen von lync Server 2013-Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 659ec7be51358e73824c322461a3e27a163dc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Bereitstellen von lync Server 2013-Clients

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Nachdem Sie Benutzer zu lync Server 2013 migriert haben, gehen Sie folgendermaßen vor:

1.  Verwenden Sie den Client Versions Filter auf dem neuen lync Server 2013-Server, um nur Clients mit den aktuellsten Updates zur Anmeldung zuzulassen.

2.  Konfigurieren Sie bei Bedarf die Gruppenrichtlinieneinstellungen, die für das Client-Bootstrapping erforderlich sind. Ausführliche Informationen finden Sie unter [Konfigurieren von clientbootstrapping-Richtlinien in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in der Bereitstellungsdokumentation. Die Konfiguration dieser Einstellungen ist nur erforderlich, wenn Sie vorhandene Client-Trap Ping-Richtlinien ändern möchten oder wenn Sie neue Client-Trap Ping-Richtlinien festlegen möchten. Wenn Sie nicht planen, clientbootstrapping-Richtlinien zu konfigurieren, oder wenn Sie möchten, dass die Richtlinien für Legacy-Client-Trap Ping weiterhin gültig sind, ist keine Aktion erforderlich.

3.  Konfigurieren Sie andere Benutzer-und Clientrichtlinien für bestimmte Benutzer oder Gruppen von Benutzern mithilfe der lync Server 2013-Systemsteuerung, der lync Server 2013-Verwaltungsshell oder beider. Ausführliche Informationen finden Sie unter [neue und geänderte Einstellungen für lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in der Planungsdokumentation.

4.  Stellen Sie die neueste Version von lync Server 2013-Clients zusammen mit den neuesten kumulativen Updates bereit. Ausführliche Informationen finden Sie unter [Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.

5.  Optional Wenn in Ihrer Organisation der Datenschutzmodus für den erweiterten Anwesenheitsstatus von lync Server 2013 erforderlich ist, definieren Sie nach Abschluss der Migration eine clientversionsrichtlinien Regel, um zu verhindern, dass frühere Clientversionen angemeldet werden. Aktivieren Sie dann den erweiterten Anwesenheitsdaten Schutzmodus.
    
    <div>
    

    > [!IMPORTANT]  
    > Aktivieren Sie den Datenschutzmodus für den erweiterten Anwesenheitsstatus von lync 2013 erst, nachdem jeder Benutzer in einem bestimmten Serverpool die aktuellsten Clientversionen installiert hat.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

