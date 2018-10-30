---
title: 'Lync Server 2013: Veröffentlichen von Office Web Apps Server mithilfe eines Reverseproxyservers'
TOCTitle: Veröffentlichen von Office Web Apps Server mithilfe eines Reverseproxyservers
ms:assetid: 0babe39f-c4b9-46f0-995a-33dc99c2be03
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204665(v=OCS.15)
ms:contentKeyID: 49293145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Veröffentlichen von Office Web Apps Server in Lync Server 2013 mithilfe eines Reverseproxyservers

 

_**Letztes Änderungsdatum des Themas:** 2013-02-25_

Wenn externe Benutzer (d. h. Benutzer, die sich außerhalb der Firewall Ihrer Organisation anmelden) Zugriff auf PowerPoint-Präsentationen auf dem Office Web Apps-Server haben sollen, müssen Sie den Office Web Apps-Server und einen Reverseproxyserver wie Microsoft Forefront Threat Management Gateway verwenden. Das bedeutet auch, dass Sie eine Website-Veröffentlichungsregel erstellen und konfigurieren müssen. Diese Regel trägt zur Sicherstellung bei, dass Benutzer eine Verbindung mit dem Server herstellen können. Wenn Sie externen Benutzern keinen Zugriff zur Verfügung stellen, müssen Sie keine Website-Veröffentlichungsregel konfigurieren.

Führen Sie das folgende Verfahren aus, um in Forefront Threat Management Gateway eine Website-Veröffentlichungsregel zu konfigurieren:

1.  Klicken Sie im **Startmenü** auf **Alle Programme** , dann auf **Microsoft Forefront TMG** und anschließend auf **Forefront TMG Management** .

2.  Klicken Sie in Forefront TMG mit der rechten Maustaste auf **Firewallrichtlinie** zeigen Sie auf **Neu** , und klicken Sie dann auf **Website-Veröffentlichungsregel** .

3.  Geben Sie im Assistenten für neue Webveröffentlichungsregeln auf der **Willkommensseite** im Feld **Name der Webveröffentlichungsregel** einen Namen für Ihre neue Regel ein (z. B. **Office Web Apps-Serverregel** ), und klicken Sie dann auf **Weiter** .

4.  Klicken Sie auf der Seite **Regelaktion festlegen** auf **Zulassen** und dann auf **Weiter** .

5.  Aktivieren Sie auf der Seite **Veröffentlichungstyp** die Option **Einzelne Website oder Lastenausgleich veröffentlichen** , und klicken Sie dann auf **Weiter** .

6.  Klicken Sie auf der Seite **Sicherheit der Serververbindung** auf **SSL verwenden, um eine Verbindung zum veröffentlichten Webserver oder zur Serverfarm herzustellen** , und klicken Sie dann auf **Weiter** .

7.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Interner Sitename** den FQDN Ihres Office Web Apps-Servers ein (z. B. **officewebapps01.contoso.com** ), und klicken Sie dann auf **Weiter** . Der im Feld **Interner Sitename** eingegebene Name muss im Betrefffeld oder dem Feld "Alternativer Antragstellername" des Zertifikats angezeigt werden, das Sie dem Office Web Apps-Server zugeordnet haben.

8.  Geben Sie auf der Seite **Interne Veröffentlichungsdetails** im Feld **Pfad (optional)** **/\*** ein, und klicken Sie dann auf **Weiter** . Die Syntax "/\*" trägt zur Sicherstellung bei, dass alle Ordner und Unterordner der Website veröffentlicht werden.

9.  Wählen Sie auf der Seite **Details des öffentlichen Namen** in der Dropdownliste **Anforderungen annehmen für** die Option **Diesen Domänennamen (unten eingeben)** , und geben Sie dann den vollqualifizierten Domänennamen für Ihren Office Web Apps-Server in das Feld "Öffentlicher Name" ein. Dieser Name sollte der Name für den Zugriff auf Ihre Website sein. Wird auf Ihre Seite z. B. mit der URL "http://officewebapps01.contoso.com" zugegriffen, geben Sie im Feld **Öffentlicher Name** **officewebapps01.contoso.com** ein.

10. Klicken Sie auf **Weiter** .

11. Klicken Sie auf der Seite **Weblistener auswählen** auf **Neu** .

12. Geben Sie im Assistenten für neue Weblistenerdefinition im Feld **Weblistenername** einen Namen für den neuen Weblistener ein (z. B. **SSL** ), und klicken Sie dann auf **Weiter** .

13. Wählen Sie auf der Seite **Sicherheit der Clientverbindung** die Option **Sichere SSL-Verbindungen mit Clients erforderlich** aus, und klicken Sie dann auf **Weiter** .

14. Wählen Sie auf der Seite **Weblistener-IP-Adressen** die Optionen **Extern** und **Intern** , und klicken Sie dann auf **Weiter** .

15. Wählen Sie auf der Seite **Listener-SSL-Zertifikate** die Option **Ein einziges Zertifikat für diesen Weblistener verwenden** , und klicken Sie dann auf **Zertifikat auswählen** .

16. Wählen Sie im Dialogfeld **Zertifikat auswählen** das Zertifikat aus, das für diesen Weblistener verwendet werden soll, und klicken Sie dann auf **Auswählen**

17. Klicken Sie auf der Seite **Listener-SSL-Zertifikate** auf **Weiter** .

18. Wählen Sie auf der Seite **Authentifizierungseinstellungen** in der Dropdownliste **Legen Sie fest, wie die Clients die Anmeldeinformationen an Forefront TMG übermitteln sollen** die Option **Keine Authentifizierung** aus, und klicken Sie dann auf **Weiter** .

19. Klicken Sie auf der Seite **Einstellungen für einmaliges Anmelden (SSO)** auf **Weiter** .

20. Überprüfen Sie auf der Seite **Fertigstellen des Assistenten** die Zusammenfassung der Konfigurationsauswahlen, und klicken Sie anschließend auf **Fertig stellen** .

21. Klicken Sie auf der Seite **Weblistener auswählen** auf **Weiter** .

22. Wählen Sie auf der Seite **Authentifizierungsdelegierung** in der Dropdownliste **Legen Sie die Methode fest, mit der Forefront TMG sich beim veröffentlichten Webserver authentifizieren soll** die Option **Keine Delegierung, aber direkte Authentifizierung des Clients** , und klicken Sie dann auf **Weiter** .

23. Bestätigen Sie auf der Seite **Benutzersätze** , dass die richtigen Benutzersätze aufgeführt sind. Standardmäßig ist dies der Benutzersatz **Alle Benutzer** . Klicken Sie auf **Hinzufügen** , um ggf. andere Benutzersätze hinzuzufügen, die Sie definiert haben. Klicken Sie anschließend auf **Weiter** .

24. Klicken Sie auf der Seite **Fertigstellen des Assistenten** auf **Fertig stellen** .

Beachten Sie, dass der Prozess nicht durch Klicken auf **Fertig stellen** abgeschlossen ist, d. h. die neue Regel wird dadurch nicht angewendet und aktiviert. Stattdessen müssen Sie auf der Forefront TMG- Benutzeroberfläche auf die Schaltfläche **Anwenden** klicken. Wenn Sie auf **Anwenden** klicken, wird das Dialogfeld **Configuration Change Description** angezeigt. Klicken Sie in diesem Dialogfeld auf **Anwenden** , um die neue Veröffentlichungsregel zu aktivieren.

Nachdem Ihre neue Regel angewendet wurde, müssen Sie einige geringfügige Änderungen an der Regel vornehmen, um sicherzustellen, dass Benutzer die neuen PowerPoint-Präsentationsfunktionen nutzen können. Verwenden Sie hierzu das folgende Verfahren.

1.  Klicken Sie in Forefront TMG mit der rechten Maustaste auf die neue Veröffentlichungsregel, und klicken Sie dann auf **Eigenschaften** .

2.  Wählen Sie im Dialogfeld **Eigenschaften** auf der Registerkarte **Bis** die Option **Ursprünglichen Hostheader anstelle des aktuellen Headers weiterleiten** .

3.  Klicken Sie auf der Registerkarte **Verkehr** auf **Filtern** und dann auf **HTTP konfigurieren** .

4.  Deaktivieren Sie im Dialogfeld **HTTP-Richtlinie für diese Regel konfigurieren** das Kontrollkästchen **Normalisierung überprüfen** , und klicken Sie dann auf **OK** .

5.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK** .

6.  Klicken Sie in Forefront TMG auf **Anwenden** , um die Änderungen zu übernehmen. Wenn das Dialogfeld **Configuration Change Description** angezeigt wird, klicken Sie auf **Anwenden** .

Nach dem Abschluss der Installation können Sie Ihren Office Web Apps-Server mit den Verfahren in Thema [Überprüfen der Konfiguration von Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md) testen.

