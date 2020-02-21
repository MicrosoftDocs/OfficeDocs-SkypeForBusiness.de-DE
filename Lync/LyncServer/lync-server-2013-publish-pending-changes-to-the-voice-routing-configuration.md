---
title: 'Lync Server 2013: Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86444047759c2eab605d8791a6445329651ad43f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-08-07_

Nachdem Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie dieses Verfahren aus, um die ausstehenden Änderungen zu überprüfen, zu veröffentlichen oder abzubrechen.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass nur ein Benutzer gleichzeitig die Konfigurationseinstellungen für das VoIP-Routing ändert.<BR>Alle ausstehenden Änderungen müssen gleichzeitig veröffentlicht werden, indem der Befehl <STRONG>Commit</STRONG> ausführen ausgeführt wird. Ausstehende Änderungen können nicht selektiv veröffentlicht werden. Führen Sie vor dem Veröffentlichen von ausstehenden Änderungen den Befehl nicht <STRONG>Commit für Änderungen überprüfen</STRONG> aus, und löschen Sie alle Konfigurationsänderungen, die nicht veröffentlicht werden sollen.<BR>Wenn Sie von den Seiten in der VoIP- <STRONG>Routing</STRONG> Gruppe Weg navigieren, bevor Sie ausstehende Änderungen committen, gehen alle ausstehenden Änderungen verloren. Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine sprach Konfigurationsdatei exportieren und anschließend die aktualisierte Konfiguration importieren und veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Export a Voice Route Configuration File in lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder kündigen Sie Konfigurationsänderungen für das VoIP-Routing

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf jeder Seite der **VoIP-Routing** Gruppe vor.

5.  Um ausstehende Änderungen zu überprüfen, ohne Sie zu veröffentlichen, wählen Sie im Menü **Commit** die Option nicht **übernommene Änderungen überprüfen** aus.

6.  Wenn Sie die ausstehenden Änderungen abbrechen möchten, führen Sie einen der folgenden Schritte aus:
    
      - Wählen Sie im Menü **Commit** die Option **alle nicht übernommenen Änderungen abbrechen** aus.
    
      - Navigieren Sie zur Registerkarte der **VoIP-Routing** Seite mit ausstehenden Änderungen, die Sie abbrechen möchten, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit**, und klicken Sie dann auf **ausgewählte Änderungen abbrechen**.

7.  Nachdem Sie alle ausstehenden Änderungen überprüft und alle gelöscht haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit**, und klicken Sie dann auf **Commit für alle**.

8.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen ohne Commit** , in dem eine Liste aller ausstehenden Änderungen angezeigt wird, auf **OK**.
    
    Wenn lync Server-Systemsteuerung die Änderungen übernommen hat, wird die Meldung **erfolgreich veröffentlichter VoIP-Routing-Konfiguration** angezeigt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

