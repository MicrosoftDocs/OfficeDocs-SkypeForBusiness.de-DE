---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 515be9190f9c5012dfd75cdda6621b7f4acfd88f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server, auf dem Exchange Server Unified Messaging läuft

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Wenn Sie Exchange Unified Messaging (um) bereitgestellt haben, wie unter [Planen der Integration von Exchange Unified Messaging in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in der Planungsdokumentation beschrieben, und Sie den Enterprise-VoIP-Benutzern in Ihrer Organisation Exchange um Funktionen bereitstellen möchten, können Sie die folgenden Verfahren zum Konfigurieren des Zertifikats auf dem Server verwenden, auf dem Exchange um läuft.

<div>


> [!IMPORTANT]  
> Bei internen Zertifikaten müssen sowohl die Server mit lync Server 2013 als auch die Server, auf denen Microsoft Exchange läuft, vertrauenswürdige Stammzertifizierungsstellen Zertifikate besitzen, die gegenseitig vertrauenswürdig sind. Die Zertifizierungsstelle (Certification Authority, ca) kann identisch sein oder eine andere Zertifizierungsstelle, solange die Stammzertifikate der Zertifizierungsstelle in Ihrem Zertifikatspeicher für vertrauenswürdige Stammzertifizierungsstellen registriert sind.



</div>

Das Exchange Server muss mit einem Server Zertifikat konfiguriert sein, damit eine Verbindung mit lync Server 2013 hergestellt werden kann:

1.  Laden Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer herunter.

2.  Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange Server-Computer.

3.  Vergewissern Sie sich, dass sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Computers mit Exchange Server befindet.

4.  Erstellen Sie eine Zertifikatanforderung für den Computer mit Exchange Server, und installieren Sie das Zertifikat.

5.  Weisen Sie das Zertifikat für den Computer mit Exchange Server zu.

<div>

## <a name="to-download-the-ca-certificate"></a>So laden Sie das Zertifizierungsstellenzertifikat herunter

1.  Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **\<http://Namen des ausstellenden Zertifizierungsstellenservers\>/certsrv ein**, und klicken Sie dann auf **OK**.

2.  Klicken Sie unter **Task auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste**.

3.  Wählen Sie unter **Herunterladen eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL** **die Option Encoding method to base 64**aus, und klicken Sie dann auf **Zertifizierungsstellenzertifikat herunterladen**.
    
    <div>
    

    > [!NOTE]  
    > In diesem Schritt können Sie auch die Encoding-Codierungsregeln (Distinguished Encoding Rules, der) angeben. Beachten Sie Folgendes, wenn Sie die DER-Codierung auswählen: Der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 unter <STRONG>So installieren Sie das Zertifizierungsstellenzertifikat</STRONG> ist P7B und nicht CER.

    
    </div>

4.  Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**, und speichern Sie die Datei auf der Festplatte des Servers. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie im vorherigen Schritt gewählt haben.)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>So installieren Sie das Zertifizierungsstellenzertifikat

1.  Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, Microsoft Management Console (MMC), indem Sie auf **Start**und dann auf **Ausführen**klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK**klicken.

2.  Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.

3.  Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.

4.  Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.

5.  Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole läuft)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

6.  Klicken Sie auf **Schließen** und dann auf **OK**.

7.  Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)** und dann **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie anschließend auf **Zertifikate**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikate**, und klicken Sie dann auf **Alle Tasks** und **Importieren**.

9.  Klicken Sie auf **Weiter**.

10. Klicken Sie auf **Durchsuchen**, um auf die Datei zuzugreifen, und klicken Sie dann auf **Weiter**. (Die Datei hat entweder die Dateierweiterung CER oder P7B. Dies richtet sich nach der Codierung, die Sie in Schritt 3 unter **So laden Sie das Zertifizierungsstellenzertifikat herunter** gewählt haben.)

11. Aktivieren Sie die Option **Alle Zertifikate in folgendem Speicher speichern**.

12. Klicken Sie auf **Durchsuchen**, und wählen Sie **Vertrauenswürdige Stammzertifizierungsstellen** aus.

13. Klicken Sie auf **Weiter**, um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>So überprüfen Sie, ob die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen aufgeführt ist

1.  Erweitern Sie auf dem Server mit Exchange um unter MMC die Option **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.

2.  Überprüfen Sie im Detailbereich, ob Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen Zertifizierungsstellen aufgeführt ist.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>So konfigurieren Sie Exchange Server 2013 um mit lync Server

1.  Ausführliche Informationen finden Sie unter "integrieren Exchange 2013 um mit lync Server" in die Exchange Server Dokumentation [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)unter.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>So erstellen Sie eine Zertifikatanforderung und installieren Sie das Zertifikat auf Exchange Server 2007 (SP1)

1.  Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **\<http://** Namen des ausstellenden Zertifizierungsstellenservers**\>/certsrv ein**, und klicken Sie dann auf **OK**.

2.  Klicken Sie unter **Task auswählen** auf **Zertifikat anfordern**.

3.  Klicken Sie unter **Zertifikat anfordern** auf **Erweiterte Zertifikatanforderung**.

4.  Klicken Sie unter **Erweiterte Zertifikatanforderung** auf **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen**.

5.  Wählen Sie unter **Erweiterte Zertifikatanforderung** den Eintrag **Webserver** oder eine andere für die Serverauthentifizierung konfigurierte Serverzertifikatvorlage aus.

6.  Geben Sie unter **identifizierende Informationen für Offline Vorlage**im Feld **Name** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange Server ein.
    
    <div>
    

    > [!NOTE]  
    > Sie müssen den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.

    
    </div>

7.  Aktivieren Sie unter **Schlüsseloptionen** das Kontrollkästchen **Zertifikat in lokalem Zertifikatspeicher aufbewahren**.

8.  Klicken Sie unten auf der Webseite auf die Schaltfläche **Absenden**.

9.  Klicken Sie im Bestätigungsdialogfeld auf **Ja**.

10. Klicken Sie auf der Seite **Zertifikat wurde ausgestellt** auf **Dieses Zertifikat installieren**.

11. Klicken Sie im Bestätigungsdialogfeld auf **Ja**.

12. Vergewissern Sie sich, dass die folgende Meldung angezeigt wird: Das neue Zertifikat wurde installiert.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>So erstellen Sie ein Zertifikat auf Exchange Server 2010

1.  Melden Sie sich bei dem Server an, auf dem Exchange um mit den entsprechenden Benutzerrechten ausführt. Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)unter.

2.  Anweisungen zum Erstellen des Zertifikats finden Sie in den folgenden Vorgehensweisen:
    
    1.  "Erstellen eines neuen Exchange-Zertifikats" unter[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importieren eines Exchange-Zertifikats" unter[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Im Feld <STRONG>Antragstellername</STRONG> des Zertifikats müssen Sie den FQDN des Exchange Server-Computers eingeben, damit die Kommunikation funktioniert.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>So weisen Sie das Zertifikat auf Exchange Server 2007 (SP1) zu

1.  Öffnen Sie auf dem Server mit Exchange um MMC.

2.  Erweitern Sie in der Konsolenstruktur den Eintrag **Persönlich**, und klicken Sie auf **Zertifikate**.

3.  Vergewissern Sie sich, dass im Detailfenster Ihr eigenes Zertifikat angezeigt wird.

4.  Doppelklicken Sie auf das Zertifikat, um die Details zu lesen und sicherzustellen, dass es gültig ist.
    
    <div>
    

    > [!NOTE]  
    > Es kann eine Weile dauern, bis das Zertifikat als gültig angezeigt wird.

    
    </div>

5.  Starten Sie den Microsoft Exchange Unified Messaging-Dienst.
    
    <div>
    

    > [!NOTE]  
    > Der Server, auf dem Exchange Server 2007 SP1 Unified Messaging ausgeführt wird, ruft automatisch das richtige Zertifikat ab.

    
    </div>

6.  Öffnen Sie die Ereignisanzeige, und suchen Sie nach der Ereignis-ID 1112. Dieses Ereignis gibt an, welches Zertifikat der Server, auf dem Exchange Server 2007 SP1 Unified Messaging ausgeführt wird, abgerufen hat.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>So weisen Sie das Zertifikat auf Exchange Server 2010 zu

1.  Melden Sie sich bei dem Server an, auf dem Exchange um mit den entsprechenden Benutzerrechten ausführt. Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)unter.

2.  Das Verfahren zum Zuweisen des Zertifikats finden Sie unter "Zuweisen von Diensten zu einem Zertifikat" [https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

