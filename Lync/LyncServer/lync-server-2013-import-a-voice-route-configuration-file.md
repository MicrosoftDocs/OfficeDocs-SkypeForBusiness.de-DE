---
title: 'Lync Server 2013: Importieren einer Konfigurationsdatei für die VoIP-Route'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import a voice route configuration file
ms:assetid: 4bac05e5-ed8b-4f10-96b0-b8a65ff356ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398301(v=OCS.15)
ms:contentKeyID: 48184049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ce270b4321c484b40a20271ad21c2701c749d6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038737"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-a-voice-route-configuration-file-in-lync-server-2013"></a>Importieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn Sie Ihre VoIP-Routingkonfiguration ohne Veröffentlichung speichern möchten, führen Sie die folgenden Schritte aus, um die lync Server-Systemsteuerung Konfigurations Export-und Importbefehle zu verwenden, um eine Momentaufnahme Ihrer VoIP-Routingkonfiguration zu speichern und abzurufen. Wenn Sie eine VoIP-Routing Konfigurationsdatei (. vcfg) importieren, Änderungen an der VoIP-Routingkonfiguration auf dem Server in der Zwischenzeit vorgenommen wurden, geben die Seiten in der Gruppe **VoIP-Routing** in lync Server-Systemsteuerung an, dass keine Commits für Änderungen an der VoIP-Weiterleitung vorgenommen werden. Diese noch nicht übernommenen Änderungen stellen die Unterschiede zwischen den zwei Konfigurationen dar, die einer Zusammenführung bedürfen.

Wenn Sie Änderungen an den Einstellungen auf einer beliebigen Seite innerhalb der Gruppe vorgenommen haben, werden die Änderungen in der exportierten VoIP-Konfigurationsdatei (. vcfg) gespeichert. Auf diese Weise können Sie Konfigurationsänderungen für das VoIP-Routing in mehreren Sitzungen vornehmen, bevor Sie die Änderungen veröffentlichen.

<div>

## <a name="to-import-a-voice-routing-configuration"></a>So importieren Sie eine VoIP-Routingkonfiguration

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Klicken Sie im Menü **Aktionen** auf **Konfiguration importieren**.

5.  Suchen Sie nach der Konfigurationsdatei, die Sie importieren möchten, und klicken Sie dann auf **Öffnen**.

6.  Klicken Sie auf **Commit** und anschließend auf **Commit für alle**.
    
    <div>
    

    > [!NOTE]  
    > Jedes Mal, wenn Sie eine VoIP-Konfigurationsdatei importieren, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um die Konfigurationsänderung zu veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013</A> in der Betriebsdokumentation.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Exportieren einer VoIP-Route-Konfigurationsdatei in lync Server 2013](lync-server-2013-export-a-voice-route-configuration-file.md)  
[Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

