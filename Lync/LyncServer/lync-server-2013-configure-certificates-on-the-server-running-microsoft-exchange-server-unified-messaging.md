---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird'
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
ms.openlocfilehash: 6d31ed8b750d0162a2c09d49ca8a350731896086
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Wenn Sie Exchange Unified Messaging (um) bereitgestellt haben, wie unter [Planen der Integration von Exchange Unified Messaging in lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in der Planning-Dokumentation beschrieben, und Sie Exchange um-Features für Enterprise-VoIP-Benutzer in Ihrer Organisation bereitstellen möchten, können Sie die folgenden Verfahren verwenden, um das Zertifikat auf dem Server mit Exchange um zu konfigurieren.

<div>


> [!IMPORTANT]  
> Für interne Zertifikate müssen sowohl auf den Servern mit lync Server 2013 als auch auf den Servern, auf denen Microsoft Exchange ausgeführt wird, vertrauenswürdige Stammzertifizierungsstellen Zertifikate vorhanden sein, die gegenseitig vertrauenswürdig sind. Die Zertifizierungsstelle (Certification Authority, ca) kann entweder dieselbe oder eine andere Zertifizierungsstelle sein, sofern die Server das Stammzertifikat der Zertifizierungsstelle im Zertifikatspeicher der vertrauenswürdigen Stammzertifizierungsstelle registriert haben.



</div>

Der Exchange-Server muss mit einem Server Zertifikat konfiguriert sein, um eine Verbindung mit lync Server 2013 herzustellen:

1.  Laden Sie das Zertifizierungsstellenzertifikat für den Exchange-Server herunter.

2.  Installieren Sie das Zertifizierungsstellenzertifikat für den Exchange-Server.

3.  Überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste der vertrauenswürdigen Stammzertifizierungsstellen des Exchange-Servers befindet.

4.  Erstellen Sie eine Zertifikatanforderung für den Exchange-Server, und installieren Sie das Zertifikat.

5.  Weisen Sie das Zertifikat für den Exchange-Server zu.

<div>

## <a name="to-download-the-ca-certificate"></a>So laden Sie das Zertifizierungsstellenzertifikat herunter

1.  Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **http://\<Namen der ausstellenden CA-\>Server/CertSrv**ein, und klicken Sie dann auf **OK**.

2.  Klicken Sie unter **Aufgabe auswählen**auf **Zertifizierungsstellenzertifikat, Zertifikatkette oder CRL Herunterladen**.

3.  Wählen Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL** **die Option Encoding method to base 64**aus, und klicken Sie dann auf **CA-Zertifikat herunterladen**.
    
    <div>
    

    > [!NOTE]  
    > Sie können in diesem Schritt auch die Codierungsregeln (Distinguished Encoding Rules, der) angeben. Wenn Sie der Codierung auswählen, lautet der Dateityp im nächsten Schritt dieses Verfahrens und in Schritt 10 der <STRONG>Installation des Zertifizierungsstellenzertifikats</STRONG> P7B statt. cer.

    
    </div>

4.  Klicken Sie im Dialogfeld **Datei Download** auf **Speichern**, und speichern Sie die Datei auf der Festplatte auf dem Server. (Abhängig von der Codierung, die Sie im vorherigen Schritt ausgewählt haben, weist die Datei entweder eine CER-oder eine P7B-Dateierweiterung auf.)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>So installieren Sie das Zertifizierungsstellenzertifikat

1.  Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, Microsoft Management Console (MMC), indem Sie auf **Start**klicken, auf **Ausführen**klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK**klicken.

2.  Klicken Sie im Menü **Datei** auf **Snap-in hinzufügen/entfernen**, und klicken Sie dann auf **Hinzufügen**.

3.  Klicken Sie im Feld **eigenständige Snap-Ins hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.

4.  Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.

5.  Überprüfen Sie im Dialogfeld **Computer auswählen** , ob das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

6.  Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**.

7.  Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.

8.  Klicken Sie mit der rechten Maustaste auf **Zertifikate**, klicken Sie auf **alle Aufgaben**, und klicken Sie auf **importieren**.

9.  Klicken Sie auf **Weiter**.

10. Klicken Sie auf **Durchsuchen** , um nach der Datei zu suchen, und klicken Sie dann auf **weiter**. (Abhängig von der Codierung, die Sie in Schritt 3 **zum Herunterladen des CA-Zertifikats**ausgewählt haben, wird die Datei entweder eine CER-oder eine P7B-Dateierweiterung aufweisen.

11. Klicken Sie **im folgenden Store auf alle Zertifikate**speichern.

12. Klicken Sie auf **Durchsuchen**, und wählen Sie dann **Vertrauenswürdige Stammzertifizierungsstellen**aus.

13. Klicken Sie auf **weiter** , um die Einstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen**.

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>So überprüfen Sie, ob sich die Zertifizierungsstelle in der Liste vertrauenswürdiger Stammzertifizierungsstellen befindet

1.  Erweitern Sie auf dem Server, auf dem Exchange um ausgeführt wird, in MMC **Zertifikate (lokaler Computer)**, erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und klicken Sie dann auf **Zertifikate**.

2.  Überprüfen Sie im Detailbereich, ob sich Ihre Zertifizierungsstelle in der Liste der vertrauenswürdigen CAS befindet.

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>So konfigurieren Sie Exchange Server 2013 um mit lync Server

1.  Ausführliche Informationen finden Sie unter "integrieren von Exchange 2013 um mit lync Server" in die Exchange Server [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)-Dokumentation unter.

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>So erstellen Sie eine Zertifikatanforderung und installieren das Zertifikat auf Exchange Server 2007 (SP1)

1.  Klicken Sie auf dem Server, auf dem Exchange um ausgeführt wird, auf **Start**, klicken Sie auf **Ausführen**, geben Sie **\<http://** Namen der ausstellenden CA-Server**\>/certsrv**ein, und klicken Sie dann auf **OK**.

2.  Klicken Sie unter **Aufgabe auswählen**auf **Zertifikat anfordern**.

3.  Klicken Sie unter **Zertifikat anfordern**auf **Erweiterte Zertifikatanforderung**.

4.  Klicken Sie unter **Erweiterte Zertifikatanforderung**auf **erstellen, und senden Sie eine Anforderung an diese Zertifizierungsstelle**.

5.  Wählen Sie unter **Erweiterte Zertifikatanforderung**die Option **Webserver** oder eine andere Serverzertifikatvorlage aus, die für die Serverauthentifizierung konfiguriert ist.

6.  Geben Sie unter **identifizierende Informationen für die Offline Vorlage**im Feld **Name** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Exchange-Servers ein.
    
    <div>
    

    > [!NOTE]  
    > Sie müssen den FQDN des Exchange-Servers eingeben, damit die Kommunikation funktioniert.

    
    </div>

7.  Klicken Sie unter **Schlüsseloptionen**auf das Kontrollkästchen **Zertifikat im Zertifikatspeicher des lokalen Computers speichern** .

8.  Klicken Sie unten auf der Webseite auf die Schaltfläche " **senden** ".

9.  Klicken Sie in dem Dialogfeld, das zur Bestätigung aufgefordert wird, auf **Ja**.

10. Klicken Sie auf der Seite Zertifikat ausgestellt unter **Zertifikat ausgestellt**auf **dieses Zertifikat installieren**.

11. Klicken Sie in dem Dialogfeld, das zur Bestätigung aufgefordert wird, auf **Ja**.

12. Überprüfen Sie, ob die Meldung "Ihr neues Zertifikat wurde erfolgreich installiert" angezeigt wird.

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>So erstellen Sie ein Zertifikat auf Exchange Server 2010

1.  Melden Sie sich mit den entsprechenden Benutzerrechten beim Server mit Exchange um an. Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)unter.

2.  Die folgenden Verfahren zum Erstellen des Zertifikats finden Sie unter:
    
    1.  "Erstellen eines neuen Exchange-Zertifikats" unter[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Importieren eines Exchange-Zertifikats" unter[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > Für den Namen des Zertifikat <STRONG>Antragstellers</STRONG>müssen Sie den FQDN des Exchange-Servers eingeben, damit die Kommunikation funktioniert.

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>So weisen Sie das Zertifikat auf Exchange Server 2007 (SP1) zu

1.  Öffnen Sie auf dem Server, auf dem Exchange um ausgeführt wird, MMC.

2.  Erweitern Sie in der Konsolenstruktur **Personal** , und klicken Sie dann auf **Zertifikate**.

3.  Überprüfen Sie im Detailbereich, ob persönliches Zertifikat angezeigt wird.

4.  Doppelklicken Sie auf das Zertifikat, um dessen Details zu lesen und sicherzustellen, dass es gültig ist.
    
    <div>
    

    > [!NOTE]  
    > Es kann einige Minuten dauern, bis das Zertifikat als gültig angezeigt wird.

    
    </div>

5.  Starten Sie den Microsoft Exchange Unified Messaging-Dienst neu.
    
    <div>
    

    > [!NOTE]  
    > Der Server mit Exchange Server 2007 SP1 Unified Messaging ruft automatisch das richtige Zertifikat ab.

    
    </div>

6.  Öffnen Sie die Ereignisanzeige, und suchen Sie nach der Ereignis-ID 1112, die das Zertifikat angibt, das der Server mit Exchange Server 2007 SP1 Unified Messaging abgerufen hat.

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>So weisen Sie das Zertifikat auf Exchange Server 2010 zu

1.  Melden Sie sich mit den entsprechenden Benutzerrechten beim Server mit Exchange um an. Ausführliche Informationen finden Sie unter "Client Zugriffsberechtigungen" [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)unter.

2.  Eine Vorgehensweise zum Zuweisen des Zertifikats finden Sie unter "Zuweisen von Diensten zu [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)einem Zertifikat" unter.

</div>

</div>

<span> </span>

</div>

</div>

</div>

