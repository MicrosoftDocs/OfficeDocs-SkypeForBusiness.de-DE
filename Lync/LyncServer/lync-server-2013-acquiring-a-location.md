---
title: 'Lync Server 2013: Abrufen eines Standorts'
TOCTitle: Abrufen eines Standorts
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205110(v=OCS.15)
ms:contentKeyID: 49294881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Abrufen eines Standorts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-06-06_

In einer Lync Server 2013 E9-1-1-Bereitstellung, die jeweils intern mit Lync oder Lync Phone Edition verbunden ist, erwirbt der Client aktiv seinen eigenen Standort. Nach der SIP-Registrierung stellt der Client alle Netzwerkverbindungsinformationen, die er über sich selbst kennt, in einer Standortanforderung für den Standortinformationsdienst bereit, der als Webdienst durch eine replizierte SQL Server-Datenbank gesichert ist. Alle zentralen Standortpools haben einen Standortinformationsdienst, der die Netzwerkinformationen verwendet, um die Datensätze für einen passenden Standort abzurufen. Wenn eine Übereinstimmung ermittelt wird, gibt der Standortinformationsdienst einen Standort an den Client zurück. Wird keine Übereinstimmung ermittelt, wird der Benutzer möglicherweise zur manuellen Eingabe eines Standorts aufgefordert (abhängig von den Einstellungen in der Ortungsrichtlinie). Die Standortdaten werden in einem standardisierten IETF-XML-Format (Internet Engineering Task Force), das als PIDF-LO (Presence Information Data Format Location Object) bezeichnet wird, zurück an den Client übertragen.

Der Lync Server-Client fügt die PIDF-LO-Daten in einen Notruf ein. Diese Daten werden durch den E9-1-1-Dienstanbieter verwendet, um die passende Rettungsleitstelle zu bestimmen und den Anruf zusammen mit dem richtigen ESQK (Emergency Service Query Key) an diese Rettungsleitstelle weiterzuleiten. Hierdurch erhält die Rettungsleitstelle den Standort des Anrufers.

Das folgende Diagramm zeigt, wie ein Lync Server-Client einen Standort erwirbt (mit Ausnahme der Client-MAC-Adresse eines Drittanbieters - basierend auf dem Standortverfahren):

![Beschreibung des Abrufs eines Standorts durch einen Client (Diagramm)](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Beschreibung des Abrufs eines Standorts durch einen Client (Diagramm)")

Damit ein Client den Standort erwirbt, sind folgende Schritte erforderlich:

1.  Der Administrator pflegt die Wiremap des Netzwerks (Tabellen, die verschiedene Typen von Netzwerkadressen den zugeordneten Notfallstandorten (Emergency Response Locations, ERLs) zuordnen) in die Standortinformationsdienst-Datenbank ein.

2.  Wenn Sie einen SIP-Trunk E9-1-1-Dienstanbieter nutzen, überprüft der Administrator die Adressteile der Notfallstandorte gegen eine MSAG-Datenbank (Master Street Address Guide), die durch den E9-1-1-Dienstanbieter bereitgestellt wird. Wenn Sie ein ELIN-Gateway (Emergency Location Identification Number) nutzen, stellt der Administrator sicher, dass der PSTN-Anbieter die ELINs in die ALI-Datenbank hochlädt (Automatic Location Identification).

3.  Während der Registrierung oder wenn eine Netzwerkänderung stattfindet, sendet ein intern verbundener Client eine Standortanforderung, die die ermittelten Netzwerkadressen des Clients enthält, an den Standortinformationsdienst.

4.  Der Standortinformationsdienst ruft die für einen Standort veröffentlichten Datensätze ab und gibt die ERL im PIDF-LO-Format an den Client zurück (sofern eine Übereinstimmung ermittelt wird).

