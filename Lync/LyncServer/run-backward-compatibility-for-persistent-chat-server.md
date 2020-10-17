---
title: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat
description: Ausführen der Abwärtskompatibilität für den Server für beständigen Chat.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run backward compatibility for Persistent Chat Server
ms:assetid: 53f1a706-3104-4a94-8b4e-8badd9a066d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204901(v=OCS.15)
ms:contentKeyID: 48184175
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0486992d44e6385559d3e9df9f9ffc2125120da
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570151"
---
# <a name="run-backward-compatibility-for-persistent-chat-server"></a>Ausführen der Abwärtskompatibilität für den Server für beständigen Chat

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Der Serverendpunkt für beständigen Chat mit lync Server 2013 bietet eine Möglichkeit zum Erstellen einer einfachen URL, die auf einen Serverpool für beständigen Chat zeigt. Dies ist nützlich für Legacy-Clients (Microsoft Office Communications Server 2007 R2 Gruppenchat Server oder lync Server 2010 Gruppenchat), da Benutzer eine einfache URL in die manuelle Konfiguration eingeben können, wenn Sie versuchen, den Legacy-Client auf einen Computer mit lync 2013, beständigen Chat, zu deuten. Dieser Endpunkt wird nicht vom beständigen Chat verwendet und ist nur für ältere Clients erforderlich. Dies ist für die Zwischenzeit nützlich, in der Räume möglicherweise migriert werden, aber die lync 2013 Clients nicht in der gesamten Organisation bereitgestellt wurden. Benutzer, die lync 2010 Gruppen Chat (Client) durchführen, können dann weiterhin eine Verbindung mit dem Back-End-Server des Servers für beständigen Chat herstellen.

Sie müssen nicht mehrere persistent Chat-Server Endpunkte erstellen; Sie benötigen nur einen für jeden Server Pool für beständigen Chat. Administratoren können mehrere Endpunkte (eine pro Pool) erstellen, ältere Clients können jedoch so konfiguriert werden, dass jeweils nur eine Verbindung mit einem Pool hergestellt wird. Im üblichen oder Mainstream-Szenario ist die Legacy-Bereitstellung nur ein Pool. Eine neue Bereitstellung migriert diesen Pool im Allgemeinen zu einem neuen lync Server 2013 und fügt möglicherweise einige neue Server Pools für beständigen Chat hinzu.

Übliche Szenarien weisen i. d. R. folgendes Muster auf:

  - Sie verwalten Benutzer mit einem lync Server 2010, einem Gruppenchat Pool und ihren lync 2010 Gruppenchatclients, die eine Verbindung mit diesem Pool herstellen, indem Sie einen bekannten Benutzer verwenden (entweder standardmäßig SIP: OCSChat@ \<domainName\> . com oder ein ähnliches). Die Benutzer sind SIP-fähige Active Directory-Domänendienste, und der Nachschlage Dienst registriert sich mit diesen, um eingehende Anforderungen zu empfangen.

  - Anschließend installieren Sie einen Serverpool für beständiger Chat von lync Server 2013 Server und einen beständigen Chat.

  - Für den Zeitraum, in dem die Benutzer für gewöhnlich offline sind (z. B. am Wochenende) werden folgende Maßnahmen empfohlen:
    
      - Deaktivieren Sie lync Server 2010, Gruppen Chat.
    
      - Migrieren von Daten aus dem lync Server 2010, Gruppen Chat Pool in den beständiger Chat von lync Server 2013 Server Pool.
    
      - Löschen Sie den bekannten Benutzer aus dem Active Directory-Domänendienste.
    
      - Erstellen Sie einen neuen *Endpunkt für Vorversionen* mit dem gleichen SIP-URI wie für den zuvor gelöschten bekannten Benutzer.
    
      - Starten Sie den Server für beständigen Chat lync Server 2013.

  - Benutzer melden sich mit Ihrem lync 2010 Gruppen Chat (Client) wieder an und stellen eine Verbindung zu Ihren Daten her, ohne dass eine Konfiguration geändert werden muss.

  - Zu einem späteren Zeitpunkt können Sie den lync Server 2010 und Gruppen Chat außer Betrieb nehmen. Anschließend können Sie lync Server 2013, beständigen Chat Server bereitstellen und neue beständiger Chat von lync Server 2013 Server Pools installieren.

Ausführliche Informationen zum Migrieren von lync Server 2010, Gruppenchat zu lync Server 2013, beständiger Chat Server, finden Sie unter [Migration from lync Server 2010, Group Chat oder Office Communications Server 2007 R2 Group Chat to lync Server 2013, persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

So führen Sie Abwärtskompatibilität aus (um einen Serverendpunkt für beständigen Chat zu erstellen, der auf einen Serverpool für beständigen Chat verweist, der von Legacy Gruppen-Chat Pool Clients verwendet werden kann):

    New-CsPersistentChatEndpoint -SipAddress <CO name, ex. persistentchat@contoso.com> -PersistentChatPoolFqdn <pool FQDN, like pcpool.contoso.com>

Konfigurieren Sie als nächstes Clients für beständigen Chat so, dass diese SIP-Adresse als Kontaktobjekt verwendet wird. Die SIP-Adresse wird mit dem **New-cspersistentchatendpoint "-** Cmdlet für einen bestimmten Server Pool für beständigen Chat erstellt.

Wenn Sie den Server Endpunkt für beständigen Chat mithilfe Windows PowerShell Befehlszeilenschnittstelle hinzufügen möchten, sollten Sie das folgende Beispiel verwenden. In diesem Fall konfigurieren Sie das Kontaktobjekt und weisen ihm den Namen "persistentchat" für die Topologie "contoso.com" zu, deren vollqualifizierter Pooldomänenname "pcpool.contoso.com" lautet:

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

