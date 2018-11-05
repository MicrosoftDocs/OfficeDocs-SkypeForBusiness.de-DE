---
title: Zuweisen einer PIN-Richtlinie auf Benutzerebene
TOCTitle: Zuweisen einer PIN-Richtlinie auf Benutzerebene
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg182594(v=OCS.15)
ms:contentKeyID: 49295572
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Zuweisen einer PIN-Richtlinie auf Benutzerebene

 

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Die PIN-Richtlinie für Einwahlkonferenzen ist eine der individuellen Einstellungen für ein Benutzerkonto, die in der Systemsteuerung für Lync Server 2013 konfiguriert werden können.

Die Bereitstellung einer oder mehrerer PIN-Richtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale PIN-Richtlinie oder eine PIN-Richtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer zugewiesen wurde, gelten automatisch die Benutzerrechte und Berechtigungen im Hinblick auf die Verwendung von PINs für Einwahlkonferenzen, die in der globalen PIN-Richtlinie definiert sind.

Nachdem Sie mindestens eine PIN-Richtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema zu. Die zugewiesene Richtlinie gibt die Einschränkungen an, die der Server auf die PIN-Erstellung und -Verwendung durch einen bestimmten Benutzer anwenden soll.

Ausführliche Informationen zum Erstellen von PIN-Richtlinien für Einwahlkonferenzen für einen Benutzer finden Sie unter [Erstellen oder Ändern der PIN-Einstellungen für Einwahlkonferenzen für einen Standort oder eine Benutzergruppe in Lync Server 2013](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## So weisen Sie eine PIN-Richtlinie auf Benutzerebene zu

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
    > Wenn Sie dieselbe PIN-Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.



7.  Führen Sie im Abschnitt **Richtlinien zuweisen** unter **PIN-Richtlinie** eine der folgenden Aktionen aus:
    

    > [!NOTE]
    > Da Sie im Dialogfeld <STRONG>Richtlinien zuweisen</STRONG> mehrere Richtlinien konfigurieren können, wird die Option <STRONG>&lt;Beibehalten&gt;</STRONG> für alle Richtlinien im Dialogfeld standardmäßig aktiviert. Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.

    
      - Lassen Sie eine automatische Auswahl der globalen Richtlinie oder, falls definiert, der Richtlinie auf Standortebene durch Lync Server 2013 zu.
    
      - Klicken Sie auf der Seite **PIN-Richtlinie** auf den Namen einer PIN-Richtlinie auf Benutzerebene, die Sie zuvor definiert haben.
        

        > [!TIP]
        > Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.



8.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

## Zuweisen einer benutzerbasierten PIN-Richtlinie mithilfe der Lync Server-Verwaltungsshell-Cmdlets

Benutzerbasierte PIN-Richtlinien können Sie mit der Lync Server-Verwaltungsshell und dem **Grant-CsPinPolicy**-Cmdlet zuweisen. Dieses Cmdlet können Sie über die Verwaltungsshell für Lync Server 2013 oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## So weisen Sie einem einzelnen Benutzer eine benutzerbasierte PIN-Richtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbasierte PIN-Richtlinie RedmondPinPolicy dem Benutzer Ken Myer zugewiesen.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## So weisen Sie mehreren Benutzern eine benutzerbasierte PIN-Richtlinie zu

  - Mit dem folgenden Befehl wird die benutzerbasierte Richtlinie RedmondUsersPinPolicy allen Benutzern in der Stadt Redmond zugewiesen. Ausführliche Informationen zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## So heben Sie die Zuweisung einer benutzerbasierten PIN-Richtlinie auf

  - Mit dem folgenden Befehl wird jede benutzerbasierte PIN-Richtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Ausführliche Informationen finden Sie unter [Grant-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPinPolicy).

## Siehe auch

#### Aufgaben

[Erstellen einer neuen PIN-Richtlinie](lync-server-2013-create-a-new-pin-policy.md)  

#### Weitere Ressourcen

[Zuweisen von Richtlinien auf Benutzerebene](lync-server-2013-assigning-per-user-policies.md)

