---
title: Planen des Extensible Messaging and Presence Protocol (XMPP)-Verbunds
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for extensible messaging and presence protocol (XMPP) federation
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205107(v=OCS.15)
ms:contentKeyID: 48184892
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ee0543d36cb43a05042ca4341a837ae10b52051
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-extensible-messaging-and-presence-protocol-xmpp-federation-in-lync-server-2013"></a>Planen der erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP)-Föderation in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

In früheren Versionen von lync Server und Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. In Microsoft lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: ein XMPP-Proxy, der auf dem Edgeserver ausgeführt wird, und das XMPP-Gateway, das auf den Front-End-Servern ausgeführt wird.

Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) , die Sie zur Unterstützung von xmpp in Ihrer Organisation planen, durch Definieren von Port-und Protokollregeln für Ihre Firewall, Konfiguration von Zertifikaten und Hinzufügen von DNS-Einträgen abgedeckt. In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um die XMPP-Föderation für Ihre Bereitstellung erfolgreich zu planen.

<div>


> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Port Zusammenfassung – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS Summary – Extensible Messaging and Presence Protocol (XMPP) Federation in lync Server 2013](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  


[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/Gg425805(v=OCS.15))  
[Get-CsXmppAllowedPartner](https://technet.microsoft.com/en-us/library/JJ204981(v=OCS.15))  
[Get-CsXmppGatewayConfiguration](https://technet.microsoft.com/en-us/library/JJ204869(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

