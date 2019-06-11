---
title: 'Lync Server 2013: Einrichten der Zertifikate für die interne Edgeschnittstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53ba11db5d2c9fc727b7720a1a10d5da547075c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Einrichten der Zertifikate für die interne Edgeschnittstelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Wenn Sie den Zertifikat-Assistenten ausführen, stellen Sie sicher, dass Sie mit einem Konto angemeldet sind, das Mitglied einer Gruppe ist, der die entsprechenden Berechtigungen für den Typ der Zertifikatvorlage zugewiesen wurden, die Sie verwenden werden. Standardmäßig verwendet eine lync Server 2013-Zertifikatanforderung die Webserverzertifikatvorlage. Wenn Sie ein Konto verwenden, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat mithilfe dieser Vorlage anzufordern, stellen Sie sicher, dass der Gruppe die für die Verwendung dieser Vorlage erforderlichen Registrierungsberechtigungen zugewiesen wurden.



</div>

Auf der internen Schnittstelle jedes Edgeserver ist ein einzelnes Zertifikat erforderlich. Zertifikate für die interne Schnittstelle können von einer internen Zertifizierungsstelle (Enterprise Certification Authority, ca) oder einer öffentlichen Zertifizierungsstelle ausgestellt werden. Wenn Ihre Organisation über eine interne Zertifizierungsstelle verfügt, können Sie auf Kosten der Verwendung öffentlicher Zertifikate sparen, indem Sie die interne Zertifizierungsstelle verwenden, um das Zertifikat für die interne Schnittstelle auszustellen. Sie können eine interne Windows Server 2008-Zertifizierungsstelle oder eine Windows Server 2008 R2-Zertifizierungsstelle zum Erstellen dieser Zertifikate verwenden.

Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Gehen Sie wie folgt vor, um Zertifikate auf der Schnittstelle für den internen Edge an einer Website einzurichten:

1.  Laden Sie die Zertifizierungsstellen Zertifizierungsstelle für die interne Schnittstelle für jeden Edgeserver herunter.

2.  Importieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle auf jedem Edge-Server.

3.  Erstellen Sie die Zertifikatanforderung für die interne Schnittstelle auf einem Edgeserver, dem sogenannten First Edge-Server.

4.  Importieren Sie das Zertifikat für die interne Schnittstelle auf dem First Edge-Server.

5.  Importieren Sie das Zertifikat auf den anderen Edgeserver auf dieser Website (oder hinter diesem Lastenausgleichsmodul bereitgestellt).

6.  Weisen Sie das Zertifikat für die interne Schnittstelle jedes Edgeserver zu.

Wenn Sie mehr als eine Website mit Edgeserver (also einer mehrseitigen Edge-Topologie) oder getrennte Gruppen von Edgeserver haben, die hinter unterschiedlichen Lastenausgleichs Servern bereitgestellt werden, müssen Sie diese Schritte für jede Website mit Edgeserver und für jede Gruppe von Edgeserver ausführen. wird hinter einem anderen Load Balancer bereitgestellt.

<div>


> [!NOTE]  
> Die Schritte für die Verfahren in diesem Abschnitt basieren auf der Verwendung einer Windows&nbsp;Server 2008-Zertifizierungs&nbsp;Stelle&nbsp;, einer Windows Server 2008 R2-Zertifizierungsstelle, einer Windows Server 2012-Zertifizierungsstelle oder einer Windows Server 2012 R2-Zertifizierungsstelle zum Erstellen eines Zertifikats für jeden Edgeserver. Eine Schritt-für-Schritt-Anleitung für jede andere Zertifizierungsstelle finden Sie in der Dokumentation für diese Zertifizierungsstelle. Standardmäßig verfügen alle authentifizierten Benutzer über die entsprechenden Benutzerrechte zum Anfordern von Zertifikaten.<BR>Die Verfahren in diesem Abschnitt basieren auf dem Erstellen von Zertifikatanforderungen auf dem Edgeserver als Teil des Edgeserver-Bereitstellungsprozesses. Es ist möglich, Zertifikatanforderungen mit dem Front-End-Server zu erstellen. Sie können dies tun, um die Zertifikatanforderung zu einem frühen Zeitpunkt des Planungs-und Bereitstellungsprozesses abzuschließen, bevor Sie die Bereitstellung der Edgeserver starten. Dafür müssen Sie sicherstellen, dass das von Ihnen angeforderte Zertifikat mit einem exportierbaren privaten Schlüssel definiert ist.<BR>Die Verfahren in diesem Abschnitt beschreiben die Verwendung einer CER-und einer P7B-Datei für das Zertifikat. Wenn Sie einen anderen Dateityp verwenden, ändern Sie diese Verfahren nach Bedarf.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>So laden Sie die Zertifizierungsstellen Zertifizierungsstelle für die interne Schnittstelle mithilfe der CertSrv-Website herunter

1.  Melden Sie sich bei einem lync Server 2013-Server im internen Netzwerk (also nicht beim Edgeserver) als Mitglied der Gruppe **Administratoren** an.

2.  Führen Sie den folgenden Befehl an einer Eingabeaufforderung aus, indem Sie auf **Start**und dann auf **Ausführen**klicken und dann Folgendes eingeben:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Beispiel:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine Windows Server 2008-oder Windows Server 2008 R2 Enterprise-Zertifizierungsstelle verwenden, müssen Sie HTTPS und nicht http verwenden.

    
    </div>

3.  Klicken Sie auf der CertSrv-Webseite der ausstellenden Zertifizierungsstelle unter **Aufgabe auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatssperrliste**.

4.  Klicken Sie unter **Herunterladen eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer CRL**auf Zertifizierungsstellen **Zertifikatkette herunterladen**.

5.  Klicken Sie im Dialogfeld **Datei Download** auf **Speichern**.

6.  Speichern Sie die P7B-Datei auf dem Festplattenlaufwerk auf dem Server, und kopieren Sie Sie dann in einen Ordner auf jedem Edgeserver.
    
    <div>
    

    > [!NOTE]  
    > Die P7B-Datei enthält alle Zertifikate, die im Zertifizierungspfad enthalten sind. Wenn Sie den Zertifizierungspfad anzeigen möchten, öffnen Sie das Serverzertifikat, und klicken Sie auf den Zertifizierungspfad.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>So exportieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle mithilfe von MMC

1.  Mit der Microsoft Management Console (MMC) können Sie das Zertifizierungsstellen-Stammzertifikat von einem beliebigen, mit der Domäne verbundenen Computer exportieren. Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie dann **MMC**ein.

2.  Klicken Sie in der MMC-Konsole auf **Datei**, klicken Sie auf **hinzufügen/entfernen**.

3.  Wählen Sie in der Dialogliste **Snap-Ins hinzufügen oder entfernen** die Option **Zertifikate**aus, und klicken Sie dann auf **Hinzufügen**. Wenn Sie dazu aufgefordert werden, wählen Sie **Computer Konto**aus. Wählen Sie im Dialogfeld **Computer auswählen** die Option **lokaler Computer**aus. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**.

4.  Erweitern Sie **Zertifikate (lokaler Computer)**. Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und wählen Sie **Zertifikate**aus.

5.  Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie **alle Aufgaben**, und wählen Sie **exportieren**aus. Der **Zertifikat Export-Assistent** wird geöffnet.

6.  Klicken Sie im **Zertifikat Export-Assistenten**auf **weiter**.

7.  Wählen Sie im Dialogfeld **Dateiformat exportieren** ein Format aus, in das exportiert werden soll. Wir empfehlen die **Syntax Standard für kryptografische Nachrichten \#– PKCS 7-Zertifikate (. P7B)**. Wenn Sie die **Syntax Standard für kryptografische Nachrichten auswählen \#– PKCS 7-Zertifikate (. P7B)**, aktivieren Sie das Kontrollkästchen **alle Zertifikate in den Zertifizierungspfad einbeziehen, wenn möglich** , um die Zertifikatkette zu exportieren, einschließlich des Zertifikats der Stammzertifizierungsstelle und aller Zwischenzertifizierungsstellen Zertifikate. Klicken Sie auf **Weiter**.

8.  Geben Sie im Dialogfeld **Datei zum Exportieren** in den Dateinamen Eintrag einen Pfad und Dateinamen (die Standarderweiterung ist P7B) für das exportierte Zertifikat ein. Klicken Sie optional auf **Durchsuchen**, suchen Sie ein Verzeichnis, in dem das exportierte Zertifikat platziert werden soll, und geben Sie einen Namen für das exportierte Zertifikat an. Klicken Sie auf **Speichern**. Klicken Sie auf **Weiter**.

9.  Überprüfen Sie die Zusammenfassung der Aktionen, und klicken Sie auf **Fertig stellen** , um den Export des Zertifikats abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>So importieren Sie die Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle

1.  Öffnen Sie auf jedem Edgeserver die Microsoft Management Console (MMC), indem Sie auf **Start**klicken, auf **Ausführen**klicken, **MMC** in das Feld **Öffnen** eingeben und dann auf **OK**klicken.

2.  Klicken Sie im Menü **Datei** auf **Snap-in hinzufügen/entfernen**, und klicken Sie dann auf **Hinzufügen**.

3.  Klicken Sie im Feld **eigenständige Snap-Ins hinzufügen** auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.

4.  Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.

5.  Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

6.  Klicken Sie auf **Schließen**, und klicken Sie dann auf **OK**.

7.  Erweitern Sie in der Konsolenstruktur **Zertifikate (lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen**, zeigen Sie auf **alle Aufgaben**, und klicken Sie dann auf **importieren**.

8.  Geben Sie im Assistenten in **zu importierende Datei**den Dateinamen des Zertifikats an (also den Namen, den Sie beim Herunterladen der Zertifizierungsstellen-Zertifizierungskette für die interne Schnittstelle im vorherigen Verfahren angegeben haben).

9.  Wiederholen Sie diesen Vorgang auf jedem Edgeserver.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>So erstellen Sie die Zertifikatanforderung für die interne Schnittstelle

1.  Starten Sie auf einem der Edgeserver den Bereitstellungs-Assistenten, und klicken Sie neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **Ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie über mehrere Edgeserver an einem Speicherort in einem Pool verfügen, können Sie den Zertifikat-Assistenten auf einem beliebigen Edgeserver ausführen.<BR>Nachdem Sie Schritt 3 beim ersten Mal ausgeführt haben, wird die Schaltfläche <STRONG>erneut ausgeführt</STRONG>, und ein grünes Häkchen, das den erfolgreichen Abschluss des Vorgangs angibt, wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.

    
    </div>

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **weiter**.

4.  Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.

5.  Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen ein, zu dem die Anforderung gespeichert werden soll (beispielsweise **c\\: CERT\_Internal\_Edge. CER**).

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.

7.  Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:
    
      - Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein (beispielsweise interner Rand).
    
      - Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von **2048**) an.
        
        <div>
        

        > [!NOTE]  
        > Höhere Bit-Längen bieten mehr Sicherheit, wirken sich aber negativ auf die Geschwindigkeit aus.

        
        </div>
    
      - Wenn das Zertifikat exportierbar sein muss, aktivieren Sie das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** .

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit (z. b. eine Abteilung oder Abteilung) ein.

9.  Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.

10. Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen.

11. Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.

12. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden.

13. Führen Sie nach Abschluss der Befehle die folgenden Aktionen aus:
    
      - Wenn Sie das Protokoll für die Zertifikatanforderung anzeigen möchten, klicken Sie auf **Protokoll anzeigen**.
    
      - Klicken Sie auf **weiter**, um die Zertifikatanforderung abzuschließen.

14. Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Aktionen aus:
    
      - Klicken Sie zum Anzeigen der generierten CSR-Datei (Certificate Signing Request) auf **Ansicht**.
    
      - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

15. Senden Sie diese Datei an Ihre Zertifizierungsstelle (per e-Mail oder einer anderen von Ihrer Organisation unterstützten Methode für Ihre Unternehmenszertifizierungsstelle), und kopieren Sie das neue Zertifikat, wenn Sie die Antwortdatei erhalten, auf diesen Computer, damit es für den Import verfügbar ist.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>So importieren Sie das Zertifikat für die interne Schnittstelle

1.  Melden Sie sich bei dem Edgeserver an, auf dem Sie die Zertifikatanforderung als Mitglied der lokalen Gruppe Administratoren erstellt haben.

2.  Klicken Sie im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.
    
    Nachdem Sie Schritt 3 beim ersten Mal ausgeführt haben, wird die Schaltfläche **erneut in ausführen**geändert, aber ein grünes Häkchen (das den erfolgreichen Abschluss des Vorgangs angibt) wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.

3.  Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **Zertifikat aus a importieren. P7B, PFX-oder CER-Datei**.

4.  Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und den Dateinamen des Zertifikats ein, das Sie für die interne Schnittstelle dieses Edgeserver angefordert und empfangen haben (oder klicken Sie auf **Durchsuchen** , um die Datei zu suchen und auszuwählen).

5.  Wenn Sie Zertifikate für andere Mitglieder des Pools ein Zertifikat mit einem privaten Schlüssel importieren, aktivieren Sie das Kontrollkästchen **Zertifikatsdatei enthält den privaten Schlüsselzertifikat** , und geben Sie das Kennwort an.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool

1.  Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie das Zertifikat importiert haben.

2.  Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie **MMC**ein.

3.  Klicken Sie in der MMC-Konsole auf **Datei**, und klicken Sie auf **Snap-in hinzufügen/entfernen**.

4.  Klicken Sie auf der Seite Snap-Ins hinzufügen oder entfernen auf **Zertifikate**, und klicken Sie auf **Hinzufügen**.

5.  Wählen Sie im Dialogfeld Zertifikate-Snap-in die Option **Computer Konto**aus. Klicken Sie auf **Weiter**. Wählen Sie unter Computer auswählen **die Option Lokaler Computer aus: (der Computer, auf dem diese Konsole ausgeführt wird)**. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.

6.  Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **persönlich**, und doppelklicken Sie dann auf **Zertifikate**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn im persönlichen Zertifikatspeicher für den lokalen Computer keine Zertifikate vorhanden sind, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Schritte zum Anfordern und importieren. Wenn das Problem weiterhin besteht, wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.

    
    </div>

7.  Klicken Sie im persönlichen Zertifikatspeicher des lokalen Computers mit der rechten Maustaste auf das Zertifikat, das Sie exportieren möchten. Klicken Sie auf **alle Aufgaben**, und klicken Sie auf **exportieren**.

8.  Klicken Sie im Zertifikat Export-Assistenten auf **weiter**. Wählen Sie **Ja aus, exportieren Sie den privaten Schlüssel**. Klicken Sie auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Wenn die Auswahl <STRONG>Ja, privater Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der dem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert. Sie müssen das Zertifikat erneut anfordern, um sicherzustellen, dass das Zertifikat markiert ist, damit der Export des privaten Schlüssels zugelassen wird, bevor Sie den Export fortsetzen können. Wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.

    
    </div>

9.  Wählen Sie im Dialogfeld Dateiformate exportieren den Eintrag **Personal Information Exchange\#– PKCS 12 (. PFX)** , und wählen Sie dann die folgenden Optionen aus:
    
      - Nach Möglichkeit alle Zertifikate in den Zertifizierungspfad einbeziehen
    
      - Exportieren aller erweiterten Eigenschaften
        
        <div>
        

        > [!WARNING]  
        > Wenn Sie das Zertifikat von einem Edgeserver exportieren, wählen Sie <STRONG>den privaten Schlüssel nicht löschen aus, wenn der Export erfolgreich ist</STRONG>. Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.

        
        </div>
    
    Klicken Sie auf **Weiter**, um fortzufahren.

10. Wenn Sie zum Schützen des privaten Schlüssels ein Kennwort zuweisen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein. Klicken Sie auf **Weiter**.

11. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung .pfx verwenden. Der Pfad muss entweder für alle anderen Edgeserver im Pool zugänglich sein oder über Wechselmedien zur Verfügung stehen, beispielsweise einen USB-Speicherstick. Klicken Sie auf **Weiter**.

12. Überprüfen Sie die Zusammenfassung im Dialogfeld zum Abschließen des Zertifikat Export-Assistenten. Klicken Sie auf **Fertig stellen**.

13. Klicken Sie im Dialogfeld „Export erfolgreich“ auf **OK**.

14. Importieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und führen Sie die Schritte aus, die in den Verfahren zum [Einrichten von Zertifikaten für die externe Edge-Schnittstelle für lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) beschrieben sind.

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>So weisen Sie das interne Zertifikat auf den Edgeserver zu

1.  Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.

2.  Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **vorhandenes Zertifikat zuweisen**.

3.  Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Interner Edgeserver** aus.

4.  Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie für den internen Edge importiert haben (aus dem vorherigen Verfahren).

5.  Überprüfen Sie auf der Seite **Certificate Assignment Summary** Ihre Einstellungen, und klicken Sie dann auf **weiter** , um die Zertifikate zuzuweisen.

6.  Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.

7.  Nachdem Sie dieses Verfahren zum Zuweisen des internen Edge-Zertifikats verwendet haben, öffnen Sie das Zertifikat-Snap-in auf jedem Server, erweitern Sie **Zertifikate (lokaler Computer)**, erweitern Sie **Personal**, klicken Sie auf **Zertifikate**, und überprüfen Sie dann im Detailbereich, dass das Zertifikat für internes Edge wird aufgelistet.

8.  Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie diesen Vorgang für jeden Edgeserver.

</div>

</div>

<span> </span>

</div>

</div>

</div>

