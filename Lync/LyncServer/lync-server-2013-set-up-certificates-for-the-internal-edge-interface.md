---
title: 'Lync Server 2013: Einrichten von Zertifikaten für die interne Edge-Schnittstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34e1d0d4e87bffbf28ba600ab23d849fd664423
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Einrichten von Zertifikaten für die interne Edge-Schnittstelle in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

<div>


> [!IMPORTANT]  
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den zu verwendeten Zertifikatvorlagentyp verfügt. Standardmäßig wird für eine lync Server 2013 Zertifikatanforderung die Webserverzertifikatvorlage verwendet. Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.



</div>

Ein einzelnes Zertifikat ist für die interne Schnittstelle jedes Edgeservers erforderlich. Die Zertifikate für die interne Schnittstelle können von einer internen Unternehmenszertifizierungsstelle oder von einer öffentlichen Zertifizierungsstelle ausgestellt werden. Wenn Ihre Organisation eine interne Zertifizierungsstelle bereitstellt, können Sie die Ausgaben für die Verwendung öffentlicher Zertifikate einsparen, indem Sie das Zertifikat für die interne Schnittstelle von der internen Zertifizierungsstelle ausstellen lassen. Zum Erstellen dieser Zertifikate können Sie eine interne Windows Server 2008- oder Windows Server 2008 R2-Zertifizierungsstelle verwenden.

Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Certificate Requirements for external User Access in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Führen Sie die Schritte in diesem Abschnitt aus, um Zertifikate für die interne Edgeschnittstelle an einem Standort einzurichten:

1.  Laden Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle auf die einzelnen Edgeserver herunter.

2.  Importieren Sie die Zertifikatskette der Zertifizierungsstelle auf den einzelnen Edgeservern für die interne Schnittstelle.

3.  Erstellen Sie die Zertifikatanforderung für die interne Schnittstelle auf einem Edgeserver, der dann als erster Edgeserver bezeichnet wird.

4.  Importieren Sie das Zertifikat für die interne Schnittstelle auf dem ersten Edgeserver.

5.  Importieren Sie das Zertifikat auf den anderen Edgeservern an diesem Standort (bzw. auf Edgeservern, die hinter diesem Hardwaregerät zum Lastenausgleich bereitgestellt werden).

6.  Weisen Sie das Zertifikat für die interne Schnittstelle jedes Edgeservers zu.

Falls Sie über mehrere Standorte mit Edgeservern verfügen (also über eine Edgetopologie mit mehreren Standorten) oder falls Sie separate Gruppen von Edgeservern hinter verschiedenen Hardwaregeräten zum Lastenausgleich bereitstellen, müssen Sie diese Schritte für jeden Standort, der über Edgeserver verfügt, sowie für jede Gruppe von Edgeservern, die hinter einem Hardwaregerät zum Lastenausgleich bereitgestellt wird, separat ausführen.

<div>


> [!NOTE]  
> Die Schritte in diesem Abschnitt basieren auf der Verwendung einer Windows Server&nbsp;2008-Zertifizierungsstelle, einer&nbsp;Windows&nbsp;Server 2008 R2-Zertifizierungsstelle, Windows Server 2012 ca oder Windows Server 2012 R2-Zertifizierungsstelle, um ein Zertifikat für jede Edgeserver zu erstellen. Eine Schritt-für-Schritt-Anleitung für andere Zertifizierungsstellen finden Sie in der Dokumentation für die jeweilige Zertifizierungsstelle. Standardmäßig besitzen alle authentifizierten Benutzer die entsprechenden Benutzerrechte zum Anfordern von Zertifikaten.<BR>Die Verfahren in diesem Abschnitt basieren auf der Erstellung von Zertifikatanforderungen auf dem Edgeserver im Rahmen des Edgeserver-Bereitstellungsprozesses. Zertifikatanforderungen können mithilfe des Front-End-Servers erstellt werden. Dies ist möglich, um die Zertifikatanforderung zu einem frühen Zeitpunkt im Planungs- und Bereitstellungsprozess vor der Bereitstellung der Edgeserver abzuschließen. Hierzu müssen Sie sicherstellen, dass das angeforderte Zertifikat mit einem exportierbaren privaten Schlüssel definiert ist.<BR>Die Verfahren in diesem Abschnitt beschreiben die Verwendung einer CER- und einer P7B-Datei für das Zertifikat. Wenn Sie einen anderen Dateityp verwenden, ändern Sie diese Verfahren entsprechend ab.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>So laden Sie mithilfe der certsv-Website eine Zertifizierungskette der Zertifizierungstelle für die interne Schnittestelle herunter

1.  Melden Sie sich bei einem lync Server 2013 Server im internen Netzwerk (nicht im Edgeserver) als Mitglied der Gruppe **Administratoren** an.

2.  Führen Sie an einer Eingabeaufforderung den folgenden Befehl aus, indem Sie auf **Start** und dann auf **Ausführen** klicken und Folgendes eingeben:
    
        https://<name of your Issuing CA Server>/certsrv
    
    Beispiel:
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie eine Windows Server 2008- oder Windows Server 2008 R2-Unternehmenszertifizierungsstelle verwenden, müssen Sie "https" anstelle von "http" einsetzen.

    
    </div>

3.  Klicken Sie auf der CertSrv-Webseite der ausstellenden Zertifizierungsstelle unter **Aufgabe auswählen** auf **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste**.

4.  Klicken Sie unter **Download eines Zertifizierungsstellenzertifikats, einer Zertifikatkette oder einer Zertifikatsperrliste** auf **Download der Zertifizierungsstellen-Zertifikatkette**.

5.  Klicken Sie im Dialogfeld **Dateidownload** auf **Speichern**.

6.  Speichern Sie die P7B-Datei auf der Festplatte auf dem Server, und kopieren Sie die Datei dann in einen Ordner auf jedem Edgeserver.
    
    <div>
    

    > [!NOTE]  
    > Die P7B-Datei enthält alle Zertifikate, die sich unter dem Zertifizierungspfad befinden. Zum Anzeigen des Zertifizierungspfads öffnen Sie das Serverzertifikat, und klicken Sie auf den Zertifizierungspfad.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>So exportieren Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle mit der MMC

1.  Sie können das Stammzertifikat der Zertifizierungsstelle von einem beliebigen Computer mit der Microsoft Management Console (MMC) aus einem beliebigen Domänenbeitritt exportieren. Klicken Sie auf **Start** und dann auf **Ausführen**, und geben Sie dann **MMC** ein.

2.  Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Hinzufügen/Entfernen**.

3.  Wählen Sie in der Dialogfeldliste **Snap-Ins hinzufügen bzw. entfernen** den Eintrag **Zertifikate** aus, und klicken Sie dann auf **Hinzufügen**. Wählen Sie bei entsprechender Eingabeaufforderung **Computerkonto** aus. Wählen Sie im Dialogfeld **Computer auswählen** die Option **Lokaler Computer** aus. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK**.

4.  Erweitern Sie **Zertifikate (Lokaler Computer)**. Erweitern Sie **Vertrauenswürdige Stammzertifizierungsstellen**, und wählen Sie **Zertifikate** aus.

5.  Klicken Sie auf das von Ihrer Zertifizierungsstelle ausgestellte Stammzertifikat. Klicken Sie mit der rechten Maustaste auf das Zertifikat, wählen Sie **Alle Aufgaben** aus, und wählen Sie dann **Exportieren** aus. Daraufhin wird der **Zertifikatexport-Assistent** geöffnet.

6.  Klicken Sie im **Zertifikatexport-Assistenten** auf **Weiter**.

7.  Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** ein Format für den Export aus. Wir empfehlen die **Syntax Standard für kryptografische Nachrichten \#– PKCS 7-Zertifikate (. P7B)**. Wenn Sie die **Syntax Standard für kryptografische Nachrichten auswählen \#– PKCS 7-Zertifikate (. P7B)**, aktivieren Sie das Kontrollkästchen **alle Zertifikate im Zertifizierungspfad einschließen** , um die Zertifikatkette einschließlich Zertifikat der Stammzertifizierungsstelle und aller Zwischenzertifizierungsstellen Zertifikate zu exportieren. Klicken Sie auf **Weiter**.

8.  Geben Sie im Dialogfeld **Zu exportierende Datei** im Eingabefeld für den Dateinamen einen Pfad und Dateinamen (die Standarderweiterung lautet ".p7b") für das exportierte Zertifikat ein. Optional können Sie auf **Durchsuchen** klicken, ein Verzeichnis zum Speichern des exportierten Zertifikats suchen und einen Namen für das exportierte Zertifikat angeben. Klicken Sie auf **Speichern**. Klicken Sie auf **Weiter**.

9.  Überprüfen Sie die Zusammenfassung der Aktionen, und klicken Sie auf **Fertig stellen**, um den Zertifikatexport abzuschließen. Klicken Sie auf **OK**, um den erfolgreichen Export zu bestätigen.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>So importieren Sie die Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle

1.  Öffnen Sie auf jedem Edgeserver die MMC (Microsoft Management Console), indem Sie auf **Start** und dann auf **Ausführen** klicken, im Feld **Öffnen** den Befehl **mmc** eingeben und dann auf **OK** klicken.

2.  Klicken Sie im Menü **Datei** auf **Snap-In hinzufügen/entfernen** und dann auf **Hinzufügen**.

3.  Klicken Sie im Feld **Eigenständiges Snap-In hinzufügen** auf **Zertifikate** und anschließend auf **Hinzufügen**.

4.  Klicken Sie im Dialogfeld **Zertifikat-Snap-In** auf **Computerkonto** und anschließend auf **Weiter**.

5.  Stellen Sie im Dialogfeld **Computer auswählen** sicher, dass das Kontrollkästchen **Lokalen Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aktiviert ist, und klicken Sie dann auf **Fertig stellen**.

6.  Klicken Sie auf **Schließen** und dann auf **OK**.

7.  Erweitern Sie in der Konsolenstruktur den Eintrag **Zertifikate (Lokaler Computer)**, klicken Sie mit der rechten Maustaste auf **Vertrauenswürdige Stammzertifizierungsstellen** zeigen Sie auf **Alle Aufgaben**, und klicken Sie anschließend auf **Importieren**.

8.  Geben Sie im Assistenten unter **Zu importierende Datei** den Dateinamen des Zertifikats ein (also den Namen, den Sie im vorherigen Verfahren beim Herunterladen der Zertifikatskette der Zertifizierungsstelle für die interne Schnittstelle angegeben haben).

9.  Wiederholen Sie dieses Verfahren für jeden Edgeserver.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>So erstellen Sie die Zertifikatanforderung für die interne Schnittstelle

1.  Starten Sie auf einem der Edgeserver den Bereitstellungs-Assistenten, und klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Sie in einem Pool über mehrere Edgeserver an einem Standort verfügen, können Sie den Zertifikat-Assistenten auf jedem dieser Edgeserver ausführen.<BR>Nachdem Sie Schritt 3 erstmals ausgeführt haben, ändert sich die Schaltfläche in <STRONG>Erneut ausführen</STRONG>, und ein grünes Häkchen, das auf den erfolgreichen Abschluss der Aufgabe hinweist, wird erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.

    
    </div>

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatanforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter**.

4.  Klicken Sie auf der Seite **Verzögerte oder sofortige Anforderungen** auf **Anforderung jetzt vorbereiten, jedoch später senden**.

5.  Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Namen der Datei ein, in die die Anforderung gespeichert werden soll (beispielsweise **c:\\CERT\_Internal\_Edge. CER**).

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden**, um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

7.  Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:
    
      - Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein (Beispiel: Interner Edge).
    
      - Geben Sie in **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert **2048** verwendet).
        
        <div>
        

        > [!NOTE]  
        > Höhere Bitlängen bieten mehr Sicherheit, beeinträchtigen jedoch die Geschwindigkeit.

        
        </div>
    
      - Wenn das Zertifikat exportierbar sein muss, aktivieren Sie das Kontrollkästchen **Privaten Schlüssel des Zertifikats als "Exportierbar" markieren**.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

9.  Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.

10. Auf der Seite **Antragstellername/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden.

11. Geben Sie auf der Seite **Zusätzliche alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.

12. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

13. Nachdem die Befehle ausgeführt wurden, gehen Sie folgendermaßen vor:
    
      - Zum Anzeigen des Protokolls für die Zertifikatanforderung klicken Sie auf **Protokoll anzeigen**.
    
      - Klicken Sie auf **Weiter**, um die Zertifikatanforderung abzuschließen.

14. Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Schritte aus:
    
      - Zum Anzeigen der generierten CSR-Datei (Certificate Signing Request, Zertifikatsignieranforderung) klicken Sie auf **Anzeigen**.
    
      - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

15. Senden Sie diese Datei an die Zertifizierungsstelle (per E-Mail oder mit einer anderen von Ihrer Organisation für die Zertifizierungsstelle des Unternehmens unterstützten Methode), und kopieren Sie, nachdem Sie die Antwortdatei erhalten haben, das neue Zertifikat auf diesen Computer, sodass es für einen Import zur Verfügung steht.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>So importieren Sie das Zertifikat für die interne Schnittstelle

1.  Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.

2.  Klicken Sie im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.
    
    Nachdem Sie Schritt 3 erstmals ausgeführt haben, ändert sich die Schaltfläche in **Erneut ausführen**. Ein grünes Häkchen, das auf den erfolgreichen Abschluss der Aufgabe hinweist, wird jedoch erst angezeigt, wenn alle erforderlichen Zertifikate angefordert, installiert und zugewiesen wurden.

3.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren**.

4.  Geben Sie auf der Seite **Zertifikat importieren** den vollständigen Pfad und Dateinamen des Zertifikats an, das Sie für die interne Schnittstelle des Edgeservers angefordert und erhalten haben (oder klicken Sie auf **Durchsuchen**, um nach der Datei zu suchen und sie auszuwählen).

5.  Wenn Sie Zertifikate für andere Mitglieder des Pools importieren und ein Zertifikat einen privaten Schlüssel enthält, aktivieren Sie das Kontrollkästchen **Zertifikatdatei enthält den privaten Schlüssel des Zertifikats**, und geben Sie das Kennwort an.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool

1.  Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie das Zertifikat importiert haben.

2.  Klicken Sie auf **Start**, dann auf **Ausführen**, und geben Sie **MMC** ein.

3.  Klicken Sie in der MMC-Konsole auf **Datei** und dann auf **Snap-In hinzufügen/entfernen**.

4.  Klicken Sie auf der Seite Snap-Ins hinzufügen oder entfernen auf **Zertifikate**und anschließend auf **Hinzufügen**.

5.  Wählen Sie im Dialogfeld Zertifikat-Snap-in die Option **Computer Konto**aus. Klicken Sie auf **Weiter**. Wählen Sie unter Computer auswählen **die Option Lokaler Computer: (Computer, auf dem diese Konsole läuft)** aus. Klicken Sie auf **Fertig stellen**. Klicken Sie auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.

6.  Doppelklicken Sie auf **Zertifikate (Lokaler Computer)**, um die Zertifikatspeicher zu erweitern. Doppelklicken Sie auf **Eigene Zertifikate**, und doppelklicken Sie dann auf **Zertifikate**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn sich im Speicher Eigene Zertifikate für den lokalen Computer keine Zertifikate befinden, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Anforderungs- und Importschritte. Besteht das Problem weiterhin, wenden Sie sich an den Administrator oder Anbieter für die Zertifizierungsstelle.

    
    </div>

7.  Klicken Sie im Speicher Eigene Zertifikate für den lokalen Computer mit der rechten Maustaste auf das zu exportierende Zertifikat. Klicken Sie auf **Alle Aufgaben** und dann auf **Exportieren**.

8.  Klicken Sie im Zertifikatexport-Assistenten auf **Weiter**. Wählen Sie **Ja, privaten Schlüssel exportieren** aus, und klicken Sie dann auf **Weiter**.
    
    <div>
    

    > [!NOTE]  
    > Ist die Option <STRONG>Ja, privaten Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der diesem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert. Si müssen das Zertifikat erneut anfordern. Dabei müssen Sie sicherstellen, dass das Zertifikat für den Export des privaten Schlüssels markiert ist, bevor Sie den Export fortsetzen können. Wenden Sie sich ggf. an den Administrator oder Anbieter für die Zertifizierungsstelle.

    
    </div>

9.  Wählen Sie im Dialogfeld Dateiformate exportieren die Option **Personal Information Exchange\#– PKCS 12 (aus. PFX)** , und wählen Sie dann Folgendes aus:
    
      - Wenn möglich, alle Zertifikate im Zertifizierungspfad einbeziehen
    
      - Alle erweiterten Eigenschaften exportieren
        
        <div>
        

        > [!WARNING]  
        > Wählen Sie beim Exportieren des Zertifikats von einem Edgeserver nicht die Option <STRONG>Privaten Schlüssel nach erfolgreichem Export löschen</STRONG> aus. Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.

        
        </div>
    
    Klicken Sie auf **Weiter**, um den Vorgang fortzusetzen.

10. Wenn Sie zum Schutz des privaten Schlüssels ein Kennwort zuordnen möchten, geben Sie ein Kennwort für den privaten Schlüssel ein. Geben Sie das Kennwort zur Bestätigung erneut ein, und klicken Sie dann auf **Weiter**.

11. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung PFX verwenden. Für den Pfad gilt, dass entweder alle anderen Edgeserver in dem Pool darauf zugreifen können müssen, oder dass er für den Transport mittels Wechseldatenträger, z. B. USB-Stick, verfügbar ist. Klicken Sie auf **Weiter**.

12. Lesen Sie die Zusammenfassung im Dialogfeld abschließen des Assistenten für den Zertifikat Export. Klicken Sie auf **Fertig stellen**.

13. Klicken Sie im Dialogfeld Export erfolgreich auf **OK** .

14. Importieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, und führen Sie die Schritte aus, die in der [Benutzeroberfläche zum Einrichten von Zertifikaten für die externe edgedatei für lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) Verfahren beschrieben sind.

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>So weisen Sie das interne Zertifikat auf den Edgeservern zu

1.  Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen**.

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen**.

3.  Wählen Sie auf der Seite **Zertifikatzuweisung** in der Liste den Eintrag **Edge intern** aus.

4.  Wählen Sie auf der Seite **Zertifikatspeicher** das Zertifikat aus, das Sie (im vorherigen Verfahren) für den internen Edge importiert haben.

5.  Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen, und klicken Sie dann auf **Weiter**, um die Zertifikate zuzuweisen.

6.  Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.

7.  Nachdem Sie das interne Edgezertifikat über diese Schritte zugewiesen haben, öffnen Sie auf jedem Server das Zertifikat-Snap-In, erweitern Sie den Eintrag **Zertifikate (Lokaler Computer)** sowie den Eintrag **Eigene Zertifikate**, und klicken Sie auf **Zertifikate**. Überprüfen Sie dann im Detailbereich, ob das interne Edgezertifikat aufgeführt ist.

8.  Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie dieses Verfahren für jeden Edgeserver.

</div>

</div>

<span> </span>

</div>

</div>

</div>

