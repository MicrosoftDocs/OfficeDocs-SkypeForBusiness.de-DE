---
title: Zusammenführen mithilfe des Zusammenführungs-Assistenten des Topologie-Generators
TOCTitle: Zusammenführen mithilfe des Zusammenführungs-Assistenten des Topologie-Generators
ms:assetid: c3f3c425-dab6-4dcd-bf0e-d7fde05f2ebf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205243(v=OCS.15)
ms:contentKeyID: 49295328
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zusammenführen mithilfe des Zusammenführungs-Assistenten des Topologie-Generators

 

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

1.  Laden Sie die vorhandene Bereitstellung mithilfe des Topologie-Generators herunter.

2.  Klicken Sie im Menü **Aktion** auf **Office Communications Server 2007 R2 zusammenführen** .

3.  Klicken Sie auf **Weiter** .

4.  Klicken Sie auf der Seite **Edgesetup angeben** auf **Hinzufügen** .
    
    ![Zusammenführungs-Assistent für Topologien, Edgesetup angeben (Seite)](images/JJ205243.cdca609d-d4d5-47d9-9ff8-8b1daa4106e1(OCS.15).jpg "Zusammenführungs-Assistent für Topologien, Edgesetup angeben (Seite)")  

5.  Geben Sie in **Edgesetup angeben** den Typ der Edgeserverkonfiguration ein, und klicken Sie auf **Weiter** . In diesem Beispiel wird die Option **Einzelner Edgeserver** verwendet.
    

    > [!IMPORTANT]
    > <STRONG>Erweiterte Edgebereitstellung</STRONG> ist keine unterstützte Konfiguration. Ein <STRONG>Erweiterter Edgeserver</STRONG> muss zuerst in einen <STRONG>Einzelnen Edgeserver</STRONG> oder ein <STRONG>Konsolidiertes Edge mit Lastenausgleich</STRONG> umgewandelt werden.



6.  Geben Sie auf der Seite **Interne Edgeeinstellungen festlegen** die erforderlichen Informationen und Ports für den internen FQDN Ihres Edgepools an, und klicken Sie dann auf **Weiter** .
    
    ![Interne Edgeeinstellungen festlegen (Dialogfeld)](images/JJ205243.dd664761-839c-4ac8-bd1a-5525589dfbb0(OCS.15).jpg "Interne Edgeeinstellungen festlegen (Dialogfeld)")  

7.  Geben Sie in **Externen Edge angeben** die FQDN-Informationen für Webkonferenzen für Ihren Edgeserver ein.
    

    > [!IMPORTANT]
    > Führen Sie den nächsten Schritt dieses Verfahrens aus, bevor Sie auf <STRONG>Weiter</STRONG> klicken. Dieser Schritt darf auf keinen Fall ausgelassen werden.



8.  Aktivieren Sie das Kontrollkästchen **Dieser Edgepool wird für den Partnerverbund und die Verbindung mit öffentlichen Chatdiensten verwendet** , wenn der Office Communications Server 2007 R2-Edgeserver der Vorversion für den Partnerverbund verwendet werden soll. Bei Bereitstellung mehrerer Edgeserver wird nur einer dieser Server für den Partnerverbund aktiviert. Wenn Sie dieses Kontrollkästchen nicht aktivieren und den Partnerverbund zu einem späteren Zeitpunkt aktivieren möchten, müssen Sie den Zusammenführungs-Assistenten des Topologie-Generators ausführen und Ihre Topologie erneut veröffentlichen.
    
    ![Edgeserver-Dialogfeld, externen Edge angeben (Seite)](images/JJ205243.32e97ce5-92f0-477e-8125-5d2ece237b13(OCS.15).jpg "Edgeserver-Dialogfeld, externen Edge angeben (Seite)")  

9.  Geben Sie auf der Seite **Nächsten Hop angeben** den vollqualifizierten Domänennamen (FQDN) des nächsten Hop-Standorts in Ihrer Umgebung ein. Klicken Sie auf **Fertig stellen** .
    
    ![Edgeserver-Dialogfeld, nächsten Hop angeben (Seite)](images/JJ205243.e734ee0d-f91c-4f3f-8ae6-248ecabcf678(OCS.15).jpg "Edgeserver-Dialogfeld, nächsten Hop angeben (Seite)")  

10. Wenn all Ihre Office Communications Server 2007 R2-Edgeserver hinzugefügt wurden, klicken Sie auf der Seite **Edgesetup angeben** auf **Weiter** . Wiederholen Sie dieses Verfahren ab Schritte 4 zum Hinzufügen weiterer Office Communications Server 2007 R2-Edgeserver.

11. Wählen Sie auf der Seite **Internen SIP-Port angeben** die Standardeinstellung aus (außer Sie haben den standardmäßigen SIP-Port geändert). Ändern Sie den Port entsprechend, wenn Sie nicht den Standardport 5061 verwenden, und klicken Sie dann auf **Weiter** .

12. Klicken Sie auf der Seite **Zusammenfassung** auf **Weiter** , um mit dem Zusammenführen der Topologien zu beginnen.

13. Der Assistent überprüft, ob die Topologien erfolgreich zusammengeführt wurden.

14. Stellen Sie in der Spalte **Status** sicher, dass der Wert **Erfolg** lautet, und klicken Sie dann auf **Fertig stellen** .

15. Im linken Bereich des Topologie-Generators sollte jetzt **BackCompatSite** angezeigt werden. Dies weist darauf hin, dass die Office Communications Server 2007 R2-Umgebung mit Lync Server 2013 zusammengeführt wurde.
    
    ![Topologie-Generator mit zusammengeführter Topologie](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "Topologie-Generator mit zusammengeführter Topologie")  

16. Klicken Sie im Menü **Aktion** auf **Topologie veröffentlichen** , und klicken Sie dann auf **Weiter** .

17. Klicken Sie nach Abschluss des Assistenten für die Veröffentlichung auf **Fertig stellen** .
    

    > [!NOTE]
    > Schließen Sie das nächste Thema <A href="import-policies-and-settings.md">Importieren von Richtlinien und Einstellungen</A> ab, um sicherzustellen, dass die Richtlinieneinstellungen der Vorversion in Lync Server 2013 importiert werden.


