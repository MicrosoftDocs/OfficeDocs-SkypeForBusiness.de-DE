---
title: Erstellen Ihrer Edge-Topologie für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Edgeserver-Topologie in Skype for Business Server erstellen, veröffentlichen und exportieren.'
ms.openlocfilehash: c625656f1686b6e72be2f0223d6560464bb9e7bc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001475"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Erstellen Ihrer Edge-Topologie für Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Ihre Edge-Server Topologie in Skype for Business Server erstellen, veröffentlichen und exportieren.
  
Der Topologie-Generator ist das Tool, das Sie zum Erstellen Ihrer Edgeserver-Topologie verwenden müssen, genauso wie Sie für eine beliebige Topologie-Komponente für Skype for Business Server verwendet wird. Bevor Sie die folgenden Schritte ausführen, müssen Sie mindestens einen Front-End-Pool oder einen Standard Edition-Server eingerichtet haben.
  
In diesem Artikel werden die folgenden Themen behandelt:
  
- Erstellen der Edgeserver-Topologie
    
- Veröffentlichen der Edgeservertopologie
    
- Exportieren der Edgeservertopologie
    
  > [!NOTE]
  > Sie müssen sich bei den unten genannten Domänenservern als Benutzer anmelden, der Mitglied der folgenden Domänengruppen ist, um die nachfolgend beschriebenen Schritte ausführen zu können: 
  
- RTCUniversalServerAdmins
    
- Domänen-Admins
    
## <a name="build-your-edge-server-topology"></a>Erstellen der Edgeserver-Topologie

Der erste Bereitstellungsschritt besteht darin, Ihre Skype for Business Server-Edgeserver-Topologie zu erstellen, die eine von drei Optionen umfasst:
  
- Ein einzelner Edgeserver
    
- Edge-Pool für DNS-Lastenausgleich (mindestens ein Server)
    
- Ein Edge-Pool mit Hardwarelastenausgleich (ein oder mehrere Server)
    
Wenn Sie sich über die benötigten Anforderungen nicht sicher sind, empfehlen wir Ihnen, die Planungsdokumentation durchzugehen, bevor Sie mit den nachfolgend beschriebenen Schritten fortfahren. Ansonsten kann es losgehen.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definieren der Topologie für einen einzelnen Edgeserver

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Pool an.
    
2. Öffnen Sie **den Skype for Business Server Topology Builder**.
    
3. Erweitern Sie in der Konsolenstruktur die Website, auf der Sie den Edge-Server bereitstellen werden.
    
4. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.
    
5. Klicken Sie auf dem Bildschirm **neuen Edge-Pool definieren** auf **weiter** .
    
6. Geben Sie auf dem Bildschirm **Edge-Pool-FQDN definieren** den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgeserver verwenden soll, und wählen Sie **Einzelcomputer Pool**aus, und klicken Sie dann auf **weiter** , wenn Sie fertig sind.
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
   - Möglicherweise beabsichtigen Sie, den gleichen FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und ihren A/V-Edgedienst zu verwenden. Wenn dies der Fall ist, müssen Sie das **Kontrollkästchen einen einzelnen FQDN und eine IP-Adresse verwenden** (und beachten Sie dies für Schritt 9 weiter unten).
    
   - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
   - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
   Diese sind ziemlich selbsterklärend, ganz gleich, ob Sie IPv4-oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf dem Edgeserver anwenden (Sie müssen dies für Schritt 10 beachten). Sie haben auch die Möglichkeit, Ihren Edge-Server oder Ihren Edge-Pool so zu konfigurieren, dass eine NAT-Adresse (Network Address Translation) für die externe IP-Adresse verwendet wird. Wählen Sie dafür das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der NAT übersetzt** aus. Klicken Sie anschließend auf **Weiter**.
    
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** aktiviert haben, müssen Sie den einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Dann müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit diese alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **nur FQDN und IP-Adresse verwenden** nicht aktiviert haben, müssen Sie nun die drei externen FQDNs für den SIP- **Zugriffs** -Edgedienst, den **Webkonferenz-** Edgedienst und den **a/V** -Edgedienst eingeben. Klicken Sie anschließend auf **Weiter**.
    
10. Sie befinden sich nun auf dem Bildschirm **interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse Ihres Edge-Servers in den Textfeldern **interne IPv4-Adresse** und **interne IPv6-Adresse** ein, je nachdem, welche Optionen Sie in Schritt 8 zurückgegeben haben. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
11. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4-oder IPv6-Adresse (je nachdem, welche Sie verwenden) in das Textfeld **SIP Access** ein, und klicken Sie dann auf **weiter**.
    
    - Wenn Sie drei separate FQDNs und IP-Adressen verwenden möchten, geben Sie die externen IPv4 und IPv6-Adressen für den Edgedienst SIP-Zugriff, für den Edgedienst Webkonferenzen und für den Edgedienst A/V ein. Wenn dies der Fall ist, geben Sie Ihre externen IPv4-oder IPv6-Adressen für den **SIP Access** Edge-Dienst, den **Webkonferenz-** Edgedienst und den **A/V** -Edgedienst ein, und klicken Sie dann auf **weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
12. Wenn Sie sich für die Verwendung von NAT in Schritt 8 entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld für **öffentliche IP-Adressen** . Sie müssen die öffentliche IPv4-und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst eingerichtet haben, um von NAT übersetzt zu werden. Klicken Sie dann auf **Weiter**.
    
13. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster Hop-Pool** den Namen des internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
14. Auf dem Bildschirm " **Front-End-Pools zuordnen** " müssen Sie einen oder mehrere interne Pools angeben, einschließlich der Front-End-Pools und der Standard Edition-Server, die diesem Edgeserver zugeordnet werden sollen. Wählen Sie einfach die Namen der internen Pools aus, mit denen dieser Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwendet werden soll. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Dabei ist zu beachten, dass die internen Pools oder Standalone-Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, aber nicht über mehrere Zuordnungen verfügen können. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung fortführen, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
15. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
16. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeserver in Skype for Business Server](deploy-edge-servers.md) für die Bereitstellung auf dem Edgeserver von hier aus befolgen.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen DNS Load Balancing Edge-Server Pool

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Server an.
    
2. Öffnen Sie **den Skype for Business Server Topology Builder**.
    
3. Erweitern Sie in der Konsolenstruktur die Website, auf der Sie den Edge-Server bereitstellen werden.
    
4. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.
    
5. Klicken Sie auf dem Bildschirm **neuen Edge-Pool definieren** auf **weiter** .
    
6. Geben Sie auf dem Bildschirm **Edge-Pool-FQDN definieren** den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edge-Pool verwenden soll, und wählen Sie **mehrere Computerpool**aus, und klicken Sie dann auf **weiter** , wenn Sie fertig sind
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
    - Möglicherweise beabsichtigen Sie, den gleichen FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und ihren A/V-Edgedienst zu verwenden. Wenn dies der Fall ist, müssen Sie das **Kontrollkästchen einen einzelnen FQDN und eine IP-Adresse verwenden** (und beachten Sie dies für Schritt 9 weiter unten).
    
    - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
    - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
     Diese sind ziemlich selbsterklärend, ganz gleich, ob Sie IPv4-oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf dem Edgeserver anwenden (Sie müssen dies für Schritt 11 beachten). Sie haben auch die Möglichkeit, Ihren Edge-Server oder Ihren Edge-Pool so zu konfigurieren, dass eine NAT-Adresse (Network Address Translation) für die externe IP-Adresse verwendet wird. Wählen Sie dafür das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der NAT übersetzt** aus. Klicken Sie anschließend auf **Weiter**.
    
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** aktiviert haben, müssen Sie den einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Dann müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit diese alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **nur FQDN und IP-Adresse verwenden** nicht aktiviert haben, müssen Sie nun die drei externen FQDNs für den SIP- **Zugriffs** -Edgedienst, den **Webkonferenz-** Edgedienst und den **a/V** -Edgedienst eingeben. Klicken Sie anschließend auf **Weiter**.
    
10. Sie haben nun den Bildschirm " **Computer in diesem Pool definieren** " erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie befinden sich nun auf dem Bildschirm **interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse Ihres Edge-Servers in den Textfeldern **interne IPv4-Adresse** und **interne IPv6-Adresse** ein, je nachdem, welche Optionen Sie in Schritt 8 zurückgegeben haben. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
12. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4-oder IPv6-Adresse (je nachdem, welche Sie verwenden) in das Textfeld **SIP Access** ein, und klicken Sie dann auf **weiter**.
    
    - Wenn Sie drei separate FQDNs und IP-Adressen verwenden möchten, geben Sie die externen IPv4 und IPv6-Adressen für den Edgedienst SIP-Zugriff, für den Edgedienst Webkonferenzen und für den Edgedienst A/V ein. Wenn dies der Fall ist, geben Sie Ihre externen IPv4-oder IPv6-Adressen für den **SIP Access** Edge-Dienst, den **Webkonferenz-** Edgedienst und den **A/V** -Edgedienst ein, und klicken Sie dann auf **weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
13. Klicken Sie auf **Fertig stellen**. Der soeben erstellte Edge-Server sollte jetzt im Dialogfeld **Computer in diesem Pool definieren** aufgelistet werden.
    
14. Klicken Sie noch immer auf dem Bildschirm **Computer in diesem Pool definieren** auf die Schaltfläche **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool haben möchten. Klicken Sie auf **Weiter**, wenn Sie damit fertig sind.
    
15. Wenn Sie sich für die Verwendung von NAT in Schritt 8 entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld für **öffentliche IP-Adressen** . Sie müssen die öffentliche IPv4-und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst eingerichtet haben, um von NAT übersetzt zu werden. Klicken Sie dann auf **Weiter**.
    
16. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster Hop-Pool** den Namen des internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
17. Auf dem Bildschirm " **Front-End-Pools zuordnen** " müssen Sie einen oder mehrere interne Pools angeben, einschließlich der Front-End-Pools und der Standard Edition-Pools, die mit diesem Edgeserver verknüpft werden sollen. Wählen Sie einfach die Namen der internen Pools aus, mit denen dieser Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwendet werden soll. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Dabei ist zu beachten, dass die internen Pools oder Standalone-Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, aber nicht über mehrere Zuordnungen verfügen können. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung fortführen, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
18. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
19. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeserver in Skype for Business Server](deploy-edge-servers.md) für die Bereitstellung auf dem Edgeserver von hier aus befolgen.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen Hardwarelastenausgleich-Edgeserver-Pool

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Server an.
    
2. Öffnen Sie **den Skype for Business Server Topology Builder**.
    
3. Erweitern Sie in der Konsolenstruktur die Website, auf der Sie den Edge-Server bereitstellen werden.
    
4. Klicken Sie mit der rechten Maustaste auf **Edge-Pools**, und klicken Sie dann auf **neuer Edge-Pool**.
    
5. Klicken Sie auf dem Bildschirm **neuen Edge-Pool definieren** auf **weiter** .
    
6. Geben Sie auf dem Bildschirm **Edge-Pool-FQDN definieren** den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edge-Pool verwenden soll, und wählen Sie **mehrere Computerpool**aus, und klicken Sie dann auf **weiter** , wenn Sie fertig sind
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
   - Möglicherweise beabsichtigen Sie, den gleichen FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und ihren A/V-Edgedienst zu verwenden. Wenn dies der Fall ist, müssen Sie das **Kontrollkästchen einen einzelnen FQDN und eine IP-Adresse verwenden** (und beachten Sie dies für Schritt 9 weiter unten).
    
   - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
   - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
     Diese sind ziemlich selbsterklärend, ganz gleich, ob Sie IPv4-oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf dem Edgeserver anwenden (Sie müssen dies für Schritt 11 beachten).
    
     > [!NOTE]
     > Im Gegensatz zu den beiden anderen Topologie-Optionen müssen Sie bei Verwendung eines Hardwarelastenausgleichs die Option die **externe IP-Adresse des Edge-Pools, die von NAT übersetzt wird**, **nicht** auswählen. Dies wird **nicht unterstützt**.
  
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **einen einzelnen FQDN und eine IP-Adresse verwenden** aktiviert haben, müssen Sie den einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Dann müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit diese alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **nur FQDN und IP-Adresse verwenden** nicht aktiviert haben, müssen Sie nun die drei externen FQDNs für den SIP- **Zugriffs** -Edgedienst, den **Webkonferenz-** Edgedienst und den **a/V** -Edgedienst eingeben. Klicken Sie anschließend auf **Weiter**.
    
10. Sie haben nun den Bildschirm " **Computer in diesem Pool definieren** " erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie befinden sich nun auf dem Bildschirm **interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse Ihres Edge-Servers in den Textfeldern **interne IPv4-Adresse** und **interne IPv6-Adresse** ein, je nachdem, welche Optionen Sie in Schritt 8 zurückgegeben haben. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
12. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4-oder IPv6-Adresse (je nachdem, welche Sie verwenden) in das Textfeld **SIP Access** ein, und klicken Sie dann auf **weiter**.
    
    - Wenn Sie drei separate FQDNs und IP-Adressen verwenden möchten, geben Sie die externen IPv4 und IPv6-Adressen für den Edgedienst SIP-Zugriff, für den Edgedienst Webkonferenzen und für den Edgedienst A/V ein. Wenn dies der Fall ist, geben Sie Ihre externen IPv4-oder IPv6-Adressen für den **SIP Access** Edge-Dienst, den **Webkonferenz-** Edgedienst und den **A/V** -Edgedienst ein, und klicken Sie dann auf **weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
13. Klicken Sie auf **Fertig stellen**. Der soeben erstellte Edge-Server sollte jetzt im Dialogfeld **Computer in diesem Pool definieren** aufgelistet werden.
    
14. Klicken Sie noch immer auf dem Bildschirm **Computer in diesem Pool definieren** auf die Schaltfläche **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool haben möchten. Klicken Sie auf **Weiter**, wenn Sie damit fertig sind.
    
15. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster Hop-Pool** den Namen des internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
16. Auf dem Bildschirm " **Front-End-Pools zuordnen** " müssen Sie einen oder mehrere interne Pools angeben, einschließlich der Front-End-Pools und der Standard Edition-Pools, die mit diesem Edgeserver verknüpft werden sollen. Wählen Sie einfach die Namen der internen Pools aus, mit denen dieser Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwendet werden soll. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Dabei ist zu beachten, dass die internen Pools oder Standalone-Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, aber nicht über mehrere Zuordnungen verfügen können. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung fortführen, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
17. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
18. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeserver in Skype for Business Server](deploy-edge-servers.md) für die Bereitstellung auf dem Edgeserver von hier aus befolgen.
    
## <a name="publish-your-edge-server-topology"></a>Veröffentlichen der Edgeservertopologie

Nachdem Sie die obigen Schritte ausgeführt haben, ist es an der Zeit, diese neue Topologie zu veröffentlichen, mit der Sie Sie auch in Ihren Skype for Business Server-Edgeserver oder Edge-Pool exportieren können. Führen Sie die folgenden Schritte aus:
  
1. Starten Sie den **Topologie-Generator** (wenn dieser nicht bereits aufgrund eines vorhergehenden Verfahrens geöffnet ist).
    
2. Klicken Sie im **Topologie-Generator**in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server** , und klicken Sie dann auf **Skype for Business Server Topology Builder**.
    
3. Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.
    
4. Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.
    
5. Wenn die erfolgreiche Erstellung der Datenbank angezeigt wird, führen Sie folgende Schritte aus:
    
    - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
    - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
## <a name="export-your-edge-server-topology"></a>Exportieren der Edgeservertopologie

Zur erfolgreichen Bereitstellung benötigt der Skype for Business Server-Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers. Für interne Server in Ihrer Domäne oder Gesamtstruktur ist dies in der Regel unkompliziert. Edgeserver sind außerhalb der Domäne, und daher ist es notwendig, die topologiedatei manuell auf den Edgeserver-Speicherort zu exportieren, in der Regel auf einem physikalischen Medium. Dieser Export erfolgt über PowerShell:
  
1. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie in der **Skype for Business Server-Verwaltungsshell**die folgenden Aktionen aus:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Kopieren Sie die exportierte Datei auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die Sie vom Standort des Edge-Servers aus erreichen können).
    

