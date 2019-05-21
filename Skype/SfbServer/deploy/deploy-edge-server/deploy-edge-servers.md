---
title: Bereitstellen von Edgeserver in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server-Umgebung bereitstellen.'
ms.openlocfilehash: b8b55d4aea048faeb4bb8bda3cc0bd17f89f9f66
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306916"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Bereitstellen von Edgeserver in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server-Umgebung bereitstellen.
  
Die folgenden Abschnitte enthalten Schritte, die befolgt werden sollten, nachdem der Skype for Business Server- [Plan für Edge-Server-Bereitstellungen in der Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) -Dokumentation überprüft wurde. Es handelt sich um die folgenden Bereitstellungsschritte:
  
- Netzwerkschnittstellen
    
- Installation
    
- Zertifikate
    
- Starten der Edgeserver
    
## <a name="network-interfaces"></a>Netzwerkschnittstellen

Wie in Planung beschrieben, konfigurieren Sie entweder Ihre Netzwerkschnittstelle mit DNS im Umkreisnetzwerk, das Ihre Edgeserver hostet, oder ohne DNS im Umkreisnetzwerk.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration mit DNS-Servern im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die Schnittstelle mit externen Anschlüssen.
    
    > [!NOTE]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine** der folgenden Optionen:
    
   a. Konfiguration von drei statischen IP-Adressen im externen Subnetz des Umkreisnetzwerks und Verweis des Standardgateways auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf ein DNS-Umkreisserverpaar verweisen.
    
   b. Eine statische IP-Adresse im Subnetz des externen Umkreisnetzwerks, und zeigen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf ein DNS-Umkreisserverpaar verweisen. Diese Konfiguration ist nur akzeptabel, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass Sie nicht Standardwerte in den Portzuordnungen hat, die im Artikel [Erstellen Ihrer Edge-Topologie für Skype for Business Server](create-your-edge-topology.md) behandelt werden.
    
3. Konfigurieren Sie auf Ihrer internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway ein. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese mindestens auf einen DNS-Server, jedoch vorzugsweise auf ein DNS-Umkreisserverpaar, verweisen.
    
4. Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, auf denen sich Clients, Skype for Business Server und Exchange Unified Messaging (um)-Server befinden.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration ohne DNS-Server im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne Schnittstelle und einen für die Schnittstelle mit externen Anschlüssen.
    
    > [!NOTE]
    > Ein Routing vom internen Subnetz zum externen Subnetz (und umgekehrt) darf nicht möglich sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine** der folgenden Optionen:
    
   a. Konfiguration von drei statischen IP-Adressen im externen Subnetz des Umkreisnetzwerks. Außerdem müssen Sie das Standardgateway auf der externen Schnittstelle konfigurieren, beispielsweise das Definieren des mit dem Internet versehenen Routers oder der externen Firewall als Standardgateway. Konfigurieren Sie die DNS-Einstellungen des Netzwerkadapters so, dass diese auf einen externen DNS-Server, vorzugsweise auf ein externes DNS-Serverpaar, verweisen.
    
   b. Eine statische IP-Adresse im Subnetz des externen Umkreisnetzwerks. Außerdem müssen Sie das Standardgateway auf der externen Schnittstelle konfigurieren, beispielsweise das Definieren des mit dem Internet versehenen Routers oder der externen Firewall als Standardgateway. Konfigurieren Sie die DNS-Adaptereinstellungen so, dass Sie auf einen externen DNS-Server oder im Idealfall auf ein paar externer DNS-Server verweisen. Diese Konfiguration ist nur akzeptabel, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass Sie nicht Standardwerte in den Portzuordnungen hat, die im Artikel [Erstellen Ihrer Edge-Topologie für Skype for Business Server](create-your-edge-topology.md) behandelt werden.
    
3. Konfigurieren Sie auf Ihrer internen Schnittstelleeine statische IP-Adresse im Subnetz des internen Umkreisnetzwerks, und legen Sie kein Standardgateway ein. Lassen Sie außerdem die DNS-Einstellungen des Netzwerkadapters leer.
    
4. Erstellen Sie persistente statische Routen auf der internen Schnittstelle für alle internen Netzwerke, auf denen sich Clients, Skype for Business Server und Exchange Unified Messaging (um)-Server befinden.
    
5. Bearbeiten Sie die Hostdatei auf jedem Edgeserver, um einen Eintrag für den Server für den nächsten Hop oder für Virtual IP (VIP) zu enthalten. Bei diesem Eintrag handelt es sich um den Director, Standard Edition-Server oder Front-End-Pool, den Sie im Topologie-Generator als Adresse für den Edge-Server-nächsten Hop konfiguriert haben. Wenn Sie den DNS-Lastenausgleich verwenden, schließen Sie eine Zeile für jedes Mitglied des nächsten Hop-Pools ein.
    
## <a name="installation"></a>Installation

Damit Sie diese Schritte erfolgreich ausführen können, müssen Sie die Schritte im Artikel [Erstellen Ihrer Edge-Topologie für Skype for Business Server](create-your-edge-topology.md) befolgt haben.
  
1. Melden Sie sich bei dem Server an, den Sie für die Edge-Serverrolle konfiguriert haben, mit einem Konto, das sich in der Gruppe des lokalen Administrators befindet.
    
2. Sie benötigen die Topologie-Konfigurationsdatei, die Sie am Ende der Dokumentation zur Edge-Server-Topologie auf diesem Computer kopiert haben. Greifen Sie auf den externen Datenträger zu, auf dem Sie die Konfigurationsdatei gespeichert haben (z. B. ein USB-Laufwerk oder eine Netzwerkfreigabe).
    
3. Starten Sie den Bereitstellungs- **Assistenten**.
    
4. Klicken Sie nach dem Öffnen des Assistenten auf **Skype for Business Server System installieren oder aktualisieren**.
    
5. Der Assistent führt Prüfungen aus, um festzustellen, ob bereits etwas installiert ist. Da dies das erste Mal ist, dass der Assistent ausgeführt wird, sollten Sie mit **Schritt 1 beginnen. Installieren Sie den lokalen Konfigurationsspeicher.**
    
6. Das Dialogfeld **lokales Replikat des zentralen Verwaltungsspeichers konfigurieren** wird angezeigt. Sie müssen auf **aus einer Datei importieren (für Edgeserver empfohlen)** klicken.
    
7. Gehen Sie von hier aus zum Speicherort der Topologie, die Sie zuvor exportiert haben. Wählen Sie die ZIP-Datei aus, klicken Sie auf **Öffnen** und anschließend auf **Weiter**.
    
8. Der Bereitstellungs-Assistent liest die Konfigurationsdatei und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
9. Nachdem der Prozess **Befehle werden ausgeführt** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie im Bereitstellungs-Assistenten auf **Schritt 2. Einrichten oder Entfernen von Skype for Business Server-Komponenten**. Der Assistent installiert dann die Edge-Komponenten von Skype for Business Server, die in der XML-Konfigurationsdatei angegeben sind, die auf dem lokalen Computer gespeichert ist.
    
11. Nachdem die Installation abgeschlossen ist, können Sie die Schritte im Abschnitt **Zertifikate** weiter unten ausführen.
    
## <a name="certificates"></a>Zertifikate

Die Zertifikatanforderungen für den Edgeserver finden Sie in der Dokumentation zur Edge-Zertifikatplanung. Die erforderlichen Schritte zur Einrichtung von Zertifikaten finden Sie unten.
  
> [!NOTE]
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie als Konto mit den richtigen Berechtigungen für den Typ der Zertifikatvorlage angemeldet sein, die Sie verwenden werden. Standardmäßig wird für eine Skype for Business Server-Zertifikatanforderung die Vorlage Webserverzertifikat verwendet. Wenn Sie mit einem Konto angemeldet sind, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat über diese Vorlage anzufordern, überprüfen Sie, ob der Gruppe die Registrierungsberechtigungen für die Verwendung dieser Vorlage zugewiesen wurden. 
  
### <a name="internal-edge-interface-certificates"></a>Zertifikate der internen Edgeschnittstelle

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. herunterladen oder Exportieren der Zertifizierungsstellen Zertifizierungsstelle

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;eine. Download mit CertSrv-Website

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Melden Sie sich bei einem Skype for Business-Server in Ihrem internen Netzwerk als Mitglied der lokalen Administratorengruppe an.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Öffnen Sie **Start**, und **führen** Sie (oder **Suchen** und **Ausführen** ) aus, und geben Sie Folgendes ein:
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Zum Beispiel:
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Klicken Sie auf der certsrv-Webseite der ausstellenden Zertifizierungsstelle unter **Aufgabe auswählen**auf Zertifizierungsstellen **Zertifikat, Zertifikatkette oder CRL Herunterladen**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Klicken Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatssperrliste** auf **Download der Zertifizierungsstellen-Zertifikatkette**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Klicken Sie im Feld **Dateidownload** auf **Speichern**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Speichern Sie die P7B-Datei auf dem Festplattenlaufwerk auf dem Server, und kopieren Sie Sie dann in einen Ordner auf jedem ihrer Edgeserver.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Export mit MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Sie können das Stammzertifikat der Zertifizierungsstelle mithilfe von MMC von einem beliebigen Computer in der Domäne aus exportieren. Gehen Sie entweder zu **Starten** und **Ausführen** oder öffnen Sie **Suchen** und geben Sie **MMC** ein, um die Funktion zu öffnen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Wählen Sie in der Dialogliste **Snap-Ins hinzufügen oder entfernen** die Option **Zertifikate**aus, und klicken Sie dann auf **Hinzufügen**. Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**und dann **weiter**aus. Wählen Sie im Dialogfeld **Computer auswählen** die Option **lokaler Computer**aus. Klicken Sie auf **Fertig stellen**und dann auf **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Erweitern Sie **Zertifikate (lokaler Computer)**. Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**. Wählen Sie **Zertifikate**aus.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie im Menü **Alle Aufgaben** und anschließend **Exportieren** aus.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Der **Zertifikatexport-Assistent** wird geöffnet. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** ein Format für den Export aus. Wir empfehlen die Verwendung von **Syntaxstandard kryptografischer Meldungen – PKCS #7-Zertifikate (P7B)**. Wenn das auch Ihre Wahl ist, denken Sie daran, das Kontrollkästchen **alle Zertifikate in den Zertifizierungspfad einbeziehen** zu aktivieren, da dadurch auch die Zertifikatkette exportiert wird, einschließlich des Stammzertifizierungsstellenzertifikats und aller Zwischenzertifikate. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Geben Sie im Dialogfeld **Zu exportierende Datei** im Eingabefeld für den Dateinamen einen Pfad und Dateinamen (die Standarderweiterung lautet „.p7b“) für das exportierte Zertifikat ein. Wenn es Ihnen leichter fällt, wählen Sie die Schaltfläche **Durchsuchen** aus, um zu dem Speicherort zu wechseln, in dem das exportierte Zertifikat gespeichert werden soll, und benennen Sie das exportierte Zertifikat hier. Klicken Sie auf **Speichern**und dann auf **weiter** , wenn Sie fertig sind.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Überprüfen Sie die Zusammenfassung der von Ihnen ausgeführten Aktionen und klicken Sie auf **Fertig stellen**, um den Zertifikatexport abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Kopieren Sie die P7B-Datei auf jeden Ihrer Edge-Server.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importieren der Zertifizierungsstellen Zertifizierungsstelle

&nbsp;&nbsp;&nbsp;eine. Öffnen Sie auf jedem Edgeserver die MMC (Wählen Sie **Start** und **Ausführen**oder **Suchen**aus, und geben Sie **MMC** zum Öffnen ein).
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und wählen Sie dann **Hinzufügen** aus.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und anschließend auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;e. Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist. Klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf **Schließen** und dann auf **OK**.
    
&nbsp;&nbsp;&nbsp;g. Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen**, gehen Sie zu **Alle Aufgaben** und klicken Sie dann auf **Importieren**.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie im Textfeld **Zu importierende Datei** des Assistenten, der geöffnet wird, den Namen des Zertifikats ein (die Benennung der P7B-Datei, die Sie im vorhergehenden Abschnitt ausgewählt haben). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;Ich. Aktivieren Sie das Optionsfeld **Alle Zertifikate in folgendem Speicher speichern, Vertrauenswürdige Stammzertifizierungsstellen**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Überprüfen Sie die Zusammenfassung und klicken Sie auf **Fertig stellen**, um den Import abzuschließen.
    
&nbsp;&nbsp;&nbsp;k. Dies muss für jeden Edgeserver erfolgen, der bereitgestellt wird.
    
### <a name="3-create-the-certificate-request"></a>3. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;eine. Melden Sie sich bei einem ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen** (oder **erneut ausführen**, wenn Sie diesen Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;b. Stellen Sie sicher, dass auf der Seite **Zertifikatsanforderung** die Option **Internes Edgezertifikat** ausgewählt ist und klicken Sie auf **Anforderung**.
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **verzögerte oder unmittelbare Anforderungen** die Option **Senden Sie die Anforderung sofort an eine Onlinezertifizierungsstelle** aus, wenn Sie über Ihre Edge-Umgebung auf eine Person zugreifen oder **die Anforderung jetzt vorbereiten, aber später anderweitig senden** möchten.
    
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
    
&nbsp;&nbsp;&nbsp;k. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Änderungen nötig sind, gehen Sie zurück und führen Sie diese jetzt aus.
    
&nbsp;&nbsp;&nbsp;l. Klicken Sie dann auf **weiter** , um die CSR-Datei zu generieren, die Sie der Zertifizierungsstelle zur Verfügung stellen müssen (Sie können auch auf **Protokoll anzeigen** klicken, um das Protokoll für die Zertifikatanforderung anzuzeigen).
    
&nbsp;&nbsp;&nbsp;m. Sobald die Anforderung generiert wurde, können Sie auf **Anzeigen** klicken, um das Zertifikat anzuzeigen, und auf **Fertig stellen**, um das Fenster zu schließen. Der Inhalt der CSR-Datei muss der Zertifizierungsstelle vorgelegt werden, damit diese ein Zertifikat erstellen kann, das Sie zu diesen Computer importieren müssen (siehe nächster Abschnitt).
    

### <a name="4-import-the-certificate"></a>4. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Melden Sie sich als Mitglied der lokalen Gruppe Administratoren an dem Edgeserver an, aus dem Sie Ihre Zertifikatanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;b. Im Bereitstellungs-Assistenten neben **Schritt 3. Wenn Sie Zertifikate anfordern, installieren oder zuweisen**möchten, klicken Sie **erneut auf Ausführen**.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie auf der Seite **Verfügbare Zertifikatsaufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie im vorhergehenden Abschnitt erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen).
    
&nbsp;&nbsp;&nbsp;e. Wenn Sie Zertifikate für andere Mitglieder Ihres Edge-Pools importieren und Ihr Zertifikat einen privaten Schlüssel enthält, stellen Sie sicher, dass Sie das Kontrollkästchen **Zertifikatsdatei mit dem privaten Schlüssel des Zertifikats** auswählen, und geben Sie das Kennwort ein. Klicken Sie auf **Weiter**, um fortzufahren.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite**Zusammenfassung** auf **weiter** , nachdem Sie die Informationen bestätigt haben, und **Beenden** Sie den Vorgang, nachdem das Zertifikat erfolgreich importiert wurde.
    
 
### <a name="5-export-the-certificate"></a>5. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Stellen Sie sicher, dass Sie sich auf dem Edgeserver angemeldet haben, in den Sie das Zertifikat zuvor importiert haben, als Mitglied der lokalen Gruppe Administratoren.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf **Start**, **Ausführen** (oder **Suche** öffnen), und geben Sie **MMC**ein.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole auf **Datei** und auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Snap-In-Dialogfeld **Zertifikate** die Option **Computerkonto**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)**. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**, um die Konfiguration der MMC-Konsole abzuschließen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **Eigene Zertifikate** und klicken Sie dann auf **Zertifikate**.
    
  > [!NOTE]
  > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Zertifikatspeicher für den lokalen Computer angezeigt. Sie müssen nicht herum jagen, wenn der Schlüssel nicht vorhanden ist, dem importierten Zertifikat war kein privater Schlüssel zugeordnet. Testen Sie die Schritte zum Anfordern und Importieren noch einmal, und wenn Sie sicher sind, dass Sie alles richtig verstanden haben, sprechen Sie mit Ihrem CA-Administrator oder-Anbieter. 
  
&nbsp;&nbsp;&nbsp;h. Klicken Sie im **persönlichen Zertifikatspeicher** des lokalen Computers mit der rechten Maustaste auf das Zertifikat, das Sie exportieren möchten. Wählen Sie im daraufhin angezeigten Menü **alle Aufgaben** aus, und klicken Sie dann auf **exportieren**.
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im **Zertifikat Export-Assistenten**auf **weiter**. Wählen Sie **Ja aus, exportieren Sie den privaten Schlüssel**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** die Option **Privater Informationsaustausch – PKCS#12 (.PFX)** aus. Wählen Sie dann Folgendes aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Ich. Beziehen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen Sie **NIE** die Option **Privaten Schlüssel nach erfolgreichem Export löschen** aus. Das bedeutet, dass Sie das Zertifikat und den privaten Schlüssel wieder auf diesen Edge-Server importieren müssen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein und klicken Sie dann auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung **.pfx** verwenden. Der Pfad muss entweder von den anderen Edgeserver im Pool zugänglich sein, oder Sie müssen die Datei mithilfe externer Medien (wie einem USB-Laufwerk) verschieben. Klicken Sie auf **weiter** , wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Zertifikatexport-Assistenten** und klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.
    
 
### <a name="6-assign-the-certificate"></a>6. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3. Wenn Sie Zertifikate anfordern, installieren oder zuweisen**möchten, klicken Sie **erneut auf Ausführen**.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Interner Edgeserver** aus.
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie für den internen Edge importiert haben (im vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen und klicken Sie dann auf **Weiter**, um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Nachdem Sie dieses Verfahren abgeschlossen haben, empfiehlt es sich, das MMC-Snap-in Zertifikate auf jedem Edgeserver zu öffnen, **Zertifikate (lokaler Computer)** zu erweitern, **Personal**zu erweitern, auf **Zertifikate**zu klicken und zu bestätigen, dass der interne Edge das Zertifikat wird im Detailbereich aufgelistet.
    
### <a name="external-edge-interface-certificates"></a>Zertifikate der externen Edgeschnittstelle

 
### <a name="1-create-the-certificate-request"></a>1. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;eine. Melden Sie sich bei einem ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten auf Ausführen** (oder **erneut ausführen**, wenn Sie diesen Assistenten bereits ausgeführt haben).
    
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
    
&nbsp;&nbsp;&nbsp;k. Aktivieren Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** das Kontrollkästchen Domäne, um einen SIP hinzuzufügen.<sipdomain> Eintrag in die Liste der alternativen Subjektnamen.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** alle erforderlichen zusätzlichen alternativen Antragstellernamen an.
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Änderungen nötig sind, gehen Sie zurück und führen Sie diese jetzt aus.
    
&nbsp;&nbsp;&nbsp;n. Wenn Sie fertig sind, klicken Sie auf **weiter** , um die CSR-Datei zu generieren, die Sie der Zertifizierungsstelle zur Verfügung stellen müssen (Sie können auch auf **Protokoll anzeigen** klicken, um das Protokoll für die Zertifikatanforderung anzuzeigen).
    
&nbsp;&nbsp;&nbsp;o. Sobald die Anforderung generiert wurde, können Sie auf **Anzeigen** klicken, um das Zertifikat anzuzeigen, und auf **Fertig stellen**, um das Fenster zu schließen. Der Inhalt der CSR-Datei muss der Zertifizierungsstelle vorgelegt werden, damit diese ein Zertifikat erstellen kann, das Sie zu diesen Computer importieren müssen (siehe nächster Abschnitt).
    
&nbsp;&nbsp;&nbsp;p. (OPTIONAL) Eventuell werden Sie bei der Übermittlung der Inhalte von CSR nach bestimmten Informationen gefragt, wie z. B. Folgendes (es gibt viele Unterschiede zwischen den Zertifizierungsstellen, eventuell ist dies also nicht erforderlich):
    
  - **Microsoft** als Serverplattform
    
  - **IIS** als Version
    
  - **Web Server** als Verwendungstyp
    
  - **PKCS7** als Antwortformat
    
 
### <a name="2-import-the-certificate"></a>2. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Melden Sie sich als Mitglied der lokalen Gruppe Administratoren an dem Edgeserver an, aus dem Sie Ihre Zertifikatanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;b. Im Bereitstellungs-Assistenten neben **Schritt 3. Wenn Sie Zertifikate anfordern, installieren oder zuweisen**möchten, klicken Sie **erneut auf Ausführen**.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie auf der Seite **Verfügbare Zertifikatsaufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie im vorhergehenden Abschnitt erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen). Wenn Ihr Zertifikat einen privaten Schlüssel enthält, stellen Sie sicher, dass **Zertifikatsdatei den privaten Schlüssel des Zertifikats enthält**, und geben Sie das Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort für den privaten Schlüssel ein und klicken Sie auf **Weiter**, wenn Sie fertig sind.
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zertifikatzusammenfassung importieren** die zusammenfassenden Informationen und klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Auf der Seite **Ausführungsbefehle** können Sie das Ergebnis des Imports überprüfen, wenn es abgeschlossen ist, indem Sie auf **Protokoll anzeigen**klicken. Klicken Sie zum Abschließen des Zertifikatimports auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Wenn Sie andere Edgeserver in einem Pool haben, müssen Sie auch die beiden folgenden Verfahren befolgen. Wenn es sich um einen Standalone-Edgeserver handelt, sind externe Zertifikate fertig.
    
 
### <a name="3-export-the-certificate"></a>3. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Stellen Sie sicher, dass Sie sich beim Edgeserver, auf den Sie das Zertifikat importiert haben, als lokaler Administrator angemeldet haben.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf **Start**, **Ausführen** (oder **Suche** öffnen), und geben Sie **MMC**ein.
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Feld **Snap-In hinzufügen/entfernen** auf **Zertifikate** und auf **Hinzufügen**.
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Snap-In-Dialogfeld **Zertifikate** die Option **Computerkonto**. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)**. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**, um die Konfiguration der MMC-Konsole abzuschließen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. **Doppelklicken Sie auf Eigene Zertifikate** und klicken Sie dann auf **Zertifikate**.
    
   > [!NOTE]
   > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Zertifikatspeicher für den lokalen Computer angezeigt. Sie müssen nicht herum jagen, wenn der Schlüssel nicht vorhanden ist, dem importierten Zertifikat war kein privater Schlüssel zugeordnet. Testen Sie die Schritte zum Anfordern und Importieren noch einmal, und wenn Sie sicher sind, dass Sie alles richtig verstanden haben, sprechen Sie mit Ihrem CA-Administrator oder-Anbieter. 
  
&nbsp;&nbsp;&nbsp;h. Klicken Sie im **persönlichen Zertifikatspeicher** des lokalen Computers mit der rechten Maustaste auf das Zertifikat, das Sie exportieren möchten. **Wählen Sie** im daraufhin angezeigten Menü alle Aufgaben aus, und klicken Sie dann auf **exportieren**.
    
&nbsp;&nbsp;&nbsp;Ich. Klicken Sie im **Zertifikat Export-Assistenten**auf **weiter**. Wählen Sie **Ja aus, exportieren Sie den privaten Schlüssel**. Klicken Sie auf **Weiter**.
    
   > [!NOTE]
   > Wenn **Ja, den privaten Schlüssel nicht exportieren** , ist der private Schlüssel für dieses Zertifikat nicht für den Export markiert, bevor Sie ihn erhalten haben. Sie müssen das Zertifikat erneut beim Anbieter anfordern und den privaten Schlüssel auf Export einstellen, bevor Sie dieses Verfahren erfolgreich ausführen können.
  
&nbsp;&nbsp;&nbsp;j. Wählen Sie im Dialogfeld „Format der zu exportierenden Datei“ die Option „Privater Informationsaustausch – PKCS#12 (.PFX)“ aus. Wählen Sie dann Folgendes aus:
    
 &nbsp;&nbsp;&nbsp;Ich. Beziehen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
 &nbsp;&nbsp;&nbsp;II. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > Wählen Sie **NIE** die Option **Privaten Schlüssel nach erfolgreichem Export löschen** aus. Das bedeutet, dass Sie das Zertifikat und den privaten Schlüssel wieder auf diesen Edge-Server importieren müssen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein und klicken Sie dann auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung **.pfx** verwenden. Der Pfad muss entweder von den anderen Edgeserver im Pool zugänglich sein, oder Sie müssen die Datei mithilfe externer Medien (wie einem USB-Laufwerk) verschieben. Klicken Sie auf **weiter** , wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Zertifikatexport-Assistenten** und klicken Sie dann auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.
    
&nbsp;&nbsp;&nbsp;o. Sie müssen nun zurück zum Abschnitt "Zertifikat importieren" wechseln, bevor Sie das Zertifikat auf alle verbleibenden Edgeserver importieren und dann weiter unten die Zuweisung fortsetzen.
    
 
### <a name="4-assign-the-certificate"></a>4. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;eine. Klicken Sie auf **jedem** Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3. Wenn Sie Zertifikate anfordern, installieren oder zuweisen**möchten, klicken Sie **erneut auf Ausführen**.
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **zertifikatzuweisung** in der Liste den Eintrag **Edge External** aus.
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie für den externen Edge importiert haben (im vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen und klicken Sie dann auf **Weiter**, um das Zertifikat zuzuweisen.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Nachdem Sie dieses Verfahren abgeschlossen haben, empfiehlt es sich, das MMC-Snap-in Zertifikate auf jedem Server zu öffnen, **Zertifikate (lokaler Computer)** zu erweitern, **Personal**zu erweitern, auf **Zertifikate**zu klicken und zu bestätigen, dass der interne Edge das Zertifikat wird im Detailbereich aufgelistet.
    
   > [!NOTE]
   > Sie müssen außerdem die Zertifikate für die Reverseproxyserver eingerichtet haben. 
  
## <a name="starting-the-edge-servers"></a>Starten der Edgeserver

Nachdem die Einrichtung abgeschlossen ist, müssen Sie die Dienste auf jedem Edgeserver in Ihrer Bereitstellung starten:
  
1. Klicken Sie auf jedem Edgeserver im **Bereitstellungs-Assistenten**neben **Schritt 4: Dienste starten**auf **Ausführen**.
    
2. Überprüfen Sie auf der Seite **Skype for Business Server-Dienste starten** die Liste der Dienste, und klicken Sie dann auf **weiter** , um die Dienste zu starten.
    
3. Klicken Sie nach dem Starten der Dienste auf **Fertig stellen**, um den Assistenten zu schließen.
    
4. (Optional) Klicken Sie unter **Schritt 4: Dienste starten** auf **Dienststatus**.
    
5.  Überprüfen Sie in der **Dienste-MMC** auf den einzelnen Servern, ob alle Skype for Business Server-Dienste ausgeführt werden.
    

