---
title: 'Lync Server 2013: Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer'
TOCTitle: Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398196(v=OCS.15)
ms:contentKeyID: 49293209
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-23_

Es wird empfohlen, eine separate Voice-over-IP-Richtlinie (VoIP) für Benutzer an Zweigstellenstandorten zu erstellen. Diese Richtlinie sollte Routen vom Survivable Branch-Anwendung-Gateway oder dem externen Survivable Branch-Server-Gateway sowie Alternativrouten vom Gateway am zentralen Standort enthalten. Unabhängig davon, wo der Benutzer registriert ist (entweder in der Registrierung auf der Survivable Branch-Anwendung oder dem Survivable Branch-Server oder im Sicherungsregistrierungscluster am zentralen Standort), ist die VoIP-Richtlinie des Benutzers immer gültig.

## So konfigurieren Sie die VoIP-Routingrichtlinie für Benutzer an Zweigstellenstandorten

1.  Erstellen Sie Wählplan auf Benutzerebene, und weisen Sie ihn den Benutzern am Zweigstellenstandort zu. (Siehe [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

2.  Weisen Sie entsprechend dem Wählverhalten der Benutzer an diesem Standort Normalisierungsregeln zu. Wenn für den Survivable Branch-Anwendung- oder Survivable Branch-Server-Benutzer ein Failover zum Sicherungsregistrierungspool am zentralen Standort durchgeführt wird, bleiben dieselben Wähleinstellungen in Kraft. (Siehe [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) in der Betriebsdokumentation.)

3.  Konfigurieren Sie eine ausgehende VoIP-Route vom Survivable Branch-Anwendung-Gateway oder dem externen Survivable Branch-Server-Gateway. (Siehe [Erstellen einer VoIP-Route in Lync Server 2013](lync-server-2013-create-a-voice-route.md) in der Betriebsdokumentation.)

4.  Legen Sie eine Alternativroute für das Survivable Branch-Anwendung- oder Survivable Branch-Server-Gateway fest, die auf den Sicherungsregistrierungspool (gemeinsam ausgeführt mit dem Vermittlungsserver) am zentralen Standort verweist. (Weitere Informationen finden Sie in der Herstellerdokumentation zur Survivable Branch-Anwendung oder dem Survivable Branch-Server.)
    

    > [!NOTE]
    > Diese Alternativroute stellt sicher, dass eingehende Anrufe beim Zweigstellenbenutzer empfangen werden können, wenn die Survivable Branch-Anwendung oder der Survivable Branch-Server nicht zur Verfügung stehen (beispielsweise bei Ausfällen aufgrund einer Wartung). Wenn Registrierung und Vermittlungsserver auf der Survivable Branch-Anwendung oder dem Survivable Branch-Server nicht verfügbar sind und der Benutzer beim Sicherungsregistrierungspool am zentralen Standort registriert ist, können eingehende Anrufe weiterhin an den Benutzer geroutet werden.



**Nächster Schritt** : [Konfigurieren von Einstellungen für die Voicemailumleitung in Lync Server 2013](lync-server-2013-configure-voice-mail-rerouting-settings.md)

