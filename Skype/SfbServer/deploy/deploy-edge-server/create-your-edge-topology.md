---
title: Erstellen der Edgetopologie für Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Strat_SB_Hybrid
ms.custom: null
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Edgeservertopologie in Skype for Business Server erstellen, veröffentlichen und exportieren.'
---

# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Erstellen der Edgetopologie für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Edgeservertopologie in Skype for Business Server erstellen, veröffentlichen und exportieren.
  
Der Topologie-Generator ist das Tool, das Sie zum Erstellen Ihrer Edgeservertopologie verwenden müssen, genau wie er für alle Topologiekomponenten für Skype for Business Server verwendet wird. Bevor Sie die folgenden Schritte ausführen, müssen Sie mindestens einen Front-End-Pool oder einen Standard Edition Server eingerichtet haben.
  
Wir behandeln die folgenden Themen in diesem Artikel:
  
- Erstellen der Edgeservertopologie
    
- Veröffentlichen der Edgeservertopologie
    
- Exportieren der Edgeservertopologie
    
  > [!NOTE]
  > Um die folgenden Schritte auszuführen, müssen Sie sich bei den unten genannten Domänenservern als Benutzer anmelden, der Mitglied der folgenden Domänengruppen ist: 
  
- RTCUniversalServerAdmins
    
- Domänen-Admins
    
## <a name="build-your-edge-server-topology"></a>Erstellen der Edgeservertopologie

Der erste Bereitstellungsschritt besteht darin, ihre Skype for Business Server Edgeservertopologie zu erstellen, die aus einer von drei Optionen besteht:
  
- Ein einzelner Edgeserver
    
- Edgepool mit DNS-Lastenausgleich (ein oder mehrere Server)
    
- Edgepool mit Hardwarelastenausgleich (mindestens ein Server)
    
Wenn Sie nicht sicher sind, was Sie benötigen, ist es ein guter Zeitpunkt, die Planungsdokumentation durchzugehen, bevor Sie mit dem Ausführen dieser Schritte beginnen. Andernfalls beginnen wir.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definieren der Topologie für einen einzelnen Edgeserver

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server Front-End-Pool an.
    
2. Öffnen Sie **dort Skype for Business Server Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **"Neuer Edgepool**".
    
5. Klicken Sie auf dem Bildschirm **"Neuen Edgepool definieren**" auf **"Weiter**".
    
6. Geben **Sie auf dem Bildschirm "Edgepool-FQDN definieren** " den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgeserver verwenden wird, und wählen Sie " **Pool mit einem Computer**" aus, und klicken Sie dann auf **"Weiter** ".
    
7. Auf dem Bildschirm " **Features auswählen** " haben Sie folgende Auswahlmöglichkeiten:
    
   - Möglicherweise möchten Sie denselben FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " aktivieren (und dies für Schritt 9 unten beachten).
    
   - Wenn Sie planen, den Partnerverbund zu aktivieren, aktivieren Sie das Kontrollkästchen **Verbund für diesen Edgepool aktivieren (Port 5061).**
    
8. Sobald Sie auf " **Weiter**" geklickt haben, werden Sie sich auf dem Bildschirm " **IP-Optionen"** befinden. Ihre Optionen sind wie folgt:
    
   - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
   Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden, und Sie diese Adressen intern oder extern auf Ihrem Edgeserver anwenden (Dies müssen Sie bei Schritt 10 berücksichtigen). Sie haben auch die Möglichkeit, ihren Edgeserver oder Ihren Edgepool so zu konfigurieren, dass eine NAT-Adresse (Network Address Translation) für die externe IP-Adresse verwendet wird. Sie können dies tun, indem Sie das Kontrollkästchen **"Die externe IP-Adresse dieses Edgepools wird durch NAT übersetzt** " auswählen. Klicken Sie auf **"Weiter** ", wenn sie fertig ist.
    
9. Auf dem Bildschirm "Externe FQDNs" hängen Ihre Auswahl von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen " **Einzelnen FQDN und ip-Adresse verwenden** " aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das **SIP-Zugriffsfeld** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den **SIP-Zugriffs-Edgedienst** , 444 für den **Webkonferenz-Edgedienst** und 443 für den **A/V-Edgedienst** . Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " nicht aktiviert haben, müssen Sie jetzt die drei externen FQDNs für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben. Klicken Sie abschließend auf **Weiter**.
    
10. Sie befinden sich nun auf dem Bildschirm " **Interne IP-Adresse definieren** ". Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder " **Interne IPv4-Adresse** " und " **Interne IPv6-Adresse** " ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken Sie auf **"Weiter** ", wenn sie fertig ist.
    
11. Auf dem Bildschirm " **Externe IP-Adresse definieren** " stehen Ihnen je nach vorheriger Auswahl einige Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4- oder IPv6-Adresse (je nachdem, was Sie verwenden) in das **Textfeld für den SIP-Zugriff** ein, und klicken Sie dann auf **"Weiter**".
    
    - Möglicherweise haben Sie drei separate FQDNs und IP-Adressen für die Dienste verwendet. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder IPv6-Adressen für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter**".
    
    > [!NOTE]
    > Wenn Sie zuvor nicht die Aktivierung und Zuweisung der IPv6-Adressierung ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
12. Wenn Sie sich in Schritt 8 für die Verwendung von NAT entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem **Textfeld für öffentliche IP-Adressen** . Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst festgelegt haben, um von NAT übersetzt zu werden. Klicken Sie dann auf **Weiter**.
    
13. Der nächste Bildschirm nach oben ist **Definieren des nächsten Hops**. Wählen Sie im Feld **"Nächster Hoppool** " den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
14. Auf dem Bildschirm "**Front-End-Pools zuordnen**" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition Server, die diesem Edgeserver zugeordnet werden sollen. Wählen Sie einfach die Namen der internen Pools aus, die Sie mit diesem Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier Folgendes: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server Edgeserver verwenden, können sie nicht über mehrere Zuordnungen verfügen. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie mit dieser neuen Zuordnung fortfahren, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
15. Klicken Sie auf dem nächsten Bildschirm auf **"Fertig stellen** ".
    
16. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeservern in Skype for Business Server](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitzustellen.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen DNS-Edgeserverpool mit Lastenausgleich

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server Front-End-Server an.
    
2. Öffnen Sie **dort Skype for Business Server Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **"Neuer Edgepool**".
    
5. Klicken Sie auf dem Bildschirm **"Neuen Edgepool definieren**" auf **"Weiter**".
    
6. Geben **Sie auf dem Bildschirm "Edgepool-FQDN definieren** " den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgepool verwenden wird, und wählen Sie " **Pool mit mehreren Computern**" aus, und klicken Sie dann auf **"Weiter** ".
    
7. Auf dem Bildschirm " **Features auswählen** " haben Sie folgende Auswahlmöglichkeiten:
    
    - Möglicherweise möchten Sie den gleichen FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " aktivieren (und dies für Schritt 9 unten beachten).
    
    - Wenn Sie planen, den Partnerverbund zu aktivieren, aktivieren Sie das Kontrollkästchen **Verbund für diesen Edgepool aktivieren (Port 5061).**
    
8. Sobald Sie auf " **Weiter**" geklickt haben, werden Sie sich auf dem Bildschirm " **IP-Optionen"** befinden. Ihre Optionen sind wie folgt:
    
    - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
     Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden, und Sie diese Adressen intern oder extern auf Ihrem Edgeserver anwenden (Dies müssen Sie bei Schritt 11 berücksichtigen). Sie haben auch die Möglichkeit, ihren Edgeserver oder Ihren Edgepool so zu konfigurieren, dass eine NAT-Adresse (Network Address Translation) für die externe IP-Adresse verwendet wird. Sie können dies tun, indem Sie das Kontrollkästchen **"Die externe IP-Adresse dieses Edgepools wird durch NAT übersetzt** " auswählen. Klicken Sie auf **"Weiter** ", wenn sie fertig ist.
    
9. Auf dem Bildschirm "Externe FQDNs" hängen Ihre Auswahl von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen " **Einzelnen FQDN und ip-Adresse verwenden** " aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das **SIP-Zugriffsfeld** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den **SIP-Zugriffs-Edgedienst** , 444 für den **Webkonferenz-Edgedienst** und 443 für den **A/V-Edgedienst** . Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " nicht aktiviert haben, müssen Sie jetzt die drei externen FQDNs für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben. Klicken Sie abschließend auf **Weiter**.
    
10. Nun haben Sie den Bildschirm " **Computer in diesem Pool definieren** " erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie befinden sich nun auf dem Bildschirm " **Interne IP-Adresse definieren** ". Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder " **Interne IPv4-Adresse** " und " **Interne IPv6-Adresse** " ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken Sie auf **"Weiter** ", wenn sie fertig ist.
    
12. Auf dem Bildschirm " **Externe IP-Adresse definieren** " stehen Ihnen je nach vorheriger Auswahl einige Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4- oder IPv6-Adresse (je nachdem, was Sie verwenden) in das **Textfeld für den SIP-Zugriff** ein, und klicken Sie dann auf **"Weiter**".
    
    - Möglicherweise haben Sie drei separate FQDNs und IP-Adressen für die Dienste verwendet. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder IPv6-Adressen für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter**".
    
    > [!NOTE]
    > Wenn Sie zuvor nicht die Aktivierung und Zuweisung der IPv6-Adressierung ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
13. Klicken Sie auf **Fertig stellen**. Der Edgeserver, den Sie soeben erstellt haben, sollte nun im Dialogfeld " **Computer in diesem Pool definieren** " aufgeführt werden.
    
14. Klicken Sie noch auf dem Bildschirm " **Computer in diesem Pool definieren** " erneut auf die Schaltfläche " **Hinzufügen** ", und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool verwenden möchten. Klicken Sie nach Abschluss dieses Vorgangs auf **"Weiter**".
    
15. Wenn Sie sich in Schritt 8 für die Verwendung von NAT entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem **Textfeld für öffentliche IP-Adressen** . Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst festgelegt haben, um von NAT übersetzt zu werden. Klicken Sie dann auf **Weiter**.
    
16. Der nächste Bildschirm nach oben ist **Definieren des nächsten Hops**. Wählen Sie im Feld **"Nächster Hoppool** " den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
17. Auf dem Bildschirm "**Front-End-Pools zuordnen**" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition Pools, die diesem Edgeserver zugeordnet werden sollen. Wählen Sie einfach die Namen der internen Pools aus, die Sie mit diesem Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier Folgendes: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server Edgeserver verwenden, können sie nicht über mehrere Zuordnungen verfügen. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie mit dieser neuen Zuordnung fortfahren, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
18. Klicken Sie auf dem nächsten Bildschirm auf **"Fertig stellen** ".
    
19. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeservern in Skype for Business Server](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitzustellen.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen Edgeserverpool mit Hardwarelastenausgleich

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server Front-End-Server an.
    
2. Öffnen Sie **dort Skype for Business Server Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der rechten Maustaste auf **Edgepools**, und klicken Sie dann auf **"Neuer Edgepool**".
    
5. Klicken Sie auf dem Bildschirm **"Neuen Edgepool definieren**" auf **"Weiter**".
    
6. Geben **Sie auf dem Bildschirm "Edgepool-FQDN definieren** " den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgepool verwenden wird, und wählen Sie " **Pool mit mehreren Computern**" aus, und klicken Sie dann auf **"Weiter** ".
    
7. Auf dem Bildschirm " **Features auswählen** " haben Sie folgende Auswahlmöglichkeiten:
    
   - Möglicherweise möchten Sie den gleichen FQDN und die gleiche IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " aktivieren (und dies für Schritt 9 unten beachten).
    
   - Wenn Sie planen, den Partnerverbund zu aktivieren, aktivieren Sie das Kontrollkästchen **Verbund für diesen Edgepool aktivieren (Port 5061).**
    
8. Sobald Sie auf " **Weiter**" geklickt haben, werden Sie sich auf dem Bildschirm " **IP-Optionen"** befinden. Ihre Optionen sind wie folgt:
    
   - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
     Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden, und Sie diese Adressen intern oder extern auf Ihrem Edgeserver anwenden (Dies müssen Sie bei Schritt 11 berücksichtigen).
    
     > [!NOTE]
     > Im Gegensatz zu den beiden anderen Topologieoptionen DÜRFEN Sie bei Verwendung eines Hardwaregeräts zum Lastenausgleich **NICHT** die Option auswählen, dass die **externe IP-Adresse des Edgepools durch NAT übersetzt wird**. Dies wird **nicht unterstützt**.
  
9. Auf dem Bildschirm "Externe FQDNs" hängen Ihre Auswahl von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen " **Einzelnen FQDN und ip-Adresse verwenden** " aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das **SIP-Zugriffsfeld** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig voneinander eine Verbindung herstellen können. Wir empfehlen 5061 für den **SIP-Zugriffs-Edgedienst** , 444 für den **Webkonferenz-Edgedienst** und 443 für den **A/V-Edgedienst** . Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen " **Nur FQDN und IP-Adresse verwenden** " nicht aktiviert haben, müssen Sie jetzt die drei externen FQDNs für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben. Klicken Sie abschließend auf **Weiter**.
    
10. Nun haben Sie den Bildschirm " **Computer in diesem Pool definieren** " erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie befinden sich nun auf dem Bildschirm " **Interne IP-Adresse definieren** ". Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder " **Interne IPv4-Adresse** " und " **Interne IPv6-Adresse** " ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken Sie auf **"Weiter** ", wenn sie fertig ist.
    
12. Auf dem Bildschirm " **Externe IP-Adresse definieren** " stehen Ihnen je nach vorheriger Auswahl einige Optionen zur Verfügung:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn dies der Fall ist, geben Sie Ihre externe IPv4- oder IPv6-Adresse (je nachdem, was Sie verwenden) in das **Textfeld für den SIP-Zugriff** ein, und klicken Sie dann auf **"Weiter**".
    
    - Möglicherweise haben Sie drei separate FQDNs und IP-Adressen für die Dienste verwendet. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder IPv6-Adressen für den **SIP-Zugriffs-Edgedienst** , den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter**".
    
    > [!NOTE]
    > Wenn Sie zuvor nicht die Aktivierung und Zuweisung der IPv6-Adressierung ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
13. Klicken Sie auf **Fertig stellen**. Der Edgeserver, den Sie soeben erstellt haben, sollte nun im Dialogfeld " **Computer in diesem Pool definieren** " aufgeführt werden.
    
14. Klicken Sie noch auf dem Bildschirm " **Computer in diesem Pool definieren** " erneut auf die Schaltfläche " **Hinzufügen** ", und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool verwenden möchten. Klicken Sie nach Abschluss dieses Vorgangs auf **"Weiter**".
    
15. Der nächste Bildschirm nach oben ist **Definieren des nächsten Hops**. Wählen Sie im Feld **"Nächster Hoppool** " den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool handeln kann. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
16. Auf dem Bildschirm "**Front-End-Pools zuordnen**" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition Pools, die diesem Edgeserver zugeordnet werden sollen. Wählen Sie einfach die Namen der internen Pools aus, die Sie mit diesem Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier Folgendes: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server Edgeserver verwenden, können sie nicht über mehrere Zuordnungen verfügen. Wenn Sie einen internen Pool oder eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, die Sie über den anderen Edgeserver informiert, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie mit dieser neuen Zuordnung fortfahren, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
17. Klicken Sie auf dem nächsten Bildschirm auf **"Fertig stellen** ".
    
18. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen unter [Bereitstellen von Edgeservern in Skype for Business Server](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitzustellen.
    
## <a name="publish-your-edge-server-topology"></a>Veröffentlichen der Edgeservertopologie

Nachdem Sie die oben beschriebenen Schritte abgeschlossen haben, ist es an der Zeit, diese neue Topologie zu veröffentlichen, mit der Sie sie auch in Ihren Skype for Business Server Edgeserver oder Edgepool exportieren können. Gehen Sie folgendermaßen vor:
  
1. Starten Sie **den Topologie-Generator** (wenn er nicht bereits aus dem vorherigen Verfahren gestartet wurde).
    
2. Klicken Sie im **Topologie-Generator** in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server**, und klicken Sie dann auf **Skype for Business Server Topologie-Generator**.
    
3. Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.
    
4. Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.
    
5. Wenn der Status angibt, dass die Datenbankerstellung erfolgreich war, gehen Sie wie folgt vor:
    
    - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
    - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
## <a name="export-your-edge-server-topology"></a>Exportieren der Edgeservertopologie

Um die Bereitstellung erfolgreich durchzuführen, benötigt der Skype for Business Server Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers. Bei internen Servern in Ihrer Domäne oder Gesamtstruktur ist dies in der Regel einfach. Edgeserver befinden sich außerhalb der Domäne. Daher ist es erforderlich, die Topologiedatei manuell an den Edgeserverspeicherort zu exportieren, in der Regel auf einem physischen Medium. Dieser Export erfolgt über PowerShell:
  
1. Starten Sie die **Skype for Business Server-Verwaltungsshell**.
    
2. Führen Sie in der **Skype for Business Server Verwaltungsshell** Folgendes aus:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Kopieren Sie die exportierte Datei auf externe Medien (z. B. ein USB-Laufwerk oder eine Netzwerkfreigabe, die Sie vom Standort des Edgeservers erreichen können).
    

