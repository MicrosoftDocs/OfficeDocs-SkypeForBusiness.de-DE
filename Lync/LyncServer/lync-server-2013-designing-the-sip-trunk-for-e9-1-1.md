---
title: 'Lync Server 2013: Entwerfen des SIP-Trunks für E9-1-1'
TOCTitle: Entwerfen des SIP-Trunks für E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398323(v=OCS.15)
ms:contentKeyID: 49293976
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entwerfen des SIP-Trunks für E9-1-1 in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync Server verwendet SIP-Trunks, um einen Notruf an den E9-1-1-Dienstanbieter weiterzuleiten. Sie können für E9-1-1 an einem zentralen Standort, an mehreren zentralen Standorten oder an jeder Zweigstelle einrichten. Wenn jedoch die WAN-Verbindung zwischen dem Standort des Anrufers und dem Standort, an dem der Notfalldienst-SIP-Trunk gehostet wird, nicht verfügbar ist, ist für einen Anruf von einem Benutzer an dem nicht verbundenen Standort ein spezieller Telefonverwendungsdatensatz in der VoIP-Richtlinie des Benutzers erforderlich, der den Anruf über das lokale PSTN-Gateway an das ECRC weiterleitet. Das gleiche trifft zu, wenn in der Anrufsteuerung Begrenzungen für gleichzeitige Anrufe aktiviert sind.


> [!NOTE]
> Es gibt zwei Methoden, um einen SIP-Trunk in einer Lync Server-Umgebung zu implementieren: 
> <UL>
> <LI>
> <P>Verwendung mehrfach vernetzter Vermittlungsserver, die ihre extern ausgerichteten öffentlich weitergeleiteten Schnittstellen zur Kommunikation mit dem SIP-Trunk-Anbieter nutzen.</P>
> <LI>
> <P>Verwenden eines lokalen SBC (Session Border Controller), um eine sichere Trennung der Vermittlungsserver von den Diensten des SIP-Trunk-Anbieters zu bieten.</P></LI></UL>Wenn Sie sich für die zweite Methode entscheiden, stellen Sie sicher, dass die Marke/das Modell des von Ihnen ausgewählten SBC die Weitergabe von PIDF-LO (Presence Information Data Format Location Object)-Standortdaten als Teil der SIP INVITE unterstützt. Andernfalls gehen die Anrufe ohne Standortinformationen beim Anbieter für die Notrufunterstützung ein. Nähere Informationen über zertifizierte SBS finden in <A class=uri href="http://go.microsoft.com/fwlink/?linkid=248425">http://go.microsoft.com/fwlink/?linkid=248425</A> unter "Qualifizierte Infrastruktur für Microsoft Lync".<BR>Über E9-1-1-Dienstanbieter erhalten Sie Zugriff auf ein SBC-Paar, um Redundanz zu gewährleisten. Sie müssen mehrere Entscheidungen bezüglich der Vermittlungsserver-Topologie und Anrufweiterleitungskonfiguration treffen. Möchten Sie beide SBCs als gleichwertig behandeln und Roundrobinrouting für Anrufe zwischen ihnen verwenden, oder legen Sie einen SBC als primären und den anderen als sekundären SBC fest?



Ausführliche Informationen zum Bereitstellen eines SIP-Trunks in Lync Server finden Sie unter [Implementierung von SIP-Trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md). Zur einfacheren Bereitstellung der SIP-Trunks für E9-1-1 sollten Sie zunächst die folgenden Fragen beantworten.

  - **Soll der SIP-Trunk über eine dedizierte geleaste oder eine gemeinsam genutzte Internetverbindung bereitgestellt werden?**  
    Es ist wichtig, dass Notrufe jederzeit getätigt werden können. Eine dedizierte Leitung bietet eine Verbindung, die nicht durch anderen Datenverkehr im Netzwerk belegt ist, und bietet gleichzeitig die Möglichkeit zur Implementierung von QoS. Denken Sie daran, dass eine IPSec-Verschlüsselung erforderlich ist, wenn Sie beim Herstellen einer Verbindung mit Anbietern für die Notrufunterstützung über das öffentliche Internet die Vertraulichkeit von Notrufen gewährleisten müssen.

<!-- end list -->

  - **Ist Ihre E9-1-1-Bereitstellung für Ausfalltoleranz ausgelegt?**  
    Da es sich um eine Lösung für Notrufe handelt, ist die Ausfallsicherheit von grundlegender Bedeutung. Stellen Sie Ihre primären und sekundären Vermittlungsserver und SIP-Trunks an ausfallsicheren Standorten bereit. Es ist sinnvoll, den primären Vermittlungsserver in geografischer Nähe zu den unterstützten Benutzern bereitzustellen und ein Failover für Anrufe über den sekundären Vermittlungsserver (an einem anderen geografischen Standort) abzuwickeln.

<!-- end list -->

  - **Sollten Sie einen separaten SIP-Trunk für jeden Zweigstellenstandort bereitstellen?**  
    Lync Server bietet verschiedene Strategien für das Gewährleisten von VoIP-Ausfallsicherheit in Zweigstellen, darunter: Konfigurieren ausfallsicherer Datennetzwerke, Bereitstellen eines SIP-Trunks an jedem Zweigstellenstandort oder Weiterleiten von Anrufen an das lokale Gateway bei einem Ausfall. Ausführliche Informationen finden Sie unter [SIP-Trunking für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).

<!-- end list -->

  - **Ist die Anrufsteuerung aktiviert?**  
    Lync Server verarbeitet Notrufe in gleicher Weise wie gewöhnliche Anrufe. Aus diesem Grund kann sich die Bandbreitenverwaltung oder Anrufsteuerung negativ auf die E9-1-1-Konfiguration auswirken. Notrufe werden möglicherweise blockiert oder zum lokalen PSTN-Gateway geroutet, wenn die Anrufsteuerung aktiviert ist und der konfigurierte Grenzwert für die Verbindung überschritten wird, über die Notrufe geroutet werden. Wie bereits in diesem Thema besprochen verfügen solche Anrufe über keine Standortdaten und müssen manuell an das ECRC weitergeleitet werden.

