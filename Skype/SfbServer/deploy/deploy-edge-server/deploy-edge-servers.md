---
title: Stellen Sie Edgeserver in Skype für Business Server
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
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Zusammenfassung: Informationen Sie zum Bereitstellen von Edge-Servern in Ihrer Skype für Business Server-Umgebung.'
ms.openlocfilehash: 28a3262e49816976110aab0adde07a64c8d126fb
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "23890950"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Stellen Sie Edgeserver in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Bereitstellen von Edge-Servern in Ihrer Skype für Business Server-Umgebung.
  
Die folgenden Abschnitte enthalten Schritte, die einen befolgt werden, wenn die Skype Dokumentation Business Server [Planen von Edge-Server-Bereitstellungen in Skype für Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) überprüft wurde. Es handelt sich um die folgenden Bereitstellungsschritte:
  
- Netzwerkschnittstellen
    
- Installation
    
- Zertifikate
    
- Starten Sie die Edge-Server
    
## <a name="network-interfaces"></a>Netzwerkschnittstellen

Wie in Planning bereits erwähnt, werden Sie entweder die Netzwerkschnittstelle mit DNS im Umkreisnetzwerk Ihrer Edge-Server gehostet oder ohne DNS im Umkreisnetzwerk konfigurieren.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration mit DNS-Servern im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, eine für die interne Schnittstelle und eine für die externe Schnittstelle.
    
    > [!NOTE]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein. 
  
2. Für die externe Schnittstelle benötigen Sie **eine** der folgenden konfigurieren:
    
   a. Konfiguration von drei statischen IP-Adressen im externen Subnetz des Umkreisnetzwerks und Verweis des Standardgateways auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf ein DNS-Umkreisserverpaar verweisen.
    
   b. Eine statische IP-Adresse Adresse auf die externe Umkreisnetzwerk Netzwerksubnetz, und zeigen Sie das Standardgateway auf die interne Schnittstelle von der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf ein DNS-Umkreisserverpaar verweisen. Diese Konfiguration ist nur zulässig, wenn Sie zuvor Topologie zur nicht standardmäßigen Werte haben in die Zuordnungen Port konfiguriert haben, [Erstellen Sie eine Edge-Topologie für Skype für Business Server](create-your-edge-topology.md) Artikel behandelt wird.
    
3. Konfigurieren Sie für die interne Schnittstelle eine statische IP-Adresse auf die interne Umkreisnetzwerk Netzwerksubnetz, und festlegen Sie einen Standardgateway nicht. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese mindestens auf einen DNS-Server, jedoch vorzugsweise auf ein DNS-Umkreisserverpaar, verweisen.
    
4. Erstellen Sie dauerhafte statische Routen für die interne Schnittstelle zu allen internen Netzwerken, in denen Clients Skype für Business Server und Exchange Unified Messaging (UM) Server befinden.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration ohne DNS-Server im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, eine für die interne Schnittstelle und eine für die externe Schnittstelle.
    
    > [!NOTE]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein. 
  
2. Für die externe Schnittstelle benötigen Sie **eine** der folgenden konfigurieren:
    
   a. Konfiguration von drei statischen IP-Adressen im externen Subnetz des Umkreisnetzwerks. Sie auch müssen so konfigurieren Sie das Standardgateway auf die externe Schnittstelle, beispielsweise dem Internet verbundenen Router oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf einen externen DNS-Server, vorzugsweise auf ein externes DNS-Serverpaar, verweisen.
    
   b. Eine statische IP-Adresse auf die externe Umkreisnetzwerk Netzwerksubnetz. Sie auch müssen so konfigurieren Sie das Standardgateway auf die externe Schnittstelle, beispielsweise dem Internet verbundenen Router oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie so zeigen Sie auf einen externen DNS-Server oder idealerweise ein Paar von externen DNS-Server die Adapter DNS-Einstellungen. Diese Konfiguration ist nur zulässig, wenn Sie zuvor Topologie zur nicht standardmäßigen Werte haben in die Zuordnungen Port konfiguriert haben, [Erstellen Sie eine Edge-Topologie für Skype für Business Server](create-your-edge-topology.md) Artikel behandelt wird.
    
3. Konfigurieren Sie für die interne Schnittstelle eine statische IP-Adresse auf die interne Umkreisnetzwerk Netzwerksubnetz, und festlegen Sie einen Standardgateway nicht. Lassen Sie außerdem die DNS-Einstellungen des Netzwerkadapters leer.
    
4. Erstellen Sie dauerhafte statische Routen für die interne Schnittstelle zu allen internen Netzwerken, in denen Clients Skype für Business Server und Exchange Unified Messaging (UM) Server befinden.
    
5. Bearbeiten der Hostdatei auf jedem Edgeserver enthält einen Eintrag für den nächsten Hopserver oder virtuelle IP-Adresse (VIP). Dieser Eintrag wird den Director, Standard Edition-Server oder Front-End-Pools, den Sie als nächsten Hop-Adresse von Edge-Server im Topologie-Generator konfiguriert sein. Wenn Sie DNS-Lastenausgleich verwenden, fügen Sie eine Zeile für jedes Mitglied den nächsten hoppool aus.
    
## <a name="installation"></a>Installation

Um diese Schritte erfolgreich abgeschlossen werden, müssen Sie die Schritte im Artikel [Erstellen Sie eine Edge-Topologie für Skype für Business Server](create-your-edge-topology.md) durchgeführt haben.
  
1. Melden Sie sich an den Server, der für den Edge-Server-Role über ein Konto konfiguriert wurde haben, die in der lokalen Administratorgruppe ist.
    
2. Sie benötigen die topologiekonfigurationsdatei, die Sie am Ende der Edge-Server-Topologie-Dokumentation auf diesem Computer kopiert. Greifen Sie auf den externen Datenträger zu, auf dem Sie die Konfigurationsdatei gespeichert haben (z. B. ein USB-Laufwerk oder eine Netzwerkfreigabe).
    
3. Starten Sie den **Bereitstellungs-Assistenten**.
    
4. Nachdem der Assistent geöffnet wird, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**.
    
5. Der Assistent wird ausgeführt, überprüft, um festzustellen, ob etwas bereits installiert ist. Da es sich beim ersten Ausführen des Assistenten handelt, sollten Sie unter Schritt 1 **starten. Installieren des lokalen Konfigurationsspeichers.**
    
6. Das Dialogfeld **Speichern lokalen Replikat des zentralen Management konfigurieren** wird angezeigt. Sie müssen auf **Import aus einer Datei (für Edgeserver empfohlen)** klicken.
    
7. Gehen Sie von hier aus zum Speicherort der Topologie, die Sie zuvor exportiert haben. Wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen** und anschließend auf **Weiter**.
    
8. Im Bereitstellungs-Assistenten wird die Konfigurationsdatei lesen und Schreiben von XML-Konfigurationsdatei auf dem lokalen Computer.
    
9. Nachdem der Prozess **Befehle werden ausgeführt** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie im Bereitstellungs-Assistenten auf Schritt2 **. Einrichten oder Entfernen von Skype für Business Server-Komponenten**. Der Assistent installiert dann die Skype für Business Server Edge-Komponenten in der XML-Konfigurationsdatei, die auf dem lokalen Computer gespeichert wurden, wird angegeben.
    
11. Nachdem die Installation abgeschlossen zugrunde, können Sie auf die Schritte im Abschnitt **Zertifikate** verschieben.
    
## <a name="certificates"></a>Zertifikate

Die zertifikatanforderungen für den Edge-Server finden Sie in der Edge-Zertifikat in der Planungsdokumentation. Die erforderlichen Schritte zur Einrichtung von Zertifikaten finden Sie unten.
  
> [!NOTE]
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie angemeldet sein, mit einem Konto mit den entsprechenden Berechtigungen für den Typ der Zertifikatvorlage an, dass Sie verwenden möchten. Standardmäßig wird eine Skype für zertifikatanforderung Business Server verwenden Sie die Webserver-Zertifikatvorlage sollte. Wenn Sie sich mit einem Konto, die zum Anfordern eines Zertifikats über diese Vorlage angemeldet sind, überprüfen, um sicherzustellen, dass der Gruppe ein Mitglied der Gruppe RTCUniversalServerAdmins ist wurde die Berechtigung registrieren, die diese Vorlage verwenden zugewiesen. 
  
### <a name="internal-edge-interface-certificates"></a>Zertifikate der internen Edgeschnittstelle

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. herunterladen Sie oder exportieren Sie die Zertifikatskette der Zertifizierungsstelle

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;ein. Download mit CertSrv-Website

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Melden Sie sich einen Skype für Business Server im internen Netzwerk als Mitglied der Gruppe der lokalen Administratoren.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Öffnen Sie **Starten**, und **Führen Sie** (oder **Suche** und **Ausführen** ), und geben Sie Folgendes:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Zum Beispiel:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Klicken Sie auf die ausstellende Zertifizierungsstelle Certsrv Webseite wählen Sie unter **Task auswählen**auf **Herunterladen einer Zertifizierungsstellen-Zertifikat, Zertifikatkette oder einer Zertifikatsperrliste**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Klicken Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatssperrliste** auf **Download der Zertifizierungsstellen-Zertifikatkette**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V. Klicken Sie im Feld **Dateidownload** auf **Speichern**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Speichern Sie die P7B-Datei auf der Festplatte auf dem Server, und kopieren Sie sie in einen Ordner auf jedem Ihrer Edgeserver.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Export mit MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Sie können das Stammzertifikat der Zertifizierungsstelle mithilfe von MMC von einem beliebigen Computer in der Domäne aus exportieren. Gehen Sie entweder zu **Starten** und **Ausführen** oder öffnen Sie **Suchen** und geben Sie **MMC** ein, um die Funktion zu öffnen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. In der Liste **Hinzufügen oder Entfernen von-Snap-ins** Dialogfeld Wählen Sie **Zertifikate**aus, und klicken Sie dann auf **Hinzufügen**. Wenn Sie aufgefordert werden, wählen Sie **Computerkonto**und anschließend auf **Weiter**. Wählen Sie **Lokaler Computer**, klicken Sie im Dialogfeld **Computer auswählen** . Klicken Sie auf **Fertig stellen,** und klicken Sie dann auf **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Erweitern Sie den Knoten Sie **Zertifikate (lokaler Computer)**. Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**. Die Option **Zertifikate**aus.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;V. Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie im Menü **Alle Aufgaben** und anschließend **Exportieren** aus.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Der **Zertifikatexport-Assistent** wird geöffnet. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** ein Format für den Export aus. Wir empfehlen die Verwendung von **Syntaxstandard kryptografischer Meldungen – PKCS #7-Zertifikate (P7B)**. Ist, die ebenfalls Ihrer Wahl, denken Sie daran, auch das Kontrollkästchen **Wenn möglich, alle Zertifikate im Zertifizierungspfad einbeziehen** auswählen, wie dies auch die Zertifikatkette, einschließlich das Zertifikat der Stammzertifizierungsstelle und alle Intermediate Zertifikate exportiert wird. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Geben Sie im Dialogfeld **Zu exportierende Datei** im Eingabefeld für den Dateinamen einen Pfad und Dateinamen (die Standarderweiterung lautet „.p7b“) für das exportierte Zertifikat ein. Wenn auf Sie einfacher ist, wählen Sie die Schaltfläche **Durchsuchen** , um zu dem Speicherort zu wechseln, das exportierte Zertifikat gespeichert werden soll, und nennen Sie das exportierte Zertifikat hier. Wenn Sie bereit sind, klicken Sie auf **Speichern**und anschließend auf **Weiter** .
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Überprüfen Sie die Zusammenfassung der von Ihnen ausgeführten Aktionen und klicken Sie auf **Fertig stellen**, um den Zertifikatexport abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;X. Kopieren Sie die P7B-Datei auf jedem Ihrer Edgeserver.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importieren Sie die Zertifikatskette der Zertifizierungsstelle

&nbsp;&nbsp;&nbsp;ein. Öffnen Sie auf jedem Edgeserver die MMC (Wählen Sie **Start** und **Ausführen**, oder **Suchen**, und geben Sie **MMC** geöffnet).
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und wählen Sie dann **Hinzufügen** aus.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und anschließend auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;e. Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist. Klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf **Schließen** und dann auf **OK**.
    
&nbsp;&nbsp;&nbsp;g. Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen**, gehen Sie zu **Alle Aufgaben** und klicken Sie dann auf **Importieren**.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie im Textfeld **Zu importierende Datei** des Assistenten, der geöffnet wird, den Namen des Zertifikats ein (die Benennung der P7B-Datei, die Sie im vorhergehenden Abschnitt ausgewählt haben). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;Ich. Aktivieren Sie das Optionsfeld **Alle Zertifikate in folgendem Speicher speichern, Vertrauenswürdige Stammzertifizierungsstellen**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Überprüfen Sie die Zusammenfassung und klicken Sie auf **Fertig stellen**, um den Import abzuschließen.
    
&nbsp;&nbsp;&nbsp;k. Dies muss für jeden Edge-Server ausgeführt werden, die Sie bereitstellen.
    
### <a name="3-create-the-certificate-request"></a>3. erstellen Sie die zertifikatanforderung

&nbsp;&nbsp;&nbsp;ein. Melden Sie sich an einen der Edge-Server, starten Sie den Bereitstellungs-Assistenten, und klicken Sie auf **Schritt 3: Zertifikate anfordern, installieren, oder weisen Sie**, klicken Sie auf **Ausführen** (oder **Erneut ausführen**, wenn Sie dieses Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;b. Stellen Sie sicher, dass auf der Seite **Zertifikatsanforderung** die Option **Internes Edgezertifikat** ausgewählt ist und klicken Sie auf **Anforderung**.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** wählen Sie **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** , wenn Sie Zugriff auf eine über edgeumgebung oder eine **Anforderung jetzt vorbereiten, jedoch später senden** andernfalls haben.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie auf der Seite **Zertifikatsanforderungsdatei** den vollständigen Pfad und Dateinamen an, um zu bestimmen, wo die Datei gespeichert wird (z. B. c:\SkypeInternalEdgeCert.cer). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;e. Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage „WebServer“ zu verwenden. Wenn Sie dies nicht wünschen, müssen Sie diesen Schritt nicht ausführen.
    
&nbsp;&nbsp;&nbsp;f. Führen Sie auf der Seite  Namens- und Sicherheitseinstellungen  die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein (z. B. „Interner Edgeserver“).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Wählen Sie unter **Bitlänge** die Bitlänge aus (Standard ist 2048, sie können diesen Wert zur Sicherheit erhöhen, dies verlangsamt jedoch die Leistung).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktivieren.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;g. Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit (OE) ein. Sie können den Geschäftsbereich oder die Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie auf der Seite **Geografische Informationen** die Angaben zum Standort ein.
    
&nbsp;&nbsp;&nbsp;Ich. Die Seite **Antragstellernamen/Alternative Antragstellernamen** sollte automatisch vom Assistenten aufgefüllt werden.
    
&nbsp;&nbsp;&nbsp;j. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** alle erforderlichen zusätzlichen alternativen Antragstellernamen an.
    
&nbsp;&nbsp;&nbsp;k. Suchen Sie auf der Seite **Zusammenfassung der Anforderung** über die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden soll. Wenn Änderungen nötig sind, gehen Sie zurück und führen Sie diese jetzt aus.
    
&nbsp;&nbsp;&nbsp;l. Klicken Sie dann auf **Weiter** , um die CSR-Datei zu generieren, die Sie benötigen, an der Zertifizierungsstelle übermitteln (Sie können auch **Protokoll anzeigen** , um das Protokoll für die zertifikatanforderung betrachten klicken).
    
&nbsp;&nbsp;&nbsp;m. Sobald die Anforderung generiert wurde, können Sie auf **Anzeigen** klicken, um das Zertifikat anzuzeigen, und auf **Fertig stellen**, um das Fenster zu schließen. Der Inhalt der CSR-Datei muss der Zertifizierungsstelle vorgelegt werden, damit diese ein Zertifikat erstellen kann, das Sie zu diesen Computer importieren müssen (siehe nächster Abschnitt).
    

### <a name="4-import-the-certificate"></a>4. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Melden Sie sich, als Mitglied der lokalen Gruppe Administratoren auf den Edge-Server, die Sie in der letzten Prozedur aus der zertifikatanforderung vorgenommen.
    
&nbsp;&nbsp;&nbsp;b. Der Bereitstellungs-Assistenten neben Schritt 3 **. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **Erneut ausführen**.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie auf der Seite **Verfügbare Zertifikatsaufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie im vorhergehenden Abschnitt erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen).
    
&nbsp;&nbsp;&nbsp;e. Wenn Sie Zertifikate für andere Mitglieder Ihres edgepools importieren und das Zertifikat einen privaten Schlüssel enthält, müssen Sie unbedingt das Kontrollkästchen **Zertifikat-Testdatei, die privaten Schlüssel des Zertifikats enthält** , und geben Sie das Kennwort an. Klicken Sie auf **Weiter**, um fortzufahren.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite**Zusammenfassung** auf **Weiter** , nachdem Sie die Informationen und **Fertig stellen** bestätigt haben, nachdem das Zertifikat erfolgreich importiert wurde.
    
 
### <a name="5-export-the-certificate"></a>5. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Stellen Sie sicher, dass Sie auf dem Edge-Server angemeldet haben Sie das Zertifikat, das zuvor, als Mitglied der Gruppe der lokalen Administratoren importiert.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf **Start**, **Ausführen** (oder **Suche** öffnen), und geben Sie **MMC**ein.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole auf **Datei** und auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Snap-In-Dialogfeld **Zertifikate** die Option **Computerkonto**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)**. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**, um die Konfiguration der MMC-Konsole abzuschließen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **Eigene Zertifikate** und klicken Sie dann auf **Zertifikate**.
    
  > [!NOTE]
  > Sie hier möglicherweise, und alle Zertifikate in die eigene Zertifikate für den lokalen Computer nicht angezeigt. Sie müssen nicht Sammelanschlüssen, wenn der Schlüssel nicht vorhanden, die importierten's nicht Zertifikat einen privaten Schlüssel zugeordnet haben. Wiederholen Sie die Anforderung und Schritte noch einmal importieren, und wenn Sie sicher, dass Sie alle diese richtig sind, wenden Sie sich an den Zertifizierungsstellen-Administrator oder vom Anbieter. 
  
&nbsp;&nbsp;&nbsp;h. **Speichern Sie eigene Zertifikate** für den lokalen Computer mit der Maustaste des Zertifikats, das Sie exportieren. Wählen Sie im eingeblendeten Menü **Alle Tasks** aus, und klicken Sie dann auf **Exportieren**.
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im **Zertifikatexport-Assistenten**auf **Weiter**. Wählen Sie **Ja, privaten Schlüssel exportieren**aus. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** die Option **Privater Informationsaustausch – PKCS#12 (.PFX)** aus. Wählen Sie dann Folgendes aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Beziehen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen Sie **NIE** die Option **Privaten Schlüssel nach erfolgreichem Export löschen** aus. Es werden bedeutet, dass Sie zum Importieren des Zertifikats und privaten Schlüssel wieder mit diesem Edgeserver verfügen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein und klicken Sie dann auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung **.pfx** verwenden. Der Pfad muss entweder den anderen Edge-Servern im Pool zugänglich sein, oder müssen Sie die Datei über externe Medien (beispielsweise ein USB-Laufwerk) zu verschieben. Wenn Sie Ihre Auswahl getroffen haben, klicken Sie auf **Weiter** .
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Zertifikatexport-Assistenten** und klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.
    
 
### <a name="6-assign-the-certificate"></a>6. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben Schritt 3 **. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **erneut ausführen**.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Interner Edgeserver** aus.
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat, das Sie für die interne Schnittstelle (aus dem vorherigen Abschnitt) importiert haben.
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen und klicken Sie dann auf **Weiter**, um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Wenn Sie dieses Verfahren abgeschlossen haben, ist es eine gute Wahl, öffnen Sie das Zertifikat-MMC-Snap-in auf jedem Edgeserver, den Knoten **Zertifikate (lokaler Computer)**, erweitern **Persönlich**, klicken Sie auf **Zertifikate**und bestätigen Sie, dass die interne Schnittstelle das Zertifikat wird im Detailbereich aufgeführt.
    
### <a name="external-edge-interface-certificates"></a>Zertifikate der externen Edgeschnittstelle

 
### <a name="1-create-the-certificate-request"></a>1. erstellen Sie 1. die zertifikatanforderung

&nbsp;&nbsp;&nbsp;ein. Melden Sie sich an einen der Edge-Server, starten Sie den Bereitstellungs-Assistenten, und klicken Sie auf **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten, klicken Sie auf Ausführen** (oder **Erneut ausführen**, wenn Sie dieses Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.
    
&nbsp;&nbsp;&nbsp;c. Stellen Sie sicher, dass auf der Seite **Zertifikatsanforderung** die Option **Externes Edgezertifikat** ausgewählt ist und klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.
    
&nbsp;&nbsp;&nbsp;e. Geben Sie auf der Seite **Zertifikatsanforderungsdatei** den vollständigen Pfad und Dateinamen an, um zu bestimmen, wo die Datei gespeichert wird (z. B. c:\SkypeInternalEdgeCert.cer). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage „WebServer“ zu verwenden.
    
&nbsp;&nbsp;&nbsp;g. Führen Sie auf der Seite  Namens- und Sicherheitseinstellungen  die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein (z. B. „Externer Edgeserver“.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Wählen Sie unter **Bitlänge** die Bitlänge aus (Standard ist 2048, sie können diesen Wert zur Sicherheit erhöhen, dies verlangsamt jedoch die Leistung).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktivieren.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit (OE) ein. Sie können den Geschäftsbereich oder die Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;Ich. Geben Sie auf der Seite **Geografische Informationen** die Angaben zum Standort ein.
    
&nbsp;&nbsp;&nbsp;j. Auf der Seite **Antragstellernamen/Alternative Antragstellernamen** sollten die erforderlichen Informationen automatisch vom Assistenten aufgefüllt werden.
    
&nbsp;&nbsp;&nbsp;k. Klicken Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen (SANs)** das Kontrollkästchen Sie Domäne um eine Sip hinzuzufügen.<sipdomain> -Eintrag, um der Liste alternative Antragstellernamen.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** alle erforderlichen zusätzlichen alternativen Antragstellernamen an.
    
&nbsp;&nbsp;&nbsp;m. Suchen Sie auf der Seite **Zusammenfassung der Anforderung** über die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden soll. Wenn Änderungen nötig sind, gehen Sie zurück und führen Sie diese jetzt aus.
    
&nbsp;&nbsp;&nbsp;n. Wenn Sie bereit sind, klicken Sie auf **Weiter** , um die CSR-Datei zu generieren, die Sie benötigen, an der Zertifizierungsstelle übermitteln (Sie können auch **Protokoll anzeigen** , um das Protokoll für die zertifikatanforderung betrachten klicken).
    
&nbsp;&nbsp;&nbsp;o. Sobald die Anforderung generiert wurde, können Sie auf **Anzeigen** klicken, um das Zertifikat anzuzeigen, und auf **Fertig stellen**, um das Fenster zu schließen. Der Inhalt der CSR-Datei muss der Zertifizierungsstelle vorgelegt werden, damit diese ein Zertifikat erstellen kann, das Sie zu diesen Computer importieren müssen (siehe nächster Abschnitt).
    
&nbsp;&nbsp;&nbsp;p. (OPTIONAL) Eventuell werden Sie bei der Übermittlung der Inhalte von CSR nach bestimmten Informationen gefragt, wie z. B. Folgendes (es gibt viele Unterschiede zwischen den Zertifizierungsstellen, eventuell ist dies also nicht erforderlich):
    
  - **Microsoft** als Serverplattform
    
  - **IIS** als Version
    
  - **Web Server** als Verwendungstyp
    
  - **PKCS7** als Antwortformat
    
 
### <a name="2-import-the-certificate"></a>2. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Melden Sie sich, als Mitglied der lokalen Gruppe Administratoren auf den Edge-Server, die Sie in der letzten Prozedur aus der zertifikatanforderung vorgenommen.
    
&nbsp;&nbsp;&nbsp;b. Der Bereitstellungs-Assistenten neben Schritt 3 **. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **Erneut ausführen**.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie auf der Seite **Verfügbare Zertifikatsaufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie im vorhergehenden Abschnitt erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen). Wenn Ihr Zertifikat einen privaten Schlüssel enthält, stellen Sie sicher, dass Sie die **Zertifikatdatei enthält den privaten Schlüssel des Zertifikats**wählen Sie aus, und geben Sie das Kennwort für den privaten Schlüssel. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zertifikatzusammenfassung importieren** die zusammenfassenden Informationen und klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite **Befehle ausführen** können Sie das Ergebnis des Imports überprüfen, wenn er abgeschlossen ist, indem Sie auf **Protokoll anzeigen**. Klicken Sie zum Abschließen des Zertifikatimports auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Wenn Sie andere Edge-Server in einem Pool verfügen, müssen Sie auch die folgenden beiden Verfahren befolgen. Dies ist eine eigenständige Edge-Server fertig Sie Zertifikate für externe Benutzer.
    
 
### <a name="3-export-the-certificate"></a>3. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Stellen Sie sicher, dass Sie auf dem Edge-Server angemeldet haben Sie das Zertifikat als lokaler Administrator importiert haben.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf **Start**, **Ausführen** (oder **Suche** öffnen), und geben Sie **MMC**ein.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Snap-In-Dialogfeld **Zertifikate** die Option **Computerkonto**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)**. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**, um die Konfiguration der MMC-Konsole abzuschließen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. **Doppelklicken Sie auf Eigene Zertifikate** und klicken Sie dann auf **Zertifikate**.
    
   > [!NOTE]
   > Sie hier möglicherweise, und alle Zertifikate in die eigene Zertifikate für den lokalen Computer nicht angezeigt. Sie müssen nicht Sammelanschlüssen, wenn der Schlüssel nicht vorhanden, die importierten's nicht Zertifikat einen privaten Schlüssel zugeordnet haben. Wiederholen Sie die Anforderung und Schritte noch einmal importieren, und wenn Sie sicher, dass Sie alle diese richtig sind, wenden Sie sich an den Zertifizierungsstellen-Administrator oder vom Anbieter. 
  
&nbsp;&nbsp;&nbsp;h. **Speichern Sie eigene Zertifikate** für den lokalen Computer mit der Maustaste des Zertifikats, das Sie exportieren. **Wählen Sie alle Aufgaben** im eingeblendeten Menü, und klicken Sie dann auf **Exportieren**.
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im **Zertifikatexport-Assistenten**auf **Weiter**. Wählen Sie **Ja, privaten Schlüssel exportieren**aus. Klicken Sie auf **Weiter**.
    
   > [!NOTE]
   > Wenn **Ja, privaten Schlüssel exportieren** nicht verfügbar ist, wurde nicht der private Schlüssel für dieses Zertifikat für den Export markiert, bevor Sie das richtige für Sie. Sie müssen das Zertifikat erneut beim Anbieter anfordern und den privaten Schlüssel auf Export einstellen, bevor Sie dieses Verfahren erfolgreich ausführen können.
  
&nbsp;&nbsp;&nbsp;j. Wählen Sie im Dialogfeld „Format der zu exportierenden Datei“ die Option „Privater Informationsaustausch – PKCS#12 (.PFX)“ aus. Wählen Sie dann Folgendes aus:
    
 &nbsp;&nbsp;&nbsp;Ich. Beziehen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
 &nbsp;&nbsp;&nbsp;II. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen Sie **NIE** die Option **Privaten Schlüssel nach erfolgreichem Export löschen** aus. Es werden bedeutet, dass Sie zum Importieren des Zertifikats und privaten Schlüssel wieder mit diesem Edgeserver verfügen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein und klicken Sie dann auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung **.pfx** verwenden. Der Pfad muss entweder den anderen Edge-Servern im Pool zugänglich sein, oder müssen Sie die Datei über externe Medien (beispielsweise ein USB-Laufwerk) zu verschieben. Wenn Sie Ihre Auswahl getroffen haben, klicken Sie auf **Weiter** .
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Zertifikatexport-Assistenten** und klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.
    
&nbsp;&nbsp;&nbsp;o. Sie müssen nun wechseln wieder zum Importieren im Abschnitt Zertifikat, bevor Sie diese und importieren Sie das Zertifikat für alle verbleibenden Edgeserver, und klicken Sie dann fortsetzen zuweisen, darunter.
    
 
### <a name="4-assign-the-certificate"></a>4. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;ein. Klicken Sie auf **EACH** Edgeserver im Bereitstellungs-Assistenten neben Schritt 3 **. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **erneut ausführen**.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste **Externer Edge** .
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat, das Sie für den externen Rand (aus dem vorherigen Abschnitt) importiert haben.
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen und klicken Sie dann auf **Weiter**, um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Wenn Sie dieses Verfahren abgeschlossen haben, ist es eine gute Wahl, öffnen Sie das Zertifikat-MMC-Snap-in auf jedem Server, den Knoten **Zertifikate (lokaler Computer)**, erweitern **Persönlich**, klicken Sie auf **Zertifikate**und bestätigen Sie, dass die interne Schnittstelle das Zertifikat wird im Detailbereich aufgeführt.
    
   > [!NOTE]
   > Sie müssen außerdem die Zertifikate für die Reverseproxyserver eingerichtet haben. 
  
## <a name="starting-the-edge-servers"></a>Starten Sie die Edge-Server

Nachdem die Installation abgeschlossen ist, müssen Sie die Dienste auf jedem Edgeserver in Ihrer Bereitstellung zu starten:
  
1. Klicken Sie auf jedem Edgeserver im **Bereitstellungs-Assistenten**neben **Schritt 4: Dienste starten**, klicken Sie auf **Ausführen**.
    
2. Klicken Sie auf der Seite **Skype für Business Server-Dienste starten** überprüfen Sie die Liste der Dienste, und klicken Sie dann auf **Weiter** , um die Dienste zu starten.
    
3. Klicken Sie nach dem Starten der Dienste auf **Fertig stellen**, um den Assistenten zu schließen.
    
4. (Optional) Klicken Sie unter **Schritt 4: Dienste starten** auf **Dienststatus**.
    
5.  In der **MMC Dienste** auf jedem Server stellen Sie sicher, dass alle Skype für Business Server-Dienste ausgeführt werden.
    

