---
title: Benutzermodell für Konferenzen
TOCTitle: Benutzermodell für Konferenzen
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205199(v=OCS.15)
ms:contentKeyID: 49295216
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Benutzermodell für Konferenzen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Ein entscheidender Bestandteil des Lync Server-Konferenzbenutzermodells ist der Besprechungsumfang. Nach dem Erfassen der Daten von den verschiedenen Datenpunkten (wie im vorigen Abschnitt beschrieben) wurde Folgendes ermittelt:

  - Im Durchschnitt weisen die meisten Besprechungen eine Teilnehmerzahl von vier bis sechs Personen auf

  - Circa 80 Prozent der Besprechungen haben weniger als 20 Teilnehmer.

  - 99,98 Prozent der Besprechungen haben weniger als 100 Teilnehmer.

Neben dem Besprechungsumfang berücksichtigt das Konferenzbenutzermodell auch eine Reihe von Faktoren, wie zum Beispiel:

  - **Gleichzeitige Besprechungen**   Wie viele Benutzer befinden sich zur gleichen Zeit in Besprechungen ?

  - **Kombinierter Mediendatenverkehr**   Welche Medienarten stehen zur Verfügung, von deren Verwendung in Besprechungen durch die Benutzer ausgegangen werden kann?

  - **Benutzertypen**   Handelt es sich um interne Benutzer, Remote-Benutzer, Verbundbenutzer oder anonyme Benutzer?

  - **Anlaufzeit für eine Besprechung**   Wieviel Zeit vergeht, bis alle Benutzer einer Besprechung beigetreten sind?

Ausführliche Informationen zum Benutzermodell finden Sie unter [Benutzermodelle in Lync Server 2013](lync-server-2013-user-models.md).

Zur Ermittlung der Anzahl von Besprechungen und Benutzern, die für den Test verwendet wurden, wurde wie folgt vorgegangen:

  - Die Gesamtzahl der Benutzer in einer Organisation (zum Beispiel 80.000 Benutzer) wurde mit der Gleichzeitigkeitsrate von Besprechungen (zum Beispiel 5 % aller Benutzer) multipliziert, um die Gesamtzahl der Benutzer zu ermitteln, die erwartungsgemäß zur gleichen Zeit an Besprechungen teilnehmen (in diesem Beispiel 4.000 Benutzer).

  - Die Gesamtzahl der Benutzer wurde durch die Anzahl der Lync Server 2013-Front-End-Server in der Bereitstellung (zum Beispiel acht Server) dividiert, um die geschätzte Anzahl der Besprechungsteilnehmer pro Front-End-Server (in diesem Beispiel 500 Benutzer pro Front-End-Server) zu ermitteln.

  - Die Anzahl der Benutzer pro Front-End-Server wurde durch die durchschnittliche Konferenzgröße (zum Beispiel vier Benutzer) dividiert, um die geschätzte durchschnittliche Anzahl der Konferenzen pro Front-End-Server (in diesem Beispiel 125 Konferenzen pro Front-End-Server) zu ermitteln.

  - Zur Ermittlung der Medienlast auf jedem Front-End-Server wurde der kombinierte Mediendatenverkehr geschätzt. Nimmt man zum Beispiel an, dass für 75 Prozent der Konferenzen mehr als lediglich Audiounterstützung und für 50 Prozent dieser Besprechungen Anwendungsfreigabe erforderlich ist, stellen im Durchschnitt 47 Besprechungen und 188 Benutzer gleichzeitig Verbindungen zu Front-End-Server zur Anwendungsfreigabe her.

  - Es wurden verschiedene Besprechungsgrößen getestet (auf Basis des Modells mit bis zu 250 Benutzern in einem freigegebenen Pool), um die Serverskalierbarkeit zu gewährleisten.

