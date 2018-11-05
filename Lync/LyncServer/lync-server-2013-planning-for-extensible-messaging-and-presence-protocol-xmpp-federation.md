---
title: Planen eines XMPP-Partnerverbunds (Extensible Messaging and Presence Protocol) in Lync Server 2013
TOCTitle: Planen eines XMPP-Partnerverbunds (Extensible Messaging and Presence Protocol) in Lync Server 2013
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205107(v=OCS.15)
ms:contentKeyID: 49294790
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen eines XMPP-Partnerverbunds (Extensible Messaging and Presence Protocol) in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Frühere Versionen von Lync Server und Office Communications Server boten ein XMPP-Gateway, das als separate Serverrolle bereitgestellt werden konnte, um den Verbund mit XMPP-Bereitstellungen zu ermöglichen. In Microsoft Lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden. Die XMPP-Funktion wird in zwei Teilen installiert: einem XMPP-Proxy, der auf dem Edgeserver ausgeführt wird, und dem XMPP-Gateway, das auf den Front-End-Servern ausgeführt wird.

Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) behandelt. Die Planung der XMPP-Unterstützung in Ihrer Organisation umfasst die Definition von Port- und Protokollregeln in der Firewall, die Konfiguration von Zertifikaten und das Hinzufügen von DNS-Datensätzen. Die folgenden Themen in diesem Abschnitt fassen die Informationen zusammen, die Sie für die erfolgreiche Planung eines XMPP-Verbunds für Ihre Bereitstellung benötigen.


> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



## In diesem Abschnitt

  - [Zertifikatzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [Portzusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS-Zusammenfassung für XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## Siehe auch

#### Aufgaben

[Einrichten eines XMPP-Partnerverbunds in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md)  
[Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### Weitere Ressourcen

[Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

