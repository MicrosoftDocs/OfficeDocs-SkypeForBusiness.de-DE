---
title: 'Lync Server 2013: Abrufen eines Standorts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb123cf2f38d935bc0cc641c67e6d0ff1d54e4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Abrufen eines Standorts in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

In einer lync Server 2013 E9-1-1-Bereitstellung erwirbt jeder intern verbundene lync-oder lync Phone Edition-Client aktiv seinen eigenen Standort. Nach der SIP-Registrierung liefert der Client alle Netzwerk Verbindungsinformationen, die er über sich selbst weiß, in einer standortanforderung an den standortinformationsdienst, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server-Datenbank gesichert wird. Jeder zentrale Website Pool verfügt über einen standortinformationsdienst, der die Netzwerkinformationen verwendet, um seine Datensätze nach einem übereinstimmenden Speicherort abzufragen. Wenn eine Übereinstimmung vorliegt, gibt der standortinformationsdienst einen Speicherort an den Client zurück. Wenn keine Übereinstimmung vorliegt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Standortrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der lync Server-Client enthält die PIDF-Lo-Daten als Teil eines Notrufs, und diese Daten werden vom Dienstanbieter E9-1-1 verwendet, um den entsprechenden PSAP zu ermitteln und den Anruf an diesen PSAP zusammen mit dem korrekten ESQK weiterzuleiten, wodurch der PSAP-Verteiler die Standort des Anrufers.

Das folgende Diagramm zeigt, wie ein lync Server-Client einen Standort erwirbt (mit Ausnahme der Standort Methode eines Drittanbieters für Mac-Adressen auf dem Client):

![So erwirbt der Client ein Standort Diagramm] (images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "So erwirbt der Client ein Standort Diagramm")

Damit ein Client den Standort erwirbt, sind folgende Schritte erforderlich:

1.  Der Administrator füllt die Datenbank des Standort Informationsdiensts mit dem Netzwerk Wiremap (Tabellen, in denen verschiedene Arten von Netzwerkadressen den entsprechenden Notfall Speicherorten zugeordnet werden (ERLs)).

2.  Wenn Sie einen SIP-Trunk E9-1-1-Dienstanbieter nutzen, überprüft der Administrator die Adressteile der Notfallstandorte gegen eine MSAG-Datenbank (Master Street Address Guide), die durch den E9-1-1-Dienstanbieter bereitgestellt wird. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) nutzen, stellt der Administrator sicher, dass der PSTN-Anbieter die ELINs in die ALI-Datenbank hochlädt (Automatic Location Identification).

3.  Bei der Registrierung oder bei jeder Netzwerkänderung sendet ein intern verbundener Client eine Standortanfrage, die die gefundenen Netzwerkadressen des Clients enthält, an den standortinformationsdienst.

4.  Der standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab, und gibt, wenn eine Übereinstimmung gefunden wird, das Erl an den Client im PIDF-Lo-Format zurück.

</div>

<span> </span>

</div>

</div>

</div>

