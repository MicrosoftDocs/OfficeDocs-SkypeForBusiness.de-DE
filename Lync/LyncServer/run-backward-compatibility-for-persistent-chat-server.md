---
title: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b512d18449c881efd856674477a727cec137b64c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Ausführen der Abwärtskompatibilität für den Server für beständigen Chat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Der lync Server 2013, beständiger Chat Serverendpunkt bietet eine Möglichkeit zum Erstellen einer einfachen URL, die auf einen beständigen Chat Serverpool verweist. Dies ist nützlich für Legacy-Clients (Microsoft Office Communications Server 2007 R2-Gruppen-Chat Server oder lync Server 2010, Gruppen-Chat), da Benutzer in der manuellen Konfiguration eine einfache URL eingeben können, wenn Sie versuchen, den Legacyclient auf einen Computer mit lync 2013 zu verweisen. Beständiger Chat. Dieser Endpunkt wird nicht vom beständigen Chat verwendet und ist nur für Legacyclients erforderlich. Dies ist für den zwischen Zeitraum nützlich, in dem Räume migriert werden können, die lync 2013-Clients aber nicht in der gesamten Organisation bereitgestellt wurden. Benutzer, die den lync 2010-Gruppen-Chat (Client) ausführen, können dann weiterhin eine Verbindung mit dem Server für beständigen Chat-Server herstellen.

Sie müssen nicht mehrere Endpunkte für beständigen Chat Server erstellen; Sie benötigen nur eine für jeden beständigen Chat Server Pool. Administratoren können mehrere Endpunkte (eine pro Pool) erstellen, ältere Clients können jedoch so konfiguriert werden, dass Sie nur mit einem Pool verbunden sind. Im normalen oder Mainstream-Szenario ist die Legacy Bereitstellung nur ein Pool. Eine neue Bereitstellung migriert in der Regel diesen Pool zu einem neuen lync Server 2013 und fügt möglicherweise einige neue Server Pools für beständigen Chat hinzu.

Dieses Mainstream-Szenario folgt in der Regel diesem Muster:

  - Sie verwalten Benutzer mit einem lync Server 2010, Gruppen-Chat-Pool und ihren lync 2010-Gruppen-Chat-Clients, die eine Verbindung mit diesem Pool herstellen, indem Sie einen bekannten Benutzer\<verwenden (\>entweder standardmäßig SIP: OCSChat @ Domain Name. com oder eine ähnliche). Die Benutzer sind SIP-fähige Active Directory-Domänendienste, und der Suchdienst registriert sich, um eingehende Anforderungen zu empfangen.

  - Anschließend installieren Sie einen lync Server 2013-beständigen Chat Server und einen beständigen Chat Serverpool.

  - In einer Zeit, in der Benutzer im allgemeinen offline sind (beispielsweise ein Wochenende):
    
      - Deaktivieren Sie lync Server 2010, Gruppen-Chat.
    
      - Migrieren Sie Daten aus dem lync Server 2010, Gruppen-Chat-Pool, in den lync Server 2013-Serverpool für beständigen Chat.
    
      - Löschen Sie den bekannten Benutzer aus den Active Directory-Domänendiensten.
    
      - Erstellen Sie einen neuen *Legacy Endpunkt* mit dem gleichen SIP-URI wie der zuvor gelöschte bekannte Benutzer.
    
      - Starten Sie die lync Server 2013, persistent Chat Server.

  - Benutzer melden sich mit Ihrem lync 2010-Gruppen-Chat (Client) wieder an und stellen eine Verbindung mit Ihren Daten her, ohne dass eine Konfiguration geändert werden muss.

  - Zu einem späteren Zeitpunkt können Sie den lync Server 2010, Gruppen-Chat, außer Betrieb nehmen. Anschließend können Sie lync Server 2013, beständiger Chat Server und neue lync Server 2013-Server Pools für beständige Chats installieren.

Details zur Migration von lync Server 2010, Gruppen-Chat zu lync Server 2013, beständiger Chat Server, finden Sie unter [Migration von lync Server 2010, Gruppen-Chat oder Office Communications Server 2007 R2-Gruppenchat zu lync Server 2013, beständiger Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

So führen Sie Abwärtskompatibilität aus (zum Erstellen eines beständigen Chat Server-Endpunkts, der auf einen beständigen Chat Serverpool verweist, der von Legacy-Gruppen-Chat Pool-Clients verwendet werden kann):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Konfigurieren Sie als nächstes Clients für beständigen Chat, um diese SIP-Adresse als Kontaktobjekt zu verwenden. Die SIP-Adresse wird mit dem Cmdlet **New-CsPersistentChatEndpoint** für einen bestimmten beständigen Chat Server Pool erstellt.

Wenn Sie den beständigen Chat-Server Endpunkt mithilfe der Windows PowerShell-Befehlszeilenschnittstelle hinzufügen möchten, sollten Sie das folgende Beispiel Bedenken. In diesem Fall konfigurieren Sie das Kontaktobjekt mit dem Namen "persistentchat" in der Topologie "contoso.com", wobei der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Pools "pcpool.contoso.com" lautet:

    New-CsPersistentChatEndpoint -SipAddress sip:persistentchat@contoso.com -PersistentChatPoolFqdn pcpool.contoso.com

<div>

## <a name="see-also"></a>Siehe auch


[Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

