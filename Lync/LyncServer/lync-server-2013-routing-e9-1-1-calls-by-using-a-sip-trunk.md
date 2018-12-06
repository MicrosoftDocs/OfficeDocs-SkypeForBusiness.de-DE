---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk'
TOCTitle: Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204701(v=OCS.15)
ms:contentKeyID: 49293274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-29_

Das Verwenden eines SIP-Trunks zum Herstellen einer Verbindung mit einem qualifizierten E9-1-1-Dienstanbieter ist eine Möglichkeit der Bereitstellung von E9-1-1. Nähere Informationen zur Verwendung eines ELIN-Gateway zum Herstellen einer Verbindung mit einem Telefonfestnetzbasierten E9-1-1-Dienstanbieter finden Sie unter [Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Die folgende Abbildung zeigt, wie ein Notruf von Lync Server an die Rettungsleitstelle weitergeleitet wird, wenn Sie einen SIP-Trunk und einen qualifizierten E9-1-1-Dienstanbieter verwenden.

**Weiterleiten von E9-1-1-Anrufen über einen SIP-Trunk**

![Emergency Call Routing vom Lync Server an PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Emergency Call Routing vom Lync Server an PSAP")

Wenn ein Notruf über einen kompatiblen Lync Server-Client abgesetzt wird, werden folgende Schritte ausgeführt:

1.  SIP INVITE-Anforderung mit dem Standort, der Rückrufnummer des Anrufers sowie der (optionalen) Benachrichtigungs-URL und Konferenzrückrufnummer wird an Lync Server weitergeleitet.

2.  Lync Server ordnet die Notrufnummer zu, und leitet den Anruf (basierend auf dem in der anwendbaren Ortungsrichtlinie angegebenen Wert für **PSTN-Verwendung** ) an einer Vermittlungsserver und von dort über einen SIP-Trunk an den E9-1-1-Dienstanbieter weiter.

3.  Der E9-1-1-Dienstanbieter leitet den Notruf basierend auf dem Standort, der dem Anruf zugeordnet ist, an die richtige Rettungsleitstelle weiter. Wenn der Notruf des Clients einen überprüften Standort für Notrufmaßnahmen umfasst, leitet der Anbieter den Anruf automatisch an die richtige Rettungsstelle weiter. Wenn der Standort vom Benutzer manuell eingegeben wurde, überprüft die Notrufzentrale zunächst die Genauigkeit des Standorts mit dem Anrufer, bevor der Notruf an die Rettungsstelle weitergeleitet wird.

4.  Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, erhält mindestens ein Sicherheitsbeauftragte Ihres Unternehmens eine spezielle Lync-Sofortnachricht für Notfälle. Die Nachricht wird immer direkt auf dem Bildschirm des Sicherheitsbeauftragten angezeigt. Sie enthält den Namen des Anrufers, seine Telefonnummer sowie die Uhrzeit und den Standort. Auf diese Weise wird eine schnelle Reaktion auf den Notruf via Sofort- oder Sprachnachricht ermöglicht.

5.  Wenn Sie die Ortungsrichtlinie für Konferenzen konfiguriert haben und diese vom E9-1-1-Dienstanbieter unterstützt wird, wird der Konferenz ein internes Sicherheitsdesk entweder mit unidirektionalem oder bidirektionalem Audio hinzugefügt.

6.  Wenn ein Anruf vorzeitig unterbrochen wird, verwendet die Rettungsleitstelle die Rückrufnummer, um den Anrufer direkt zu kontaktieren.

