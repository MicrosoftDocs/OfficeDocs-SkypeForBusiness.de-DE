---
title: 'Lync Server 2013: veröffentlichen ausstehender Änderungen in der VoIP-Routingkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22cabe1725d899ace42e5b525105c1753c3d9925
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823651"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Veröffentlichen ausstehender Änderungen an der VoIP-Routingkonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Wenn Sie Änderungen an den Konfigurationseinstellungen auf den Seiten in der Gruppe **VoIP-Routing** vorgenommen haben, führen Sie zum Überprüfen, Veröffentlichen oder Verwerfen der ausstehenden Änderungen die folgenden Schritte aus.

<div>


> [!IMPORTANT]  
> Stellen Sie sicher, dass jeweils nur ein Benutzer Änderungen an den Konfigurationseinstellungen für das VoIP-Routing vornimmt.<BR>Alle ausstehenden Änderungen müssen gleichzeitig über den Befehl <STRONG>Commit für alle Element ausführen</STRONG> veröffentlicht werden. Es ist nicht möglich, nur ausgewählte ausstehende Änderungen zu veröffentlichen. Führen Sie den Befehl <STRONG>Noch nicht übernommene Änderungen überprüfen</STRONG> aus, bevor Sie ausstehende Änderungen veröffentlichen, und verwerfen Sie Konfigurationsänderungen, die nicht veröffentlicht werden sollen.<BR>Wenn Sie die Seiten in der Gruppe <STRONG>VoIP-Routing</STRONG> verlassen, bevor Sie für ausstehende Änderungen ein Commit ausführen, gehen alle ausstehenden Änderungen verloren. Sie können die aktuelle Konfiguration (einschließlich ausstehender Änderungen) jedoch in eine VoIP-Konfigurationsdatei exportieren und die aktualisierte Konfiguration anschließend importieren und veröffentlichen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-export-a-voice-route-configuration-file.md">Exportieren einer sprach Routen-Konfigurationsdatei in lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>So überprüfen, veröffentlichen oder verwerfen Sie Konfigurationsänderungen für das VoIP-Routing

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing**.

4.  Nehmen Sie die gewünschten Konfigurationsänderungen an den Einstellungen auf den einzelnen Seiten der Gruppe **VoIP-Routing** vor.

5.  Wählen Sie im Menü **Commit** die Option **Noch nicht übernommene Änderungen überprüfen** aus, um ausstehende Änderungen zu überprüfen, ohne sie zu veröffentlichen.

6.  Führen Sie eine der folgenden Aktionen aus, um ausstehende Änderungen zu verwerfen:
    
      - Wählen Sie im Menü **Commit** die Option **Alle noch nicht übernommenen Änderungen verwerfen** aus.
    
      - Wechseln Sie auf der Seite **VoIP-Routing** zur Registerkarte mit ausstehenden Änderungen, die verworfen werden sollen, wählen Sie das Element mit den ausstehenden Änderungen aus, klicken Sie auf **Commit** und klicken Sie dann auf **Ausgewählte Änderungen verwerfen**.

7.  Nachdem Sie alle ausstehenden Änderungen überprüft und die Änderungen verworfen haben, die nicht veröffentlicht werden sollen, klicken Sie auf **Commit** und dann auf **Commit für alle Element ausführen**.

8.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde**, das eine Liste aller ausstehenden Änderungen enthält, auf **OK**.
    
    Wenn die lync Server-Systemsteuerung die Änderungen übernommen hat, wird die Meldung **erfolgreich veröffentlichte sprach Routingkonfiguration** angezeigt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

