---
title: Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird
TOCTitle: Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398564(v=OCS.15)
ms:contentKeyID: 49294408
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wenn Sie Exchange Unified Messaging (UM) wie unter [Planen der Integration von Exchange Unified Messaging in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in der Planungsdokumentation beschrieben bereitgestellt haben und Exchange UM-Features für Enterprise-VoIP-Benutzer in Ihrer Organisation bereitstellen möchten, führen Sie zur Konfiguration des Zertifikats auf dem Server mit Exchange UM die folgenden Schritte aus.


> [!IMPORTANT]
> Für interne Zertifikate müssen sowohl die Server, auf denen Lync Server 2013 ausgeführt wird, als auch die Server, auf denen Microsoft Exchange ausgeführt wird, über Zertifikate der vertrauenswürdigen Stammzertifizierungsstelle verfügen, die sich gegenseitig als vertrauenswürdig einstufen. Die Zertifizierungsstelle kann entweder dieselbe oder eine andere Zertifizierungsstelle sein, sofern auf den Servern das Stammzertifikat der Zertifizierungsstelle im Zertifikatspeicher der vertrauenswürdigen Zertifizierungsstelle registriert ist.



Der Computer mit Exchange Server muss mit einem Serverzertifikat konfiguriert sein, um eine Verbindung mit Lync Server 2013-Computern herstellen zu können.

1.  Laden Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer herunter.

2.  Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer.

3.  Vergewissern Sie sich, dass sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Computers mit Exchange Server befindet.

4.  Erstellen Sie eine Zertifikatanforderung für den Computer mit Exchange Server, und installieren Sie das Zertifikat.

5.  Weisen Sie das Zertifikat für den Computer mit Exchange Server zu.

## So laden Sie das Zertifizierungsstellenzertifikat herunter

1.  Klicken Sie auf dem Server mit Exchange UM auf **Start** und auf **Ausführen**, geben Sie **http://\<Name des Servers der ausstellenden Zertifizierungsstelle\>/certsrv** ein, und klicken Sie auf **OK**.

2.  Klicken Sie unter **Task auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste**.

3.  Wählen Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste** die **Kodierungsmethode für Base 64** aus, und klicken Sie dann auf **Download des Zertifizierungsstellenzertifikats**.
    

    > [!NOTE]
    > Sie können in diesem Schritt auch die DER-Codierung (Distinguished Encoding Rules) angeben. Beachten Sie Folgendes, wenn Sie die DER-Codierung auswählen: Der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt&nbsp;10 unter <STRONG>So installieren Sie das Zertifizierungsstellenzertifikat</STRONG> ist P7B und nicht CER.



4.  Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**, und speichern Sie die Datei auf der Festplatte des Servers. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie im vorherigen Schritt gewählt haben.)

## So installieren Sie das Zertifizierungsstellenzertifikat

1.  Öffnen Sie auf dem Server mit Exchange UM eine MMC-Konsole (Microsoft Management Console), indem Sie auf **Start** und auf **Ausführen** klicken, im Feld **Öffnen** den Befehl **mmc** eingeben und dann auf **OK** klicken.

2.  Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.

3.  Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.

4.  Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.

5.  Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **Lokalen Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

6.  Klicken Sie auf **Schließen** und dann auf **OK**.

7.  Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)** und dann **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie anschließend auf **Zertifikate**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikate**, und klicken Sie dann auf **Alle Tasks** und **Importieren**.

9.  Klicken Sie auf **Weiter**.

10. Klicken Sie auf **Durchsuchen**, um auf die Datei zuzugreifen, und klicken Sie dann auf **Weiter**. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie in Schritt 3 unter **So laden Sie das Zertifizierungsstellenzertifikat herunter** gewählt haben.)

11. Aktivieren Sie die Option **Alle Zertifikate in folgendem Speicher speichern**.

12. Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen** aus.

13. Klicken Sie auf **Weiter**, um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**.

## So überprüfen Sie, ob die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen aufgeführt ist

1.  Erweitern Sie auf dem Server mit Exchange UM in der MMC **Zertifikate (Lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie auf **Zertifikate**.

2.  Überprüfen Sie im Detailbereich, ob Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen aufgeführt ist.

## So konfigurieren Sie Exchange Server 2013 UM mit Lync Server

1.  Ausführliche Informationen finden Sie im Thema „Integrate Exchange 2013 UM with Lync Server“ in der Dokumenatition zu Exchange Server unter [http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0x407).

## So erstellen Sie eine Zertifikatanforderung und installieren Sie das Zertifikat auf Exchange Server 2007 (SP1)

1.  Klicken Sie auf dem Server mit Exchange UM auf **Start** und auf **Ausführen**, geben Sie **http://\<***Name des Servers der ausstellenden Zertifizierungsstelle***\>/certsrv** ein, und klicken Sie auf **OK**.

2.  Klicken Sie unter **Task auswählen** auf **Zertifikat anfordern**.

3.  Klicken Sie unter **Zertifikat anfordern** auf **Erweiterte Zertifikatanforderung**.

4.  Klicken Sie unter **Erweiterte Zertifikatanforderung** auf **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen**.

5.  Wählen Sie unter **Erweiterte Zertifikatanforderung** den Eintrag **Webserver** oder eine andere für die Serverauthentifizierung konfigurierte Serverzertifikatvorlage aus.

6.  Geben Sie unter **Identifikationsinformationen für Offlinevorlage** im Feld **Name** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Computers mit Exchange Server ein.
    

    > [!NOTE]
    > Sie müssen den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.



7.  Aktivieren Sie unter **Schlüsseloptionen** das Kontrollkästchen **Zertifikat in lokalem Zertifikatspeicher aufbewahren**.

8.  Klicken Sie unten auf der Webseite auf die Schaltfläche **Absenden**.

9.  Klicken Sie im Bestätigungsdialogfeld auf **Ja**.

10. Klicken Sie auf der Seite **Zertifikat wurde ausgestellt** auf **Dieses Zertifikat installieren**.

11. Klicken Sie im Bestätigungsdialogfeld auf **Ja**.

12. Vergewissern Sie sich, dass die folgende Meldung angezeigt wird: Das neue Zertifikat wurde installiert.

## So erstellen Sie ein Zertifikat auf Exchange Server 2010

1.  Melden Sie sich am Server mit Exchange UM mit den erforderlichen Benutzerrechten an. Ausführliche Informationen finden Sie unter "Clientzugriffsberechtigungen" unter [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x407).

2.  Anweisungen zum Erstellen des Zertifikats finden Sie in den folgenden Vorgehensweisen:
    
    1.  "Erstellen eines neuen Exchange-Zertifikats" unter [http://go.microsoft.com/fwlink/?linkid=195494\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=195494%26clcid=0x407)
    
    2.  "Importieren eines Exchange-Zertifikats" unter [http://go.microsoft.com/fwlink/?linkid=195496\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=195496%26clcid=0x407)
    

    > [!NOTE]
    > Im Feld <STRONG>Antragstellername</STRONG> des Zertifikats müssen Sie den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.



## So weisen Sie das Zertifikat auf Exchange Server 2007 (SP1) zu

1.  Öffnen Sie auf dem Server mit Exchange UM die MMC.

2.  Erweitern Sie in der Konsolenstruktur den Eintrag **Persönlich**, und klicken Sie auf **Zertifikate**.

3.  Vergewissern Sie sich, dass im Detailfenster Ihr eigenes Zertifikat angezeigt wird.

4.  Doppelklicken Sie auf das Zertifikat, wenn Sie Detailinformationen einsehen und sich vergewissern möchten, dass das Zertifikat gültig ist.
    

    > [!NOTE]
    > Es kann eine Weile dauern, bis das Zertifikat als gültig angezeigt wird.



5.  Starten Sie den Microsoft Exchange Unified Messaging-Dienst.
    

    > [!NOTE]
    > Der Server, auf dem Exchange Server&nbsp;2007&nbsp;SP1 Unified Messaging ausgeführt wird, ruft automatisch das richtige Zertifikat ab.



6.  Öffnen Sie die Ereignisanzeige, und suchen Sie nach der Ereignis-ID 1112. Dieses Ereignis gibt an, welches Zertifikat der Server, auf dem Exchange Server 2007 SP1 Unified Messaging ausgeführt wird, abgerufen hat.

## So weisen Sie das Zertifikat auf Exchange Server 2010 zu

1.  Melden Sie sich am Server mit Exchange UM mit den erforderlichen Benutzerrechten an. Ausführliche Informationen finden Sie unter "Clientzugriffsberechtigungen" unter [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x407).

2.  Die Vorgehensweise zum Zuweisen des Zertifikats ist unter "Zuordnen von Diensten zu einem Zertifikat" auf der folgenden Website beschrieben: [http://go.microsoft.com/fwlink/?linkid=195497\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=195497%26clcid=0x407).

