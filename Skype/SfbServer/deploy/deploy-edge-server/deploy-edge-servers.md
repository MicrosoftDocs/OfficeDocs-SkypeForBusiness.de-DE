---
title: Bereitstellen von Edgeservern in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Zusammenfassung: Erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server Umgebung bereitstellen.'
ms.openlocfilehash: 611e2e6b4bbc3ef8f1d140b02d8dc3f2bc719953
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58623027"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Bereitstellen von Edgeservern in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server Umgebung bereitstellen.
  
Die folgenden Abschnitte enthalten Schritte, die ausgeführt werden sollen, nachdem der Skype for Business Server [Plan for Edge Server deployments in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) Documentation überprüft wurde. Die Bereitstellungsschritte sind wie folgt:
  
- Netzwerkschnittstellen
    
- Installation
    
- Zertifikate
    
- Starten der Edgeserver
    
## <a name="network-interfaces"></a>Netzwerkschnittstellen

Wie in der Planung erwähnt, konfigurieren Sie entweder Ihre Netzwerkschnittstelle mit DNS im Umkreisnetzwerk, in dem Ihre Edgeserver gehostet werden, oder ohne DNS im Umkreisnetzwerk.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration mit DNS-Servern im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die externe Schnittstelle.
    
    > [!NOTE]
    > Die internen und externen Subnetze dürfen nicht miteinander umleitbar sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine** der folgenden Optionen:
    
   a. Drei statische IP-Adressen im subnetz des externen Umkreisnetzwerks und verweisen das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass sie auf ein DNS-Umkreisserverpaar verweisen.
    
   b. Eine statische IP-Adresse im externen Subnetz des Umkreisnetzwerks und Verweisen des Standardgateways auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass sie auf ein DNS-Umkreisserverpaar verweisen. Diese Konfiguration ist NUR zulässig, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass sie nicht standardmäßige Werte in den Portzuweisungen aufweist, die im Artikel ["Erstellen der Edgetopologie für Skype for Business Server"](create-your-edge-topology.md) behandelt werden.
    
3. Konfigurieren Sie auf der internen Schnittstelle eine statische IP im internen Subnetz des Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Konfigurieren Sie die ADAPTOR-DNS-Einstellungen so, dass sie auf mindestens einen DNS-Server verweisen, vorzugsweise aber auf ein Dns-Umkreisserverpaar.
    
4. Erstellen Sie dauerhafte statische Routen auf der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, Skype for Business Server und Exchange Unified Messaging (UM)-Server befinden.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration ohne DNS-Server im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die externe Schnittstelle.
    
    > [!NOTE]
    > Die internen und externen Subnetze dürfen nicht miteinander umleitbar sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine** der folgenden Optionen:
    
   a. Drei statische IP-Adressen im externen Subnetz des Umkreisnetzwerks. Außerdem müssen Sie das Standardgateway auf der externen Schnittstelle konfigurieren, z. B. indem Sie den Router für das Internet oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass sie auf einen externen DNS-Server verweisen, idealerweise auf ein Paar externer DNS-Server.
    
   b. Eine statische IP-Adresse im externen Subnetz des Umkreisnetzwerks. Außerdem müssen Sie das Standardgateway auf der externen Schnittstelle konfigurieren, z. B. indem Sie den Router für das Internet oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie die DNS-Einstellungen des Adapters so, dass sie auf einen externen DNS-Server oder im Idealfall auf ein Paar externer DNS-Server verweisen. Diese Konfiguration ist NUR zulässig, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass sie nicht standardmäßige Werte in den Portzuweisungen aufweist, die im Artikel ["Erstellen der Edgetopologie für Skype for Business Server"](create-your-edge-topology.md) behandelt werden.
    
3. Konfigurieren Sie auf der internen Schnittstelle eine statische IP im internen Subnetz des Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Lassen Sie außerdem die DNS-Einstellungen des Adapters leer.
    
4. Erstellen Sie dauerhafte statische Routen auf der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, Skype for Business Server und Exchange Unified Messaging (UM)-Server befinden.
    
5. Bearbeiten Sie die HOST-Datei auf jedem Edgeserver so, dass sie einen Eintrag für den nächsten Hopserver oder die virtuelle IP (VIP) enthält. Dieser Datensatz ist der Director Standard Edition Server oder Front-End-Pool, den Sie im Topologie-Generator als nächste Hopadresse des Edgeservers konfiguriert haben. Wenn Sie den DNS-Lastenausgleich verwenden, fügen Sie eine Zeile für jedes Mitglied des nächsten Hoppools ein.
    
## <a name="installation"></a>Installation

Um diese Schritte erfolgreich abzuschließen, müssen Sie die Schritte im Artikel ["Erstellen der Edgetopologie für Skype for Business Server"](create-your-edge-topology.md) befolgt haben.
  
1. Melden Sie sich bei dem Server an, den Sie für die Edgeserverrolle konfiguriert haben, mit einem Konto, das sich in der lokalen Administratorgruppe befindet.
    
2. Sie benötigen die Topologiekonfigurationsdatei, die Sie am Ende der Dokumentation zur Edgeservertopologie auf diesem Computer kopiert haben. Greifen Sie auf die externen Medien zu, auf denen Sie diese Konfigurationsdatei abgelegt haben (z. B. ein USB-Laufwerk oder eine Freigabe).
    
3. Starten Sie den **Bereitstellungs-Assistenten.**
    
4. Klicken Sie nach dem Öffnen des Assistenten auf **"Installieren" oder "Aktualisieren" Skype for Business Server System.**
    
5. Der Assistent führt Prüfungen aus, um festzustellen, ob etwas bereits installiert ist. Da der Assistent zum ersten Mal ausgeführt wird, sollten Sie mit **Schritt 1 beginnen. Installieren Sie die lokale Konfiguration Store.**
    
6. Das Dialogfeld **"Lokales Replikat des zentralen Verwaltungsspeichers** konfigurieren" wird angezeigt. Sie müssen auf **"Aus Datei importieren" klicken (empfohlen für Edgeserver).**
    
7. Navigieren Sie hier zum Speicherort der Topologie, die Sie zuvor exportiert haben, wählen Sie die .zip Datei aus, klicken Sie auf **"Öffnen"** und dann auf **"Weiter".**
    
8. Der Bereitstellungs-Assistent liest die Konfigurationsdatei und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
9. Nachdem der Prozess **Befehle ausführen** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2. Setup or Remove Skype for Business Server Components**. Der Assistent installiert dann die Skype for Business Server Edgekomponenten, die in der XML-Konfigurationsdatei angegeben sind, die auf dem lokalen Computer gespeichert wurde.
    
11. Nach Abschluss der Installation können Sie mit den Schritten im Abschnitt **"Zertifikate"** weiter unten beginnen.
    
## <a name="certificates"></a>Zertifikate

Die Zertifikatanforderungen für den Edgeserver finden Sie in der Dokumentation zur Edgezertifikatsplanung. Die Schritte zum Einrichten von Zertifikaten finden Sie unten.
  
> [!NOTE]
> Beim Ausführen des Zertifikat-Assistenten müssen Sie als Konto mit den richtigen Berechtigungen für den Typ der Zertifikatvorlage angemeldet sein, die Sie verwenden möchten. Standardmäßig verwendet eine Skype for Business Server Zertifikatanforderung die Webserver-Zertifikatvorlage. Wenn Sie mit einem Konto angemeldet sind, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, um über diese Vorlage ein Zertifikat anzufordern, überprüfen Sie, ob der Gruppe die Berechtigungen "Registrieren" für die Verwendung dieser Vorlage zugewiesen wurden. 
  
### <a name="internal-edge-interface-certificates"></a>Interne Edgeschnittstellenzertifikate

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Herunterladen oder Exportieren der Zertifizierungskette der Zertifizierungsstelle

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; Eine. Herunterladen mithilfe der certsrv-Website

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Melden Sie sich bei einem Skype for Business Server in Ihrem internen Netzwerk als Mitglied der lokalen Administratorengruppe an.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ii. Öffnen **Sie "Start"** und **"Ausführen"** (oder **"Suchen** und **Ausführen"),** und geben Sie dann Folgendes ein:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Zum Beispiel:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Iii. Klicken Sie auf der Zertifikatswebseite der ausstellenden Zertifizierungsstelle unter **"Aufgabe auswählen"** auf **"Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL herunterladen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Iv. Klicken Sie unter **"Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL herunterladen"** auf **"Zertifizierungsstellenzertifikatkette herunterladen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V. Klicken Sie im **Feld "Dateidownload"** auf **"Speichern".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Vi. Speichern Sie die P7B-Datei auf dem Festplattenlaufwerk auf dem Server, und kopieren Sie sie dann in einen Ordner auf jedem Edgeserver.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;B. Exportieren mit MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Sie können das Stammzertifikat der Zertifizierungsstelle mithilfe der MMC von einem beliebigen Computer exportieren, der der Domäne beigetreten ist. Wechseln Sie entweder zu **"Start"** und **"Ausführen",** oder öffnen Sie die **Suche,** und geben Sie **"MMC"** ein, um sie zu öffnen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ii. Klicken Sie in der MMC-Konsole auf **"Datei"** und dann auf **"Snap-In hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Iii. Wählen Sie in der Dialogfeldliste **"Snap-Ins hinzufügen" oder "Snap-Ins entfernen"** die Option **"Zertifikate"** aus, und klicken Sie dann auf **"Hinzufügen".** Wenn Sie dazu aufgefordert werden, wählen Sie **"Computerkonto"** und dann **"Weiter"** aus. Wählen **Sie** im Dialogfeld Computer auswählen die Option **"Lokaler Computer" aus.** Klicken Sie auf **"Fertig stellen"** und dann auf **"OK".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Iv. Erweitern **Sie Zertifikate (lokaler Computer).** Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**. Wählen Sie **Zertifikate aus.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V. Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie im Menü **"Alle Aufgaben"** und dann **"Exportieren"** aus.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Vi. Der **Zertifikatexport-Assistent** wird geöffnet. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Vii. Wählen Sie im Dialogfeld **Dateiformat exportieren** das Format aus, in das Sie exportieren möchten. Unsere Empfehlung ist **kryptografischer Nachrichtensyntaxstandard – PKCS #7 Certificates (P7b)**. Wenn Sie auch dies auswählen, sollten Sie nach Möglichkeit auch das Kontrollkästchen **"Alle Zertifikate in den Zertifizierungspfad einschließen"** aktivieren, da dadurch auch die Zertifikatkette exportiert wird, einschließlich des Zertifikats der Stammzertifizierungsstelle und aller Zwischenzertifikate. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Viii. Geben Sie im Dialogfeld **"Zu exportierende Datei"** im Dateinameneintrag einen Pfad und einen Dateinamen (die Standarderweiterung wäre .p7b) für das exportierte Zertifikat ein. Wenn dies für Sie einfacher ist, wählen Sie die Schaltfläche **"Durchsuchen"** aus, um zu dem Speicherort zu wechseln, an dem Sie das exportierte Zertifikat speichern möchten, und nennen Sie das exportierte Zertifikat hier. Klicken Sie auf **"Speichern"** und dann auf **"Weiter",** wenn Sie fertig sind.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ix. Überprüfen Sie die Zusammenfassung Ihrer Aktionen, und klicken Sie auf **Fertig stellen,** um den Export des Zertifikats abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;X. Kopieren Sie die P7B-Datei auf jeden Ihrer Edgeserver.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importieren der Zertifizierungskette der Zertifizierungsstelle

&nbsp;&nbsp;&nbsp;Eine. Öffnen Sie auf jedem Edgeserver das MMC (wählen Sie **Start** und **Ausführen** oder **Suchen** aus, und geben Sie **MMC** ein, um es zu öffnen).
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie im Menü **"Datei"** auf **"Snap-In hinzufügen/entfernen",** und wählen Sie dann **"Hinzufügen"** aus.
    
&nbsp;&nbsp;&nbsp;C. Klicken Sie im Feld **"Snap-Ins hinzufügen" oder "Entfernen"** auf **"Zertifikate"** und dann auf **"Hinzufügen".**
    
&nbsp;&nbsp;&nbsp;D. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;E. Stellen **Sie** im Dialogfeld Computer auswählen sicher, dass das Kontrollkästchen **"Lokaler Computer: (der Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen.**
    
&nbsp;&nbsp;&nbsp;F. Klicken Sie auf **"Schließen"** und dann auf **"OK".**
    
&nbsp;&nbsp;&nbsp;G. Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer),** klicken Sie mit der rechten Maustaste auf **"Vertrauenswürdige Stammzertifizierungsstellen",** wechseln Sie zu **"Alle Aufgaben",** und klicken Sie dann auf **"Importieren".**
    
&nbsp;&nbsp;&nbsp;H. Geben Sie im angezeigten Assistenten im Textfeld **"Zu importierende Datei"** den Dateinamen des Zertifikats an (den Namen, den Sie der P7B-Datei im vorherigen Abschnitt gegeben haben). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;Ich. Lassen Sie das Optionsfeld auf **"Alle Zertifikate im folgenden Speicher platzieren", da vertrauenswürdige Stammzertifizierungsstellen** ausgewählt werden sollten. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;J. Überprüfen Sie die Zusammenfassung, und klicken Sie auf **Fertig stellen,** um den Import abzuschließen.
    
&nbsp;&nbsp;&nbsp;K. Dies muss für jeden Edgeserver erfolgen, den Sie bereitstellen.
    
### <a name="3-create-the-certificate-request"></a>3. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;Eine. Melden Sie sich bei einem Ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in **Schritt 3: Anfordern, Installieren oder Zuweisen** von Zertifikaten auf **"Ausführen"** (oder **"Erneut ausführen",** wenn Sie diesen Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;B. Stellen Sie auf der Seite **"Zertifikatanforderung"** sicher, dass **das interne Edgezertifikat** ausgewählt ist, und klicken Sie auf **"Anfordern".**
    
&nbsp;&nbsp;&nbsp;C. Wählen Sie auf der Seite **"Verzögerte oder sofortige Anforderungen"** **die Option "Anforderung sofort an eine Onlinezertifizierungsstelle senden"** aus, wenn Sie Zugriff auf eine Anforderung aus Ihrer Edgeumgebung haben, oder **bereiten Sie die Anforderung jetzt vor, aber senden Sie sie später,** andernfalls.
    
&nbsp;&nbsp;&nbsp;D. Geben Sie auf der Seite **"Zertifikatanforderungsdatei"** den vollständigen Teil und den Dateinamen für den Speicherort der Datei ein (z. B. c:\SkypeInternalEdgeCert.cer). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;E. Aktivieren Sie auf der Seite **"Alternative Zertifikatvorlage angeben"** die Option **"Alternative Zertifikatvorlage verwenden" für das ausgewählte** Kontrollkästchen "Zertifizierungsstelle", um eine andere Vorlage als die Standardmäßige WebServer-Vorlage zu verwenden. Führen Sie andernfalls nichts aus.
    
&nbsp;&nbsp;&nbsp;F. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Ich. Geben Sie im **Anzeigenamen** einen Anzeigenamen für das Zertifikat ein (z. B. interner Edge).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Ii. Wählen Sie in **Bitlänge** Die Bitlänge aus (der Standardwert ist 2048, Sie können höher gehen und sicherer sein, aber die Leistung wird verlangsamt).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Iii. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen **"Privaten Zertifikatschlüssel als exportierbar** markieren" aktivieren.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Iv. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;G. Geben Sie auf der Seite **"Organisationsinformationen"** den Namen für Ihre Organisation und Organisationseinheit ein. Sie können Ihre Abteilung oder Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;H. Geben Sie auf der Seite **"Geografische Informationen"** Ihre Standortinformationen ein.
    
&nbsp;&nbsp;&nbsp;Ich. Auf der Seite **"Antragstellername/Alternative Antragstellernamen"** sollte dies automatisch vom Assistenten ausgefüllt werden.
    
&nbsp;&nbsp;&nbsp;J. Auf der Seite **"Zusätzliche alternative Antragstellernamen konfigurieren"** müssen Sie alle zusätzlichen alternativen Antragstellernamen hinzufügen, die Sie benötigen.
    
&nbsp;&nbsp;&nbsp;K. Schauen Sie sich auf der Seite **"Anforderungszusammenfassung"** die Zertifikatinformationen an, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Sie Änderungen vornehmen müssen, gehen Sie zurück und tun Sie dies jetzt.
    
&nbsp;&nbsp;&nbsp;L. Klicken Sie dann auf **"Weiter",** um die CSR-Datei zu generieren, die Sie der Zertifizierungsstelle bereitstellen müssen (Sie können auch auf **"Protokoll anzeigen"** klicken, um das Protokoll für die Zertifikatanforderung anzuzeigen).
    
&nbsp;&nbsp;&nbsp;M. Nachdem die Anforderung generiert wurde, können Sie auf **Ansicht** klicken, um das Zertifikat anzuzeigen, und **fertig stellen,** um das Fenster zu schließen. Der Inhalt der CSR-Datei muss Ihrer Zertifizierungsstelle übergeben werden, damit sie ein Zertifikat generieren kann, das Sie im nächsten Abschnitt auf diesen Computer importieren können.
    

### <a name="4-import-the-certificate"></a>4. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Melden Sie sich als Mitglied der lokalen Gruppe "Administratoren" beim Edgeserver an, von dem Sie ihre Zertifikatsanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;B. Im Bereitstellungs-Assistenten neben **Schritt 3. Anfordern, Installieren oder Zuweisen von Zertifikaten**, klicken Sie auf **"Erneut ausführen".**
    
&nbsp;&nbsp;&nbsp;C. Klicken Sie auf der Seite **"Verfügbare Zertifikataufgaben"** auf **"Zertifikat aus einem importieren". P7b-, PFX- oder CER-Datei.**
    
&nbsp;&nbsp;&nbsp;D. Geben Sie auf der Seite **"Zertifikat importieren"** den vollständigen Pfad und Dateinamen des Zertifikats ein, das Sie im vorherigen Abschnitt erhalten haben (oder klicken Sie auf **"Durchsuchen",** um die Datei auf diese Weise zu suchen und auszuwählen).
    
&nbsp;&nbsp;&nbsp;E. Wenn Sie Zertifikate für andere Mitglieder Ihres Edgepools importieren und Ihr Zertifikat einen privaten Schlüssel enthält, aktivieren Sie unbedingt die Zertifikatdatei, die das **private Schlüsselkontrollkästchen des Zertifikats enthält,** und geben Sie das Kennwort an. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.
    
&nbsp;&nbsp;&nbsp;F. Klicken Sie auf der Seite **"Zusammenfassung"** auf **"Weiter",** nachdem Sie die Informationen bestätigt haben, und **"Fertig stellen",** sobald das Zertifikat erfolgreich importiert wurde.
    
 
### <a name="5-export-the-certificate"></a>5. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Stellen Sie sicher, dass Sie sich bei dem Edgeserver angemeldet haben, auf dem Sie das Zertifikat zuvor als Mitglied der lokalen Gruppe "Administratoren" importiert haben.
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie auf **"Start",** **"Ausführen"** (oder **"Suche** öffnen") und geben Sie **MMC** ein.
    
&nbsp;&nbsp;&nbsp;C. Klicken Sie in der MMC-Konsole auf **"Datei"** und dann auf **"Snap-In hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;D. Klicken Sie im Feld **"Snap-Ins hinzufügen" oder "Entfernen"** auf **"Zertifikate",** und klicken Sie auf **"Hinzufügen".**
    
&nbsp;&nbsp;&nbsp;E. Wählen  Sie im Dialogfeld Zertifikat-Snap-In **Computerkonto** aus. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;F. Wählen Sie im Dialogfeld **"Computer auswählen"** die Option **"Lokaler Computer" aus: (der Computer, auf dem diese Konsole ausgeführt wird).** Klicken Sie auf **Fertig stellen**. Klicken Sie auf **"OK",** und die Konfiguration der MMC-Konsole ist abgeschlossen.
    
&nbsp;&nbsp;&nbsp;G. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **"Persönlich",** und klicken Sie dann auf **"Zertifikate".**
    
  > [!NOTE]
  > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Zertifikatspeicher für den lokalen Computer angezeigt. Sie müssen nicht suchen, wenn der Schlüssel nicht vorhanden ist, war dem importierten Zertifikat kein privater Schlüssel zugeordnet. Probieren Sie die obigen Anforderungs- und Importschritte noch einmal aus. Wenn Sie sicher sind, dass Sie alle richtigen Schritte ausgeführt haben, wenden Sie sich an ihren Zertifizierungsstellenadministrator oder -anbieter. 
  
&nbsp;&nbsp;&nbsp;H. Klicken Sie im **persönlichen Zertifikatspeicher** für den lokalen Computer mit der rechten Maustaste auf das Zertifikat, das Sie exportieren. Wählen Sie im resultierenden Menü **"Alle Aufgaben"** aus, und klicken Sie dann auf **"Exportieren".**
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im Assistenten für den Zertifikatexport auf **Weiter**. Wählen Sie **"Ja", exportieren** Sie den privaten Schlüssel. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;J. Wählen Sie im Dialogfeld **"Dateiformate exportieren"** die Option **"Persönliche Informationen Exchange – PKCS#12 (. PFX)** und wählen Sie dann Folgendes aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Ich. Fügen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Ii. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen **Sie NIEMALS** den privaten Schlüssel **löschen aus, wenn der Export erfolgreich war.** Dies bedeutet, dass Sie das Zertifikat und den privaten Schlüssel erneut zu diesem Edgeserver importieren müssen.
  
&nbsp;&nbsp;&nbsp;K. Wenn Sie ein Kennwort zum Schutz des privaten Schlüssels zuweisen möchten, können Sie ein Kennwort für den privaten Schlüssel eingeben. Geben Sie das Kennwort erneut ein, um es zu bestätigen, und klicken Sie dann auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;L. Geben Sie mithilfe der Dateierweiterung **PFX** einen Pfad und einen Dateinamen für das exportierte Zertifikat ein. Der Pfad muss entweder von den anderen Edgeservern im Pool zugänglich sein, oder Sie müssen die Datei über externe Medien (z. B. ein USB-Laufwerk) verschieben. Klicken Sie auf **"Weiter",** wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;M. Überprüfen Sie die Zusammenfassung im Dialogfeld **"Zertifikatexport-Assistent abschließen",** und klicken Sie dann auf **"Fertig stellen".**
    
&nbsp;&nbsp;&nbsp;N. Klicken Sie im Dialogfeld für erfolgreichen Export auf **"OK".**
    
 
### <a name="6-assign-the-certificate"></a>6. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Auf jedem Edgeserver, im Bereitstellungs-Assistenten, neben **Schritt 3. Anfordern, Installieren oder Zuweisen von Zertifikaten**, klicken Sie erneut auf **"Ausführen".**
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie auf der Seite **"Verfügbare Zertifikataufgaben"** auf **"Vorhandenes Zertifikat zuweisen".**
    
&nbsp;&nbsp;&nbsp;C. Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Edge intern** aus.
    
&nbsp;&nbsp;&nbsp;D. Wählen Sie auf der Seite **"Zertifikat Store"** das Zertifikat aus, das Sie für den internen Edge importiert haben (aus dem vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;E. Sehen Sie sich auf der Seite "Zusammenfassung der **Zertifikatzuweisung"** die Einstellungen an, und klicken Sie dann auf **"Weiter",** um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;F. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;G. Nachdem Sie dieses Verfahren abgeschlossen haben, empfiehlt es sich, das MMC-Snap-In "Zertifikate" auf jedem Edgeserver zu öffnen, **Zertifikate (lokaler Computer)** zu erweitern, **"Persönlich"** zu erweitern, auf **"Zertifikate"** zu klicken und zu bestätigen, dass das interne Edgezertifikat im Detailbereich aufgeführt ist.
    
### <a name="external-edge-interface-certificates"></a>Zertifikate für externe Edgeschnittstellen

 
### <a name="1-create-the-certificate-request"></a>1. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;Eine. Melden Sie sich bei einem Ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in **Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten auf "Ausführen"** (oder **"Erneut ausführen",** wenn Sie diesen Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.
    
&nbsp;&nbsp;&nbsp;C. Stellen Sie auf der Seite **"Zertifikatanforderung"** sicher, dass **das externe Edgezertifikat** ausgewählt ist, und klicken Sie auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;D. Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.
    
&nbsp;&nbsp;&nbsp;E. Geben Sie auf der Seite **"Zertifikatanforderungsdatei"** den vollständigen Teil und den Dateinamen für den Speicherort der Datei ein (z. B. c:\SkypeInternalEdgeCert.cer). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;F. Aktivieren Sie auf der Seite **"Alternative Zertifikatvorlage angeben"** die Option **"Alternative Zertifikatvorlage verwenden" für das ausgewählte** Kontrollkästchen "Zertifizierungsstelle", um eine andere Vorlage als die Standardmäßige WebServer-Vorlage zu verwenden.
    
&nbsp;&nbsp;&nbsp;G. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   Ich. Geben Sie im **Anzeigenamen** einen Anzeigenamen für das Zertifikat ein (z. B. externer Edge).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Ii. Wählen Sie in **Bitlänge** die Bitlänge aus (der Standardwert ist 2048, Sie können höher gehen und sicherer sein, aber die Leistung wird verlangsamt).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  Iii. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen **"Privaten Zertifikatschlüssel als exportierbar** markieren" aktivieren.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Iv. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;H. Geben Sie auf der Seite **"Organisationsinformationen"** den Namen für Ihre Organisation und Organisationseinheit ein. Sie können Ihre Abteilung oder Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;Ich. Geben Sie auf der Seite **"Geografische Informationen"** Ihre Standortinformationen ein.
    
&nbsp;&nbsp;&nbsp;J. Auf der Seite **"Antragstellername/Alternative Antragstellernamen"** sollten die erforderlichen Informationen automatisch vom Assistenten aufgefüllt werden.
    
&nbsp;&nbsp;&nbsp;K. Aktivieren Sie auf der Seite **"SIP-Domäneneinstellung" auf der Seite "Alternative Antragstellernamen" (SANs)** das Domänenkontrollkästchen, um einen SIP hinzuzufügen.<sipdomain> Eintrag in der Liste alternativer Antragstellernamen.
    
&nbsp;&nbsp;&nbsp;L. Auf der Seite **"Zusätzliche alternative Antragstellernamen konfigurieren"** müssen Sie alle zusätzlichen alternativen Antragstellernamen hinzufügen, die Sie benötigen.
    
&nbsp;&nbsp;&nbsp;M. Schauen Sie sich auf der Seite **"Anforderungszusammenfassung"** die Zertifikatinformationen an, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Sie Änderungen vornehmen müssen, gehen Sie zurück und tun Sie dies jetzt.
    
&nbsp;&nbsp;&nbsp;N. Wenn Sie bereit sind, klicken Sie auf **"Weiter",** um die CSR-Datei zu generieren, die Sie der Zertifizierungsstelle bereitstellen müssen (Sie können auch auf **"Protokoll anzeigen"** klicken, um das Protokoll für die Zertifikatanforderung anzuzeigen).
    
&nbsp;&nbsp;&nbsp;O. Nachdem die Anforderung generiert wurde, können Sie auf **Ansicht** klicken, um das Zertifikat anzuzeigen, und **fertig stellen,** um das Fenster zu schließen. Der Inhalt der CSR-Datei muss Ihrer Zertifizierungsstelle übergeben werden, damit sie ein Zertifikat generieren kann, das Sie im nächsten Abschnitt auf diesen Computer importieren können.
    
&nbsp;&nbsp;&nbsp;P. (OPTIONAL) Sie können, wenn Sie den Inhalt der CSR übermitteln, wie folgt nach bestimmten Informationen gefragt werden (CAs variieren erheblich, daher ist dies möglicherweise nicht erforderlich):
    
  - **Microsoft** als Serverplattform
    
  - **IIS** als Version
    
  - **Webserver** als Verwendungstyp
    
  - **PKCS7** als Antwortformat
    
 
### <a name="2-import-the-certificate"></a>2. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Melden Sie sich als Mitglied der lokalen Gruppe "Administratoren" beim Edgeserver an, von dem Sie ihre Zertifikatsanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;B. Im Bereitstellungs-Assistenten neben **Schritt 3. Anfordern, Installieren oder Zuweisen von Zertifikaten**, klicken Sie auf **"Erneut ausführen".**
    
&nbsp;&nbsp;&nbsp;C. Klicken Sie auf der Seite **"Verfügbare Zertifikataufgaben"** auf **"Zertifikat aus einem importieren". P7b-, PFX- oder CER-Datei.**
    
&nbsp;&nbsp;&nbsp;D. Geben Sie auf der Seite **"Zertifikat importieren"** den vollständigen Pfad und Dateinamen des Zertifikats ein, das Sie im vorherigen Abschnitt erhalten haben (oder klicken Sie auf **"Durchsuchen",** um die Datei auf diese Weise zu suchen und auszuwählen). Wenn Ihr Zertifikat einen privaten Schlüssel enthält, stellen Sie sicher, dass die Zertifikatdatei den **privaten Schlüssel des Zertifikats enthält,** und geben Sie das Kennwort für den privaten Schlüssel ein. Klicken Sie auf **"Weiter",** wenn sie fertig ist.
    
&nbsp;&nbsp;&nbsp;E. Überprüfen Sie auf der Seite **"Zertifikatzusammenfassung importieren"** die Zusammenfassungsinformationen, und klicken Sie auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;F. Auf der Seite **"Befehle ausführen"** können Sie das Ergebnis des Imports überprüfen, wenn er abgeschlossen ist, indem Sie auf **"Protokoll anzeigen"** klicken. Klicken Sie auf **Fertig stellen,** um den Zertifikatimport abzuschließen.
    
&nbsp;&nbsp;&nbsp;G. Wenn sich andere Edgeserver in einem Pool befinden, müssen Sie auch die nächsten beiden Verfahren ausführen. Wenn es sich um einen eigenständigen Edgeserver handelt, müssen Sie externe Zertifikate verwenden.
    
 
### <a name="3-export-the-certificate"></a>3. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Stellen Sie sicher, dass Sie sich beim Edgeserver angemeldet haben, auf dem Sie das Zertifikat als lokaler Administrator importiert haben.
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie auf **"Start",** **"Ausführen"** (oder **"Suche** öffnen") und geben Sie **MMC** ein.
    
&nbsp;&nbsp;&nbsp;C. Klicken Sie in der MMC-Konsole auf **"Datei"** und dann auf **"Snap-In hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;D. Klicken Sie im Feld **"Snap-Ins hinzufügen" oder "Entfernen"** auf **"Zertifikate",** und klicken Sie auf **"Hinzufügen".**
    
&nbsp;&nbsp;&nbsp;E. Wählen  Sie im Dialogfeld Zertifikat-Snap-In **Computerkonto** aus. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;F. Wählen Sie im Dialogfeld **"Computer auswählen"** die Option **"Lokaler Computer" aus: (der Computer, auf dem diese Konsole ausgeführt wird).** Klicken Sie auf **Fertig stellen**. Klicken Sie auf **"OK",** und die Konfiguration der MMC-Konsole ist abgeschlossen.
    
&nbsp;&nbsp;&nbsp;G. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. **Doppelklicken Sie auf "Persönlich",** und klicken Sie dann auf **"Zertifikate".**
    
   > [!NOTE]
   > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Zertifikatspeicher für den lokalen Computer angezeigt. Sie müssen nicht suchen, wenn der Schlüssel nicht vorhanden ist, war dem importierten Zertifikat kein privater Schlüssel zugeordnet. Probieren Sie die obigen Anforderungs- und Importschritte noch einmal aus. Wenn Sie sicher sind, dass Sie alle richtigen Schritte ausgeführt haben, wenden Sie sich an ihren Zertifizierungsstellenadministrator oder -anbieter. 
  
&nbsp;&nbsp;&nbsp;H. Klicken Sie im **persönlichen Zertifikatspeicher** für den lokalen Computer mit der rechten Maustaste auf das Zertifikat, das Sie exportieren. Wählen Sie im resultierenden Menü **"Alle Aufgaben"** aus, und klicken Sie dann auf **"Exportieren".**
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im Assistenten für den Zertifikatexport auf **Weiter**. Wählen Sie **"Ja", exportieren** Sie den privaten Schlüssel. Klicken Sie auf **Weiter**.
    
   > [!NOTE]
   > If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it. Sie müssen das Zertifikat erneut vom Anbieter anfordern, wobei der private Schlüssel für den Export festgelegt ist, bevor Sie dies erfolgreich ausführen.
  
&nbsp;&nbsp;&nbsp;J. Wählen Sie im Dialogfeld "Dateiformate exportieren" die Option "Persönliche Informationen Exchange – PKCS#12 (. PFX) und wählen Sie dann Folgendes aus:
    
 &nbsp;&nbsp;&nbsp;  Ich. Fügen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
 &nbsp;&nbsp;&nbsp;  Ii. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen **Sie NIEMALS** den privaten Schlüssel **löschen aus, wenn der Export erfolgreich war.** Dies bedeutet, dass Sie das Zertifikat und den privaten Schlüssel erneut zu diesem Edgeserver importieren müssen.
  
&nbsp;&nbsp;&nbsp;K. Wenn Sie ein Kennwort zum Schutz des privaten Schlüssels zuweisen möchten, können Sie ein Kennwort für den privaten Schlüssel eingeben. Geben Sie das Kennwort erneut ein, um es zu bestätigen, und klicken Sie dann auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;L. Geben Sie mithilfe der Dateierweiterung **PFX** einen Pfad und einen Dateinamen für das exportierte Zertifikat ein. Der Pfad muss entweder von den anderen Edgeservern im Pool zugänglich sein, oder Sie müssen die Datei über externe Medien (z. B. ein USB-Laufwerk) verschieben. Klicken Sie auf **"Weiter",** wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;M. Überprüfen Sie die Zusammenfassung im Dialogfeld **"Zertifikatexport-Assistent abschließen",** und klicken Sie dann auf **"Fertig stellen".**
    
&nbsp;&nbsp;&nbsp;N. Klicken Sie im Dialogfeld für erfolgreichen Export auf **"OK".**
    
&nbsp;&nbsp;&nbsp;O. Sie müssen nun zu diesem Abschnitt "Zertifikat importieren" zurückkehren und das Zertifikat in alle verbleibenden Edgeserver importieren. Fahren Sie dann mit der Zuweisung fort, unten.
    
 
### <a name="4-assign-the-certificate"></a>4. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;Eine. Auf **jedem** Edgeserver, im Bereitstellungs-Assistenten, neben **Schritt 3. Anfordern, Installieren oder Zuweisen von Zertifikaten**, klicken Sie erneut auf **"Ausführen".**
    
&nbsp;&nbsp;&nbsp;B. Klicken Sie auf der Seite **"Verfügbare Zertifikataufgaben"** auf **"Vorhandenes Zertifikat zuweisen".**
    
&nbsp;&nbsp;&nbsp;C. Wählen Sie auf der Seite **"Zertifikatzuweisung"** in der Liste **"Edge extern"** aus.
    
&nbsp;&nbsp;&nbsp;D. Wählen Sie auf der Seite **"Zertifikat Store"** das Zertifikat aus, das Sie für den externen Edge importiert haben (aus dem vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;E. Sehen Sie sich auf der Seite "Zusammenfassung der **Zertifikatzuweisung"** die Einstellungen an, und klicken Sie dann auf **"Weiter",** um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;F. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;G. Nachdem Sie dieses Verfahren abgeschlossen haben, empfiehlt es sich, das MMC-Snap-In "Zertifikate" auf jedem Server zu öffnen, **Zertifikate (lokaler Computer)** zu erweitern, **"Persönlich"** zu erweitern, auf **"Zertifikate"** zu klicken und zu bestätigen, dass das interne Edgezertifikat im Detailbereich aufgeführt ist.
    
   > [!NOTE]
   > Außerdem müssen Sie die Zertifikate für Ihren Reverseproxyserver einrichten. 
  
## <a name="starting-the-edge-servers"></a>Starten der Edgeserver

Sobald das Setup abgeschlossen ist, müssen Sie die Dienste auf jedem Edgeserver in Ihrer Bereitstellung starten:
  
1. Klicken Sie auf jedem Edgeserver im **Bereitstellungs-Assistenten** neben **Schritt 4: Dienste starten** auf **"Ausführen".**
    
2. Überprüfen Sie auf der Seite **"Start Skype for Business Server Services"** die Liste der Dienste, und klicken Sie dann auf **"Weiter",** um die Dienste zu starten.
    
3. Nachdem die Dienste gestartet wurden, können Sie auf **Fertig stellen** klicken, um den Assistenten zu schließen.
    
4. (Optional) Klicken Sie weiterhin unter **Schritt 4: Dienste starten** auf **Dienststatus**.
    
5.  Überprüfen Sie in der **Dienst-MMC** auf jedem Server, ob alle Skype for Business Server Dienste ausgeführt werden.
    

