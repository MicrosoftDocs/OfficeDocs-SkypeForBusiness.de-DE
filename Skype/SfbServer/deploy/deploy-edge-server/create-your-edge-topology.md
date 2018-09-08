---
title: Erstellen Sie eine Edge-Topologie für Skype für Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Zusammenfassung: Informationen Sie zum Erstellen, veröffentlichen und Exportieren der Edge-Server-Topologie in Skype für Business Server.'
ms.openlocfilehash: 772a37437af902513d7245a1e8bd18a565fca5e9
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883915"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Erstellen Sie eine Edge-Topologie für Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Erstellen, veröffentlichen und Exportieren der Edge-Server-Topologie in Skype für Business Server.
  
Topologie-Generator ist das Tool müssen Sie zum Erstellen Ihrer Topologie Edge-Server verwenden, wie sie für jede Komponente Topologie für Skype für Business Server verwendet wird. Bevor Sie die folgenden Schritte, müssen Sie mindestens einen Front-End-Pool oder Standard Edition-Server eingerichtet haben.
  
In diesem Artikel werden die folgenden Themen behandelt:
  
- Erstellen Sie die Edge-Server-Topologie
    
- Veröffentlichen der Edgeservertopologie
    
- Exportieren der Edgeservertopologie
    
  > [!NOTE]
  > Sie müssen sich bei den unten genannten Domänenservern als Benutzer anmelden, der Mitglied der folgenden Domänengruppen ist, um die nachfolgend beschriebenen Schritte ausführen zu können: 
  
- "RTCUniversalServerAdmins"
    
- Domänen-Admins
    
## <a name="build-your-edge-server-topology"></a>Erstellen Sie die Edge-Server-Topologie

Der erste Bereitstellungsschritt erstellt Ihre Skype für Business Server Edge-Server-Topologie besteht aus eine der drei Optionen:
  
- Ein einzelner Edgeserver
    
- Einen edgepool mit DNS-Lastenausgleich (einem oder mehreren Servern)
    
- Ein Hardwaregerät zum Lastenausgleich des Edge-Pool (einem oder mehreren Servern)
    
Wenn Sie sich über die benötigten Anforderungen nicht sicher sind, empfehlen wir Ihnen, die Planungsdokumentation durchzugehen, bevor Sie mit den nachfolgend beschriebenen Schritten fortfahren. Ansonsten kann es losgehen.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definieren der Topologie für einen einzelnen Edgeserver

1. Melden Sie sich Ihre Skype für Business Server Standard Edition-Server oder einen Skype für Business Server-Front-End-Pool an.
    
2. Einmal vorhanden, öffnen Sie **Skype für Business Server-Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, den Sie zum Bereitstellen der Edge-Server an.
    
4. Maustaste auf **edgepools**, und klicken Sie dann auf **Neuer edgepool**.
    
5. Sie müssen auf dem Bildschirm des **neuen edgepool definieren** **Weiter** klicken.
    
6. Geben Sie den internen vollqualifizierten Domänennamen (FQDN) an, die der Edge-Server verwenden, und wählen Sie **Pool mit einem Computer**, klicken Sie auf **nächste** nach Abschluss, auf dem Bildschirm **definieren den FQDN des Edge-Pools** .
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
   - Sie möchten verwenden Sie dieselbe FQDN und IP-Adresse für Ihre SIP-Dienst, der Skype für Business Server-Webkonferenzdienst und des A / V-edgedienst. In diesem Fall müssen Sie wählen, **Verwenden Sie ein Kontrollkästchen einzelnen FQDN und IP-Adresse** (und beachten Sie dies für Schritt 9 weiter unten)
    
   - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
   - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
   Dies sind mehr oder weniger selbsterklärend, ob Sie IPv4 oder IPv6-Adressen verwenden, und Sie diese Adressen auf Edge-Server, intern oder extern anwenden können (Sie müssen dies für Schritt 10 im Hinterkopf behalten). Sie haben auch die Möglichkeit, den Edge-Server oder den Edge-Pool konfigurieren eine Netzwerkadresse für Adresse Netzwerkadressübersetzung (NAT) für die externe IP-Adresse verwenden. Wählen Sie dafür das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der NAT übersetzt** aus. Klicken Sie anschließend auf **Weiter**.
    
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** überprüft haben, müssen Sie Ihre einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Klicken Sie dann müssen Sie unterschiedliche Portnummern für jeden edgedienst, um alle unabhängig voneinander herstellen dürfen eingeben. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** nicht aktivieren, müssen Sie jetzt die drei externe FQDNs für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** eingeben und die **A / V** -Edgedienst. Klicken Sie anschließend auf **Weiter**.
    
10. Sie sind jetzt auf dem Bildschirm **die interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse des Edgeservers in die Textfelder **interne IPv4-Adresse** und **interne IPv6-Adresse** je nach der Auswahl der Optionen, die Sie in Schritt 8 vorgenommen. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
11. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Sie können einen einzelnen FQDN für alle Dienste verwenden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4 oder IPv6-Adresse (je nachdem, was Sie verwenden) im Textfeld **SIP-Zugriff** , und klicken Sie dann auf **Weiter**.
    
    - Sie haben ausgewählt, Verwendung von drei separaten FQDNs und IP-Adressen für die Dienste. Wenn dies der Fall ist, geben Sie die externen IPv4 oder IPv6-Adressen für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** und die **A / V** Edge-Dienst, und klicken Sie dann auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
12. Wenn Sie wieder in Schritt 8 NAT verwendet haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld **öffentliche IP-Adresse** . Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse Geben Sie, für den A festgelegt haben / V-Edgeserver von NAT übersetzt werden Klicken Sie dann auf **Weiter**.
    
13. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster hoppool** den Namen des internen Pools, die möglicherweise einen Front-End-Pool oder einen eigenständigen Pool. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
14. Auf dem Bildschirm **Zuordnen von Front-End-Pools** müssen Sie einen oder mehrere interne Pools, einschließlich der Front-End-Pools und Standard Edition-Servern zuordnen zu diesem Edgeserver angeben. Wählen Sie nur die Namen der internen Pools mit diesem Edgeserver mit unterstützten externen Benutzern kommunizieren. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Hier Bedenken liegt, wenn die interne Pools oder eigenständige Server bereits einen anderen Skype für Business Server Edge-Server verwenden, mehrere Zuordnungen haben kann. Wenn Sie Wählen einer internen Pool oder eigenständigen Server, der in diesem Fall ist, sehen Sie sich mit dem Hinweis zu den Edge-Server eine Warnung angezeigt, und Sie können entscheiden, ob Sie den Vorgang fortsetzen oder nicht. Wenn Sie nun mit diesem neuen Zuordnung wechseln, wird die Verbindung mit der Edge-Server beendet. 
  
15. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
16. Jetzt müssen Sie möglicherweise diese aktualisierte Technologie veröffentlichen, und befolgen die Anweisungen unter [Bereitstellen von Edgeservern in Skype für Business Server](deploy-edge-servers.md) bereitstellen auf den Edge-Server von hier aus.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen DNS-Lastenausgleich mit Edge-Server-pool

1. Melden Sie sich Ihre Skype für Business Server Standard Edition-Server oder einen Skype für Business Server-Front-End-Server an.
    
2. Einmal vorhanden, öffnen Sie **Skype für Business Server-Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, den Sie zum Bereitstellen der Edge-Server an.
    
4. Maustaste auf **edgepools**, und klicken Sie dann auf **Neuer edgepool**.
    
5. Sie müssen auf dem Bildschirm des **neuen edgepool definieren** **Weiter** klicken.
    
6. Geben Sie den internen vollqualifizierten Domänennamen (FQDN) an, die der Edge-Pool verwenden, und wählen Sie **Pool mit mehreren Computern**, auf die **nächste** nach Abschluss, auf dem Bildschirm **definieren den FQDN des Edge-Pools** .
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
    - Sie möchten verwenden Sie dieselbe FQDN und IP-Adresse für Ihre SIP-Dienst, der Skype für Business Server Webkonferenzdienst und des A / V-edgedienst. In diesem Fall müssen Sie wählen, **Verwenden Sie ein Kontrollkästchen einzelnen FQDN und IP-Adresse** (und beachten Sie dies für Schritt 9 weiter unten)
    
    - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
    - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
    Dies sind mehr oder weniger selbsterklärend, ob Sie IPv4 oder IPv6-Adressen verwenden, und Sie diese Adressen auf Edge-Server, intern oder extern anwenden können (Sie müssen dies für Schritt 11 im Hinterkopf behalten). Sie haben auch die Möglichkeit, den Edge-Server oder den Edge-Pool konfigurieren eine Netzwerkadresse für Adresse Netzwerkadressübersetzung (NAT) für die externe IP-Adresse verwenden. Wählen Sie dafür das Kontrollkästchen **Die externe IP-Adresse dieses Edgepools wird von der NAT übersetzt** aus. Klicken Sie anschließend auf **Weiter**.
    
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** überprüft haben, müssen Sie Ihre einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Klicken Sie dann müssen Sie unterschiedliche Portnummern für jeden edgedienst, um alle unabhängig voneinander herstellen dürfen eingeben. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** nicht aktivieren, müssen Sie jetzt die drei externe FQDNs für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** eingeben und die **A / V** -Edgedienst. Klicken Sie anschließend auf **Weiter**.
    
10. Jetzt haben Sie den Bildschirm **Definieren der Computer in diesem Pool** erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie sind jetzt auf dem Bildschirm **die interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse des Edgeservers in die Textfelder **interne IPv4-Adresse** und **interne IPv6-Adresse** je nach der Auswahl der Optionen, die Sie in Schritt 8 vorgenommen. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
12. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Sie können einen einzelnen FQDN für alle Dienste verwenden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4 oder IPv6-Adresse (je nachdem, was Sie verwenden) im Textfeld **SIP-Zugriff** , und klicken Sie dann auf **Weiter**.
    
    - Sie haben ausgewählt, Verwendung von drei separaten FQDNs und IP-Adressen für die Dienste. Wenn dies der Fall ist, geben Sie die externen IPv4 oder IPv6-Adressen für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** und die **A / V** Edge-Dienst, und klicken Sie dann auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
13. Klicken Sie auf **Fertig stellen**. Der Edge-Server, den Sie gerade erstellt haben, sollte jetzt im Dialogfeld **Definieren der Computer in diesem Pool** eingetragen sein.
    
14. Weiterhin im Fenster **Definieren der Computer in diesem Pool** , klicken Sie erneut auf die Schaltfläche **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edge-Server hinzugefügt haben, haben in diesem Pool werden soll. Klicken Sie auf **Weiter**, wenn Sie damit fertig sind.
    
15. Wenn Sie wieder in Schritt 8 NAT verwendet haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld **öffentliche IP-Adresse** . Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse Geben Sie, für den A festgelegt haben / V-Edgeserver von NAT übersetzt werden Klicken Sie dann auf **Weiter**.
    
16. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster hoppool** den Namen des internen Pools, die möglicherweise einen Front-End-Pool oder einen eigenständigen Pool. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
17. Auf dem Bildschirm **Zuordnen von Front-End-Pools** müssen Sie einen oder mehrere interne Pools, einschließlich der Front-End-Pools und Standard Edition-Pools zuordnen zu diesem Edgeserver angeben. Wählen Sie nur die Namen der internen Pools mit diesem Edgeserver mit unterstützten externen Benutzern kommunizieren. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Hier Bedenken liegt, wenn die interne Pools oder eigenständige Server bereits einen anderen Skype für Business Server Edge-Server verwenden, mehrere Zuordnungen haben kann. Wenn Sie Wählen einer internen Pool oder eigenständigen Server, der in diesem Fall ist, sehen Sie sich mit dem Hinweis zu den Edge-Server eine Warnung angezeigt, und Sie können entscheiden, ob Sie den Vorgang fortsetzen oder nicht. Wenn Sie nun mit diesem neuen Zuordnung wechseln, wird die Verbindung mit der Edge-Server beendet. 
  
18. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
19. Jetzt müssen Sie möglicherweise diese aktualisierte Technologie veröffentlichen, und befolgen die Anweisungen unter [Bereitstellen von Edgeservern in Skype für Business Server](deploy-edge-servers.md) bereitstellen auf den Edge-Server von hier aus.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Edge-Server-Pool Definieren der Topologie für ein Hardwaregerät zum Lastenausgleich

1. Melden Sie sich Ihre Skype für Business Server Standard Edition-Server oder einen Skype für Business Server-Front-End-Server an.
    
2. Einmal vorhanden, öffnen Sie **Skype für Business Server-Topologie-Generator**.
    
3. Erweitern Sie in der Konsolenstruktur den Standort, den Sie zum Bereitstellen der Edge-Server an.
    
4. Maustaste auf **edgepools**, und klicken Sie dann auf **Neuer edgepool**.
    
5. Sie müssen auf dem Bildschirm des **neuen edgepool definieren** **Weiter** klicken.
    
6. Geben Sie den internen vollqualifizierten Domänennamen (FQDN) an, die der Edge-Pool verwenden, und wählen Sie **Pool mit mehreren Computern**, auf die **nächste** nach Abschluss, auf dem Bildschirm **definieren den FQDN des Edge-Pools** .
    
7. Auf dem Bildschirm **Funktionen auswählen** haben Sie die folgende Wahl:
    
   - Sie möchten verwenden Sie dieselbe FQDN und IP-Adresse für Ihre SIP-Dienst, der Skype für Business Server Webkonferenzdienst und des A / V-edgedienst. In diesem Fall müssen Sie wählen, **Verwenden Sie ein Kontrollkästchen einzelnen FQDN und IP-Adresse** (und beachten Sie dies für Schritt 9 weiter unten)
    
   - Wenn der Partnerverbund aktiviert werden soll, wählen Sie das Kontrollkästchen **Partnerverbund für diesen Edgepool aktivieren (Port 5061)** aus.
    
8. Wenn Sie auf **Weiter** klicken, werden Sie zum Bildschirm **IP-Optionen** weitergeleitet. Hier haben Sie folgende Optionen:
    
   - IPv4 für die interne Schnittstelle aktivieren
    
   - IPv6 für die interne Schnittstelle aktivieren
    
   - IPv4 für die externe Schnittstelle aktivieren
    
   - IPv6 für die externe Schnittstelle aktivieren
    
    Dies sind mehr oder weniger selbsterklärend, ob Sie IPv4 oder IPv6-Adressen verwenden, und Sie diese Adressen auf Edge-Server, intern oder extern anwenden können (Sie müssen dies für Schritt 11 im Hinterkopf behalten).
    
    > [!NOTE]
    > Im Gegensatz zu den anderen zwei Topologieoptionen, wenn Sie ein Hardwaregerät zum Lastenausgleich verwenden Wählen Sie **Darf nicht** die Option **wird die externe IP-Adresse des Edge-Pools von NAT übersetzt**. Dies wird **nicht unterstützt**.
  
9. Die Auswahlmöglichkeiten auf dem Bildschirm der externen FQDNs hängen von der in Schritt 7 getroffenen Auswahl ab.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** überprüft haben, müssen Sie Ihre einzelnen externen FQDN im Feld **SIP-Zugriff** eingeben. Klicken Sie dann müssen Sie unterschiedliche Portnummern für jeden edgedienst, um alle unabhängig voneinander herstellen dürfen eingeben. Wir empfehlen 5061 für den Edgedienst **SIP-Zugriff**, 444 für den Edgedienst **Webkonferenzen** und 443 für den Edgedienst **A/V**. Klicken Sie anschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen **Verwenden Sie eine einzelne FQDN und IP-Adresse** nicht aktivieren, müssen Sie jetzt die drei externe FQDNs für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** eingeben und die **A / V** -Edgedienst. Klicken Sie anschließend auf **Weiter**.
    
10. Jetzt haben Sie den Bildschirm **Definieren der Computer in diesem Pool** erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie sind jetzt auf dem Bildschirm **die interne IP-Adresse definieren** . Hier geben Sie die IP-Adresse des Edgeservers in die Textfelder **interne IPv4-Adresse** und **interne IPv6-Adresse** je nach der Auswahl der Optionen, die Sie in Schritt 8 vorgenommen. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
12. Auf dem Bildschirm **Externe IP-Adresse definieren** stehen Ihnen abhängig von den zuvor getroffen Entscheidungen ein paar Optionen zur Verfügung:
    
    - Sie können einen einzelnen FQDN für alle Dienste verwenden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4 oder IPv6-Adresse (je nachdem, was Sie verwenden) im Textfeld **SIP-Zugriff** , und klicken Sie dann auf **Weiter**.
    
    - Sie haben ausgewählt, Verwendung von drei separaten FQDNs und IP-Adressen für die Dienste. Wenn dies der Fall ist, geben Sie die externen IPv4 oder IPv6-Adressen für den **SIP-Zugriffs** -edgedienst **Edge Webkonferenzdienst,** und die **A / V** Edge-Dienst, und klicken Sie dann auf **Weiter**.
    
    > [!NOTE]
    > Wenn Sie die Aktivierung und Zuweisung von IPv6-Adressen vorher nicht ausgewählt haben, wird dieses Dialogfeld nicht angezeigt. Das ist normal und Sie können mit dem nächsten Schritt fortfahren. 
  
13. Klicken Sie auf **Fertig stellen**. Der Edge-Server, den Sie gerade erstellt haben, sollte jetzt im Dialogfeld **Definieren der Computer in diesem Pool** eingetragen sein.
    
14. Weiterhin im Fenster **Definieren der Computer in diesem Pool** , klicken Sie erneut auf die Schaltfläche **Hinzufügen** , und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edge-Server hinzugefügt haben, haben in diesem Pool werden soll. Klicken Sie auf **Weiter**, wenn Sie damit fertig sind.
    
15. Beim nächsten Bildschirm handelt es sich um **Nächsten Hop definieren**. Wählen Sie im Feld **Nächster hoppool** den Namen des internen Pools, die möglicherweise einen Front-End-Pool oder einen eigenständigen Pool. Wenn Sie einen Director in Ihrer Umgebung haben, sollten Sie den Director auswählen. Klicken Sie dann auf **Weiter**.
    
16. Auf dem Bildschirm **Zuordnen von Front-End-Pools** müssen Sie einen oder mehrere interne Pools, einschließlich der Front-End-Pools und Standard Edition-Pools zuordnen zu diesem Edgeserver angeben. Wählen Sie nur die Namen der internen Pools mit diesem Edgeserver mit unterstützten externen Benutzern kommunizieren. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Hier Bedenken liegt, wenn die interne Pools oder eigenständige Server bereits einen anderen Skype für Business Server Edge-Server verwenden, mehrere Zuordnungen haben kann. Wenn Sie Wählen einer internen Pool oder eigenständigen Server, der in diesem Fall ist, sehen Sie sich mit dem Hinweis zu den Edge-Server eine Warnung angezeigt, und Sie können entscheiden, ob Sie den Vorgang fortsetzen oder nicht. Wenn Sie nun mit diesem neuen Zuordnung wechseln, wird die Verbindung mit der Edge-Server beendet. 
  
17. Klicken Sie auf dem nächsten Bildschirm auf **Fertig stellen**.
    
18. Jetzt müssen Sie möglicherweise diese aktualisierte Technologie veröffentlichen, und befolgen die Anweisungen unter [Bereitstellen von Edgeservern in Skype für Business Server](deploy-edge-servers.md) bereitstellen auf den Edge-Server von hier aus.
    
## <a name="publish-your-edge-server-topology"></a>Veröffentlichen der Edgeservertopologie

Nachdem Sie die oben beschriebenen Schritte abgeschlossen haben, ist es Zeit zu dieser neuen Topologie veröffentlichen, die auch Sie es in Ihrer Skype für Business Server-Edgeserver oder Edgepool exportieren können. Gehen Sie folgendermaßen vor:
  
1. Starten Sie den **Topologie-Generator** (wenn dieser nicht bereits aufgrund eines vorhergehenden Verfahrens geöffnet ist).
    
2. Im **Topologie-Generator**in der Konsolenstruktur mit der rechten Maustaste **Skype für Business Server** , und klicken Sie dann auf **Skype für Business Server-Topologie-Generator**.
    
3. Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.
    
4. Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.
    
5. Wenn die erfolgreiche Erstellung der Datenbank angezeigt wird, führen Sie folgende Schritte aus:
    
    - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
    - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
## <a name="export-your-edge-server-topology"></a>Exportieren der Edgeservertopologie

Zur erfolgreichen Bereitstellung benötigt die Skype für Business Server-Bereitstellungsassistenten Zugriff auf die zentralen Speicherdaten. Dies ist für interne Server in Ihrer Domäne oder der Gesamtstruktur in der Regel recht einfach. Edge-Server sind außerhalb der Domäne, und es ist also erforderlich sind, um die topologiedatei manuell an Edge-Server in der Regel auf einem physischen Datenträgern zu exportieren. Dieser Export erfolgt über die PowerShell:
  
1. Starten Sie die **Skype für Business Server-Verwaltungsshell**.
    
2. Führen Sie die folgenden in der **Skype für Business Server-Verwaltungsshell**aus:
    
   ```
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Kopieren Sie die exportierte Datei auf externe Medien (beispielsweise ein USB-Laufwerk oder eine Netzwerkfreigabe, die Sie über die Edge-Server-Ort erreichen können).
    

