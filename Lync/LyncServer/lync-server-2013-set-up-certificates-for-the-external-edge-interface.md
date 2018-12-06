---
title: 'Lync Server 2013: Einrichten der Zertifikate für die externe Edgeschnittstelle'
TOCTitle: Einrichten der Zertifikate für die externe Edgeschnittstelle
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398409(v=OCS.15)
ms:contentKeyID: 49294142
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten der Zertifikate für die externe Edgeschnittstelle für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_


> [!IMPORTANT]
> Wenn Sie den Zertifikat-Assistenten ausführen, müssen Sie mit einem Konto angemeldet sein, das Mitglied einer Gruppe ist, die über die entsprechenden Berechtigungen für den von Ihnen verwendeten Zertifikatvorlagentyp verfügt. Für eine Lync Server -Zertifikatanforderung wird standardmäßig die Webserver-Zertifikatvorlage verwendet. Wenn Sie ein Konto verwenden, das Mitglied der RTCUniversalServerAdmins-Gruppe ist, kann mit dieser Vorlage nur ein Zertifikat angefordert werden, wenn dieser Gruppe die zum Verwenden dieser Vorlage erforderlichen Registrierungsberechtigungen erteilt wurden.



Jeder Edgeserver benötigt ein öffentliches Zertifikat für die Schnittstelle zwischen dem Umkreisnetzwerk und dem Internet. Der alternative Antragstellername des Zertifikats muss die externen Namen des Zugriffs-Edgediensts und die vollqualifizierten Domänennamen des Webkonferenz-Edgediensts enthalten.

Ausführliche Informationen zu diesen und anderen Voraussetzungen für Zertifikate finden Sie unter [Zertifikatanforderungen für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Eine Liste öffentlicher Zertifizierungsstellen, die Zertifikate bereitstellen, die den speziellen Anforderungen an Unified Communications-Zertifikate entsprechen und eine Partnerschaft mit Microsoft eingegangen sind, um sicherzustellen, dass ihre Zertifikate mit dem Zertifikat-Assistenten von Lync Server 2013 verwendet werden können, finden Sie im Microsoft Knowledge Base-Artikel 929395, "Partner für Unified Communications-Zertifikate für Exchange Server und Communications Server", unter [http://go.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).

## Konfigurieren von Zertifikaten für die externen Schnittstellen

Führen Sie die Schritte in diesem Abschnitt aus, um ein Zertifikat für die externe Edgeschnittstelle an einem Standort einzurichten:

  - Erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edgeservers.

  - Senden Sie die Anforderung an die öffentliche Zertifizierungsstelle.

  - Importieren Sie das Zertifikat für die externe Schnittstelle jedes Edgeservers.

  - Weisen Sie das Zertifikat für die externe Schnittstelle jedem Edgeserver zu.

  - Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, exportieren Sie das Zertifikat gemeinsam mit seinem privaten Schlüssel, und kopieren Sie es auf die anderen Edgeserver. Importieren Sie das Zertifikat anschließend für jeden Edgeserver, und weisen Sie es wie zuvor beschrieben zu. Wiederholen Sie dieses Verfahren für jeden Edgeserver.

Sie können öffentliche Zertifikate direkt von einer öffentlichen Zertifizierungsstelle anfordern (z. B. über die Website einer öffentlichen Zertifizierungsstelle). Bei den Verfahren in diesem Abschnitt wird für die meisten Aufgaben im Zusammenhang mit Zertifikaten der Zertifikat-Assistent verwendet. Wenn Sie ein Zertifikat direkt von einer öffentlichen Zertifizierungsstelle anfordern, ändern Sie die einzelnen Vorgehensweisen zum Anfordern, Transportieren und Importieren des Zertifikats sowie zum Importieren der Zertifikatkette entsprechend.

Wenn Sie ein Zertifikat von einer externen Zertifizierungsstelle anfordern, müssen die angegebenen Anmeldeinformationen mit den erforderlichen Rechten zum Anfordern eines Zertifikats von dieser Zertifizierungsstelle verknüpft sein. Jede Zertifizierungsstelle verfügt über eine Sicherheitsrichtlinie zur Definition, über welche Anmeldeinformationen (also bestimmte Benutzer- und Gruppennamen) Zertifikate angefordert, ausgestellt, verwaltet oder gelesen werden dürfen.

Wenn Sie die Microsoft Management Console (MMC) zum Importieren der Zertifikatkette und des Zertifikats verwenden, müssen Sie diese Elemente in den Zertifikatspeicher für den Computer importieren. Wenn Sie diese Elemente in den Zertifikatspeicher des Benutzers oder Diensts importieren, kann das Zertifikat nicht im Zertifikat-Assistenten von Lync Server 2013 zugewiesen werden.

## So erstellen Sie die Zertifikatanforderung für die externe Schnittstelle des Edgeservers

1.  Klicken Sie auf dem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen** .
    

    > [!NOTE]
    > Wenn Ihre Organisation Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL unterstützen möchte, können Sie das Zertifikat nicht mit dem Lync Server-Bereitstellungs-Assistenten anfordern. Führen Sie stattdessen das weiter unten in diesem Thema beschriebene Verfahren "So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Sofortnachrichtendiensten über AOL" aus.<BR>Wenn Sie an einem Standort über mehrere Edgeserver in einem Pool verfügen, können Sie den Lync Server 2013-Zertifikat-Assistenten auf jedem dieser Edgeserver ausführen.



2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Neue Zertifikatsanforderung erstellen** .

3.  Klicken Sie auf der Seite **Zertifikatsanforderung** auf **Externes Edgezertifikat** .

4.  Aktivieren Sie auf der Seite **Verzögerte oder sofortige Anforderungen** das Kontrollkästchen **Anforderung jetzt vorbereiten, jedoch später senden** .

5.  Geben Sie auf der Seite **Zertifikatsanforderungsdatei** den vollständigen Pfad und Namen der Datei ein, in der die Anforderung gespeichert werden soll (Beispiel: c:\\cert\_exernal\_edge.cer ).

6.  Aktivieren Sie auf der Seite **Alternative Zertifikatvorlage angeben** das Kontrollkästchen **Alternative Zertifikatvorlage für ausgewählte Zertifizierungsstelle verwenden** , um eine andere Vorlage als die Standardvorlage "WebServer" zu verwenden.

7.  Führen Sie auf der Seite **Namens- und Sicherheitseinstellungen** die folgenden Aufgaben aus:
    
      - Geben Sie im Feld **Anzeigename** einen Anzeigenamen für das Zertifikat ein.
    
      - Geben Sie in **Bitlänge** die Bitlänge ein (typischerweise wird der Standardwert **2048** verwendet).
    
      - Stellen Sie sicher, dass das Kontrollkästchen **Privaten Schlüssel des Zertifikats als exportierbar markieren** aktiviert ist.

8.  Geben Sie auf der Seite **Organisationsinformationen** den Namen für die Organisation und Organisationseinheit ein (z. B. eine Gruppe oder Abteilung).

9.  Geben Sie auf der Seite **Geografische Informationen** die Standortinformationen ein.

10. Auf der Seite **Antragstellernamen/Alternative Antragstellernamen** werden die Informationen angezeigt, die automatisch vom Assistenten aufgefüllt werden. Wenn zusätzliche alternative Antragstellernamen erforderlich sind, werden diese in den nächsten zwei Schritten angegeben.

11. Wählen Sie auf der Seite **SIP-Domäneneinstellung für alternative Antragstellernamen** das Kontrollkästchen der Domäne, um einen Eintrag "sip. *\<SIP-Domäne\>* " zur Liste der alternativen Antragstellernamen hinzuzufügen.

12. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzliche alternative Antragstellernamen an, die benötigt werden.

13. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Zertifikatinformationen, die zum Generieren der Anforderung verwendet werden sollen.

14. Nachdem die Befehle ausgeführt wurden, führen Sie die folgenden Aufgaben aus:
    
      - Zum Anzeigen des Protokolls für die Zertifikatanforderung klicken Sie auf **Protokoll anzeigen** .
    
      - Klicken Sie auf **Weiter** , um die Zertifikatanforderung abzuschließen.

15. Führen Sie auf der Seite **Zertifikatanforderungsdatei** die folgenden Schritte aus:
    
      - Zum Anzeigen der generierten CSR-Datei (Certificate Signing Request, Zertifikatsignieranforderung) klicken Sie auf **Anzeigen** .
    
      - Klicken Sie auf **Fertig stellen** , um den Assistenten zu schließen.

16. Kopieren Sie die Ausgabedatei an einen Speicherort, von dem aus Sie diese an die öffentliche Zertifizierungsstelle übermitteln können.

## So erstellen Sie eine Zertifikatanforderung für die externe Schnittstelle des Edgeservers zur Unterstützung von Verbindungen mit öffentlichen Instant Messaging-Diensten über AOL

1.  Wenn die erforderliche Vorlage für die Zertifizierungsstelle zur Verfügung gestellt wurde, verwenden Sie auf dem Edgeserver das folgende Cmdlet der Windows PowerShell, um das Zertifikat anzufordern:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Der standardmäßige Zertifikatname der in Lync Server 2013 bereitgestellten Vorlage lautet "Web Server". Geben Sie *\<Vorlagenname\>* nur an, wenn eine andere Vorlage verwendet werden muss als die Standardvorlage.
    

    > [!NOTE]
    > Wenn Ihre Organisation die Verbindung mit öffentlichen Instant Messaging-Diensten über AOL unterstützen möchte, müssen Sie anstelle des Zertifikat-Assistenten die Windows PowerShell zum Anfordern des Zertifikats verwenden, das dem externen Edge für den Zugriffs-Edgedienst zugewiesen werden soll. Der Grund dafür ist, dass die Lync Server 2013-Vorlage "Web Server", die der Zertifikat-Assistent zum Anfordern von Zertifikaten verwendet, keine EKU-Clientkonfiguration unterstützt. Vor der Verwendung der Windows PowerShell zum Erstellen des Zertifikats muss der Administrator der Zertifizierungsstelle eine neue Vorlage mit Unterstützung für Client-EKU erstellen und bereitstellen.



## So übermitteln Sie eine Anforderung an eine öffentliche Zertifizierungsstelle

1.  Öffnen Sie die Ausgabedatei.

2.  Kopieren Sie den Inhalt der Signieranforderung für das Zertifikat, und fügen Sie ihn ein.

3.  Geben Sie nach Aufforderung Folgendes an:
    
      - **Microsoft** als Serverplattform.
    
      - **IIS** als Version.
    
      - **Web Server** als Verwendungstyp.
    
      - **PKCS7** als Antwortformat.

4.  Wenn die öffentliche Zertifizierungsstelle Ihre Informationen überprüft hat, erhalten Sie eine E-Mail mit dem erforderlichen Text für das Zertifikat.

5.  Kopieren Sie den Text aus der E-Mail, und speichern Sie ihn in einer Textdatei (TXT-Datei) auf Ihrem lokalen Computer.

## So importieren Sie das Zertifikat für die externe Schnittstelle des Edgeservers

1.  Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie die Zertifikatanforderung erstellt haben.

2.  Klicken Sie im Bereitstellungs-Assistenten auf der Seite **Edgeserver bereitstellen** neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen** .

3.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Zertifikat aus einer P7B-, PFX- oder CER-Datei importieren** .

4.  Klicken Sie auf der Seite **Zertifikat importieren** auf **Durchsuchen** , um das Zertifikat zu finden und auszuwählen, das Sie für die externe Schnittstelle des Edgeservers angefordert haben (oder geben Sie den vollständigen Pfad und Dateinamen ein). Wenn das Zertifikat einen privaten Schlüssel enthält, aktivieren Sie das Kontrollkästchen **Zertifikatdatei enthält den privaten Schlüssel des Zertifikats** , und geben Sie das Kennwort für den privaten Schlüssel ein. Klicken Sie dann auf **Weiter** .

5.  Überprüfen Sie auf der Seite **Zertifikat importieren - Zusammenfassung** die Angaben, und klicken Sie dann auf **Weiter** .

6.  Überprüfen Sie auf der Seite **Befehle ausführen** die Ergebnisse des Imports, klicken Sie auf **Protokoll anzeigen** , um ggf. mehr Informationen einzublenden, und klicken Sie zum Abschließen des Zertifikatimports auf **Fertig stellen** .

7.  Wenn Sie einen Edgeserverpool konfigurieren, exportieren Sie das Zertifikat mit seinem privaten Schlüssel, wie im Verfahren "So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool" weiter unten in diesem Thema beschrieben. Kopieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, und importieren Sie sie in den Computerspeicher auf den einzelnen Edgeservern.

## So exportieren Sie das Zertifikat mit dem privaten Schlüssel für Edgeserver in einem Pool

1.  Melden Sie sich als Mitglied der Administratorgruppe bei demselben Edgeserver an, auf dem Sie das Zertifikat importiert haben.

2.  Klicken Sie auf **Start** , dann auf **Ausführen** , und geben Sie **MMC** ein.

3.  Klicken Sie in der Microsoft Management Console (MMC) auf **Datei** und dann auf **Snap-In hinzufügen/entfernen** .

4.  Klicken Sie in **Snap-Ins hinzufügen bzw. entfernen** auf **Zertifikate** und dann auf **Hinzufügen** .

5.  Wählen Sie im Dialogfeld **Zertifikate** den Eintrag **Computerkonto** aus, klicken Sie auf **Weiter** , wählen Sie unter **Computer auswählen** die Option **Lokaler Computer: (Computer, auf dem diese Konsole ausgeführt wird)** aus, klicken Sie auf **Fertig stellen** , und klicken Sie dann auf **OK** , um die Konfiguration der MMC-Konsole abzuschließen.

6.  Doppelklicken Sie auf **Zertifikate (Lokaler Computer)** , um die Zertifikatspeicher zu erweitern, doppelklicken Sie auf **Eigene Zertifikate** , und doppelklicken Sie dann auf **Zertifikate** .
    

    > [!IMPORTANT]
    > Wenn sich im Speicher <STRONG>Eigene Zertifikate</STRONG> für den lokalen Computer keine Zertifikate befinden, ist dem importierten Zertifikat kein privater Schlüssel zugeordnet. Überprüfen Sie die Anforderungs- und Importschritte. Besteht das Problem weiterhin, wenden Sie sich an den Administrator oder Anbieter für die Zertifizierungsstelle.



7.  Klicken Sie im Speicher **Eigene Zertifikate** für den lokalen Computer mit der rechten Maustaste auf das zu exportierende Zertifikat, klicken Sie auf **Alle Aufgaben** und dann auf **Exportieren** .

8.  Klicken Sie im Zertifikatexport-Assistenten auf **Weiter** , wählen Sie **Ja, privaten Schlüssel exportieren** aus, und klicken Sie dann auf **Weiter** .
    

    > [!NOTE]
    > Ist die Option <STRONG>Ja, privaten Schlüssel exportieren</STRONG> nicht verfügbar ist, wurde der diesem Zertifikat zugeordnete private Schlüssel nicht für den Export markiert. Si müssen das Zertifikat erneut anfordern. Dabei müssen Sie sicherstellen, dass das Zertifikat für den Export des privaten Schlüssels markiert ist, bevor Sie den Export fortsetzen können. Wenden Sie sich ggf. an den Administrator oder Anbieter für die Zertifizierungsstelle.



9.  Wählen Sie im Dialogfeld **Format der zu exportierenden Datei** die Option **Privater Informationsaustausch - PKCS\#12 (.PFX)** aus und wählen Sie dann Folgendes aus:
    
      - **Wenn möglich, alle Zertifikate im Zertifizierungspfad einbeziehen**
    
      - **Alle erweiterten Eigenschaften exportieren**
        

        > [!WARNING]
        > Wählen Sie beim Exportieren des Zertifikats von einem Edgeserver nicht die Option <STRONG>Privaten Schlüssel nach erfolgreichem Export löschen</STRONG> aus. Wenn Sie diese Option auswählen, müssen Sie das Zertifikat und den privaten Schlüssel auf diesen Edgeserver importieren.



10. Klicken Sie auf **Weiter** .

11. Geben Sie ein Kennwort für den privaten Schlüssel ein, geben Sie das Kennwort zur Bestätigung erneut ein, und klicken Sie dann auf **Weiter** .

12. Geben Sie einen Pfad und einen Dateinamen für das exportierte Zertifikat ein, wobei Sie die Dateierweiterung PFX verwenden. Für den Pfad gilt, dass entweder alle anderen Edgeserver in dem Pool darauf zugreifen können müssen, oder dass er für den Transport mittels Wechseldatenträger, z. B. USB-Stick, verfügbar ist. Klicken Sie auf **Weiter** .

13. Überprüfen Sie die Zusammenfassung im Dialogfeld **Fertigstellen des Assistenten** , und klicken Sie dann auf **Fertig stellen** .

14. Klicken Sie im Dialogfeld **Export erfolgreich** auf **OK** .

15. Importieren Sie die exportierte Zertifikatdatei auf die anderen Edgeserver, indem Sie das weiter oben in diesem Thema beschriebene Verfahren "So importieren Sie das Zertifikat für die externe Schnittstelle des Edgeservers" ausführen.

## So weisen Sie der externen Schnittstelle des Edgeservers das Zertifikat zu

1.  Klicken Sie auf jedem Edgeserver im Bereitstellungs-Assistenten neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Erneut ausführen** .

2.  Klicken Sie auf der Seite **Verfügbare Zertifikataufgaben** auf **Vorhandenes Zertifikat zuweisen** .

3.  Klicken Sie auf der Seite **Zertifikatzuweisung** auf **Externes Edgezertifikat** , und aktivieren Sie das Kontrollkästchen **Erweiterte Zertifikatverwendungen** .

4.  Aktivieren Sie auf der Seite **Erweiterte Zertifikatverwendungen** alle Kontrollkästchen, um das Zertifikat allen Verwendungen zuzuweisen.

5.  Wählen Sie auf der Seite **Zertifikatspeicher** das öffentliche Zertifikat aus, das Sie für die externe Schnittstelle dieses Edgeservers angefordert und importiert haben.
    

    > [!NOTE]
    > Wenn das angeforderte und importierte Zertifikat nicht in der Liste aufgeführt wird, stellen Sie sicher, dass der Antragstellername und die alternativen Antragstellernamen des Zertifikats alle Anforderungen für das Zertifikat erfüllen. Wenn Sie das Zertifikat und die Zertifikatkette nicht über die vorstehenden Verfahren, sondern manuell importiert haben, überprüfen Sie zudem, ob sich das Zertifikat im richtigen Zertifikatspeicher befindet (im Zertifikatspeicher des Computers, nicht des Benutzers oder Diensts).



6.  Überprüfen Sie auf der Seite **Zusammenfassung der Zertifikatzuweisung** die Einstellungen, und klicken Sie dann auf **Weiter** , um die Zertifikate zuzuweisen.

7.  Klicken Sie auf der Seite zum Abschließen des Assistenten auf **Fertig stellen** .

8.  Nachdem Sie das Edgezertifikat über diese Schritte zugewiesen haben, öffnen Sie auf jedem Server das Zertifikat-Snap-In, erweitern Sie den Eintrag **Zertifikate (Lokaler Computer)** sowie den Eintrag **Eigene Zertifikate** , und klicken Sie auf **Zertifikate** . Überprüfen Sie dann im Detailbereich, ob das Zertifikat aufgeführt ist.

9.  Wenn Ihre Bereitstellung mehrere Edgeserver umfasst, wiederholen Sie dieses Verfahren für jeden Edgeserver.

