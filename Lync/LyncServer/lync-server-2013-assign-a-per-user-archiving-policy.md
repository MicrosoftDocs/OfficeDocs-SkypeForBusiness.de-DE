---
title: Zuweisen einer Archivierungsrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Archivierungsrichtlinie auf Benutzerebene
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182560(v=OCS.15)
ms:contentKeyID: 49294940
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Archivierungsrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Archivierungsrichtlinie ist eine der Einstellungen für ein Benutzerkonto, die Sie in der Systemsteuerung für Lync Server 2013 konfigurieren können.

Die Bereitstellung einer oder mehrerer Archivierungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Archivierungsrichtlinie auf globaler oder Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer definiert wurde, werden automatisch die Archivierungsanforderungen in der globalen Konferenzrichtlinie verwendet.

Nachdem Sie mindestens eine Archivierungsrichtlinie auf Benutzerebene erstellt haben, können Sie anhand der Verfahren in diesem Thema diese Richtlinie zuweisen, mit der gemäß Ihren Anforderungen angegeben wird, ob die interne und/oder externe Kommunikation eines bestimmten Benutzers vom Server archiviert wird.

Ausführliche Informationen zum Erstellen von Archivierungsrichtlinien finden Sie unter [Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).

## So weisen Sie eine Archivierungsrichtlinie auf Benutzerebene zu

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
        

        > [!TIP]
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

    
    5.  Klicken Sie auf **Suchen**.

6.  Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.
    

    > [!TIP]
    > Wenn Sie dieselbe Benutzerarchivierungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Archivierungsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Lassen Sie eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Standortebene durch Lync Server 2013 zu.
    
      - Klicken Sie auf der Seite **Archivierungsrichtlinie** auf den Namen einer Archivierungsrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## Zuordnen einer benutzerbezogenen Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets

Benutzerbezogene Archivierungsrichtlinien können auch mithilfe der Windows PowerShell und des **Grant-CsArchivingPolicy**-Cmdlets zugeordnet werden. Dieses Cmdlet kann entweder über Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Zuordnen einer benutzerbezogenen Archivierungsrichtlinie zu einem einzelnen Benutzer

  - Mithilfe des folgenden Befehls wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer Ken Myer zugeordnet.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Zuordnen einer benutzerbezogenen Archivierungsrichtlinie zu mehreren Benutzern

  - Mithilfe dieses Befehls wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zugeordnet, deren Konten im Registrar-Pool "atl-cs-001.litwareinc.com" verwaltet werden. Weitere Informationen zu dem in diesem Befehl verwendeten Filterparameter finden Sie in der Dokumentation für das [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Aufheben der Zuordnung benutzerbezogener Archivierungsrichtlinien

  - Mithilfe des folgenden Befehls wird die Zuordnung aller benutzerbezogenen Archivierungsrichtlinien aufgehoben, die zuvor Ken Myer zugeordnet wurden. Nach dem Aufheben der Zuordnung der benutzerbezogenen Richtlinie wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, sofern vorhanden, mithilfe seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsarchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen dazu finden Sie im Hilfethema für das [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy)-Cmdlet.

## Siehe auch

#### Aufgaben

[Erstellen einer Archivierungsrichtlinie zum Aktivieren oder Deaktivieren der Archivierung von interner oder externer Kommunikation für bestimmte Standorte oder Benutzer](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  

#### Weitere Ressourcen

[Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)

