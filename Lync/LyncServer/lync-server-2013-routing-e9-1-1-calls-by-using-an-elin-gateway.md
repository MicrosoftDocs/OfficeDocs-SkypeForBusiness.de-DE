---
title: 'Lync Server 2013: Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway'
TOCTitle: Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204919(v=OCS.15)
ms:contentKeyID: 49294100
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Weiterleiten von E9-1-1-Anrufen über ein ELIN-Gateway in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Einige Partner im Unified Communications Open Interoperability Program ermöglichen die Nutzung von ELIN-Gateways (Emergency Location Identification Number). Diese können als Alternative zu einer SIP-Trunkverbindung mit einem zertifizierten E9-1-1-Dienstanbieter fungieren. ELIN-Gateways unterstützen ISDN- oder CAMA (Centralized Automatic Message Accounting)-Verbindungen zu E9-1-1-Diensten im Telefonfestnetz (Public Switched Telephone Network, PSTN). Nähere Informationen zu den Partnern, die ELIN-Gateways bereitstellen, sowie Links zu einschlägiger Dokumentation finden Sie unter [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).

Analog zu SIP-Trunkverbindungen mit E9-1-1-Dienstanbietern ermöglichen ELIN-Gateways auch das Routing eines Notrufs an die nächstgelegene Notrufzentrale (Public Safety Answering Point, PSAP) des Anrufers. Allerdings verwenden diese Gateways eine ELIN als Standort-ID. Die ELINs für die einzelnen Notfallreaktionsstandorte (ERL) in Ihrer Organisation müssen von Ihnen festgelegt werden. (Nähere Informationen finden Sie unter [Verwalten von Standorten für ELIN-Gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md).)

Wenn Sie ein ELIN-Gateway für Notrufe benutzen, verwenden Sie die gleiche E9-1-1-Infrastruktur von Lync Server wie für eine SIP-Trunkverbindung. Dies bedeutet, dass der Standort gegenüber dem Lync Server-Client von der Standortinformationsdienst-Datenbank angegeben wird. Die Standortrichtlinie aktiviert die Funktionen und definiert das Routing. In einem ELIN-Gateway müssen Sie die ELINs jedoch der Standortinformationsdienst-Datenbank hinzufügen. Außerdem müssen diese vom PSTN-Betreiber in die ALI-Datenbank (Automatic Location Identification) hochgeladen werden.

Wenn ein Lync-Client den Standort vom Standortinformationsdienst abruft, ist darin auch die ELIN enthalten. Die ELIN wird während eines Notrufs zusammen mit dem Standort an das ELIN-Gateway gesendet. Das ELIN-Gateway identifiziert den Anruf als Notruf und tauscht die Nummer des Anrufers mit der ELIN. Das ELIN-Gateway leitet den Anruf mit der ELIN als Anrufernummer an das Telefonfestnetz weiter. Der E9-1-1-Anbieter im Festnetz schlägt die ELIN in der ALI-Datenbank nach. Diese Datenbank ist eine Zusatzdatenbank zur MSAG-Datenbank (Master Street Address Guide). Anschließend sendet der PSTN-Anbieter den Anruf zur (nach der ALI-Datenbank) nächstgelegenen PSAP, und die PSAP sendet Ersthelfer zum Standort des Anrufers (nach der ALI-Datenbank). Die Nummer des Anrufers wird für einen vorher festgelegten Zeitraum im ELIN-Gateway zwischengespeichert, um Rückrufe zu ermöglichen. Bei einem Rückruf erreicht die PSAP das ELIN-Gateway, und die ELIN wird mit der DID-Nummer (Direct Inward Dialing) des Anrufers getauscht.

ELIN-Gateways unterstützen Notrufe nur innerhalb des Netzwerks Ihrer Organisation. Notrufe von außerhalb dieses Netzwerks werden nicht unterstützt.


> [!NOTE]
> Nähere Informationen über die Verwendung einer SIP-Trunkverbindung für Notrufe finden Sie unter <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Weiterleiten von E9-1-1-Anrufen mittels SIP-Trunk in Lync Server 2013</A>.



Das folgende Diagramm veranschaulicht, wie ein Notruf von Lync Server bei Verwendung eines ELIN-Gateways an den PSAP geroutet wird.

**Routen von E9-1-1-Anrufen in einem ELIN-Gateway**

![ELIN-Anrufweiterleitung](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ELIN-Anrufweiterleitung")

1.  Eine SIP INVITE-Anforderung mit dem Standort, der Rückrufnummer des Anrufers sowie (optional) der Benachrichtigungs-URL und einer Konferenzrückrufnummer wird an Lync Server weitergeleitet.

2.  Lync Server gleicht die Notrufnummer ab und leitet den Anruf (anhand des Werts für die **PSTN-Verwendung** in der betreffenden Standortrichtlinie) an einen Vermittlungsserver und von dort an ein ELIN-Gateway weiter.

3.  Das ELIN-Gateway leitet den Anruf über einen ISDN- oder CAMA-Trunk an das PSTN weiter.

4.  Das PSTN identifiziert den Anruf als Notruf und leitet ihn an einen selektiven E9-1-1-Router im Netzwerk weiter. Der selektive E9-1-1-Router schlägt die Nummer des Anrufers in der ALI-Datenbank nach, um seinen geografischen Standort zu bestimmen. Anschließend sendet der selektive E9-1-1-Router den Anruf an den (nach der ALI-Datenbank) nächstgelegenen PSAP.

5.  Wenn Sie die Standortrichtlinie für Benachrichtigungen konfiguriert haben, erhält mindestens ein Sicherheitsbeauftragte Ihres Unternehmens eine spezielle Lync-Sofortnachricht für Notfälle. Die Nachricht wird immer direkt auf dem Bildschirm des Sicherheitsbeauftragten angezeigt. Sie enthält den Namen des Anrufers, seine Telefonnummer sowie die Uhrzeit und den Standort. Auf diese Weise wird eine schnelle Reaktion auf den Notruf via Sofort- oder Sprachnachricht ermöglicht.

6.  Wenn der Anruf vorzeitig unterbrochen wird, kontaktiert der PSAP den Anrufer mithilfe der ELIN direkt. Das ELIN-Gateway tauscht die ELIN mit der DID des Anrufers.

