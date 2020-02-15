---
title: Bereitstellen von lync Server 2013 Clients
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac6dce30e356ed3161f985f32d8f26dc0e34ac6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a>Bereitstellen von lync Server 2013 Clients

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Nachdem Sie Benutzer zu lync Server 2013 migriert haben, gehen Sie wie folgt vor:

1.  Verwenden Sie den Client Versions Filter auf dem neuen lync Server 2013 Server, um nur Clients mit den aktuellsten Updates zur Anmeldung zuzulassen.

2.  Konfigurieren Sie, falls erforderlich, die Gruppenrichtlinieneinstellungen, die für das Clientbootstrapping benötigt werden. Ausführliche Informationen finden Sie unter [Configuring clientbootstrapping Policies in lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in der Bereitstellungsdokumentation. Diese Einstellungen müssen nur dann konfiguriert werden, wenn Sie vorhandene Clientbootstrapping-Richtlinien ändern oder neue Clientbootstrapping-Richtlinien festlegen möchten. Wenn Sie keine Clientbootstrapping-Richtlinien konfigurieren möchten oder Clientbootstrapping-Richtlinien der Vorgängerversion gültig bleiben sollen, ist keine Aktion erforderlich.

3.  Konfigurieren Sie andere Benutzer-und Clientrichtlinien für bestimmte Benutzer oder Benutzergruppen mithilfe lync Server 2013 Systemsteuerung, lync Server 2013 Verwaltungsshell oder beides. Ausführliche Informationen finden Sie unter [neue und geänderte Einstellungen für lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in der Planungsdokumentation.

4.  Stellen Sie die neueste Version von lync Server 2013-Clients zusammen mit den neuesten kumulativen Updates bereit. Ausführliche Informationen finden Sie unter [Deploying Clients and Devices in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in der Bereitstellungsdokumentation.

5.  Optional Wenn Ihre Organisation lync Server 2013 erweiterten Datenschutzmodus für Anwesenheitsinformationen benötigt, definieren Sie nach Abschluss der Migration eine Richtlinienregel für Clientversionen, um zu verhindern, dass frühere Clientversionen sich anmelden. Aktivieren Sie dann den Datenschutzmodus für erweiterte Anwesenheitsinformationen.
    
    <div>
    

    > [!IMPORTANT]  
    > Aktivieren Sie lync 2013 erweiterten Datenschutzmodus für Anwesenheitsinformationen erst, wenn jeder Benutzer in einem bestimmten Serverpool die neuesten Clientversionen installiert hat.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

