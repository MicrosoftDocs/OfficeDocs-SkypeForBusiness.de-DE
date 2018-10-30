---
title: 'Lync Server 2013: Schätzen von VoIP-Nutzung und -Datenverkehr'
TOCTitle: Schätzen von VoIP-Nutzung und -Datenverkehr
ms:assetid: 621b08fb-f894-4d91-ac38-e443401b098b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398439(v=OCS.15)
ms:contentKeyID: 49294189
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Schätzen von VoIP-Nutzung und -Datenverkehr für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-08-07_

Das Microsoft Lync Server 2013, Planungstool verwendet die folgenden Metriken zur Schätzung des Benutzerdatenverkehrs an den einzelnen Standorten und der Anzahl von Ports, die zur Verarbeitung dieses Datenverkehr erforderlich sind.

  - Für **geringes Datenaufkommen** (ein Festnetzanruf pro Benutzer und Stunde) gehen Sie von 15 Benutzern pro Anschluss aus.

  - Für **mittleres Datenverkehrsaufkommen** (zwei Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 10 Benutzern pro Anschluss aus.

  - Für **hohes Datenverkehrsaufkommen** (drei oder mehr Festnetzanrufe pro Benutzer und Stunde) gehen Sie von 5 Benutzern pro Anschluss aus.

Die Anzahl von Ports wiederum bestimmt die Anzahl der erforderlichen Vermittlungsserver und Gateways. Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports (es gibt sogar größere Gateways, diese werden jedoch hauptsächlich von Telefonieanbietern verwendet).

Eine Organisation mit 10.000 Benutzern und mittlerem Datenverkehrsaufkommen würde z. B. 1000 Ports benötigen. Die Anzahl der erforderlichen Gateways entspricht der Gesamtzahl der erforderlichen Ports, die durch die Gesamtkapazität der Gateways bestimmt ist.

