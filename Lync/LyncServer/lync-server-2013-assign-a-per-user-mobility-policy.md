---
title: Zuweisen einer Mobilitätsrichtlinie auf Benutzerebene
TOCTitle: Zuweisen einer Mobilitätsrichtlinie auf Benutzerebene
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49890965
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer Mobilitätsrichtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die Mobilitätsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, die Sie in der Lync Server-Systemsteuerung oder Lync Server-Verwaltungsshell konfigurieren können.

## So weisen Sie eine benutzerbasierte Mobilitätsrichtlinie in der Lync Server-Systemsteuerung zu

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
    > Wenn Sie dieselbe benutzerbasierte Mobilitätsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Mobilitätsrichtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Wählen Sie **\<Automatisch\>**, um eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Standortebene durch Lync Server 2013 zuzulassen.
    
      - Klicken Sie auf der Seite **Mobilitätsrichtlinie** auf den Namen einer benutzerbasierten Mobilitätsrichtlinie, die Sie zuvor definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## Zuweisen einer benutzerbasierten Mobilitätsrichtlinie mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Benutzerbasierte Mobilitätsrichtlinien können Sie mit der Lync Server-Verwaltungsshell und dem **Grant-CsMobilityPolicy**-Cmdlet zuweisen. Dieses Cmdlet können Sie über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So weisen Sie einem einzelnen Benutzer eine benutzerbasierte Mobilitätsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Mobilitätsrichtlinie RedmondMobilityPolicy dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## So weisen Sie mehreren Benutzern eine benutzerbasierte Mobilitätsrichtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Mobilitätsrichtlinie RedmondMobilityPolicy allen Benutzern zugewiesen, denen aktuell die Richtlinie NorthAmericaMobilityPolicy zugewiesen ist. Ausführliche Informationen zu dem in diesem Befehl verwendeten Filter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## So heben Sie die Zuweisung einer benutzerbasierten Mobilitätsrichtlinie auf

  - Mit dem folgenden Befehl wird jede benutzerbasierte Mobilitätsrichtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Ausführliche Informationen finden Sie unter [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy).

## Siehe auch

#### Aufgaben

[Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

