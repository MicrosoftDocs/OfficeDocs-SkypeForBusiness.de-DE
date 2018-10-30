---
title: 'Lync Server 2013: Features und Funktionen für Front-End-Server, Chat und Anwesenheit'
TOCTitle: Features und Funktionen für Front-End-Server, Chat und Anwesenheit
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398109(v=OCS.15)
ms:contentKeyID: 49293053
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Features und Funktionen für Front-End-Server, Chat und Anwesenheit in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-17_

Front-End-Server bieten einen Großteil der Lync Server-Funktionen. Zwei Editionen sind verfügbar: Lync Server Enterprise Edition, primär für größere Organisationen, und Lync Server Standard Edition, primär für kleinere Organisationen, die weniger in Hardware investieren möchten und keine hohe Verfügbarkeit benötigen. Beide Editionen unterstützen alle Lync Server-Arbeitsauslastungen, einschließlich Instant Messaging, Anwesenheit, Konferenzen und Enterprise-VoIP.

Mit der Chatfunktion können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Chatnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Sofortnachrichtensitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.


> [!IMPORTANT]
> Wenn Lync- und Communicator-Clients an einer Eins-zu-Eins-Kommunikation beteiligt sind, wird dies häufig als Peer-to-Peer-Situation bezeichnet. Vom technischen Standpunkt aus gesehen, kommunizieren die zwei Clients in einer Eins-zu-Eins-Unterhaltung mit der Multipoint Control Unit für Instant Messaging (IMMCU) als Bindeglied. Die IMMCU stellt eine Komponente von Front-End-Server dar. Die Platzierung der IMMCU im erforderlichen Kommunikationsworkflow ermöglicht die Aufzeichnung von Anrufdetails und weitere Features, die durch den Front-End-Server bereitgestellt werden. Die Kommunikation erfolgt von einem dynamischen Quellport auf dem Client an den Front-End-Server-Port TLS/TCP/5061 (bei angenommener Verwendung der empfohlenen Sicherheit in der Transportschicht). Konstruktionsbedingt ist Peer-to-Peer-Kommunikation (sowie Chat mit mehreren Teilnehmern) nur möglich, wenn Lync Server und die IMMCU aktiv und verfügbar sind.



Die *Anwesenheitsfunktion* liefert Benutzern Informationen zum Status anderer Benutzer im Netzwerk. Der Anwesenheitsstatus eines Benutzers enthält Informationen, mit deren Hilfe andere Benutzer entscheiden können, ob sie versuchen sollen, den Benutzer zu kontaktieren und ob die Kontaktaufnahme per Sofortnachricht, Telefon oder E-Mail erfolgen soll. Durch die Anwesenheitsfunktion wird, wenn möglich, eine sofortige Kommunikation gefördert. Sie liefert jedoch auch Informationen dazu, ob ein Benutzer sich in einer Besprechung befindet oder unterwegs ist und eine sofortige Kommunikation demnach nicht möglich ist. Dieser Anwesenheitsstatus wird als Anwesenheitssymbol in Lync und anderen Anwendungen mit Unterstützung der Anwesenheitsfunktion angezeigt. Hierzu zählen beispielsweise der Microsoft Outlook-Client für Messaging und Zusammenarbeit, Microsoft SharePoint-Technologien, Microsoft Word-Teamdienste oder Portalserver oder -dienste sowie die Microsoft Excel-Tabellenkalkulationssoftware. Das Anwesenheitssymbol für den Benutzer spiegelt die aktuelle Verfügbarkeit und die Bereitschaft einer Person zur Kommunikation wider.

