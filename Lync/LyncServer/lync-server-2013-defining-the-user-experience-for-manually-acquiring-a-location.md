---
title: 'Lync Server 2013: Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts'
TOCTitle: Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398912(v=OCS.15)
ms:contentKeyID: 49295502
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert, und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet wird.

  - **Sollten Benutzer zur Eingabe eines Standorts aufgefordert werden, wenn dieser nicht automatisch vom Standortinformationsdienst bereitgestellt wird?**  
    Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
    Sie können die Einstellung **Standort erforderlich** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung Nein , wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung Ja , wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung Haftungsausschluss wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn der Benutzer versucht, diese Aufforderung zu verwerfen, wird ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.

Wenn ein Benutzer manuell einen Standort eingibt, wird dieser basierend auf der MAC-Adresse des Standardgateways für das Netzwerk des Clients zugeordnet und in einer benutzerspezifischen Tabelle auf dem Client gespeichert. Kehrt der Benutzer an einen zuvor gespeicherten Standort zurück, wird der Lync-Client automatisch auf diesen Standort eingestellt.


> [!NOTE]
> Sie können nur den aktuellen Standort Ihres Clients ändern. Darüber hinaus können Sie jeden Standort, der in der Tabelle des lokalen Benutzers gespeichert ist, löschen.


