---
title: 'Lync Server 2013: Testen der Poolbereitstellung'
TOCTitle: Testen der Poolbereitstellung
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg413092(v=OCS.15)
ms:contentKeyID: 49296027
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Testen der Poolbereitstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-09-25_

Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellung des Front-End-Pools testen.

## So testen Sie die Poolbereitstellung

1.  Fügen Sie in "Active Directory-Computer und -Benutzer" das Active Directory-Benutzerobjekt der Administratorrolle für die Lync Server 2013-Bereitstellung (für die die Systemsteuerung für Lync Server 2013 installiert ist) der Gruppe **CSAdministrator** hinzu.
    

    > [!IMPORTANT]
    > Wenn Sie der Gruppe "CsAdministors" nicht die geeigneten Benutzer und Gruppen hinzufügen, erhalten Sie beim Öffnen der Lync Server-Systemsteuerung, die folgende Fehlermeldung: "Nicht autorisiert: Der Zugriff wird aufgrund eines Fehler bei der rollenbasierten Zugriffssteuerung verweigert."



2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    

    > [!NOTE]
    > Bei dem Benutzerkonto darf es sich nicht um den lokalen Administrator eines Servers handeln, auf dem Lync Server 2013 ausgeführt wird.



3.  Melden Sie sich mit dem Verwaltungskonto bei dem Computer an, auf dem die Lync Server-Systemsteuerung installiert ist.

4.  Starten Sie die Lync Server-Systemsteuerung, und geben Sie bei Aufforderung die Anmeldeinformationen ein. Die Lync Server-Systemsteuerung zeigt Informationen zur Bereitstellung an.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie** , und vergewissern Sie sich, dass für jede Lync Server-Serverrolle, die bereitgestellt und online geschaltet wurde, unter **Status** ein Computer mit einem grünen Pfeil und unter **Replikation** ein grünes Häkchen angezeigt wird.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer** und dann auf **Benutzer aktivieren** .

7.  Klicken Sie im Dialogfeld **Neuer Lync Server-Benutzer** auf **Hinzufügen** .

8.  Wenn Sie Suchparameter für zu ermittelnde Objekte definieren möchten, aktivieren Sie auf der Seite **Aus Active Directory auswählen** die Option **Suchen** und klicken optional auf **Filter hinzufügen** . Alternativ können Sie auch die Option **LDAP-Suche** aktivieren und einen LDAP-Ausdruck eingeben, um die zurückgegebenen Objekte zu filtern oder einzuschränken. Klicken Sie auf **Suchen** , nachdem Sie die gewünschten Suchoptionen festgelegt haben.

9.  Wählen Sie auf der Seite mit den Suchergebnissen alle Objekte für diese Suchsitzung aus, und klicken Sie dann auf **OK** .

10. Auf der Seite **Neuer Lync Server-Benutzer** werden die ausgewählten Objekte in der Ansicht **Benutzer** angezeigt. Wählen Sie in der Liste **Benutzer einem Pool zuweisen** den Server aus, auf dem die Objekte verwaltet werden sollen.
    
    Nachfolgend werden verschiedene Optionen zum Konfigurieren der Objekte genannt.
    
      - **Benutzer-SIP-URI generieren**
    
      - **Telefonie**
    
      - **Anschluss-URI**
    
      - **Konferenzrichtlinie**
    
      - **Clientversionsrichtlinie**
    
      - **PIN-Richtlinie**
    
      - **Richtlinie für den externen Zugriff**
    
      - **Archivierungsrichtlinie**
    
      - **Ortungsrichtlinie**
    
      - **Clientrichtlinie**
    
    Zum Testen der Basisfunktionalität wählen Sie für **Benutzer-SIP-URI generieren** die gewünschte Einstellung (für die weiteren Optionen in der Konfiguration werden die Standardeinstellungen verwendet), und klicken Sie dann auf **Aktivieren** .

11. Es wird eine Zusammenfassungsseite angezeigt, bei der ein Häkchen in der Spalte **Aktiviert** darauf hinweist, dass die Objekte jetzt verwendet werden können. In der Spalte **SIP-Adresse** wird die Adresse gezeigt, die Sie zur Konfiguration der Benutzeranmeldung benötigen.

12. Melden Sie einen Benutzer bei einem Computer an, der Teil der Domäne ist, und einen weiteren Benutzer bei einem anderen Computer in der Domäne.

13. Installieren Sie Lync 2013 auf den beiden Clientcomputern, und vergewissern Sie sich anschließend, dass sich beide Benutzer bei Lync Server 2013 anmelden und Chatnachrichten austauschen können können.

## Siehe auch

#### Konzepte

[Bereitstellen von Clients und Geräten in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)

