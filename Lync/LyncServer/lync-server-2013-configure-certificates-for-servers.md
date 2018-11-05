---
title: 'Lync Server 2013: Konfigurieren von Zertifikaten für Server'
TOCTitle: Konfigurieren von Zertifikaten für Server
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398995(v=OCS.15)
ms:contentKeyID: 49295673
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Zertifikaten für Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein, oder an Sie müssen geeignete Berechtigungen delegiert worden sein. Ausführliche Informationen zum Delegieren von Berechtigungen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md). In Abhängigkeit von Ihrer Organisation und den Anforderungen zum Anfordern von Zertifikaten sind möglicherweise weitere Gruppenmitgliedschaften erforderlich. Wenden Sie sich an die Gruppe, die Ihre Public Key-Infrastruktur-Zertifizierungsstelle verwaltet.


> [!NOTE]
> Lync Server 2013 bietet Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digestlängen von 224, 256, 384 oder 512 Bits) von Digesthash- und Signaturalgorithmen für Verbindungen von Clients, die neben Lync Phone Edition die Betriebssysteme Windows&nbsp;7, Windows Server&nbsp;2008&nbsp;R2, Windows Server&nbsp;2008, Windows Vista oder Windows&nbsp;XP ausführen. Damit der externe Zugriff über die SHA-2-Suite unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit einem Digest gleicher Bitlänge ausstellen kann.



> [!CAUTION]  
> Die Auswahl des verwendeten Hashdigests und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden sollen, sowie von den anderen Computern und Geräten, mit denen Clients und Server kommunizieren sollen, die ebenfalls imstande sein müssen, die im Zertifikat benutzten Algorithmen zu verwenden. Informationen zu den vom Betriebssystem und einigen Clientanwendungen Digestlängen finden Sie unter <a href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</a>.


Für jeden Standard Edition-Server oder Front-End-Server werden bis zu vier Zertifikate benötigt: das oAuthTokenIssuer -Zertifikat, ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat. Es ist jedoch möglich, mit geeigneten Einträgen für alternative Antragstellernamen ein einzelnes Standardzertifikat sowie das oAuthTokenIssuer -Zertifikat anzufordern und zuzuweisen. Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Anforderungen an Zertifikate für interne Server in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md). Ausführliche Informationen zum Anfordern, Zuweisen und Installieren des oAuthTokenIssuer -Zertifikats finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md).

Verwenden Sie das folgende Verfahren, um die Standard Edition-Server- oder Front-End-Server-Zertifikate anzufordern, zuzuweisen und zu installieren. Wiederholen Sie das Verfahren für jeden Front-End-Server.


> [!IMPORTANT]
> Im folgenden Verfahren wird beschrieben, wie Sie Zertifikate einer internen Public Key-Infrastruktur konfigurieren, die von Ihrer Organisation bereitgestellt wird. Zertifikatanforderungen werden in diesem Verfahren offline verarbeitet. Ausführliche Informationen zum Beziehen von Zertifikaten von einer öffentlichen Zertifizierungsstelle finden Sie unter <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Anforderungen an Zertifikate für interne Server in Lync Server 2013</A> in der Planungsdokumentation. Dieses Verfahren beschreibt außerdem, wie während der Einrichtung des Front-End-Servers Zertifikate angefordert, zugewiesen und installiert werden. Wenn Sie Zertifikate im Voraus angefordert haben (siehe Abschnitt <A href="lync-server-2013-request-certificates-in-advance-optional.md">Vorabanforderung von Zertifikaten (optional) für Lync Server 2013</A> in der vorliegenden Bereitstellungsdokumentation), oder Sie in Ihrer Organisation keine interne Public Key-Infrastruktur zum Anfordern von Zertifikaten verwenden, müssen Sie dieses Verfahren nach Bedarf anpassen.



## So konfigurieren Sie Zertifikate für einen Front-End-Server

1.  Klicken Sie im Lync Server-Bereitstellungs-Assistent auf **Ausführen** neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** .

2.  Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern** .

3.  Klicken Sie auf der Seite **Zertifikatanforderung** auf **Weiter** .

4.  Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.

5.  Aktivieren Sie auf der Seite **Zertifizierungsstelle auswählen** die Option **Zertifizierungsstelle aus der in der Umgebung gefundenen Liste auswählen** , und wählen Sie aus der Liste eine (durch Registrierung in den Active Directory-Domänendienste) bekannte Zertifizierungsstelle aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.

6.  Auf der Seite **Zertifizierungsstellenkonto** werden Sie zur Angabe von Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatanforderung bei der Zertifizierungsstelle aufgefordert. Sie müssen vorab festlegen, ob ein Benutzername und Kennwort zum Anfordern eines Zertifikats erforderlich ist. Der Zertifizierungsstellenadministrator verfügt über die benötigten Informationen und kann Ihnen ggf. bei diesem Schritt helfen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben einen Benutzernamen und ein Kennwort in die Textfelder ein und klicken dann auf **Weiter** .

7.  Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter** , um die standardmäßige Webservervorlage zu verwenden.
    

    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben.



8.  Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen Wert für **Anzeigename** ein, anhand dessen das Zertifikat und sein Zweck bestimmt werden. Falls leer gelassen, wird ein Name automatisch generiert. Geben Sie in **Bitlänge** die Bitlänge des Schlüssels ein, oder übernehmen Sie den Standardwert von 2048 Bits. Durch Auswahl der Option **Privaten Schlüssel des Zertifikats als exportierbar markieren** können Sie bei Bedarf das Zertifikat und den privaten Schlüssel in andere Systeme verschieben oder kopieren. Klicken Sie anschließend auf **Weiter** .
    

    > [!NOTE]
    > Lync Server 2013 stellt minimale Anforderungen an einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet.



9.  Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter** .

10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter** .

11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter** .

12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne** , und klicken Sie dann auf **Weiter** .

13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter** .

14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter** . Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück** , um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.

15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter** .

16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Falls das Zertifikat laut Bericht ausgegeben und installiert wurde, jedoch ungültig ist, vergewissern Sie sich, dass das Zertifikat der Stammzertifizierungsstelle im Speicher der vertrauenswürdigen Stammzertifizierungsstellen installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen** , wenn Sie das angeforderte Zertifikat anzeigen möchten. Das Kontrollkästchen **Dieses Zertifikat Lync Server-Zertifikatsverwendungen zuweisen** ist standardmäßig aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen** .

17. Wenn das Kontrollkästchen **Dieses Zertifikat Lync Server-Zertifikatsverwendungen zuweisen** auf der vorherigen Seite deaktiviert wurde, wird die Seite **Zertifikatzuweisung** angezeigt. Klicken Sie auf **Weiter** .

18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen** , wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter** .
    

    > [!NOTE]
    > Wenn auf der Seite <STRONG>Status der Onlinezertifikatsanforderung</STRONG> ein Problem mit dem Zertifikat gemeldet wird (wenn das Zertifikat beispielsweise als ungültig angezeigt wird), kann das Anzeigen des tatsächlichen Zertifikats bei der Lösung des Problems helfen. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.



19. Überprüfen Sie anhand der Informationen auf der Seite **Zusammenfassung der Zertifikatzuweisung** , dass es sich um das zuzuweisende Zertifikat handelt, und klicken Sie dann auf **Weiter** .

20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen** , um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen** .

21. Stellen Sie sicher, dass der **Status** des Zertifikats auf der Seite **Zertifikat-Assistent** als **Zugewiesen** angegeben ist, und klicken Sie dann auf **Schließen** .

## Siehe auch

#### Weitere Ressourcen

[Anforderungen in Bezug auf die Zertifikatinfrastruktur für Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md)

