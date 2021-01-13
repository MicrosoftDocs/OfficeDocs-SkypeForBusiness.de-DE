---
title: Erstellen Ihrer Edgetopologie für Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 5ea18841-afdc-4ccb-8d86-30584c1f5aca
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Edgeservertopologie in Skype for Business Server erstellen, veröffentlichen und exportieren.'
ms.openlocfilehash: 8dff318b5d198eb1e8d59ef465bf648125f31327
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804395"
---
# <a name="create-your-edge-topology-for-skype-for-business-server"></a>Erstellen Ihrer Edgetopologie für Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Edgeservertopologie in Skype for Business Server erstellen, veröffentlichen und exportieren.
  
Der Topologie-Generator ist das Tool, das Sie zum Erstellen Ihrer Edgeservertopologie verwenden müssen, genau wie es für jede Topologiekomponente für Skype for Business Server verwendet wird. Bevor Sie die folgenden Schritte ausführen, müssen Sie mindestens einen Front-End-Pool oder einen Standard Edition-Server eingerichtet haben.
  
In diesem Artikel werden die folgenden Themen behandelt:
  
- Erstellen der Edgeservertopologie
    
- Veröffentlichen der Edgeservertopologie
    
- Exportieren der Edgeservertopologie
    
  > [!NOTE]
  > Um die folgenden Schritte ausführen zu können, müssen Sie sich bei den unten genannten Domänenservern als Benutzer anmelden, der Mitglied der folgenden Domänengruppen ist: 
  
- RTCUniversalServerAdmins
    
- Domänen-Admins
    
## <a name="build-your-edge-server-topology"></a>Erstellen der Edgeservertopologie

Der erste Bereitstellungsschritt besteht darin, Ihre Skype for Business Server Edge Server-Topologie zu erstellen, die aus einer von drei Optionen besteht:
  
- Ein einzelner Edgeserver
    
- Ein Edgepool mit DNS-Lastenausgleich (mindestens ein Server)
    
- Ein Edgepool mit Hardwarelastenausgleich (mindestens ein Server)
    
Wenn Sie nicht sicher sind, was Sie benötigen, sollten Sie die Planungsdokumentation lesen, bevor Sie mit den folgenden Schritten beginnen. Andernfalls beginnen wir.
  
### <a name="defining-the-topology-for-a-single-edge-server"></a>Definieren der Topologie für einen einzelnen Edgeserver

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Pool an.
    
2. Öffnen Sie dort den **Skype for Business Server-Topologie-Generator.**
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der **rechten Maustaste auf Edgepools,** und klicken Sie dann **auf "Neuer Edgepool".**
    
5. Klicken Sie auf **dem** Bildschirm "Neuen **Edgepool definieren" auf** "Weiter".
    
6. Geben Sie auf dem Bildschirm "FQDN des Edgepools definieren" den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgeserver verwenden soll, und wählen Sie "Pool mit einem Computer" **aus,** und klicken Sie anschließend auf "Weiter".  
    
7. Auf dem **Bildschirm "Features auswählen"** haben Sie die Wahl:
    
   - Möglicherweise möchten Sie denselben FQDN und dieselbe IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktivieren (und beachten Sie dies für Schritt 9 unten).
    
   - Wenn Sie den Verbund aktivieren möchten, aktivieren Sie das Kontrollkästchen "Verbund für diesen **Edgepool aktivieren (Port 5061).**
    
8. Nachdem Sie auf **"Weiter"** geklickt haben, werden Sie sich selbst auf dem Bildschirm **"IP-Optionen"** angezeigt. Folgende Optionen stehen zur Verfügung:
    
   - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
   Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf Ihren Edgeserver anwenden (Sie müssen dies für Schritt 10 berücksichtigen). Sie haben auch die Möglichkeit, Ihren Edgeserver oder Edgepool so zu konfigurieren, dass eine Netzwerkadressenübersetzungsadresse (Network Address Translation, NAT) für die externe IP-Adresse verwendet wird. Wählen Sie dazu die externe IP-Adresse dieses **Edgepools** über das Kontrollkästchen NAT aus. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
9. Auf dem Bildschirm mit externen FQDNs hängen Ihre Auswahlmöglichkeiten von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das Feld **"SIP-Zugriff"** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig eine Verbindung herstellen können. Wir empfehlen 5061  für den SIP-Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den  **A/V-Edgedienst.** Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen "Nur **FQDN** und IP-Adresse verwenden" nicht aktivieren, müssen Sie jetzt die drei externen FQDNs für den SIP-Zugriffs-Edgedienst, den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben.  Klicken Sie abschließend auf **Weiter**.
    
10. Sie sind jetzt auf dem Bildschirm "Interne **IP-Adress definieren"** angezeigt. Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder "Interne **IPv4"-** und **"Interne IPv6-Adresse"** ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
11. Auf dem **Bildschirm "Externe IP-Adress** definieren" haben Sie je nach vorheriger Auswahl einige Optionen:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn ja, geben Sie Ihre externe IPv4- oder -IPv6-Adresse (unabhängig davon, was Sie verwenden) in das **Textfeld "SIP Access"** ein, und klicken Sie dann auf **"Weiter".**
    
    - Möglicherweise haben Sie sich für die Verwendung von drei separaten FQDNs und -IP-Adressen für die Dienste entschieden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder -IPv6-Adressen für den **SIP-Zugriffs-Edgedienst,** den Webkonferenz-Edgedienst und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter".** 
    
    > [!NOTE]
    > Wenn Sie sich zuvor nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entscheiden, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
12. Wenn Sie sich in Schritt 8 für die Verwendung von NAT entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld für öffentliche **IP-Adressen.** Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst festgelegt haben, um von natrierten Netzwerkadressen übersetzt zu werden. Then click **Next**.
    
13. Nächster Bildschirm nach oben ist **Definieren des nächsten Hops.** Wählen Sie **im Feld "Nächster** Hoppool" den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool geben kann. Wenn Sie in Ihrer Umgebung über einen Director verfügen, sollten Sie den Director auswählen. Then click **Next**.
    
14. Auf dem **Bildschirm "Front-End-Pools** zuordnen" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition-Servern, die diesem Edgeserver zugeordnet werden. Wählen Sie einfach die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, können sie nicht mehrere Zuordnungen haben. Wenn Sie einen internen Pool oder einen eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, in der Sie über den anderen Edgeserver erfahren, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung verwenden, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
15. Klicken **Sie auf** dem nächsten Bildschirm auf "Fertig stellen".
    
16. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen in ["Bereitstellen von Edgeservern in Skype for Business Server"](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitstellen zu können.
    
### <a name="defining-the-topology-for-a-dns-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen Edgeserverpool mit DNS-Lastenausgleich

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Server an.
    
2. Öffnen Sie dort den **Skype for Business Server-Topologie-Generator.**
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der **rechten Maustaste auf Edgepools,** und klicken Sie dann **auf "Neuer Edgepool".**
    
5. Klicken Sie auf **dem** Bildschirm "Neuen **Edgepool definieren" auf** "Weiter".
    
6. Geben Sie auf dem Bildschirm "FQDN des Edgepools definieren" den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgepool verwenden soll, und wählen Sie "Pool mit mehreren Computern" **aus,** und klicken Sie anschließend auf "Weiter".  
    
7. Auf dem **Bildschirm "Features auswählen"** haben Sie die Wahl:
    
    - Möglicherweise möchten Sie denselben FQDN und dieselbe IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktivieren (und beachten Sie dies für Schritt 9 unten).
    
    - Wenn Sie den Verbund aktivieren möchten, aktivieren Sie das Kontrollkästchen "Verbund für diesen **Edgepool aktivieren (Port 5061).**
    
8. Nachdem Sie auf **"Weiter"** geklickt haben, werden Sie sich selbst auf dem Bildschirm **"IP-Optionen"** angezeigt. Folgende Optionen stehen zur Verfügung:
    
    - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
     Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf Ihren Edgeserver anwenden (Sie müssen dies für Schritt 11 berücksichtigen). Sie haben auch die Möglichkeit, Ihren Edgeserver oder Edgepool so zu konfigurieren, dass eine Netzwerkadressenübersetzungsadresse (Network Address Translation, NAT) für die externe IP-Adresse verwendet wird. Wählen Sie dazu die externe IP-Adresse dieses **Edgepools** über das Kontrollkästchen NAT aus. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
9. Auf dem Bildschirm mit externen FQDNs hängen Ihre Auswahlmöglichkeiten von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das Feld **"SIP-Zugriff"** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig eine Verbindung herstellen können. Wir empfehlen 5061  für den SIP-Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den  **A/V-Edgedienst.** Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen "Nur **FQDN** und IP-Adresse verwenden" nicht aktivieren, müssen Sie jetzt die drei externen FQDNs für den SIP-Zugriffs-Edgedienst, den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben.  Klicken Sie abschließend auf **Weiter**.
    
10. Jetzt haben Sie den Bildschirm **"Computer in diesem Pool definieren"** erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie sind jetzt auf dem Bildschirm "Interne **IP-Adress definieren"** angezeigt. Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder "Interne **IPv4"-** und **"Interne IPv6-Adresse"** ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
12. Auf dem **Bildschirm "Externe IP-Adress** definieren" haben Sie je nach vorheriger Auswahl einige Optionen:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn ja, geben Sie Ihre externe IPv4- oder -IPv6-Adresse (unabhängig davon, was Sie verwenden) in das **Textfeld "SIP Access"** ein, und klicken Sie dann auf **"Weiter".**
    
    - Möglicherweise haben Sie sich für die Verwendung von drei separaten FQDNs und -IP-Adressen für die Dienste entschieden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder -IPv6-Adressen für den **SIP-Zugriffs-Edgedienst,** den Webkonferenz-Edgedienst und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter".** 
    
    > [!NOTE]
    > Wenn Sie sich zuvor nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entscheiden, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
13. Klicken Sie auf **Fertig stellen**. Der gerade erstellte Edgeserver sollte jetzt im Dialogfeld "Computer **in diesem** Pool definieren" aufgeführt werden.
    
14. Klicken Sie auf dem Bildschirm "Computer **in** diesem Pool definieren" noch einmal auf die Schaltfläche "Hinzufügen", und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool verwenden möchten.  Klicken Sie nach Abschluss des Vorgangs auf **"Weiter".**
    
15. Wenn Sie sich in Schritt 8 für die Verwendung von NAT entschieden haben, erhalten Sie jetzt einen Bildschirm mit einem Textfeld für öffentliche **IP-Adressen.** Sie müssen die öffentliche IPv4- und/oder IPv6-Adresse eingeben, die Sie für den A/V-Edgedienst festgelegt haben, um von natrierten Netzwerkadressen übersetzt zu werden. Then click **Next**.
    
16. Nächster Bildschirm nach oben ist **Definieren des nächsten Hops.** Wählen Sie **im Feld "Nächster** Hoppool" den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool geben kann. Wenn Sie in Ihrer Umgebung über einen Director verfügen, sollten Sie den Director auswählen. Then click **Next**.
    
17. Auf dem **Bildschirm "Front-End-Pools** zuordnen" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition-Pools, die diesem Edgeserver zugeordnet werden. Wählen Sie einfach die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, können sie nicht mehrere Zuordnungen haben. Wenn Sie einen internen Pool oder einen eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, in der Sie über den anderen Edgeserver erfahren, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung verwenden, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
18. Klicken **Sie auf** dem nächsten Bildschirm auf "Fertig stellen".
    
19. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen in ["Bereitstellen von Edgeservern in Skype for Business Server"](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitstellen zu können.
    
### <a name="defining-the-topology-for-a-hardware-load-balanced-edge-server-pool"></a>Definieren der Topologie für einen Edgeserverpool mit Hardwarelastenausgleich

1. Melden Sie sich bei Ihrem Skype for Business Server Standard Edition-Server oder einem Skype for Business Server-Front-End-Server an.
    
2. Öffnen Sie dort den **Skype for Business Server-Topologie-Generator.**
    
3. Erweitern Sie in der Konsolenstruktur den Standort, für den Sie den Edgeserver bereitstellen möchten.
    
4. Klicken Sie mit der **rechten Maustaste auf Edgepools,** und klicken Sie dann **auf "Neuer Edgepool".**
    
5. Klicken Sie auf **dem** Bildschirm "Neuen **Edgepool definieren" auf** "Weiter".
    
6. Geben Sie auf dem Bildschirm "FQDN des Edgepools definieren" den internen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) ein, den der Edgepool verwenden soll, und wählen Sie "Pool mit mehreren Computern" **aus,** und klicken Sie anschließend auf "Weiter".  
    
7. Auf dem **Bildschirm "Features auswählen"** haben Sie die Wahl:
    
   - Möglicherweise möchten Sie denselben FQDN und dieselbe IP-Adresse für Ihren SIP-Zugriffsdienst, Ihren Skype for Business Server-Webkonferenzdienst und Ihren A/V-Edgedienst verwenden. Wenn ja, müssen Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktivieren (und beachten Sie dies für Schritt 9 unten).
    
   - Wenn Sie den Verbund aktivieren möchten, aktivieren Sie das Kontrollkästchen "Verbund für diesen **Edgepool aktivieren (Port 5061).**
    
8. Nachdem Sie auf **"Weiter"** geklickt haben, werden Sie sich selbst auf dem Bildschirm **"IP-Optionen"** angezeigt. Folgende Optionen stehen zur Verfügung:
    
   - Aktivieren von IPv4 auf der internen Schnittstelle
    
   - Aktivieren von IPv6 auf der internen Schnittstelle
    
   - Aktivieren von IPv4 auf der externen Schnittstelle
    
   - Aktivieren von IPv6 auf der externen Schnittstelle
    
     Diese sind ziemlich selbsterklärend, unabhängig davon, ob Sie IPv4- oder IPv6-Adressen verwenden und diese Adressen intern oder extern auf Ihren Edgeserver anwenden (Sie müssen dies für Schritt 11 berücksichtigen).
    
     > [!NOTE]
     > Im Gegensatz zu den anderen beiden Topologieoptionen müssen  Sie bei Verwendung eines Hardwaregeräts zum Lastenausgleich NICHT die Option "Externe IP-Adresse des Edgepools wird von **NAT übersetzt" auswählen.** Dies **wird nicht unterstützt.**
  
9. Auf dem Bildschirm mit externen FQDNs hängen Ihre Auswahlmöglichkeiten von der Auswahl ab, die Sie in Schritt 7 oben getroffen haben.
    
   - Wenn Sie das Kontrollkästchen "Einen einzelnen **FQDN** und eine einzelne IP-Adresse verwenden" aktiviert haben, müssen Sie ihren einzelnen externen FQDN in das Feld **"SIP-Zugriff"** eingeben. Anschließend müssen Sie für jeden Edgedienst unterschiedliche Portnummern eingeben, damit alle unabhängig eine Verbindung herstellen können. Wir empfehlen 5061  für den SIP-Zugriffs-Edgedienst, 444 für den Webkonferenz-Edgedienst und 443 für den  **A/V-Edgedienst.** Klicken Sie abschließend auf **Weiter**.
    
   - Wenn Sie das Kontrollkästchen "Nur **FQDN** und IP-Adresse verwenden" nicht aktivieren, müssen Sie jetzt die drei externen FQDNs für den SIP-Zugriffs-Edgedienst, den **Webkonferenz-Edgedienst** und den **A/V-Edgedienst** eingeben.  Klicken Sie abschließend auf **Weiter**.
    
10. Jetzt haben Sie den Bildschirm **"Computer in diesem Pool definieren"** erreicht. Klicken Sie auf die Schaltfläche **Hinzufügen**.
    
11. Sie sind jetzt auf dem Bildschirm "Interne **IP-Adress definieren"** angezeigt. Hier geben Sie die IP-Adresse Ihres Edgeservers in die Textfelder "Interne **IPv4"-** und **"Interne IPv6-Adresse"** ein, je nachdem, welche Auswahl Sie in Schritt 8 getroffen haben. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
12. Auf dem **Bildschirm "Externe IP-Adress** definieren" haben Sie je nach vorheriger Auswahl einige Optionen:
    
    - Möglicherweise verwenden Sie einen einzelnen FQDN für alle Dienste. Wenn ja, geben Sie Ihre externe IPv4- oder -IPv6-Adresse (unabhängig davon, was Sie verwenden) in das **Textfeld "SIP Access"** ein, und klicken Sie dann auf **"Weiter".**
    
    - Möglicherweise haben Sie sich für die Verwendung von drei separaten FQDNs und -IP-Adressen für die Dienste entschieden. Wenn dies der Fall ist, geben Sie Ihre externen IPv4- oder -IPv6-Adressen für den **SIP-Zugriffs-Edgedienst,** den Webkonferenz-Edgedienst und den **A/V-Edgedienst** ein, und klicken Sie dann auf **"Weiter".** 
    
    > [!NOTE]
    > Wenn Sie sich zuvor nicht für die Aktivierung und Zuweisung von IPv6-Adressierung entscheiden, wird dieses Dialogfeld nicht angezeigt. Das ist normal, fahren Sie einfach mit dem nächsten Schritt fort. 
  
13. Klicken Sie auf **Fertig stellen**. Der gerade erstellte Edgeserver sollte jetzt im Dialogfeld "Computer **in diesem** Pool definieren" aufgeführt werden.
    
14. Klicken Sie auf dem Bildschirm "Computer **in** diesem Pool definieren" noch einmal auf die Schaltfläche "Hinzufügen", und wiederholen Sie die Schritte 11 bis 13, bis Sie alle Edgeserver hinzugefügt haben, die Sie in diesem Pool verwenden möchten.  Klicken Sie nach Abschluss des Vorgangs auf **"Weiter".**
    
15. Nächster Bildschirm nach oben ist **Definieren des nächsten Hops.** Wählen Sie **im Feld "Nächster** Hoppool" den Namen Ihres internen Pools aus, bei dem es sich um einen Front-End-Pool oder einen eigenständigen Pool geben kann. Wenn Sie in Ihrer Umgebung über einen Director verfügen, sollten Sie den Director auswählen. Then click **Next**.
    
16. Auf dem **Bildschirm "Front-End-Pools** zuordnen" müssen Sie einen oder mehrere interne Pools angeben, einschließlich Front-End-Pools und Standard Edition-Pools, die diesem Edgeserver zugeordnet werden. Wählen Sie einfach die Namen der internen Pools aus, die diesen Edgeserver für die Kommunikation mit unterstützten externen Benutzern verwenden möchten. Klicken Sie auf **Weiter**.
    
    > [!NOTE]
    > Beachten Sie hier: Wenn Ihre internen Pools oder eigenständigen Server bereits einen anderen Skype for Business Server-Edgeserver verwenden, können sie nicht mehrere Zuordnungen haben. Wenn Sie einen internen Pool oder einen eigenständigen Server auswählen, der sich in dieser Situation befindet, wird eine Warnung angezeigt, in der Sie über den anderen Edgeserver erfahren, und Sie können entscheiden, ob Sie fortfahren möchten oder nicht. Wenn Sie diese neue Zuordnung verwenden, wird die Verbindung mit dem anderen Edgeserver beendet. 
  
17. Klicken **Sie auf** dem nächsten Bildschirm auf "Fertig stellen".
    
18. Jetzt können Sie diese aktualisierte Technologie veröffentlichen und die Anweisungen in ["Bereitstellen von Edgeservern in Skype for Business Server"](deploy-edge-servers.md) befolgen, um sie von hier aus auf Ihrem Edgeserver bereitstellen zu können.
    
## <a name="publish-your-edge-server-topology"></a>Veröffentlichen der Edgeservertopologie

Nachdem Sie die oben genannten Schritte abgeschlossen haben, ist es an der Zeit, diese neue Topologie zu veröffentlichen, mit der Sie sie auch in Ihren Skype for Business Server-Edgeserver oder -Edgepool exportieren können. Gehen Sie folgendermaßen vor:
  
1. Starten **Sie den Topologie-Generator** (wenn er nicht bereits aus dem vorherigen Verfahren gestartet wurde).
    
2. Klicken **Sie im Topologie-Generator** in der Konsolenstruktur mit der rechten Maustaste auf **Skype for Business Server,** und klicken Sie dann auf **Den Skype for Business Server-Topologie-Generator.**
    
3. Klicken Sie auf der Seite **Willkommen** des Assistenten auf **Weiter**.
    
4. Klicken Sie auf der Seite **Weitere Datenbanken erstellen** auf **Weiter**.
    
5. Wenn der Status angibt, dass die Datenbankerstellung erfolgreich war, gehen Sie wie folgt vor:
    
    - Klicken Sie zum Anzeigen des Protokolls auf **Protokoll anzeigen**.
    
    - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.
    
## <a name="export-your-edge-server-topology"></a>Exportieren der Edgeservertopologie

Für eine erfolgreiche Bereitstellung benötigt der Skype for Business Server-Bereitstellungs-Assistent Zugriff auf die Daten des zentralen Verwaltungsspeichers. Für interne Server in Ihrer Domäne oder Gesamtstruktur ist dies in der Regel einfach. Edgeserver befinden sich außerhalb der Domäne. Daher muss die Topologiedatei manuell an den Edgeserverspeicherort exportiert werden, in der Regel auf einem physischen Medium. Dieser Export erfolgt über PowerShell:
  
1. Starten Sie **die Skype for Business Server-Verwaltungsshell.**
    
2. Führen Sie **in der Skype for Business Server-Verwaltungsshell** Folgendes aus:
    
   ```powershell
   Export-CsConfiguration -FileName <ConfigurationFilePath.zip>
   ```

3. Kopieren Sie die exportierte Datei auf externe Medien (z. B. ein USB-Laufwerk oder eine Netzwerkfreigabe, die Sie vom Standort des Edgeservers aus erreichen können).
    

