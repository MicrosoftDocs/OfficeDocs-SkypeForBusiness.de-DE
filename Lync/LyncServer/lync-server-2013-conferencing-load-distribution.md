---
title: Lastverteilung für Konferenzen
TOCTitle: Lastverteilung für Konferenzen
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204922(v=OCS.15)
ms:contentKeyID: 49294085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lastverteilung für Konferenzen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Im Gegensatz zu einigen anderen Konferenzlösungen liegt der Lync Server-Architektur ein Hardwarefreigabemodell zugrunde. Dies bedeutet, dass die Hardware von zahlreichen Softwarekomponenten gemeinsam verwendet wird, die jeweils andere Echtzeitkommunikationsmodi unterstützen. Jeder Echtzeitkommunikationsmodus stellt eine spezifische Serverlast dar. Beispielsweise können auf dem Front-End-Server die SIP-Routingkomponenten (Session Initiation Protocol), Webanwendungen (wie die Adressbuchsuche), der Webkonferenzdienst, der A/V-Konferenzdienst und Enterprise-VoIP-Anwendungen (z. B. Konferenzzentrale oder Reaktionsgruppenanwendung) sowie Vermittlungsserver ausgeführt werden. Eine Reihe von Datenbanken auf dem Front-End-Server stellen darüber hinaus Speicher- und Verarbeitungskapazitäten für Benutzer-, Kontakt-, Anwesenheits-, Konferenz- und VoIP-Routing-Daten bereit. Aufgrund der Hardwarefreigabe konkurrieren die einzelnen Komponenten, Dienste und Prozesse um die CPU- und Speicherressourcen. Dies hat zur Folge, dass sich Arbeitsauslastungen, die nicht auf Konferenzen zurückzuführen sind, unmittelbar auf die Serverskalierung auswirken.

Im Gegensatz zu anderen portbasierten Hardwarekonferenzlösungen stellt die Lync Server-Konferenzarchitektur ein Modell ohne Reservierungen dar. Wenn ein Benutzer eine Besprechung plant, erstellt Lync Server einen Eintrag in der Konferenzdatenbank. In diesem Eintrag werden die Konferenzdaten gespeichert. Hardwareressourcen für die geplante Besprechung werden jedoch nicht im Voraus reserviert. Lync Server verfügt stattdessen über eine integrierte Lastenausgleichslogik zur dynamischen Allokation der Konferenzressourcen von Front-End-Server. Diese sorgt dafür, dass die Arbeitslasten gleichmäßig auf alle Front-End-Server im Pool verteilt werden. Hardwareressourcen können so effizient bereitgestellt und genutzt werden. Allerdings stellt die Unterstützung sehr großer Besprechungen, insbesondere bei unzureichender Planung) eine besondere Herausforderung für dieses Modell dar. Wenn ein Lync Server 2013-Pool beispielsweise seine Leistungsgrenze annähernd erreicht hat, können auf jedem Front-End-Server etwa 125 Besprechungen durchschnittlicher Größe gehostet werden. Kleine Besprechungen können jetzt ohne Probleme noch hinzugefügt werden. Eine weitere Besprechung mit 1000 Benutzern würde jedoch ein Problem darstellen, da Front-End-Server voraussichtlich nicht in der Lage wäre, diese zusätzlich zu den bereits bestehenden 125 Besprechungen zu unterstützen.

