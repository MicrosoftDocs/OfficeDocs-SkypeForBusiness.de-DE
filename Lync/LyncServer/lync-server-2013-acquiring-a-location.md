---
title: 'Lync Server 2013: Abrufen eines Standorts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de591298d6509ce14b9a4b1ebe55e0a327d517b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a>Erwerben eines Standorts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-06_

In einer lync Server 2013 E9-1 -1-Bereitstellung erwirbt jeder intern verbundene lync-oder lync Phone Edition-Client aktiv einen eigenen Standort. Nach der SIP-Registrierung stellt der Client alle Netzwerk Verbindungsinformationen bereit, die er über sich selbst in einer standortanforderung an den Standortinformationsdienst kennt, bei dem es sich um einen Webdienst handelt, der von einer replizierten SQL Server Datenbank unterstützt wird. Jeder zentrale Website Pool verfügt über eine Standortinformationsdienst, die die Netzwerkinformationen verwendet, um die Datensätze für einen passenden Speicherort abzufragen. Wenn eine Übereinstimmung vorliegt, gibt der Standortinformationsdienst einen Speicherort an den Client zurück. Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der lync Server-Client enthält die PIDF-Lo-Daten im Rahmen eines Notrufs, und diese Daten werden vom E9-1 -1-Dienstanbieter verwendet, um den entsprechenden Rettungsleitstelle zu bestimmen und den Anruf an diesen Rettungsleitstelle zusammen mit dem korrekten ESQK weiterzuleiten, sodass der Rettungsleitstelle-Dispatcher die Standort des Anrufers.

Das folgende Diagramm zeigt, wie ein lync Server-Client einen Standort erwirbt (mit Ausnahme der Adress basierten Ortungsmethode eines Drittanbieters für Client Mac):

![So erwirbt Client ein Standort Diagramm](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "So erwirbt Client ein Standort Diagramm")

Damit ein Client einen Standort abrufen kann, müssen die folgenden Schritte ausgeführt werden:

1.  Der Administrator füllt die Standortinformationsdienst Datenbank mit dem Netzwerk Wiremap (Tabellen, die verschiedene Arten von Netzwerkadressen den entsprechenden Notfall Antwort Standorten zuordnen (ERLs)).

2.  Wenn Sie einen SIP-Trunk-E9-1-1-Dienstanbieter verwenden, überprüft der Administrator die Teile der ERLs mit den allgemeinen Adressen anhand einer MSAG (Master Street Address Guide)-Datenbank, die vom E9-1-1-Dienstanbieter verwaltet wird. Wenn Sie ein ELIN-Gateway verwenden, stellt der Administrator sicher, dass der PSTN-Netzbetreiber die ELINs in die ALI (Automatic Location Identification)-Datenbank hochlädt.

3.  Während der Registrierung oder wenn eine Netzwerkänderung erfolgt, sendet ein intern verbundener Client eine standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.

4.  Das Standortinformationsdienst fragt seine veröffentlichten Datensätze nach einem Speicherort ab und gibt, wenn eine Übereinstimmung gefunden wird, das Erl an den Client im PIDF-Lo-Format zurück.

</div>

<span> </span>

</div>

</div>

</div>

