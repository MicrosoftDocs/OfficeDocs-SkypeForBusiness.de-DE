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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Zusammenfassung: Erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server-Umgebung bereitstellen.'
ms.openlocfilehash: 8e23e157d4eb86f5b3d2bd5fa3ab3a54fd8aadc8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804375"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Bereitstellen von Edgeservern in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Edgeserver in Ihrer Skype for Business Server-Umgebung bereitstellen.
  
Die folgenden Abschnitte enthalten Schritte, die ausgeführt werden sollen, nachdem die Dokumentation zum Skype for Business Server [Plan für Edgeserverbereitstellungen in Skype for Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) überprüft wurde. Die Bereitstellungsschritte sind wie folgt:
  
- Netzwerkschnittstellen
    
- Installation
    
- Zertifikate
    
- Starten der Edgeserver
    
## <a name="network-interfaces"></a>Netzwerkschnittstellen

Wie bereits in der Planung erwähnt, konfigurieren Sie Entweder Ihre Netzwerkschnittstelle mit DNS im Umkreisnetzwerk, das Ihre Edgeserver hosten soll, oder ohne DNS im Umkreisnetzwerk.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration mit DNS-Servern im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne schnittstelle und einen für die externe Schnittstelle.
    
    > [!NOTE]
    > Die internen und externen Subnetze dürfen nicht miteinander routingfähig sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine der** folgenden Optionen:
    
   a. Drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks, und verweisen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass sie auf ein Umkreis-DNS-Serverpaar verweisen.
    
   b. Eine statische IP-Adresse im Subnetz des externen Umkreisnetzwerks, und verweisen Sie das Standardgateway auf die interne Schnittstelle der externen Firewall. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass sie auf ein Umkreis-DNS-Serverpaar verweisen. Diese Konfiguration ist NUR akzeptabel, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass sie nicht standardmäßige Werte in den Portzuweisungen enthält. Dies wird im Artikel "Erstellen Ihrer Edgetopologie für [Skype for Business Server"](create-your-edge-topology.md) behandelt.
    
3. Konfigurieren Sie an der internen Schnittstelle eine statische IP im internen Subnetz des Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Konfigurieren Sie die Adaptor-DNS-Einstellungen so, dass sie auf mindestens einen DNS-Server, vorzugsweise jedoch auf ein Umkreis-DNS-Serverpaar, verweisen.
    
4. Erstellen Sie persistente statische Routen an der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, Skype for Business Server und Exchange Unified Messaging (UM)-Server befinden.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Schnittstellenkonfiguration ohne DNS-Server im Umkreisnetzwerk

1. Installieren Sie zwei Netzwerkadapter für jeden Edgeserver, einen für die interne schnittstelle und einen für die externe Schnittstelle.
    
    > [!NOTE]
    > Die internen und externen Subnetze dürfen nicht miteinander routingfähig sein. 
  
2. Auf Ihrer externen Schnittstelle konfigurieren Sie **eine der** folgenden Optionen:
    
   a. Drei statische IP-Adressen im Subnetz des externen Umkreisnetzwerks. Sie müssen auch das Standardgateway auf der externen Schnittstelle konfigurieren, z. B. den mit dem Internet verbundenen Router oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass sie auf einen externen DNS-Server verweisen, idealerweise auf ein Paar externer DNS-Server.
    
   b. Eine statische IP-Adresse im externen Subnetz des Umkreisnetzwerks. Sie müssen auch das Standardgateway auf der externen Schnittstelle konfigurieren, z. B. den mit dem Internet verbundenen Router oder die externe Firewall als Standardgateway definieren. Konfigurieren Sie die Adapter-DNS-Einstellungen so, dass sie auf einen externen DNS-Server oder im Idealfall auf ein Paar externer DNS-Server verweisen. Diese Konfiguration ist NUR akzeptabel, wenn Sie Ihre Topologie zuvor so konfiguriert haben, dass sie nicht standardmäßige Werte in den Portzuweisungen enthält. Dies wird im Artikel "Erstellen Ihrer Edgetopologie für [Skype for Business Server"](create-your-edge-topology.md) behandelt.
    
3. Konfigurieren Sie an der internen Schnittstelle eine statische IP im internen Subnetz des Umkreisnetzwerks, und legen Sie kein Standardgateway fest. Lassen Sie außerdem die Adapter-DNS-Einstellungen leer.
    
4. Erstellen Sie persistente statische Routen an der internen Schnittstelle zu allen internen Netzwerken, in denen sich Clients, Skype for Business Server und Exchange Unified Messaging (UM)-Server befinden.
    
5. Bearbeiten Sie die HOST-Datei auf jedem Edgeserver, um einen Eintrag für den nächsten Hopserver oder die virtuelle IP (VIP) zu enthalten. Dieser Eintrag ist der Director, Standard Edition-Server oder Front-End-Pool, den Sie als Adresse des nächsten Edgeservers im Topologie-Generator konfiguriert haben. Wenn Sie den DNS-Lastenausgleich verwenden, fügen Sie für jedes Mitglied des nächsten Hoppools eine Zeile ein.
    
## <a name="installation"></a>Installation

Um diese Schritte erfolgreich durchführen zu können, müssen Sie die Schritte im Artikel "Erstellen Ihrer [Edgetopologie für Skype for Business Server" ausgeführt](create-your-edge-topology.md) haben.
  
1. Melden Sie sich mit einem Konto in der lokalen Administratorgruppe bei dem Server an, den Sie für die Edgeserverrolle konfiguriert haben.
    
2. Sie benötigen die Topologiekonfigurationsdatei, die Sie am Ende der Edgeservertopologiedokumentation auf diesem Computer kopiert haben. Greifen Sie auf das externe Medium zu, auf dem Sie diese Konfigurationsdatei platziert haben (z. B. ein USB-Laufwerk oder eine Freigabe).
    
3. Starten Sie den **Bereitstellungs-Assistenten.**
    
4. Klicken Sie nach dem Öffnen des Assistenten auf "Skype for Business Server System installieren **oder aktualisieren".**
    
5. Der Assistent führt Überprüfungen aus, um zu überprüfen, ob bereits etwas installiert ist. Da der Assistent zum ersten Mal ausgeführt wird, sollten Sie mit Schritt **1 beginnen. Installieren Sie den lokalen Konfigurationsspeicher.**
    
6. Das **Dialogfeld "Lokales Replikat des zentralen Verwaltungsspeichers** konfigurieren" wird angezeigt. Sie müssen auf "Aus Datei **importieren" klicken (empfohlen für Edgeserver).**
    
7. Navigieren Sie hier zum Speicherort der Topologie, die Sie zuvor exportiert haben, wählen Sie die ZIP-Datei aus, klicken Sie auf "Öffnen" **und** dann auf **"Weiter".**
    
8. Der Bereitstellungsassistent liest die Konfigurationsdatei und schreibt die XML-Konfigurationsdatei auf den lokalen Computer.
    
9. Nachdem der Prozess **Befehle ausführen** abgeschlossen wurde, klicken Sie auf **Fertig stellen**.
    
10. Klicken Sie im Assistenten für die Bereitstellung auf **Schritt 2. Einrichten oder Entfernen von Skype for Business Server-Komponenten.** Der Assistent installiert dann die Skype for Business Server-Edgekomponenten, die in der auf dem lokalen Computer gespeicherten XML-Konfigurationsdatei angegeben sind.
    
11. Sobald die Installation abgeschlossen ist, können Sie mit den Schritten im Abschnitt **"Zertifikate"** weiter unten wechseln.
    
## <a name="certificates"></a>Zertifikate

Die Zertifikatanforderungen für den Edgeserver finden Sie in der Dokumentation zur Planung von Edgezertifikaten. Die Schritte zum Einrichten von Zertifikaten sind unten aufgeführt.
  
> [!NOTE]
> Beim Ausführen des Zertifikat-Assistenten müssen Sie als Konto mit den richtigen Berechtigungen für den Zertifikatvorlagentyp angemeldet sein, den Sie verwenden möchten. Standardmäßig verwendet eine Skype for Business Server-Zertifikatanforderung die Webserver-Zertifikatvorlage. Wenn Sie mit einem Konto angemeldet sind, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist, um ein Zertifikat über diese Vorlage an fordern, überprüfen Sie, ob der Gruppe die Berechtigungen zum Registrieren zur Verwendung dieser Vorlage zugewiesen wurden. 
  
### <a name="internal-edge-interface-certificates"></a>Interne Edgeschnittstellenzertifikate

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Herunterladen oder Exportieren der Zertifizierungskette der Zertifizierungsstelle

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. Herunterladen mithilfe der Website "certsrv"

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Melden Sie sich bei einem Skype for Business Server in Ihrem internen Netzwerk als Mitglied der lokalen Administratorgruppe an.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Öffnen Sie **"Start"** und **"Ausführen"** (oder **"Suchen** und **Ausführen"),** und geben Sie Folgendes ein:
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Zum Beispiel:
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Klicken Sie auf der Certsrv-Webseite der ausstellenden Zertifizierungsstelle unter "Aufgabe auswählen" auf "Zertifizierungsstellenzertifikat, Zertifikatkette oder **Zertifikatsperrliste herunterladen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Klicken **Sie unter "Zertifizierungsstellenzertifikat herunterladen", "Zertifikatkette" oder "Zertifikatsperrliste** herunterladen" auf **"Zertifizierungsstellenzertifikatkette herunterladen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Klicken Sie **im Feld "Dateidownload"** auf **"Speichern".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Speichern Sie die P7B-Datei auf der Festplatte auf dem Server, und kopieren Sie sie dann in einen Ordner auf den einzelnen Edgeservern.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportieren mithilfe von MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Sie können das Stammzertifikat der Zertifizierungsstelle von einem beliebigen computer, der der Domäne beigetreten ist, mithilfe der MMC exportieren. Wechseln Sie entweder **zu "Start"** und **"Ausführen"** oder öffnen **Sie "Suche",** und geben Sie **MMC ein, um** es zu öffnen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Klicken Sie in der MMC-Konsole **auf "Datei"** und dann auf "Snap-In **hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Wählen Sie **in der Dialogfeldliste "Snap-Ins** hinzufügen oder entfernen" die Option **"Zertifikate"** aus, und klicken Sie dann auf **"Hinzufügen".** Wenn Sie dazu aufgefordert werden, wählen **Sie "Computerkonto"** und dann **"Weiter" aus.** Wählen Sie **im Dialogfeld "Computer** auswählen" die **Option "Lokaler Computer" aus.** Klicken Sie **auf "Fertig** stellen" und dann **auf "OK".**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Erweitern **Sie Zertifikate (lokaler Computer).** Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**. Wählen Sie **Zertifikate aus.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie **im** Menü "Alle Aufgaben" aus, und wählen Sie dann **"Exportieren" aus.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Der **Assistent zum Exportieren von Zertifikaten** wird geöffnet. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. Wählen Sie **im Dialogfeld "Dateiformat exportieren"** das Format aus, in das Sie exportieren möchten. Unsere Empfehlung lautet **Cryptographic Message Syntax Standard - PKCS #7 Certificates (P7b).** Wenn Dies auch Ihre Wahl ist, aktivieren Sie nach Möglichkeit auch das Kontrollkästchen "Alle Zertifikate **im** Zertifizierungspfad enthalten", da dadurch auch die Zertifikatkette exportiert wird, einschließlich des Zertifikats der Stammzertifizierungsstelle und aller Zwischenzertifikate. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Geben Sie **im** Dialogfeld "Zu exportierende Datei" im Dateinameneintrag einen Pfad und Dateinamen (die Standarderweiterung ist P7b) für das exportierte Zertifikat ein. Wenn es einfacher für Sie  ist, wählen Sie die Schaltfläche "Durchsuchen" aus, um zu dem Speicherort zu wechseln, an dem Sie das exportierte Zertifikat speichern möchten, und benennen Sie das exportierte Zertifikat hier. Klicken **Sie auf**"Speichern" und dann auf **"Weiter",** wenn Sie bereit sind.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Überprüfen Sie die Zusammenfassung Ihrer Aktionen, und klicken Sie auf **"Fertig** stellen", um den Export des Zertifikats fertig zu stellen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Kopieren Sie die .p7b-Datei auf jeden Edgeserver.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importieren der Zertifizierungskette der Zertifizierungsstelle

&nbsp;&nbsp;&nbsp;a. Öffnen Sie auf jedem Edgeserver die MMC (wählen **Sie "Start"** und **"Ausführen"** oder **"Suchen"** aus, und geben Sie **MMC ein,** um es zu öffnen).
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie **im Menü "Datei"** auf **"Snap-In hinzufügen/entfernen",** und wählen Sie dann **"Hinzufügen" aus.**
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie **im Feld "Snap-Ins hinzufügen** oder entfernen" auf **"Zertifikate"** und dann auf "Hinzufügen". 
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;e. Stellen Sie **im Dialogfeld "Computer** auswählen" sicher, dass das Kontrollkästchen "Lokaler **Computer: (Computer,** auf dem diese Konsole ausgeführt wird) aktiviert ist, und klicken Sie dann auf "Fertig **stellen".**
    
&nbsp;&nbsp;&nbsp;f. Klicken **Sie auf**"Schließen" und dann auf **"OK".**
    
&nbsp;&nbsp;&nbsp;g. Erweitern Sie in der Konsolenstruktur Zertifikate **(Lokaler Computer),** klicken Sie mit der rechten Maustaste auf Vertrauenswürdige Stammzertifizierungsstellen, wechseln Sie zu **"Alle** Aufgaben", und klicken Sie dann auf **"Importieren".** 
    
&nbsp;&nbsp;&nbsp;h. Geben Sie im angezeigten  Assistenten im Textfeld "Zu importierende Datei" den Dateinamen des Zertifikats an (den Namen, den Sie der .p7b-Datei im vorherigen Abschnitt gegeben haben). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;i. Lassen Sie das Optionsfeld "Alle Zertifikate im folgenden Speicher **platzieren", da** vertrauenswürdige Stammzertifizierungsstellen ausgewählt werden sollten. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Überprüfen Sie die Zusammenfassung, und klicken Sie auf **"Fertig** stellen", um den Importvorgang abschließen zu können.
    
&nbsp;&nbsp;&nbsp;k. Dies muss für jeden Edgeserver durchgeführt werden, den Sie bereitstellen.
    
### <a name="3-create-the-certificate-request"></a>3. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;a. Melden Sie sich bei einem Ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in Schritt **3:** Zertifikate anfordern, installieren oder zuweisen auf "Ausführen" **(oder** "Erneut ausführen", wenn Sie diesen Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;b. Stellen Sie **sicher, dass auf** der Seite "Zertifikatanforderung" das interne **Edgezertifikat** ausgewählt ist, und klicken Sie auf **"Anfordern".**
    
&nbsp;&nbsp;&nbsp;c. Wählen  Sie auf der Seite  "Verzögerte oder sofortige Anforderungen" die Option "Anforderung sofort an eine Onlinezertifizierungsstelle senden" aus, wenn Sie von Ihrer Edgeumgebung aus auf eine Anforderung zugreifen können, oder bereiten Sie die Anforderung jetzt **vor,** senden Sie sie aber andernfalls später.
    
&nbsp;&nbsp;&nbsp;d. Geben Sie **auf** der Seite Zertifikatanforderungsdatei den vollständigen Teil und den Dateinamen für den Ort ein, an dem die Datei gespeichert wird (z. B. c:\SkypeInternalEdgeCert.cer ). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;e. Aktivieren Sie **auf der** Seite "Alternative Zertifikatvorlage angeben" das Kontrollkästchen "Alternative Zertifikatvorlage verwenden" für das ausgewählte Zertifizierungsstelle-Kontrollkästchen, um eine andere Vorlage als die Standardvorlage "WebServer" **zu** verwenden. Andernfalls nichts.
    
&nbsp;&nbsp;&nbsp;f. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Geben **Sie im Anzeigenamen** einen Anzeigenamen für das Zertifikat ein (z. B. interner Edge).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. Wählen **Sie in** der Bitlänge Ihre Bitlänge aus (der Standardwert ist 2048, Sie können höher gehen und sicherer sein, aber die Leistung wird verlangsamt).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen privaten Schlüssel des Zertifikats als **exportierbar** markieren.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;g. Geben Sie **auf der Seite "Organisationsinformationen"** den Namen für Ihre Organisation und Organisationseinheit ein. Sie können beispielsweise Ihre Abteilung oder Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie **auf der Seite "Geografische** Informationen" Ihre Standortinformationen ein.
    
&nbsp;&nbsp;&nbsp;i. Auf der **Seite "Subject Name/Subject Alternate Names"** sollte dies automatisch vom Assistenten ausgefüllt werden.
    
&nbsp;&nbsp;&nbsp;j. Auf der **Seite "Zusätzliche** alternative Betreffnamen konfigurieren" müssen Sie alle zusätzlichen alternativen Betreffnamen hinzufügen, die Sie benötigen.
    
&nbsp;&nbsp;&nbsp;k. Sehen Sie **sich auf der** Seite "Anforderungszusammenfassung" die Zertifikatinformationen an, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Sie Änderungen vornehmen müssen, wechseln Sie zurück und tun Sie dies jetzt.
    
&nbsp;&nbsp;&nbsp;l. Klicken Sie **dann** auf "Weiter", um die CSR-Datei zu  generieren, die Sie der Zertifizierungsstelle bereitstellen müssen (Sie können auch auf "Protokoll anzeigen" klicken, um das Protokoll für die Zertifikatanforderung zu sehen).
    
&nbsp;&nbsp;&nbsp;m. Nachdem die Anforderung generiert wurde, können Sie auf "Ansicht" **klicken,** um das Zertifikat anzuzeigen, und fertig stellen, um das Fenster zu schließen.  Der Inhalt der Datei "CSR" muss An ihre Zertifizierungsstelle übertragen werden, damit sie im nächsten Abschnitt ein Zertifikat generieren kann, das Sie auf diesen Computer importieren können.
    

### <a name="4-import-the-certificate"></a>4. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;a. Melden Sie sich als Mitglied der lokalen Administratorengruppe an dem Edgeserver an, von dem Sie die Zertifikatanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;b. Im Bereitstellungsassistenten neben **Schritt 3. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **"Erneut ausführen".**
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie **auf der Seite "Verfügbare Zertifikataufgaben"** **auf "Zertifikat aus einem importieren". P7b-, PFX- oder CER-Datei.**
    
&nbsp;&nbsp;&nbsp;d. Geben Sie **auf** der Seite Zertifikat importieren den vollständigen Pfad und Dateinamen des  Zertifikats ein, das Sie im vorherigen Abschnitt erhalten haben (oder Sie können auf "Durchsuchen" klicken, um die Datei auf diese Weise zu suchen und zu wählen).
    
&nbsp;&nbsp;&nbsp;e. Wenn Sie Zertifikate für andere Mitglieder Ihres Edgepools importieren und Ihr Zertifikat einen  privaten Schlüssel enthält, aktivieren Sie unbedingt das Kontrollkästchen Zertifikatdatei, die den privaten Schlüssel des Zertifikats enthält, und geben Sie das Kennwort an. Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf  der Seite **"Zusammenfassung"** auf "Weiter", sobald Sie die Informationen bestätigt haben, und fertig stellen, **sobald** das Zertifikat erfolgreich importiert wurde.
    
 
### <a name="5-export-the-certificate"></a>5. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;a. Stellen Sie sicher, dass Sie sich als Mitglied der lokalen Administratorengruppe am Edgeserver angemeldet haben, auf den Sie das Zertifikat zuvor importiert haben.
    
&nbsp;&nbsp;&nbsp;b. Klicken **Sie auf "Start",** **"Ausführen"** (oder **"Suche** öffnen"), und geben Sie **MMC ein.**
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole **auf "Datei"** und dann auf "Snap-In **hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie **im Feld "Snap-Ins hinzufügen** oder entfernen" auf **"Zertifikate"** und dann auf **"Hinzufügen".**
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Dialogfeld "Zertifikate-Snap-In" die Option **"Computerkonto" aus.**  Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie **im Dialogfeld "Computer** auswählen" die Option **"Lokaler Computer: (Der** Computer, auf dem diese Konsole ausgeführt wird) aus. Klicken Sie auf **Fertig stellen**. Klicken **Sie auf "OK",** und die Konfiguration der MMC-Konsole ist abgeschlossen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **"Persönlich",** und klicken Sie dann auf **"Zertifikate".**
    
  > [!NOTE]
  > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Speicher "Zertifikate" für den lokalen Computer angezeigt. Sie müssen nicht herumsuchen, wenn der Schlüssel nicht da ist, dem importierten Zertifikat kein privater Schlüssel zugeordnet war. Probieren Sie die oben genannten Anforderungs- und Importschritte aus, und wenn Sie sicher sind, dass Sie alles richtig gemacht haben, wenden Sie sich an Ihren Zertifizierungsstellenadministrator oder -anbieter. 
  
&nbsp;&nbsp;&nbsp;h. Klicken Sie **im Persönlichen Speicher für Zertifikate** für den lokalen Computer mit der rechten Maustaste auf das Zertifikat, das Sie exportieren. Wählen **Sie im** resultierenden Menü alle Vorgänge aus, und klicken Sie dann auf **"Exportieren".**
    
&nbsp;&nbsp;&nbsp;i. Klicken Sie im Assistenten für den Zertifikatexport auf **Weiter**. Wählen **Sie "Ja" aus, und exportieren Sie den privaten Schlüssel.** Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;j. Wählen Sie **im Dialogfeld "Dateiformate** exportieren" die Option **"Persönlicher Informationsaustausch - PKCS#12" (. PFX)** und wählen Sie dann Folgendes aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Schließen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > **WÄHLEN Sie** **niemals "Privaten Schlüssel löschen" aus, wenn der Export erfolgreich war.** Das bedeutet, dass Sie das Zertifikat und den privaten Schlüssel wieder auf diesen Edgeserver importieren müssen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuweisen möchten, können Sie ein Kennwort für den privaten Schlüssel eingeben. Reenter the password to confirm, and then click **Next**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie unter Verwendung der Dateierweiterung PFX einen Pfad und Dateinamen für das exportierte **Zertifikat ein.** Auf den Pfad muss entweder von den anderen Edgeservern im Pool zugegriffen werden können, oder Sie müssen die Datei über externe Medien (z. B. ein USB-Laufwerk) verschieben. Klicken **Sie auf** "Weiter", wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die  Zusammenfassung im Dialogfeld "Zertifikatexport-Assistent abschließen", und klicken Sie dann auf **"Fertig stellen".**
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld für den erfolgreichen Export auf **"OK".**
    
 
### <a name="6-assign-the-certificate"></a>6. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;a. Auf jedem Edgeserver im Assistenten für die Bereitstellung neben **Schritt 3. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie erneut **auf "Ausführen".**
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie **auf der Seite "Verfügbare Zertifikataufgaben"** auf **"Vorhandenes Zertifikat zuweisen".**
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Edge intern** aus.
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie **auf der Seite Zertifikatspeicher** das Zertifikat aus, das Sie für den internen Edge importiert haben (aus dem vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie **auf der Seite** "Zertifikatzuweisungszusammenfassung" die Einstellungen, und klicken Sie dann auf "Weiter", um das Zertifikat zuzuordnen. 
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Nachdem Sie dieses Verfahren abgeschlossen haben, sollten Sie das MMC-Snap-In "Zertifikate" auf jedem Edgeserver öffnen, Zertifikate **(lokaler Computer)** erweitern, **"Persönlich"** erweitern, auf "Zertifikate" klicken und bestätigen, dass das interne Edgezertifikat im Detailbereich aufgeführt ist.
    
### <a name="external-edge-interface-certificates"></a>Externe Edgeschnittstellenzertifikate

 
### <a name="1-create-the-certificate-request"></a>1. Erstellen der Zertifikatanforderung

&nbsp;&nbsp;&nbsp;a. Melden Sie sich bei einem Ihrer Edgeserver an, starten Sie den Bereitstellungs-Assistenten, und klicken Sie in Schritt **3:** Zertifikate anfordern, installieren oder zuweisen auf "Ausführen" (oder "Erneut ausführen", wenn Sie diesen Assistenten bereits ausgeführt haben).
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.
    
&nbsp;&nbsp;&nbsp;c. Stellen Sie **sicher, dass auf** der Seite "Zertifikatanforderung" das externe **Edgezertifikat** ausgewählt ist, und klicken Sie auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.
    
&nbsp;&nbsp;&nbsp;e. Geben Sie **auf** der Seite Zertifikatanforderungsdatei den vollständigen Teil und den Dateinamen für den Ort ein, an dem die Datei gespeichert wird (z. B. c:\SkypeInternalEdgeCert.cer ). Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Aktivieren Sie **auf der** Seite "Alternative Zertifikatvorlage angeben" das Kontrollkästchen "Alternative Zertifikatvorlage verwenden" für das ausgewählte Zertifizierungsstelle-Kontrollkästchen, um eine andere Vorlage als die Standardvorlage "WebServer" **zu** verwenden.
    
&nbsp;&nbsp;&nbsp;g. Führen Sie auf der Seite Namens- und Sicherheitseinstellungen die folgenden Aufgaben aus:
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Geben **Sie im Anzeigenamen** einen Anzeigenamen für das Zertifikat ein (z. B. externer Edge).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. Wählen **Sie in** der Bitlänge Ihre Bitlänge aus (der Standardwert ist 2048, Sie können höher gehen und sicherer sein, aber die Leistung wird verlangsamt).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Wenn Sie ein exportierbares Zertifikat benötigen, müssen Sie das Kontrollkästchen privaten Schlüssel des Zertifikats als **exportierbar** markieren.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;h. Geben Sie **auf der Seite "Organisationsinformationen"** den Namen für Ihre Organisation und Organisationseinheit ein. Sie können beispielsweise Ihre Abteilung oder Abteilung (z. B. IT) eingeben.
    
&nbsp;&nbsp;&nbsp;i. Geben Sie **auf der Seite "Geografische** Informationen" Ihre Standortinformationen ein.
    
&nbsp;&nbsp;&nbsp;j. Auf der **Seite "Subject Name/Subject Alternate Names"** sollten die erforderlichen Informationen automatisch vom Assistenten ausgefüllt werden.
    
&nbsp;&nbsp;&nbsp;k. Aktivieren Sie auf der Seite **"SIP-Domäneneinstellung für alternative Betreffnamen(SANs)"** das Kontrollkästchen "Domäne", um einen Sip hinzuzufügen.<sipdomain> Eintrag in die Liste alternativer Betreffnamen.
    
&nbsp;&nbsp;&nbsp;l. Auf der **Seite "Zusätzliche** alternative Betreffnamen konfigurieren" müssen Sie alle zusätzlichen alternativen Betreffnamen hinzufügen, die Sie benötigen.
    
&nbsp;&nbsp;&nbsp;m. Sehen Sie **sich auf der** Seite "Anforderungszusammenfassung" die Zertifikatinformationen an, die zum Generieren Ihrer Anforderung verwendet werden. Wenn Sie Änderungen vornehmen müssen, wechseln Sie zurück und tun Sie dies jetzt.
    
&nbsp;&nbsp;&nbsp;n. Wenn Sie bereit sind, klicken Sie auf "Weiter", um die CSR-Datei  zu generieren, die Sie der Zertifizierungsstelle bereitstellen müssen (Sie können auch auf "Protokoll anzeigen" klicken, um das Protokoll für die Zertifikatanforderung zu sehen). 
    
&nbsp;&nbsp;&nbsp;o. Nachdem die Anforderung generiert wurde, können Sie auf "Ansicht" **klicken,** um das Zertifikat anzuzeigen, und fertig stellen, um das Fenster zu schließen.  Der Inhalt der Datei "CSR" muss An ihre Zertifizierungsstelle übertragen werden, damit sie im nächsten Abschnitt ein Zertifikat generieren kann, das Sie auf diesen Computer importieren können.
    
&nbsp;&nbsp;&nbsp;p. (OPTIONAL) Sie können bei der Übermittlung der Inhalte der CSR wie folgt nach bestimmten Informationen gefragt werden (ZS variieren stark, sodass dies möglicherweise nicht erforderlich ist):
    
  - **Microsoft** als Serverplattform
    
  - **IIS** als Version
    
  - **Webserver als** Verwendungstyp
    
  - **PKCS7** als Antwortformat
    
 
### <a name="2-import-the-certificate"></a>2. Importieren des Zertifikats

&nbsp;&nbsp;&nbsp;a. Melden Sie sich als Mitglied der lokalen Administratorengruppe an dem Edgeserver an, von dem Sie die Zertifikatanforderung im letzten Verfahren vorgenommen haben.
    
&nbsp;&nbsp;&nbsp;b. Im Bereitstellungsassistenten neben **Schritt 3. Zertifikate anfordern, installieren oder zuweisen**, klicken Sie auf **"Erneut ausführen".**
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie **auf der Seite "Verfügbare Zertifikataufgaben"** **auf "Zertifikat aus einem importieren". P7b-, PFX- oder CER-Datei.**
    
&nbsp;&nbsp;&nbsp;d. Geben Sie **auf** der Seite Zertifikat importieren den vollständigen Pfad und Dateinamen des  Zertifikats ein, das Sie im vorherigen Abschnitt erhalten haben (oder Sie können auf "Durchsuchen" klicken, um die Datei auf diese Weise zu suchen und zu wählen). Wenn Ihr Zertifikat einen privaten Schlüssel enthält, stellen Sie sicher, dass die Zertifikatdatei den **privaten** Schlüssel des Zertifikats enthält, und geben Sie das Kennwort für den privaten Schlüssel ein. Klicken **Sie auf "Weiter",** wenn Sie bereit sind.
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie **auf der Seite "Zertifikatzusammenfassung** importieren" die Zusammenfassungsinformationen, und klicken Sie auf **"Weiter".**
    
&nbsp;&nbsp;&nbsp;f. Auf der **Seite "Befehle** ausführen" können Sie das Ergebnis des Imports überprüfen, wenn er abgeschlossen ist, indem Sie auf **"Protokoll anzeigen" klicken.** Klicken Sie **auf "Fertig** stellen", um den Zertifikatimport fertig zu stellen.
    
&nbsp;&nbsp;&nbsp;g. Wenn sie über andere Edgeserver in einem Pool verfügen, müssen Sie auch die nächsten beiden Verfahren befolgen. Wenn es sich um einen eigenständigen Edgeserver handelt, sind Sie mit externen Zertifikaten fertig.
    
 
### <a name="3-export-the-certificate"></a>3. Exportieren des Zertifikats

&nbsp;&nbsp;&nbsp;a. Stellen Sie sicher, dass Sie sich am Edgeserver angemeldet haben, auf den Sie das Zertifikat als lokalen Administrator importiert haben.
    
&nbsp;&nbsp;&nbsp;b. Klicken **Sie auf "Start",** **"Ausführen"** (oder **"Suche** öffnen"), und geben Sie **MMC ein.**
    
&nbsp;&nbsp;&nbsp;c. Klicken Sie in der MMC-Konsole **auf "Datei"** und dann auf "Snap-In **hinzufügen/entfernen".**
    
&nbsp;&nbsp;&nbsp;d. Klicken Sie **im Feld "Snap-Ins hinzufügen** oder entfernen" auf **"Zertifikate"** und dann auf **"Hinzufügen".**
    
&nbsp;&nbsp;&nbsp;e. Wählen Sie im Dialogfeld "Zertifikate-Snap-In" die Option **"Computerkonto" aus.**  Klicken Sie auf **Weiter**.
    
&nbsp;&nbsp;&nbsp;f. Wählen Sie **im Dialogfeld "Computer** auswählen" die Option **"Lokaler Computer: (Der** Computer, auf dem diese Konsole ausgeführt wird) aus. Klicken Sie auf **Fertig stellen**. Klicken **Sie auf "OK",** und die Konfiguration der MMC-Konsole ist abgeschlossen.
    
&nbsp;&nbsp;&nbsp;g. Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. **Doppelklicken Sie auf "Persönlich",** und klicken Sie dann auf **"Zertifikate".**
    
   > [!NOTE]
   > Möglicherweise sind Sie hier, und es werden keine Zertifikate im persönlichen Speicher "Zertifikate" für den lokalen Computer angezeigt. Sie müssen nicht herumsuchen, wenn der Schlüssel nicht da ist, dem importierten Zertifikat kein privater Schlüssel zugeordnet war. Probieren Sie die oben genannten Anforderungs- und Importschritte aus, und wenn Sie sicher sind, dass Sie alles richtig gemacht haben, wenden Sie sich an Ihren Zertifizierungsstellenadministrator oder -anbieter. 
  
&nbsp;&nbsp;&nbsp;h. Klicken Sie **im Persönlichen Speicher für Zertifikate** für den lokalen Computer mit der rechten Maustaste auf das Zertifikat, das Sie exportieren. **Wählen Sie im** resultierenden Menü alle Vorgänge aus, und klicken Sie dann auf **"Exportieren".**
    
&nbsp;&nbsp;&nbsp;i. Klicken Sie im Assistenten für den Zertifikatexport auf **Weiter**. Wählen **Sie "Ja" aus, und exportieren Sie den privaten Schlüssel.** Klicken Sie auf **Weiter**.
    
   > [!NOTE]
   > If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it. Sie müssen das Zertifikat erneut vom Anbieter anfordern, und der private Schlüssel ist für den Export festgelegt, bevor Sie dies erfolgreich tun.
  
&nbsp;&nbsp;&nbsp;j. Wählen Sie im Dialogfeld "Dateiformate exportieren" die Option "Persönlicher Informationsaustausch - PKCS#12" (. PFX) und wählen Sie dann Folgendes aus:
    
 &nbsp;&nbsp;&nbsp;  i. Schließen Sie nach Möglichkeit alle Zertifikate in den Zertifizierungspfad ein.
    
 &nbsp;&nbsp;&nbsp;  ii. Exportieren Sie alle erweiterten Eigenschaften.
    
   > [!NOTE]
   > **WÄHLEN Sie** **niemals "Privaten Schlüssel löschen" aus, wenn der Export erfolgreich war.** Das bedeutet, dass Sie das Zertifikat und den privaten Schlüssel wieder auf diesen Edgeserver importieren müssen.
  
&nbsp;&nbsp;&nbsp;k. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuweisen möchten, können Sie ein Kennwort für den privaten Schlüssel eingeben. Reenter the password to confirm, and then click **Next**.
    
&nbsp;&nbsp;&nbsp;l. Geben Sie unter Verwendung der Dateierweiterung PFX einen Pfad und Dateinamen für das exportierte **Zertifikat ein.** Auf den Pfad muss entweder von den anderen Edgeservern im Pool zugegriffen werden können, oder Sie müssen die Datei über externe Medien (z. B. ein USB-Laufwerk) verschieben. Klicken **Sie auf** "Weiter", wenn Sie Ihre Wahl getroffen haben.
    
&nbsp;&nbsp;&nbsp;m. Überprüfen Sie die  Zusammenfassung im Dialogfeld "Zertifikatexport-Assistent abschließen", und klicken Sie dann auf **"Fertig stellen".**
    
&nbsp;&nbsp;&nbsp;n. Klicken Sie im Dialogfeld für den erfolgreichen Export auf **"OK".**
    
&nbsp;&nbsp;&nbsp;o. Sie müssen jetzt zum Abschnitt "Importieren des Zertifikats" vor diesem Vorgang zurück wechseln und das Zertifikat auf alle verbleibenden Edgeserver importieren. Fahren Sie dann mit der Zuweisung weiter unten fort.
    
 
### <a name="4-assign-the-certificate"></a>4. Zuweisen des Zertifikats

&nbsp;&nbsp;&nbsp;a. Auf **jedem** Edgeserver im Assistenten für die Bereitstellung neben **Schritt 3. Zertifikate anfordern, installieren oder zuweisen,** klicken Sie auf **erneut ausführen.**
    
&nbsp;&nbsp;&nbsp;b. Klicken Sie **auf der Seite "Verfügbare Zertifikataufgaben"** auf **"Vorhandenes Zertifikat zuweisen".**
    
&nbsp;&nbsp;&nbsp;c. Wählen Sie **auf der Seite "Zertifikatzuweisung"** **in der Liste "Edge Extern"** aus.
    
&nbsp;&nbsp;&nbsp;d. Wählen Sie **auf der Seite Zertifikatspeicher** das Zertifikat aus, das Sie für den externen Edge importiert haben (aus dem vorherigen Abschnitt).
    
&nbsp;&nbsp;&nbsp;e. Überprüfen Sie **auf der Seite** "Zertifikatzuweisungszusammenfassung" die Einstellungen, und klicken Sie dann auf "Weiter", um das Zertifikat zuzuordnen. 
    
&nbsp;&nbsp;&nbsp;f. Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.
    
&nbsp;&nbsp;&nbsp;g. Nachdem Sie dieses Verfahren abgeschlossen haben, sollten Sie das MMC-Snap-In "Zertifikate" auf jedem Server öffnen, Zertifikate **(lokaler Computer)** erweitern, **"Persönlich"** erweitern, auf "Zertifikate" klicken und bestätigen, dass das interne Edgezertifikat im Detailbereich aufgeführt ist.
    
   > [!NOTE]
   > Außerdem müssen Sie die Zertifikate für den Reverseproxyserver einrichten. 
  
## <a name="starting-the-edge-servers"></a>Starten der Edgeserver

Sobald das Setup abgeschlossen ist, müssen Sie die Dienste auf jedem Edgeserver in Ihrer Bereitstellung starten:
  
1. Klicken Sie auf jedem Edgeserver im **Assistenten** für die Bereitstellung neben **Schritt 4: Dienste** starten auf **"Ausführen".**
    
2. Überprüfen Sie **auf der Seite "Skype for Business Server Services** starten" die Liste der Dienste, und klicken Sie dann auf "Weiter", um die Dienste zu starten. 
    
3. Nachdem die Dienste gestartet wurden, können Sie auf **"Fertig stellen" klicken,** um den Assistenten zu schließen.
    
4. (Optional) Klicken Sie **weiterhin unter Schritt 4: Dienste starten** auf **Dienststatus**.
    
5.  Überprüfen Sie **in der MMC** "Dienste" auf jedem Server, ob alle Skype for Business Server-Dienste ausgeführt werden.
    

