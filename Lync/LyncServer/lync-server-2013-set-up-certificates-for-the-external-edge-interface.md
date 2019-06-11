---
title: 'Lync Server 2013: Einrichten der Zertifikate für die externe Edgeschnittstelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cb33a91d6609f9109e6416f5688d1b2ddfb9ed
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Einrichten der Zertifikate für die externe Edgeschnittstelle für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

<div>


> [!IMPORTANT]  
> Wenn Sie den Zertifikat-Assistenten ausführen, stellen Sie sicher, dass Sie mit einem Konto angemeldet sind, das Mitglied einer Gruppe ist, der die entsprechenden Berechtigungen für den Typ der Zertifikatvorlage zugewiesen wurden, die Sie verwenden werden. Standardmäßig wird für eine lync Server-Zertifikatanforderung die Vorlage Webserverzertifikat verwendet. Wenn Sie ein Konto verwenden, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, um ein Zertifikat mithilfe dieser Vorlage anzufordern, stellen Sie sicher, dass der Gruppe die für die Verwendung dieser Vorlage erforderlichen Registrierungsberechtigungen zugewiesen wurden.



</div>

Jeder Edgeserver erfordert ein öffentliches Zertifikat auf der Schnittstelle zwischen dem Umkreisnetzwerk und dem Internet, und der Alternative Name des Zertifikats muss die externen Namen des Access Edge-Diensts und des Webkonferenz-Edgedienst vollständig enthalten qualifizierte Domänennamen (FQDNs).

Ausführliche Informationen zu diesen und anderen Zertifikatanforderungen finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Eine Liste der öffentlichen Zertifizierungsstellen, die Zertifikate zur Verfügung stellen, die bestimmte Anforderungen für Unified Communications-Zertifikate erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem lync Server 2013-Zertifikat-Assistenten funktionieren, finden Sie unter Microsoft Knowledge Base-Artikel 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server", [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)unter.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Konfigurieren von Zertifikaten für die externen Schnittstellen

Gehen Sie wie folgt vor, um ein Zertifikat für die externe Edge-Schnittstelle an einer Website einzurichten:

  - Erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edge-Servers.

  - Senden Sie die Anfrage an Ihre öffentliche Zertifizierungsstelle.

  - Importieren Sie das Zertifikat für die externe Schnittstelle jedes Edge-Servers.

  - Weisen Sie das Zertifikat für die externe Schnittstelle jedes Edgeserver zu.

  - Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, exportieren Sie das Zertifikat zusammen mit seinem privaten Schlüssel, und kopieren Sie es auf die anderen Edgeserver. Importieren Sie die Datei für jeden Edgeserver, und weisen Sie Sie wie zuvor beschrieben zu. Wiederholen Sie diesen Vorgang für jeden Edgeserver.

Sie können öffentliche Zertifikate direkt von einer öffentlichen Zertifizierungsstelle (etwa über die Website einer öffentlichen Zertifizierungsstelle) anfordern. Die Verfahren in diesem Abschnitt verwenden den Zertifikat-Assistenten für die meisten Zertifikataufgaben. Wenn Sie sich entschieden haben, ein Zertifikat direkt von einer öffentlichen Zertifizierungsstelle anzufordern, müssen Sie die einzelnen Verfahren entsprechend anpassen, um das Zertifikat anzufordern, zu transportieren und zu importieren sowie die Zertifikatkette zu importieren.

Wenn Sie ein Zertifikat von einer externen Zertifizierungsstelle anfordern, müssen die bereitgestellten Anmeldeinformationen Rechte besitzen, um ein Zertifikat von dieser Zertifizierungsstelle anzufordern. Jede Zertifizierungsstelle verfügt über eine Sicherheitsrichtlinie, die festlegt, welche Anmeldeinformationen (also bestimmte Benutzer-und Gruppennamen) Zertifikate anfordern, ausgeben, verwalten oder lesen dürfen.

Wenn Sie die Zertifikate Microsoft Management Console (MMC) zum Importieren der Zertifikatkette und des Zertifikats verwenden möchten, müssen Sie Sie in den Zertifikatspeicher für den Computer importieren. Wenn Sie Sie in den Benutzer-oder Dienstzertifikat Speicher importieren, steht das Zertifikat im lync Server 2013-Zertifikat-Assistenten nicht für die Zuweisung zur Verfügung.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>So erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edge-Servers

1.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihre Organisation Öffentliche Instant Messaging-Verbindungen (im) mit AOL unterstützen möchte, können Sie den lync Server-Bereitstellungs-Assistenten nicht verwenden, um das Zertifikat anzufordern. Führen Sie stattdessen die Schritte im Abschnitt "So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL" weiter unten in diesem Thema aus.<BR>Wenn Sie über mehrere Edgeserver an einem Speicherort in einem Pool verfügen, können Sie den lync Server 2013-Zertifikat-Assistenten auf einem der Edgeserver ausführen.

    
    </div>

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen**.

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **externes Zertifikat**.

4.  Aktivieren Sie auf der Seite **verzögerte oder sofortige Anforderung** das Kontrollkästchen **Anforderung jetzt vorbereiten, aber später senden** .

5.  Geben Sie auf der Seite **Zertifikatanforderungsdatei** den vollständigen Pfad und den Dateinamen der Datei ein, in der die Anforderung gespeichert werden soll (beispielsweise\\c\_: CERT,\_"Edge. cer").

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** für das Kontrollkästchen **Alternative Zertifikatvorlage für die ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die standardmäßige Webservervorlage zu verwenden.

7.  Gehen Sie auf der Seite **Name und Sicherheitseinstellungen** wie folgt vor:
    
      - Geben Sie unter Anzeige **Name**einen Anzeigenamen für das Zertifikat ein.
    
      - Geben Sie in **Bit length**die Bittiefe (in der Regel den Standardwert von **2048**) an.
    
      - Überprüfen Sie, ob das Kontrollkästchen **Zertifikat privater Schlüssel als exportierbar kennzeichnen** aktiviert ist.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und die Organisationseinheit ein (beispielsweise eine Abteilung oder Abteilung).

9.  Geben Sie auf der Seite **geographische Informationen** die Standortinformationen an.

10. Auf der Seite **Betreffname/Subject Alternative** Names werden die Informationen angezeigt, die automatisch vom Assistenten ausgefüllt werden sollen. Wenn zusätzliche Alternative Namen für Subjekte benötigt werden, geben Sie diese in den nächsten beiden Schritten an.

11. Aktivieren Sie in der **SIP-Domäneneinstellung auf der Seite Subject Alternate Names (SANs)** das Kontrollkästchen Domäne, um einen SIP hinzuzufügen. \<sipdomain\> -Eintrag in der Liste Subject Alternative Names.

12. Geben Sie auf der Seite **configure additional Subject Alternative Names** alle zusätzlichen alternativen Subjektnamen an, die erforderlich sind.

13. Überprüfen Sie auf der Seite **Anforderungszusammenfassung** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

14. Führen Sie nach Abschluss der Befehle die folgenden Aktionen aus:
    
      - Wenn Sie das Protokoll für die Zertifikatanforderung anzeigen möchten, klicken Sie auf **Protokoll anzeigen**.
    
      - Klicken Sie auf **weiter**, um die Zertifikatanforderung abzuschließen.

15. Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Aktionen aus:
    
      - Klicken Sie zum Anzeigen der generierten CSR-Datei (Certificate Signing Request) auf **Ansicht**.
    
      - Klicken Sie auf **Fertig stellen**, um den Assistenten zu schließen.

16. Kopieren Sie die Ausgabedatei an einen Speicherort, an den Sie Sie an die öffentliche Zertifizierungsstelle übermitteln können.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edge-Servers zur Unterstützung öffentlicher Chat Verbindungen mit AOL

1.  Wenn die erforderliche Vorlage für die Zertifizierungsstelle verfügbar ist, verwenden Sie das folgende Windows PowerShell-Cmdlet auf dem Edgeserver, um das Zertifikat anzufordern:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Der Standardzertifikat Name der Vorlage, die in lync Server 2013 bereitgestellt wird, ist Web Server. Geben Sie nur \<den Vorlagen\> Namen an, wenn Sie eine Vorlage verwenden möchten, die sich von der Standardvorlage unterscheidet.
    
    <div>
    

    > [!NOTE]  
    > Wenn Ihre Organisation öffentliche Chat Verbindungen mit AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten Windows PowerShell verwenden, um das Zertifikat anzufordern, das dem externen Edge für den Access Edge-Dienst zugewiesen werden soll. Der Grund hierfür ist, dass die vom Zertifikat-Assistenten zum Anfordern eines Zertifikats verwendete lync Server 2013-Webservervorlage die Client-EKU-Konfiguration nicht unterstützt. Bevor Sie Windows PowerShell zum Erstellen des Zertifikats verwenden, muss der CA-Administrator eine neue Vorlage erstellen und bereitstellen, die die Client-EKU unterstützt.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>So senden Sie eine Anforderung an eine öffentliche Zertifizierungsstelle

1.  Öffnen Sie die Ausgabedatei.

2.  Kopieren Sie den Inhalt der Certificate Signing Request (CSR), und fügen Sie ihn ein.

3.  Wenn Sie dazu aufgefordert werden, geben Sie Folgendes an:
    
      - **Microsoft** als Server Plattform.
    
      - **IIS** als Version.
    
      - **Web Server** als Verwendungstyp.
    
      - **PKCS7** als Antwortformat.

4.  Wenn die öffentliche Zertifizierungsstelle Ihre Informationen überprüft hat, erhalten Sie eine e-Mail-Nachricht mit Text, der für Ihr Zertifikat erforderlich ist.

5.  Kopieren Sie den Text aus der e-Mail-Nachricht, und speichern Sie den Inhalt in einer Textdatei (txt) auf dem lokalen Computer.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>So importieren Sie das Zertifikat für die externe Schnittstelle des Edge-Servers

1.  Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.

2.  Klicken Sie im Bereitstellungs-Assistenten auf der Seite **Edgeserver bereitstellen** neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.

3.  Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **Zertifikat aus einer P7B-, PFX-oder CER-Datei importieren**.

4.  Klicken Sie auf der Seite **Zertifikat importieren** auf **Durchsuchen** , um das Zertifikat zu suchen und auszuwählen, das Sie für die externe Schnittstelle des Edge-Servers angefordert haben (oder Sie können den vollständigen Pfad und den Dateinamen eingeben). Wenn das Zertifikat einen privaten Schlüssel enthält, wählen Sie **Zertifikatdatei enthält den privaten** Schlüssel des Zertifikats aus, und geben Sie das Kennwort für den privaten Schlüssel ein. Klicken Sie auf **Weiter**.

5.  Überprüfen Sie auf der Seite **Zertifikatzusammenfassung importieren** die Zusammenfassung, und klicken Sie dann auf **weiter**.

6.  Überprüfen Sie beim **Ausführen von Befehlen**die Ergebnisse des Imports, klicken Sie auf **Protokoll anzeigen** , wenn Sie weitere Informationen benötigen, und klicken Sie dann auf **Fertig stellen** , um den Zertifikatimport abzuschließen.

7.  Wenn Sie einen Edge-Server-Pool konfigurieren, exportieren Sie das Zertifikat mit seinem privaten Schlüssel, wie im Abschnitt "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" weiter unten in diesem Thema beschrieben. Kopieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und importieren Sie Sie in den Computerspeicher auf jedem Edgeserver.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool

1.  Melden Sie sich als Mitglied der Gruppe Administratoren auf dem gleichen Edgeserver an, auf dem Sie das Zertifikat importiert haben.

2.  Klicken Sie auf **Start**, klicken Sie auf **Ausführen**, und geben Sie **MMC**ein.

3.  Klicken Sie in der MMC-Konsole (Microsoft Management Console) auf **Datei**, und klicken Sie dann auf **Snap-in hinzufügen/entfernen**.

4.  Klicken Sie unter **Snap-Ins hinzufügen oder entfernen**auf **Zertifikate**, und klicken Sie dann auf **Hinzufügen**.

5.  Wählen Sie im Dialogfeld **Zertifikate** die Option **Computerkonto**aus, klicken Sie auf **weiter**, wählen Sie **lokaler Computer aus: (der Computer, auf dem diese Konsole ausgeführt wird)** klicken Sie auf Computer **auswählen**, klicken Sie auf **Fertig stellen** , und klicken Sie dann auf **OK** , um vollständige Konfiguration der MMC-Konsole.

6.  Doppelklicken Sie auf **Zertifikate (lokaler Computer)** , um die Zertifikatspeicher zu erweitern, doppelklicken Sie auf **persönlich**, und doppelklicken Sie dann auf **Zertifikate**.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn im persönlichen Zertifikatspeicher für den lokalen Computer keine Zertifikate vorhanden sind, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Schritte zum Anfordern und importieren. Wenn das Problem weiterhin besteht, wenden Sie sich an den Administrator oder Anbieter Ihrer Zertifizierungsstelle.

    
    </div>

7.  Klicken Sie im **persönlichen Zertifikatspeicher für den lokalen Computer**mit der rechten Maustaste auf das zu exportierende Zertifikat, klicken Sie auf **alle Vorgänge**, und klicken Sie dann auf **exportieren**.

8.  Klicken Sie im Zertifikat Export-Assistenten auf **weiter**, wählen Sie ja aus, **exportieren Sie den privaten Schlüssel**, und klicken Sie dann auf **weiter**.
    
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

10. Klicken Sie auf **Weiter**.

11. Geben Sie ein Kennwort für den privaten Schlüssel ein, geben Sie das Kennwort erneut ein, um es zu bestätigen, und klicken Sie dann auf **weiter**.

12. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung .pfx verwenden. Der Pfad muss entweder für alle anderen Edgeserver im Pool zugänglich sein oder über Wechselmedien zur Verfügung stehen, beispielsweise einen USB-Speicherstick. Klicken Sie auf **Weiter**.

13. Überprüfen Sie die Zusammenfassung im **Assistenten zum Abschließen des Zertifikat Exports**, und klicken Sie dann auf **Fertig stellen**.

14. Klicken Sie im Dialogfeld erfolgreichen Export auf **OK**.

15. Importieren Sie die exportierte Zertifikatsdatei auf die anderen Edgeserver, und folgen Sie den Schritten unter "So importieren Sie das Zertifikat für das externe Interface des Edge-Servers" weiter oben in diesem Thema.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>So weisen Sie das Zertifikat für die externe Schnittstelle des Edge-Servers zu

1.  Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten**auf **erneut ausführen**.

2.  Klicken Sie auf der Seite **Verfügbare Zertifikats Aufgaben** auf **vorhandenes Zertifikat zuweisen**.

3.  Klicken Sie auf der Seite **zertifikatzuweisung** auf **externes Zertifikat** , und aktivieren Sie das Kontrollkästchen **Erweiterte Zertifikatverwendung** .

4.  Aktivieren Sie auf der Seite **Erweiterte Zertifikatverwendung** alle Kontrollkästchen, um das Zertifikat für alle Verwendungszwecke zuzuweisen.

5.  Wählen Sie auf der Seite **Zertifikatspeicher** das öffentliche Zertifikat aus, das Sie für die externe Schnittstelle des Edge-Servers angefordert und importiert haben.
    
    <div>
    

    > [!NOTE]  
    > Wenn das angeforderte und importierte Zertifikat nicht in der Liste enthalten ist, besteht eine der Problembehebungsmethoden darin, zu überprüfen, ob der Antragstellername und der Alternative Name des Zertifikats alle Anforderungen für das Zertifikat erfüllen, und wenn Sie die Datei manuell importiert haben Zertifikat-und Zertifikatkette anstelle der vorhergehenden Vorgehensweisen, dass sich das Zertifikat im richtigen Zertifikatspeicher befindet (der Computerzertifikatspeicher, nicht der Benutzer oder Dienstzertifikat Speicher).

    
    </div>

6.  Überprüfen Sie auf der Seite **Certificate Assignment Summary** Ihre Einstellungen, und klicken Sie dann auf **weiter** , um die Zertifikate zuzuweisen.

7.  Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen**.

8.  Nachdem Sie dieses Verfahren zum Zuweisen des Edge-Zertifikats verwendet haben, öffnen Sie das Zertifikat-Snap-in auf jedem Server, erweitern Sie **Zertifikate (lokaler Computer)**, erweitern Sie **Personal**, klicken Sie auf **Zertifikate**, und überprüfen Sie dann im Detailbereich, dass der Zertifikat ist aufgelistet.

9.  Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie diesen Vorgang für jeden Edgeserver.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

