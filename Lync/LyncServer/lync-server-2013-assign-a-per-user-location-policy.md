---
title: Zuweisen einer Ortungsrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Ortungsrichtlinie auf Benutzerebene
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520974(v=OCS.15)
ms:contentKeyID: 49293625
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Ortungsrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Ortungsrichtlinie ist eine der Einstellungen für ein Benutzerkonto, die Sie in der Lync Server-Systemsteuerung konfigurieren können.

Die Bereitstellung einer oder mehrerer Ortungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Ortungsrichtlinie auf globaler oder auf Subnetzebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. E9-1-1-Einstellungen werden standardmäßig auf die in der Ortungsrichtlinie auf globaler Ebene definierten Einstellungen festgelegt, wenn keine spezifische Richtlinie auf Subnetz- oder Benutzerebene zugewiesen wird.

Nach Erstellung mindestens einer Ortungsrichtlinie auf Benutzerebene führen Sie die Schritte in diesem Thema aus, um die Richtlinie mit den Einstellungen zuzuweisen, die der Server auf Notrufe von einem bestimmten Benutzer anwenden soll.

Eine Liste aller verfügbaren Standortrichtlinieneinstellungen finden Sie unter [Definieren der Standortrichtlinie für Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Ausführliche Informationen zur Erstellung von Standortrichtlinien finden Sie unter [Erstellen von Ortungsrichtlinien in Lync Server 2013](lync-server-2013-create-location-policies.md).

## So weisen Sie eine Ortungsrichtlinie auf Benutzerebene zu

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
    > Wenn Sie dieselbe Benutzerortungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Ortungsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Lassen Sie eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Subnetzebene durch Lync Server 2013 zu.
    
      - Klicken Sie auf den Namen einer Benutzerortungsrichtlinie, die Sie zuvor durch Ausführen des Cmdlets **New-CsLocationPolicy** definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## So weisen Sie eine benutzerbasierte Standortrichtlinie mithilfe der Lync Server-Verwaltungsshell zu

Sie können benutzerbasierte Standortrichtlinien mit dem Cmdlet **Grant-CsLocationPolicy** zuweisen. Dieses Cmdlet können Sie entweder über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So weisen Sie eine benutzerbasierte Standortrichtlinie einem einzelnen Benutzer zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Standortrichtlinie **RedmondLocationPolicy** dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## So weisen Sie eine benutzerbasierte Standortrichtlinie mehreren Benutzern zu

  - Dieser Befehl weist die benutzerbasierte Standortrichtlinie **AccountingDepartmentLocationPolicy** allen Benutzern zu, die in der Buchhaltungsabteilung arbeiten. Weitere Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie in der Dokumentation für das [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser)-Cmdlet.
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## So heben Sie die Zuweisung der benutzerbasierten Standortrichtlinie auf

  - Mit dem folgenden Befehl wird die für den Benutzer Ken Myer vorgenommene Zuweisung einer benutzerbasierten Standortrichtlinie aufgehoben. Nach dem Aufheben der benutzerbasierten Standortrichtlinie wird Ken Myer automatisch mithilfe der globalen Richtlinie verwaltet oder, sofern vorhanden, mit der ihm zugewiesenen lokalen Standortrichtlinie. Eine Standortrichtlinie hat Vorrang vor einer globalen Richtlinie.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Weitere Informationen finden Sie im Hilfethema für das [Grant-CsLocationPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsLocationPolicy)-Cmdlet.

