---
title: 'Lync Server 2013: Überprüfen der Konnektivität für externe Benutzer'
TOCTitle: Überprüfen der Konnektivität für externe Benutzer
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398402(v=OCS.15)
ms:contentKeyID: 49294122
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Konnektivität für externe Benutzer in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Zum Überprüfen der Konnektivität für externe Benutzer müssen Sie sicherstellen, dass sich die Benutzer mit dem Server und mit dem Port für den Zugriffs-Edgedienst verbinden können.

Eine wertvolle Ressource zur Überprüfung Ihrer Konfiguration sowie der Funktion zum Verbinden, Senden und Empfangen der richtigen Nachrichten für Szenarien, in denen der Zugriff durch externe Benutzer erforderlich ist, ist der Standort für die Remotebenutzerkonnektivität ( <https://www.testocsconnectivity.com/>). Dieser Standort wird vom Microsoft-Support verwaltet. Um die Remoteverbindungsanalyse zu verwenden, öffnen Sie die Website in einem Browser, und folgen Sie den Anweisungen zum Auswählen des Szenarios.

## Testen der Konnektivität externer Benutzer und des externen Zugriffs

Tests für den Zugriff durch externe Benutzer sollten sämtliche Typen von externen Benutzern umfassen, die von Ihrer Organisation unterstützt werden. Dazu können die folgenden Typen zählen:

  - Benutzer aus mindestens einer Partnerdomäne sowie Testen von Chat-, Anwesenheits-, A/V-Funktionen und Desktopfreigabe.

  - Benutzer öffentlicher Chatdienstanbieter, die von Ihrer Organisation unterstützt werden (und für welche die Bereitstellung abgeschlossen wurde).

  - Anonyme Benutzer.

  - Benutzer innerhalb Ihrer Organisation, die sich remote bei Lync anmelden, jedoch kein VPN verwenden.

Mithilfe dieser Tests wird ermittelt, ob Ihr Edgeserver folgende Aufgaben ausführt:

  - Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
      - Beispiel: telnet sip.contoso.com 443
    
      - Ausführen des vorstehenden Tests für Ports, die Sie abhängig von Ihrer Bereitstellung auf dem Edgeserver oder Edgeserverpool verwenden.

  - Ausführen einer präzisen externen DNS-Auflösung.
    
      - Senden Sie von außerhalb Ihres Netzwerks ein Pingsignal an jeden externen FQDN Ihres Edgeservers oder Edgeserverpools. Selbst wenn das Pingen nicht erfolgreich ist, werden die IP-Adressen angezeigt, die Sie mit den von Ihnen zugewiesenen Adressen vergleichen können.

